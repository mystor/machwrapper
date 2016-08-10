This is a very simple wrapper of mach which I use to manage my mozconfigs.

Mozconfigs are stored in `~/.mozconfigs` with no extensions.

Each branch will have an associated mozconfig, which is used to build it.

running `mach nameofmozconfig` will cause that mozconfig to become active on the current branch

Running `mach anythingelse` will forward the command to the first mach which is found in the directory tree above the current directory, with the MOZCONFIG environment variable set to the appropriate mozconfig for the current branch.

If you are not in a git tree, nothing will happen.

If you are in a servo directory (discovered by checking if PWD contains the string `servo`), then no MOZCONFIG will be passed to mach.
