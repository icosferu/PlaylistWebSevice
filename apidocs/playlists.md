# Playlists
## GET /apiv1/playlists
Returns all of the public playlists.
### Output example
	{
	   "playlist_count":1,
	   "playlists":[
	      {
			 "id":20,
	         "user":"test",
			 "name":"testplaylist",
	         "video_ids":[
	            "-sQ3Af3DpeM",
				"8S0QcINRYJs",
				"-F7A24f6gNc"
	         ]
	      }
	   ]
	}
## POST /apiv1/playlists
Used to create a new playlist. Video ids may be empty. If you already have a playlist with the same name - 400.
### Input example
	{
	   "name":"my public playlist",
	   "is_public":true,
	   "video_ids":[
	      "8S0QcINRYJs"
	   ]
	}
## GET /apiv1/playlists/user/{nickname}
Returns all of the public playlists for the person. In case you are requesting your own user, you will see the private playlists as well. If no such user - 404.
### Output example
	{
	   "playlist_count":2,
	   "playlists":[
	      {
			 "id":1,
	         "user":"me",
			 "name":"my public playlist",
	         "video_ids":[
				"8S0QcINRYJs"
	         ]
	      }
	      {
			 "id":4,
	         "user":"me",
			 "name":"my private playlist",
	         "video_ids":[
	            "-sQ3Af3DpeM",
				"8S0QcINRYJs",
				"-F7A24f6gNc"
	         ]
	      }
	   ]
	}
## GET /apiv1/playlists/id/{id}
Returns the playlist with the specified id. If not found - 404.
### Output example
	{
		 "id":1,
         "user":"me",
		 "name":"my public playlist",
         "video_ids":[
			"8S0QcINRYJs"
         ]
	}
## DELETE /apiv1/playlists/id/{id}
Deletes your playlist with the specified id. If there are no playlists with such id or it is not yours - 404.
## GET /apiv1/playlists/name/{name}
Returns all of the public playlists with the specified name. You will see your private playlists as well.
### Output example
	{
	   "playlist_count":1,
	   "playlists":[
	      {
			 "id":20,
	         "user":"test",
			 "name":"testplaylist",
	         "video_ids":[
	            "-sQ3Af3DpeM",
				"8S0QcINRYJs",
				"-F7A24f6gNc"
	         ]
	      }
	   ]
	}
## DELETE /apiv1/playlists/name/{name}
Deletes your playlist with the specified name. If you don't have a playlist with such a name - 404.
## P.S.
**NOT FINISHED.**  
Everything in this document is a subject to change.  
Authorization is still in progress.