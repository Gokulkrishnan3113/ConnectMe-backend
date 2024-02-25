# ConnectMe-backend

# DATA BASE QUERY/SCHEMA


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

# microservices/apis

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

3)Store Posts

Endpoint: /upload

Method: POST

Body:
	description: Description of the post
	img: Image URL of the post
	date: Post posted date
 
Description: Store a new post in the database.

4)User Login

Endpoint: /login

Method: POST

Body:
	username: Username of the user
	password: Password of the user
	Description: Authenticate user credentials and generate a token for accessing protected resources.

5)User Registration

Endpoint: /register

Method: POST

Body:
	fullname : Fullname of the new user
	username: Username of the new user
	email: Email of the new user
	password: Password of the new user (hashed)
Description: Register a new user in the system.

