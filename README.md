# darkroast



## Version 1: 
* Users can create posts. Users can view their own 'station' through the main menu. 
* Users can search for usernames and click on a username, then view all posts by that user.

## Version 2:
* Users will have a profile with details about them. 
* Users can now like posts.
* Liked posts by a user can be visited
* Users can now have friends.
* Friends posts show up by default on a user's dashboard

## Version 3: 
* Users can now tag their posts with keywords. 
* Users can search for posts via tagname

## Version 4:
* Users will be shown targeted content specifically catered based on common tagnames 
which they have frequently liked. 

## Version 1: 
```
Users: (reusable via Node Lambda; eventually will import this through barstool): {
id
username
password
}

Posts: (Springboot/Kotlin API): {
id
user_id
title
description
video_link
}
```

## Version 2: 
```
Profiles: (Springboot/Kotlin API): {
user_id
likes
full name
}
// friends table needs restructuring 
Friends: (Springboot/Kotlin API): {
id
friend_a
friend_b
}
```

## Version 3:
```
Tags : (Springboot/Kotlin API): 
{
id
post_id
tagname
}
```


### Barstool User Auth:
* App creates credentials with <aws>/barstool/ with {appname}, {aws database url}, and {password}, returns credentials token
* User pings <aws>/barstool/users/create?credentials={somecredentials} with {username} {password} to create a new entry in their database
* User pings <aws>/barstool/users/login?credentials={somecredentials} with {username} {passwprd}, returns true or false if credentials are correct

Eventually this code will be imported directly from barstool, although the API will remain the same externally. The code internally will be significantly less verbose.
