# Run basic operators on Select Count queries
I had an issue where there was some bad data
in a table and I needed to cross reference some counts
from two different tables. You can do basic operators on 
`SELECT count(*)` queries
```
SELECT 
(SELECT count(*)
FROM exp_channel_titles
WHERE channel_id = '3') 
-
(SELECT count(*)
FROM exp_channel_data cd
JOIN exp_channel_titles ct ON ct.entry_id = cd.entry_id
WHERE ct.channel_id = '3')
```

[Source](http://stackoverflow.com/questions/826365/how-do-i-add-two-count-results-together)
