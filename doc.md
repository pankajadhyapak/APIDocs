## /login  `POST`

####parameters
`email`,`Password`


###Response

```
{
  "id": 1,
  "name": "pankaj",
  "email": "pankaj@w3effects.com",
  "created_at": "2016-03-17 10:42:21",
  "updated_at": "2016-03-17 10:42:21",
  "token":"xyz...."
 }
```


***
## /register `POST`

####parameters
`email`,`name`,`password`,`phone`

###Response

```
{
  "id": 1,
  "name": "pankaj",
  "email": "pankaj@w3effects.com",
  "created_at": "2016-03-17 10:42:21",
  "updated_at": "2016-03-17 10:42:21",
 }
```


***

## /user/me `GET`

####parameters
`Token`


###Response
```
{
  "id": 1,
  "name": "pankaj",
  "email": "pankaj@w3effects.com",
  "created_at": "2016-03-17 10:42:21",
  "updated_at": "2016-03-17 10:42:21",
 }
```



use in user profile page to display currently logged in user

***

## /users `GET`

####parameters
`Token`

###Response

Array of all users except currently logged in user with flag of `isFriend` use this flag to add action like add or remove friend 

```
[
  {
    "id": 2,
    "name": "Kartik",
    "email": "kartik.tanksali@gmail.com",
    "created_at": "2016-03-17 10:57:23",
    "updated_at": "2016-03-17 10:57:23",
    "isFriend": true
  },
  {
    "id": 3,
    "name": "Pooja ",
    "email": "Pooja@gmail.com",
    "created_at": "2016-04-05 08:16:56",
    "updated_at": "2016-04-05 08:16:56",
    "isFriend": true
  }
 ]
```
To display in all doctors tab

***

## /user/addFriend `POST`

####parameters
`Token`, `friend_id`

###Response


Current user with friend list


```
[
  {
    "id": 2,
    "name": "Kartik",
    "email": "kartik.tanksali@gmail.com",
    "created_at": "2016-03-17 10:57:23",
    "updated_at": "2016-03-17 10:57:23",
    "isFriend": true
  },
  {
    "id": 3,
    "name": "Pooja ",
    "email": "Pooja@gmail.com",
    "created_at": "2016-04-05 08:16:56",
    "updated_at": "2016-04-05 08:16:56",
    "isFriend": true
  },
```
To display in all doctors tab, when clicked on add friend button or icon `friend_id` is id of the clicked doctor

***

## /user/getFriendRequest `POST`

####parameters
`Token`

###Response


Current user with friend list


```
[
  {
    "id": 2,
    "name": "Kartik",
    "email": "kartik.tanksali@gmail.com",
    "created_at": "2016-03-17 10:57:23",
    "updated_at": "2016-03-17 10:57:23",
    "pivot": {
      "friend_id": 1,
      "user_id": 2,
      "status": "SENT",
      "created_at": "2016-05-06 03:46:08",
      "updated_at": "2016-03-17 11:45:30"
    }
  }
]
```
To display in all Requests tab


***

## /user/acceptFriend `POST`

####parameters
`Token`, `friend_id`

###Response


Current user with friend list


```
[
  {
    "id": 2,
    "name": "Kartik",
    "email": "kartik.tanksali@gmail.com",
    "created_at": "2016-03-17 10:57:23",
    "updated_at": "2016-03-17 10:57:23",
    "isFriend": true
  },
  {
    "id": 3,
    "name": "Pooja ",
    "email": "Pooja@gmail.com",
    "created_at": "2016-04-05 08:16:56",
    "updated_at": "2016-04-05 08:16:56",
    "isFriend": true
  },
```
To display in all Requests tab, when clicked on Accept button or icon `friend_id` is id of the clicked doctor


