# Stream

Stream is a simple toolkit I use to make watching/ listening to streams/ videos
from the CLI easier.

## Stream-Helper

Simple tool that makes working with a stream instance easier. Roughly speaking
the commands entered are run as is in the shell (including flags). So as of right
now (since I havent written proper documentation yet) the best method to see how
to use each command to its full potentiol is to do the following:

## First get the list of commands
You can either run `stream-helper -c` or `grep commands=`, both will show the
commands.

Once you have the list of commands, run something like whats below on each command
```
grep -n ": <command>" stream-helper
```
This should print the line where the function can be found, along with a short
discription of its arguments.

As usual the best documentation is often the source itself.

## TODO

* Finish README
* Finish docs for `stream-helper` and `stream`
