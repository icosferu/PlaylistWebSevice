# Users
## GET /apiv1/users
Returns all of the users registered in the system with their nicknames and their public playlists.
### Output example
	{
	   "user_count":3,
	   "users":[
	      {
	         "nickname":"test",
	         "public_playlists":[
	            20,
	            40,
	            60
	         ]
	      },
	      {
	         "nickname":"me",
	         "public_playlists":[
	            1,
	            2,
	            3
	         ]
	      },
	      {
	         "nickname":"test2",
	         "public_playlists":[
	            25,
	            42,
	            610
	         ]
	      }
	   ]
	}
## GET /apiv1/users/{nickname}
Returns a single user with his public playlists. In case you are requesting your own user, you will see the private playlists as well. If not found, returns 404.
### Output example (your user)
	{
	   "nickname":"me",
	   "public_playlists":[
	      1,
	      2,
	      3
	   ],
	   "private_playlists":[
	      4,
	      5,
	      6
	   ]
	}
### Output example (other user)
	{
	   "nickname":"test",
	   "public_playlists":[
	      20,
	      40,
	      60
	   ],
	   "private_playlists":null
	}
## POST /apiv1/users
Used to register a new user with the specified nickname. The password is transfered through the body. In case of success returns 200, else 400 (if the user already exists).
### Input example
	{
	   "nickname":"test",
	   "password":"testpassword"
	}
## P.S.
Everything in this document is a subject to change.  
Authorization is still in progress.