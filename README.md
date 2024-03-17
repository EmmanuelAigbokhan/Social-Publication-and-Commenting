# Social-Publication-and-Commenting
Assignment 2: In this assignment, you will implement a Web application where registered users will be able to publish/modify
and delete text publications as well as add/modify and delete comments on these publications.
Learning Objectives
Understand how to:
- Use password hashing and verification functions for login purposes.
- Use Session variables, especially in the Login/Logout process.
- Destroy Session variables to log a user out.
- Implement and use Action Filters to verify the login status.
- Manipulate database records to reflect typical eCommerce Web app interactions.
Further understand how to:
- Implement a PHP MVC Web application.
- Use method parameters and session variables for integrity constraints and data input requirements in
Web applications.
- Implement multi-table databases.
- Use PDO and appropriate SQL to interact with this database.
Requirements
The Web app will be built with PHP, specifically using our in-class developed MVC framework and the data
storage will be ensured by a MySQL/MariaDB database. Students must use their better judgement to make
independent decisions about aspects of the application that remain unspecified or that are contradictory.
Interactions
The Web app will support two types of users: persons and users. Persons are internet users who have not yet
logged in and users are internet users that have logged in. The following features will be supported:
- To become a user, as a person, I need to be able to register
- To access the application, as a person, I need to be able to log into the application
- To protect my account, as a user, I need to be able to logout of the application
- To make publications, as a user, I need to be able to create my text
- To correct publications, as a user, I need to be able to edit my text
- To avoid embarrassment, as a user, I need to be able to delete my text
- To support the writing process, as a user, I can select to keep a publication private until I wish to make it
public
- To provide my opinion, as a user, I need to be able to add comments to existing text
- To correct my comments, as a user, I need to be able to edit my comments
- To retract my comments, as a user, I need to be able to delete my comments
- To read interesting text, as a person or user, I need to see a list of all publications, most recent first
- To find interesting text, as a person or user, I need to be able to search for text by title
- To find interesting text, as a person or user, I need to be able to search for text by content
- To manage my online content, as a user, I need to access my profile page
- To manage my profile, as a user, I can edit my profile information
Database
To store the data, we will have a few tables:
1- user: user_id, username, password_hash.
2- profile: profile_id, user_id(FK to user), first_name, middle_name, last_name
3- publication: publication_id (PK), profile_id (FK to profile), publication_title, publication_text, timestamp,
publication_status(public or private)
4- publication_comment: publication_comment_id (PK), profile_id (FK to profile), publication_id (FK to
publication), timestamp
Profile creation process
Upon registration, users will not yet have a profile created for them. However, before they can use the application,
they need to build a profile for themselves. By using access filtering, users will be redirected to profile creation if
at any moment they are accessing application functionality that requires users to be logged in.
Publication list
All publications are displayed on the main page of the application for anyone to see, whether they are logged in or
not. These are displayed as a list of hyperlinks. Each hyperlink points to the publication view and uses the
publication title as hyperlink text. When any person or user searches for a publication by title or content, the
search results are displayed in the same way. Only public publications appear in the main page and search
results.
Profile page
Each user may access their profile page. This page displays all information owned by this user on the application.
This includes their profile information, a list of their publications (as a list of hyperlinks) and a list of their
comments (as hyperlinks).
Users will be able to navigate to all publication pages through these hyperlinks. Users will be able to modify their
profiles using this page as well.
Publication view
In the publication view, users can see the publication and all comments on the publication below the publication.
Users can add comments, modify, and delete their own comments (not other user's comments). If the publication
is theirs, users are also able to modify and delete their publication.

