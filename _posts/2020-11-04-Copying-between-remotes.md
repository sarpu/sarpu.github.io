### How to copy files between two remote machines.

The other day I needed to transfer some large files from one server to another. 
As usual, I turned to `rsync`, but `rsync` does not support moving files between two
remotes. [There are ways to make it work](https://unix.stackexchange.com/questions/183504/how-to-rsync-files-between-two-remotes)
, but unless you need `rsync`'s advanced features, which I did not, I suggest `scp -3`.
This option uses your local machine as an intermediary for the two remotes. The
downside is that it is slower, and the progress option is not available; the upside is 
that you don't need to set up credentials on either machine to complete the transfer. 
For instance, If you have the two remotes configured in your `.ssh/config`, then 
`scp -3` will seamlessly use the credentials that you set up to connect to those 
machines. 
