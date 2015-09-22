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
## POST /apiv1/playlists/id/{id}
Used to change the playlist data. Video id array cannot be modified here, only the name and privacy. If you try to change the name to an alredy existing one - 400.
### Input example
	{
	   "name":"my changed playlist",
	   "is_public":true
	}
## DELETE /apiv1/playlists/id/{id}
Deletes your playlist with the specified id. If there are no playlists with such id or it is not yours - 404.
## POST /apiv1/playlists/id/{id}?action=remove
Used to remove a video from the playlist. Id or index must be specified. If there are multiple videos with the same id - 400 and return an index array.
### Input example (id)
	{
	   "video_id":8S0QcINRYJs
	}
### Output example (id)
	{
	   "indexes":[
	      3,
	      5,
	      6
	   ]
	}
### Input example (index)
	{
	   "video_index":3
	}
## POST /apiv1/playlists/id/{id}?action=add
Used to add a video or multiple videos to the playlist. Video id array is mandatory. Insertion index is not.
### Input example (no index)
	{
         "video_ids":[
			"8S0QcINRYJs"
         ]
	}
### Input example (with index)
	{
		 "index":4
         "video_ids":[
			"8S0QcINRYJs"
         ]
	}
## POST /apiv1/playlists/id/{id}?action=remove
Used to remove a video from the playlist. Id or index must be specified. If there are multiple videos with the same id - 400 and return an index array.
### Input example (id)
	{
	   "video_id":8S0QcINRYJs
	}
### Output example (id)
	{
	   "indexes":[
	      3,
	      5,
	      6
	   ]
	}
### Input example (index)
	{
	   "video_index":3
	}
## POST /apiv1/playlists/id/{id}?action=reorder
Used to reorder videos in the playlist. An array of indices must be specified. Length of the array must be equal to the playlist length (N). Indeces must be unique and from 1 to N. If the prerequisites are not met - 400.
### Input example
	{
	   "indeces":[
	      1,
	      4,
	      2,
	      3
	   ]
	}
## POST /apiv1/playlists/id/{id}?action=move
Used to move a video to another position in the playlist. Id or index must be specified. If there are multiple videos with the same id - 400 and return an index array.
### Input example (id)
	{
	   "video_id":8S0QcINRYJs,
	   "new_index":3
	}
### Output example (id)
	{
	   "indexes":[
	      4,
	      5,
	      6
	   ]
	}
### Input example (index)
	{
	   "video_index":2,
	   "new_index":3
	}
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
## DELETE /apiv1/playlists/name/{name} [Kinda wrong]
Deletes your playlist with the specified name. If you don't have a playlist with such a name - 404.
## P.S.
Everything in this document is a subject to change.  
Authorization is still in progress.