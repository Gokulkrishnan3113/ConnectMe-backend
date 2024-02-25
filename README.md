# ConnectMe-backend


# For reference

githun repo for frontend : https://github.com/Gokulkrishnan3113/ConnectMe-frontend.git


# Database queries/schema


	create table users(

		id int PRIMARY KEY AUTO_INCREMENT NOT NULL,

 		username varchar(45) NOT NULL,
	
 		email varchar(100) NOT NULL,
	
 		password varchar(100) NOT NULL,
	
 		img varchar(255) 
	
 	);


	create table posts(
	
 		id int NOT NULL  PRIMARY KEY AUTO_INCREMENT,
		
	 	description VARCHAR(255) NOT NULL,
		
	 	img VARCHAR(255) NOT NULL,
		
	 	date DATETIME NOT NULL,
		
	 	uid INT NOT NULL,
		
	 	FOREIGN KEY (uid) REFERENCES users(id)
		
	 	ON DELETE CASCADE
	
 		ON UPDATE CASCADE
	
 	);

# Microservices/Apis

	1)Search for a User
	
	Endpoint: /search/:username
	
	Method: GET
	
	Parameters: username (query parameter)
	
	Description: Retrieve user information based on username.

2)Display All Posts

Endpoint: /posts

Method: GET

Description: Retrieve all posts from the database.

3)Display Posts of Specific User

Endpoint: /profile/:username

Method: GET

Parameters: username (in URL path)

Description: Retrieve all posts of a specific user.

4)Store Posts

Endpoint: /upload

Method: POST

Body:

	description: Description of the post

 	img: Image URL of the post
	
 	date: Post posted date
 
Description: Store a new post in the database.

5)User Login

Endpoint: /login

Method: POST

Body:

	username: Username of the user
	
 	password: Password of the user
	
 	Description: Authenticate user credentials and generate a token for accessing protected resources.

6)User Registration

Endpoint: /register

Method: POST

Body:

	fullname : Fullname of the new user

 	username: Username of the new user
	
 	email: Email of the new user
	
 	password: Password of the new user (hashed)

Description: Register a new user in the system.

