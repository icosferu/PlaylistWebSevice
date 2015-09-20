# Playlist Web Sevice
Youtube playlist service with a web API.
## Features
### Authentication
* Will be required to access the API's functionality. Most likely implemented as HTTP Basic authentication over HTTPS.

### Users
* Ability to get all of the users registered in the system with their nicknames and their public playlists.  
* Ability to register a new user.

### Playlists
* Ability to remove a video from the playlist by specifying the video's index in the playlist or by specifying the video's ID. If there are multiple videos with the same ID in the playlist, API won't delete them and respond with an error an a list of indices of videos with that ID.  
* Ability to add a video(s) to an already existing playilst. Video(s) will be added to the end (default behaviour) or to the specified index (ex. if you select 4, then every video with the index greater or equal of 4 will be pushed back, and the video(s) will be put in there). If the index is less than 1, the video will be the first in the playlist, if the index is greater than the playlist length, the video be the last in the playlist.  
* Ability to rearange all videos in the playlist by specifying an array of new indices. For example, if you specify an array [3, 1, 2], then the third video will become the first, the first becomes the second, etc. If the array will be smaller or bigger than the playlist itself, an error is returned. The same happens, if one of the indeces will be greater than the array length.  
* Ability to move one video to another position by specifying the current index or the ID of the video and the new index. Other videos will be pushed back as in the "Add" operation. If there are multiple videos with the same ID, response is similar to the one in the "Remove" operation.  
* Ability to create playlists for yourself with a name and the list of youtube video IDs. They may be either private (visible only to the user, that created the playlist) or public (visible to everyone). Every playlist will have a unique ID. Name must be unique for a user.  
* Ability to delete your created playlists by specifying the ID or the name of the playlist.
* Ability to change the playlist's publicity by specifying the ID or the name of the playlist and the new privacy setting.  
* Ability to view all the public playlists (and your private ones) and filter them by user, name, id, etc.

## P.S.
Everything in this document is a subject to change.
