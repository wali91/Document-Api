FORMAT: 1A
HOST: https://private-c10997-waliusers.apiary-mock.com

# Blogging API

Simple API allowing consumers to view blogging authors, their posts and comments.

## Author [/author]

### List All Author [GET]

you may view all of Author.


+ Response 200 (application/json)

            {
            "status": "OK",
            "message": "Successful",
            "data": [
                {
                    "id" : 1,
                    "username": "Mia Huljanah",
                    "salt": "AbssnxSVF212anFVGfapalfa",
                    "email": "mia_huljanah@yahoomail.com",
                    "profile": "pelajar"
                },
                
                {
                    "id" : 2,
                    "username": "Rashif Ilmi Nurzaman",
                    "password": "************",
                    "salt": "AkasnSCTF121anSKNfaknfa",
                    "email": "rashif_ilmi@yahoomail.com",
                    "profile": "Pekerja_Swasta"
                }, 
                {
                    "id" : 3,
                    "username": "Hardo Fernando Silalahi",
                    "password": "************",
                    "salt": "AcxpASNF121anSKNfachfa",
                    "email": "hardo_fernando@yahoomail.com",
                    "profile": "PNS "
                }
            ]
        }


### Create a New Author [POST]

You may create your Authir using this action. It takes a JSON
object containing a name and username.

+ Request (application/json)

         {
            "username": "Rafli ramadhan",
            "password": "************",
            "salt": "AcxpASNF121anSKNfachfa",
            "email": "rafli@yahoomail.com",
            "profile": "petani"
        }

+ Response 201 (application/json)

    + Headers

            Location: /author/4

    + Body

               {
                "status": "OK",
                "message": "Successful",
                "data": {
                    "id" : 4
                    "username": "Rafli ramadhan",
                    "password": "************",
                    "salt": "AcxpASNF121anSKNfachfa",
                    "email": "rafli@yahoomail.com",
                    "profile": "petani"
                }
            }
            
## Users Collection with path [/author/{id}]

### Detail of Author [GET]

+ Parameters

    + id : 1 (number, required) - An unique identifier of the message

+ Response 200 (application/json)

   + Body
   
            {
            "status": "OK",
            "message": "Successful",
            "data": 
            {
                    "id" : 1,
                    "username": "Mia Huljanah",
                    "salt": "AbssnxSVF212anFVGfapalfa",
                    "email": "mia_huljanah@yahoomail.com",
                    "profile": "pelajar"
                }
            }
            
### Edit an Author [PATCH]

Edit specific author using its ID.

+ Request (application/json)

            {
            "status": "OK",
            "message": "Successful",
            "data": 
            {
            "email": "mia_hulja200@yahoomail.com" }
            }
      

+ Response 201 (application/json)

   + Body        
  
               {
            "status": "OK",
            "message": "Successful",
            "data":
            {
                    "id" : 1,
                    "username": "Mia Huljanah",
                    "salt": "AbssnxSVF212anFVGfapalfa",
                    "email": "mia_hulja200@yahoomail.com",
                    "profile": "pelajar"
                }
            }
            
### Delete an Author [DELETE]

Delete an author.

+ Response 204

## Post [/post]
### List All Posts [GET]

List all posts.

+ Response 200 (application/json)

        {
            "status": "OK",
            "message": "Successful",
            "data": [
          {
          "id": "1",
          "title": "Title 1",
          "content": "content 1",
          "tags": "tags1",
          "status": "Updated",
          "create_time": "2020-03-11T07:21:52.754Z",
          "update_time": "2020-03-11T07:28:52.754Z",
          "author_id": "1"
          },
          {
          "id": "2",
          "title": "Title 2",
          "content": "content 2",
          "tags": "tags2",
          "status": "Updated",
          "create_time": "2020-03-11T07:21:52.754Z",
          "update_time": "2020-03-11T07:28:52.754Z",
          "author_id": "2"
          },
          {
          "id": "3",
          "title": "Title 3",
          "content": "content 3",
          "tags": "tags3",
          "status": "Updated",
          "create_time": "2020-03-11T07:21:52.754Z",
          "update_time": "2020-03-11T07:28:52.754Z",
          "author_id": "3"
          }
        ]
        }
        
### Create New Post [POST]

Create new post.

+ Request 200 (application/json)

        {
          "title": "Title 4",
        "content": "content 4",
         "tags": "tags4",
        "author_id": "1"
         }
    
+ Response 201 (application/json)

    + Headers

            Location: /post/4

    + Body 
    
            {
            "status": "OK",
            "message": "Successful",
            "data":
            {
              "id": "4",
              "title": "Title 4",
             "content": "content 4",
             "tags": "tags4",
             "status": "Created",
            "create_time": "2020-03-11T07:21:52.754Z",
            "update_time": "",
             "author_id": "1"
             }
             }


## Posts Resource [/post/{id}]
+ Parameters

    + id : 1 (number, required) - An unique identifier of the message

### List Post with ID [GET]

List specific post using its ID.

+ Response 200 (application/json)
    
            {
                "status": "OK",
                "message": "Successful",
                "data":
            {
                "id": "1",
                "title": "Title 1",
                "content": "content 1",
                "tags": "tags1",
                "status": "Updated",
                "create_time": "2020-03-11T07:21:52.754Z",
                "update_time": "2020-03-11T07:28:52.754Z",
                "author_id": "1"
             }
             }

### Edit a Post [PATCH]

Edit specific post using its ID.

+ Request (application/json)

        {
            "title": "Title 1D"
        }

+ Response 201 (application/json)

        
            {
                "status": "OK",
                "message": "Successful",
                "data":
            {
                "id": "1",
                "title": "Title 1D",
                "content": "content 1",
                "tags": "tags1",
                "status": "Updated",
                "create_time": "2020-03-11T07:21:52.754Z",
                "update_time": "2020-03-11T07:28:52.754Z",
                "author_id": "1"
            }
            }
        
### Delete a Post [DELETE]

Delete a post.

+ Response 204


## Comments [/comment]

### List All Comments [GET]

List all comments.

+ Response 200 (application/json)

        
            {
                "status": "OK",
                "message": "Successful",
                "data":
            {
                "id": "1",
                "content": "content 1",
                "status": "Updated",
                "create_time": "2020-03-11T07:21:52.754Z",
                "author_id": "1",
                "email": "mia_huljah@yahoomail.com",
                "url": "miahuljah.com",
                "post_id": "1"
            },
            {
                "id": "2",
                "content": "content 2",
                "status": "Updated",
                "create_time": "2020-03-11T07:21:52.754Z",
                "author_id": "2",
                "email": "rashif_ilmi@yahoomail.com",
                "url": "rashif_ilmi.com",
                "post_id": "2"
            },
            {
                "id": "3",
                "content": "content 3",
                "status": "Updated",
                "create_time": "2020-03-11T07:21:52.754Z",
                "author_id": "3",
                "email": "hardo_fernando@yahoomail.com",
                "url": "hardo_fernando.com",
                "post_id": "3"
            }
        }

### Create New Comment [POST]

Create new comment.

+ Request (application/json)

        {
            "content": "content 4",
            "author_id": "4",
            "email": "ashraf@yahoomail.com",
            "url": "ashraf_ilmi.com",
            "post_id": "4"
        }

+ Response 201 (application/json)

    + Headers

            Location: /comment/4

    + Body

            {
                "id": "4",
                "content": "content 4",
                "status": "Created",
                "create_time": "2020-03-11T07:21:52.754Z",
                "author_id": "2",
                "email": "ashraf@yahoomail.com",
                "url": "ashraf_ilmi.com",
                "post_id": "4"
            }
            
## Posts Resource [/comment/{id}]

+ Parameters
    + id : 1 (number, required) - An unique identifier of the message

### List Post with ID [GET]

List specific comment using its ID.

+ Response 200 (application/json)

        [
            {
                "id": "1",
                "content": "content 1",
                "status": "Updated",
                "create_time": "2020-03-11T07:21:52.754Z",
                "author_id": "1",
                "email": "mia_huljah@yahomail.com",
                "url": "miahuljah.com",
                "post_id": "2"
            }
        ]

### Edit a Post [PATCH]

Edit specific post using its ID.

+ Request (application/json)

        {
            "content": "content 1c"
        }

+ Response 201 (application/json)

        [
            {
                "id": "1",
                "content": "content 1c",
                "status": "Updated",
                "create_time": "2020-03-11T07:21:52.754Z",
                "author_id": "1",
                "email": "mia_huljah@yahoomail.com",
                "url": "miahuljah.com",
                "post_id": "2"
            }
        ]
        
### Delete a Post [DELETE]

Delete a post.

+ Response 204
