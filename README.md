# syncm
Linux script for syncing an textual playlist with an ssh capable device. The script taks an Amarok Playlist in MP3 Audio (Streamed) 
format and pushes all songs in this playlist to the remote device. 

The procedure is as follows:
1. Take the playlist and normilize the paths by replacing the url encoding with readable characters, create a new file with the
   content.
2. Create a temporary folder in /tmp and store a symbolic link for every song in this folder.
3. Sync the temporary folder with the remote location, uploading any files that are missing at the destination and deleting any 
   files that are not listed at the source.
4. Create all files created in the process.

The remote device must support ssh and rsync. If you're using an Android device, I've found that SSHelper 
(http://arachnoid.com/android/SSHelper/) works very good, you might give it a try.

