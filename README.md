# Stream

Stream is a simple toolkit I use to make watching/ listening to streams/ videos
(via a url or file on disk or a live-stream) from the CLI easier.

## Usage

To listen to/Play videos look at `stream -h`.
To manipulate `stream` whilst its running look at `stream-helper -h`. Note that
to manipulate `stream` the `-a` flag should be used when running `stream` (or
set a socket with `-s`.

## Dependencies

Each script can be run with the `-d` flag to print the dependencies it needs.
Each dependency comes with a short description explaining what it is used for,
and how necessary it is. If it returns with a 0 exit code you have all the
dependencies, else it will show which dependencies you are missing.

Example: `stream -d`

## Folders

Users can make use of optional 'folders'. A folder is essentially a file
containing predefined links/urls/paths to videos. Folders make playing/ viewing
the same content easier, example usage:
* Easily watching your favorite streamer (youtube or twitch)
	- If you have an api key for twitch then the user will only be listed if
	  they are online
* Create a folder for a group of videos on your disk (I use this to keep the
  recorded lectures my lecturer posts easy to access).

Folders have the following form and note that title must be unique
```
<title>" "<url/filepath>
<title>" "<url/filepath>
.
.
.
```
The default folder is located in `$HOME/.config/stream/root`, you can edit this
to have what ever links you want.

Next if you want to create custom folders simply create
`$HOME/.config/stream/<NAME>`, what this will do is when you run `stream -f` it
will list all the titles that are present in root, as well as your other
folders (written as `Folder:<NAME>`).  Selecting one of these folders will open
and list its contents. Note folders cannot have subfolders (with the exception
of the root folder).

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
