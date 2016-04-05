# Run Commands in Parallel
I knew that running a command with a `&` after it sets it to a background task.
However, I didn't think to run two commands that way...UNTIL NOW

For example I need to run a bower install and a npm install
```
bower i & npm i
```
Neither task is dependent on each other and so doesn't require a `&&`. Under the hood
the `&` forks a new process for that command. You can see the pid outputted
when you run the command. To test:
```
echo "yo" & echo "what"
```

