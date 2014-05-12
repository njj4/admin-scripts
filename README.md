admin-scripts
=============
Miscellaneous system administration and other useful scripts.

### backup

Use `rsync` to backup directory trees to timestamped directories on a
backup drive, using hard links for unchanged files to optimise use of disk
space.

Usage: `backup <src-dir> <dest-basename>`

Example: `backup /local/fs2/photos photos` will clone `/local/fs2/photos`
to `/backup/YYYYMMDD/photos`, hard-linking unchanged files to the most
recent available previous copy.

This will also work with directories on remote machines, as long as ssh keys
are set up properly: `backup user@host:/home/user host/user` will backup
`user`'s home directory on `host` to `/backup/YYYYMMDD/host/user`.
