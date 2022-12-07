# Inventory Store Full-Stack CRUD Webapp
Michal A Uchmanowicz & Luke Walder, Grand Canyon University, 2022

*Java, Springboot, Thymeleaf*

## Abstract

We ([Luke Walder](https://github.com/lw0545/) and myself) created a web application to allow users to "purchase" items from a store. The application will base itself around polymorphic product items; they will take on the form of Weapons, Armor, or Health Items. All users will be required to register and login in order to access most of the website. An Admin user can create, edit, and delete products as they like via the products store page. A standard User can "purchase" products from the products store page which will be reflected in their own products page. Product and User information will be stored in a database.

## Design Introduction

The web application is built using springboot as a backend and thymeleaf as a front end. Spring Security will be used to properly authenticate and authorize users in order to access the application. User and Product Information will be stored in a MySQL database that will be accessed using Spring's JDBC Template object. The application will be built following an N-Layered Architecture scheme, adhering to separation of concerns and utilizing dependency injection.

## Logical Design

The user is able to access the application through their browser. The user, unless logged in, is only able to see the home page, the login page, and the register page. Login will be done through Spring Security while registration will implement it to some degree. Upon registration, a user is assigned a role of "user". Once logged in, the user has access to a products store page, a myproducts page which will show all the user's "purchased" products, and an option to logout. Only a user can access the myproducts page. 

The Product super model will consist of three product sub models: Weapons, Armor, Health. They will all be stored as products within the MySQL database.

An Admin will be able to log in and directly create, edit, or delete items using the interface provided within the products store page and will not be able to access the "myproducts" page. A user can head to the products store page, where he is given an option to purchase different products. Upon purchase of a product, a quantity of 1 of that product is removed from the "admin's inventory" (products page), and is placed into the User's inventory (MyProducts page). These create, edit, delete, and purchase operations all rely on and are supported by database operations.

## Physical Design

The user will access the application through their browser. The application is currently locally hosted using a Tomcat Server that is running on port 8080. The database is also locally hosted using Mamp and is accessed through port 3306.

## Visual Walkthrough


## Design Choices

#### Tehnologies Used

- Spring Tool Suite v. 4.15.3 
- Java v. SE17  
- Springboot v. 2.7.4 
- Springboot Starter Web  
- Springboot Starter Validation 
- Springboot Starter Thymeleaf  
- Springboot Starter Security 
- Thymeleaf Extras Spring Security  
- Springboot DevTools 
- MySQL-Connector-Java  
- Mamp  
- Chrome Devtools 
- HTML5 
- CSS3  
- Bootstrap v. 5.2.2  

#### General Technical approach

We wanted to make the design as simple as possible

#### Technical Design Decisions

We have discussed ideas of implementing friends through friend requests and friend lists in addition to having also discussed ideas of implementing trading of items among users and or friends through trade offers. Both of these implementations are currently out of scope.

___

Some Documentation is too large to be included in this README. Please refer to the [Documentation within this repository](Documentation/) for All documentation. Included are: High level Block Diagram, Logical Diagram, Physical Diagram, UML, Flowchart, DDL scripts, ER Diagram, Game Wireframe, Django Wireframes, and Sitemap. 

___
[Please check out my other projects](https://github.com/MikeUchmanowicz/Start)
