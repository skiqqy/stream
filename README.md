# Stream

Stream is a simple toolkit I use to make watching/ listening to streams/ videos
from the CLI easier.

## Stream-Helper

Simple tool that makes working with a stream instance easier. Roughly speaking
the commands entered are run as is in the shell (including flags). So as of right
now (since I havent written proper documentation yet) the best method to see how
to use each command to its full potentiol is to do the following:

## Stream-Helper: Command Help

The primary method is to run `stream-helper -t` to enter tty mode and type `help` or
`help <command>` to get information on the command(s). This also works in gui mode,
but simply prints to stdout, hence tty mode is suggested.

You can also run `stream-helper -c` or `grep commands=`, both will show the
commands available, the former prints usage as well.

Once you have the list of commands, you can run something like whats below on
each command
```
grep -n ": <command>" stream-helper
```
This should print the line where the function can be found, along with a short
discription of its arguments.

As usual the best documentation is often the source itself.

## TODO

* Finish README
* Finish docs for `stream-helper` and `stream`
