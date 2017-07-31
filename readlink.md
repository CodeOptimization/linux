## readlink $(which java)

show you the where does the java file locate, not the alias.

## For Mac:
which is actually a bad way to do things like this, as it makes guesses about your environment based on $SHELL and the startup files (it thinks) that shell uses; not only does it sometimes guess wrong, but you can't generally tell it to behave differently. (which on my Ubuntu 10.10 doesn't understand --skip-alias as mentioned by @SiegeX, for example.)  type uses the current shell environment instead of poking at your config files, and can be told to ignore parts of that environment, so it shows you what will actually happen instead of what would happen in a reconstruction of your default shell.

In this case, type -P will bypass any aliases or functions:

$ __type -P git__

/usr/bin/git

You can also ask it to peel off all the layers, one at a time, and show you what it would find:

$ __type -a git__

git is /usr/bin/git

git is /usr/local/git/bin/git

(Expanding on this from the comments:)

The problem with which is that it's usually an external program instead of a shell built-in, which means it can't see your aliases or functions and has to try to reconstruct them from the shell's startup/config files. (If it's a shell built-in, as it is in zsh but apparently not bash, it is more likely to use the shell's environment and do the right thing.)

type is a POSIX-compliant command which is required to behave as if it were a built-in (that is, it must use the environment of the shell it's invoked from including local aliases and functions), so it usually is a built-in.

It isn't generally found in csh/tcsh, although in most modern versions of those which is a shell builtin and does the right thing; sometimes the built-in is what instead, and sometimes there's no good way to see the current shell's environment from csh/tcsh at all.

### Reference
  * https://unix.stackexchange.com/questions/10525/how-to-use-which-on-an-aliased-command
