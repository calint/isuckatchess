## save data
```
(function() {
    const data = localStorage.getItem('chess_puzzles');
    if (!data) return console.error("No data found to backup!");
    
    const blob = new Blob([data], {type: 'application/json'});
    const url = URL.createObjectURL(blob);
    const link = document.createElement('a');
    
    link.href = url;
    link.download = `blindspot_backup_${new Date().toISOString().slice(0,10)}.json`;
    link.click();
    
    URL.revokeObjectURL(url);
    console.log("Backup file created!");
})();
```

## load data

```
(function() {
    const input = document.createElement('input');
    input.type = 'file';
    input.accept = '.json';
    
    input.onchange = e => {
        const file = e.target.files[0];
        const reader = new FileReader();
        reader.onload = readerEvent => {
            const content = readerEvent.target.result;
            try {
                // Validate that it is a valid JSON array before saving
                JSON.parse(content); 
                localStorage.setItem('chess_puzzles', content);
                alert("Restore successful! Refresh the page to see your data.");
                location.reload();
            } catch (err) {
                alert("Error: Invalid backup file.");
            }
        }
        reader.readAsText(file);
    }
    input.click();
})();
```