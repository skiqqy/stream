# Stream

Stream is a simple toolkit I use to make watching/ listening to streams/ videos
(via a url or file on disk or a live-stream) from the CLI easier.

## Usage

To listen to/Play videos look at `stream -h`.
To manipulate `stream` whilst its running look at `stream-helper- h`.

## Stream-Helper Continued

Stream-Helper's main goal is to make working with `stream` easier (in any
possible way). One of the nice features of `stream-helper` is the fact that you
can pipe commands to it, and it will perform them. For example if we want to
pause its stream instance we can simply do the following.
```
echo pp | stream-helper -t
```
We can then repeat the above to unpause. Piping the commands works for all
commands (see `echo help | stream-helper -t`)

This allows for Stream-Helper to be used/plugged in anywhere in a unix like
fashion of simply piping input into a program (eg binding a dwm key to run
`echo pp | stream-helper -t` to pause currently playing stream).

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
