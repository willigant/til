# Bash Date Ysterday
Not only can bash can output a date, but it can also take in params to 
take in a certain date and format it how you like

```bash
#!/bin/sh
today=`date +%Y-%m-%d`
echo $today

yesterday=`date -v -1d +%Y-%m-%d`
echo $yesterday
```

Sources:
* [Get the date a day before current time in bash](https://stackoverflow.com/questions/1706882/get-the-date-a-day-before-current-time-in-bash)


