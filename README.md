# USER DATA COLLECTION

A simple backend for user management system using MVC, RESTFul API with CRUD
Handling and stroing form data and creating CSV file. 

## Table of Contents

- [USER DATA COLLECTION](#user-data-collection)
  - [Table of Contents](#table-of-contents)
  - [Description](#description)
  - [Features](#features)
  - [Technologies Used](#technologies-used)
  - [Installation](#installation)
  - [Usage](#usage)
  - [API Endpoints](#api-endpoints)
  - [Database Schema](#database-schema)

## Description

A backend implementation for a user management system that handles various CRUD (Create, Read, Update, Delete) operations on a MongoDB database using Mongoose. It also includes functionality to export user data to a CSV file.

## Features

List the main features of the project. For example:
- Add / Delete / Edit  user data .
- Create csv file.
- Upload data in to the file structure.

## Technologies Used

Mention the technologies and libraries used in the project. For example:
- ```Node.js```
- ```Express.js```
- ```MongoDB (with Mongoose) ```
- ```Moment``` - provides a simple and efficient way to work with dates and times in JavaScript.
- ```Validator``` - provides a set of validation functions for various types of data in JavaScript. It is commonly used in both server-side (Node.js) and client-side (frontend) applications to validate data such as strings, numbers, email addresses, URLs, dates, and more.
- ```multer ```- provides middleware for handling multipart/form-data, which is typically used for file uploads in Node.js applications.
- ```fast-csv ```- provides a fast and efficient way to read and write CSV (Comma-Separated Values) data in Node.js. It is designed to handle large CSV files with high performance and minimal memory usage. The package offers both parsing (reading) and stringifying (writing) functionalities for CSV data.


## Installation

Step-by-step instructions on how to install and set up the project locally on your machine. Include prerequisites, such as Node.js and MongoDB installation.

Clone the repository
```javascript
git clone https://github.com/PiroAvni/SERVERSIDE_SEARCH_FILTERING_SORTING_PAGINATION_NODE_EXPRESS_MONGODB.git
```

Change directory
```
cd your-project
```


Install dependencies
```
npm install
```


## Usage

Instructions on how to run the application locally.

Run the development server
``` 
npm start
```




## API Endpoints

List the available API endpoints along with their descriptions. For example:

  ```POST /user/register: ``` This route is used for user registration. It uses the upload.single middleware to handle file uploads for the user profile image. When a POST request is made to this route, the userpost controller function from usersControllers is executed to handle the registration process.

```GET /user/details:``` This route is used to retrieve a list of users based on query parameters. When a GET request is made to this route, the userget controller function from usersControllers is executed to fetch the user details.

``` GET /user/:id: ``` This route is used to retrieve details of a single user based on their unique ID. When a GET request is made to this route with the user's ID as a parameter, the singleuserget controller function from usersControllers is executed.

``` PUT /user/edit/:id: ``` This route is used to update a user's information based on their unique ID. It also supports updating the profile image using the upload.single middleware. When a PUT request is made to this route with the user's ID as a parameter, the useredit controller function from usersControllers is executed to handle the update process.

``` DELETE /user/delete/:id: ``` This route is used to delete a user based on their unique ID. When a DELETE request is made to this route with the user's ID as a parameter, the userdelete controller function from usersControllers is executed to handle the deletion process.

``` PUT /user/status/:id: ```This route is used to update the status of a user based on their unique ID. When a PUT request is made to this route with the user's ID as a parameter, the userstatus controller function from usersControllers is executed to handle the status update process.

``` GET /userexport:``` This route is used to export all users' information to a CSV file. When a GET request is made to this route, the userExport controller function from usersControllers is executed to handle the export process.

## Database Schema

If applicable, provide details about the database schema and how the data is structured.

```JAVASCRIPT 

const usersSchema = new mongoose.Schema({
    fname: {
        type: String,
        required: true,
        trim: true
    },
    lname: {
        type: String,
        required: true,
        trim: true
    },
    email: {
        type: String,
        required: true,
        unique: true,
        validate(value) {
            if (!validator.isEmail(value)) {
                throw Error("not valid email")
            }
        }
    },
    mobile: {
        type: String,
        required: true,
        unique: true,
        minlength: 10,
        maxlength: 10
    },
    gender: {
        type: String,
        required: true,
    },
    status: {
        type: String,
        required: true,
    },
    profile: {
        type: String,
        required: true,
    },
    location: {
        type: String,
        required: true,
    },
    datecreated:Date,
    dateUpdated:Date
});
```
