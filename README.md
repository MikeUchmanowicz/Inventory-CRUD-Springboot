# Inventory Store Full-Stack CRUD Webapp
Michal A Uchmanowicz & Luke Walder, Grand Canyon University, 2022

*Java, Springboot, Thymeleaf*

___

All Documentation may not be posted within this repository due to it being part of the Grand Canyon University Curriculum. Documentation and Details are available upon request. 

___

## Abstract

We ([Luke Walder](https://github.com/lw0545/) and myself) created a web application to allow users to "purchase" items from a store and add eachother as friends. The application will base itself around polymorphic product items; they will take on the form of Weapons, Armor, or Health Items. All users are required to register and login in order to access most of the website. An Admin user can create, edit, and delete products as they like via the products store page. A standard User can "purchase" products from the products store page which will be reflected in their own products page (and users can delete their own products). Users will have a page to view current incoming and outcoing friend requests in addition to current friends. Users, User relationships, and Product information are stored in a MySQL database. 

A docker image of the application has been created. That docker image was uploaded to dockerhub and was uploaded to AWS's ECS.

## Design Introduction

The web application is built using springboot as a backend and thymeleaf as a front end. Spring Security is used to properly authenticate and authorize users in order to access the application. User and Product Information are stored in a MySQL database that will be accessed using Spring's JDBC Template object. The application will be built following an N-Layered Architecture scheme, adhering to separation of concerns and utilizing dependency injection.

## Logical Design

The user is able to access the application through their browser. The user, unless logged in, is only able to see the home page, the login page, and the register page. Login will be done through Spring Security while registration will implement it to some degree. Upon registration, a user is assigned a role of "user". Once logged in, the user has access to a products store page, a myproducts page which will show all the user's "purchased" products, and an option to logout. Only a user can access the myproducts page. The user will also have access to a friends page, and will be able to search user names and send friend requests, in addition to accepting or denying and incoming requests.

The Product super model will consist of three product sub models: Weapons, Armor, Health. They will all be stored as products within the MySQL database and will be owned either by an admin or a user. 

An Admin will be able to log in and directly create, edit, or delete items using the interface provided within the products store page and will not be able to access the "myproducts" page. A user can head to the products store page, where he is given an option to purchase different products. Upon purchase of a product, a quantity of 1 of that product is removed from the "admin's inventory" (products page), and is placed into the User's inventory (MyProducts page). These create, edit, delete, and purchase operations all rely on and are supported by database operations.

## Physical Design

The user will access the application through their browser. The application is currently locally hosted using a Tomcat Server that is running on port 8080. The database is also locally hosted using Mamp and is accessed through port 3306.

## Visual Walkthrough
#### Loom Video

https://www.loom.com/share/5fa5c7ccdc4146c1aedacfcdef59e0a5
Inventory and Purchasing updates

https://www.loom.com/share/aba278307114416bbcf10b060ab0b395
Adding Users as friends

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

We wanted to make the design as simple as possible-- offering the Admin ways to create, edit, and delete products on the same page that the user can purchase products from. We use dynamically shown buttons (according to currently logged in user's role) to change the interfaces on the products store page to achieve this. We use this ssame technique to hide pages the current user does not have access to, whether their role is different, or whether they are unauthenticated entirely. The same concept is carried over to the login, register, and logout buttons, which are dynamicly shown based on whether the current user is already authenticated.

#### Technical Design Decisions

Springboot and thymeleaf were used as the frameworks for this project because this application is part of a Java Level 3 class. We chose to use MySQL because MySQL offers relational database support; we needed to provide Users with their own roles in a seperate table linked by username and products in a seperate table that were linked by username as well. We chose to use polymorphic items as we wanted to challenge ourselves a little, and it made the app a tad more interesting. Springboot Security was used due to its seemless "single-class" implementation into the rest of the project.

We have discussed ideas of implementing friends through friend requests and friend lists in addition to having also discussed ideas of implementing trading of items among users and or friends through trade offers. Both of these implementations are currently out of scope.

___

All Documentation may not be posted within this repository due to it being part of the Grand Canyon University Curriculum. Documentation and Details are available upon request. 

___
[Please check out my other projects](https://github.com/MikeUchmanowicz/Start-Here)
