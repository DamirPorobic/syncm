# syncm
Linux script for syncing an textual playlist with an ssh capable device. The script takes an Amarok Playlist in MP3 Audio (Streamed) 
format and pushes all songs in this playlist to the remote device. 

## How it works
1. Take the playlist and normalize the paths by replacing the url encoding with readable characters, create a new file with the
   content.
2. Create a temporary folder in /tmp and store a symbolic link for every song in this folder.
3. Sync the temporary folder with the remote location, uploading any files that are missing at the destination and deleting any 
   files that are not listed at the source.
4. Create all files created in the process.

The remote device must support ssh and rsync. If you're using an Android device, I've found that SSHelper 
(http://arachnoid.com/android/SSHelper/) works very good, you might give it a try.

## Installing the scrips
Download both scripts, I presume you download it to your Download folder (~/Downloads/).  
&nbsp;&nbsp;&nbsp;$cd ~/Downloads/  
&nbsp;&nbsp;&nbsp;$unzip syncm-master.zip  
&nbsp;&nbsp;&nbsp;$cd syncm-master  
&nbsp;&nbsp;&nbsp;$mv syncm ~/bin/  
&nbsp;&nbsp;&nbsp;$mv url_encode ~/bin/
   
## Prepare the playlist
The script is now in place, next we need to prepare the playlist
   - Open Amarok
   - Click on "playlist" (top right corner)
   - Select "Export Playlist As..."
   - Give the playlist a meaningful name, I presume you call it "playlist".
   - Select type "MP3 audio (streamed)"
   - Select a location where to save it, I presume you've selected your home directory.
   - Click "Save"

## Pushing files to the mobile device
Now that we have the script and the playlist ready, you just need to find the ip address and ssh port of the remote device execute following:  
&nbsp;&nbsp;&nbsp;$syncm playlist ip-of-remote-device port-of-remote-device
   
It will take a few seconds for the songs to be uploaded, depending on the number of songs.

If you encounter any problems, please let me know at https://github.com/damirporobic/syncm



