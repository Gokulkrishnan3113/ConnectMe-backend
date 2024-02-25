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
