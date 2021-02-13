# Self Documenting Bash File
With `grep` and `sed` it is possible to allow function comments be outputted
via some `help` function in a bash script. This is useful when a bash script has
many functions that could be called on

Basic example:

```bash
#!/bin/sh
##
## Usage: sh start.sh
## Example self documenting help bash script
##

prog="$0"
me=`basename "$prog"`

RED='\033[0;31m'

help () {
  grep '^##' "$prog" | sed -e 's/^##//' -e "s/_PROG_/$me/" 1>&2
}

##
## Usage: sh start.sh method
## Another method that self documents!
##
method() {
    echo "method"
    echo $1
}

##
## Usage: sh start.sh another
## Another one!
##
another() {
    echo "another one! $1"
}

# this calls the function passed as the first parameter to the script
# the $2 makes the next arg available passed to the method
$1 $2
```

sources:
* [Pass in args and call a method](http://superuser.com/questions/106272/how-to-call-bash-functions)
* [Self documenting Bash Script](http://www.thelinuxdaily.com/2012/09/self-documenting-scripts/)

Example in the wild [es.sh](https://github.com/khaliqgant/bootstrap/blob/master/scripts/es.sh)

