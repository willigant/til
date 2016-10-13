# Force Cherry Pick A Commit
If you want to bring in a commit and have it override the existing content
```
git cherry-pick commitish --strategy-option theirs

# for example
git cherry-pick 2db40486dd30f6969bae8ad815d673b5347287ef --strategy-option theirs
```

Vice versa
```
git cherry-pick commitish --strategy-option ours
```

[source](http://stackoverflow.com/questions/21051850/force-git-to-accept-cherry-picks-changes)

