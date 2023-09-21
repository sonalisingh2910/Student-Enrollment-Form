
Student Enrollment Form
This is a student registration form that stores user data in JSONPowerDB. It supports REST APIs and serverless technology, allowing you to add and update student records based on their roll number. The roll number is automatically checked, and data from other input fields is retrieved through APIs, enabling users to update their information conveniently. The application utilizes AJAX requests for smooth and fast interaction, making it suitable for storing various types of data, including numbers, strings, dates, and more.

Benefits of Using JSONPowerDB
Capable of storing structured, semi-structured, and unstructured data, as well as other types of files and big data.
Dynamic relational constraints for CRUD operations, allowing you to manage relational data without pre-defining primary keys (PK), foreign keys (FK), unique keys (UK), databases, tables, etc.
Technology-agnostic, accessible via HTTP REST API from any technology, providing flexibility and ease of use.
Minimal learning curve, accelerates development, reduces time to market, and lowers development costs.
Offers a range of tools and techniques for developers to manage their databases effectively.
Release History
JSONPowerDB
Version: 2.0
Execute API
javascript
Copy code
var baseUrl = "http://api.login2explore.com:5577";
function executeCommand(reqString, apiEndPointUrl) {
    var url = baseUrl + apiEndPointUrl;
    var jsonObj;
    $.post(url, reqString, function (result) {
        jsonObj = JSON.parse(result);
    }).fail(function (result) {
        var dataJsonObj = result.responseText;
        jsonObj = JSON.parse(dataJsonObj);
    });
    return jsonObj;
}
Create a PUT Request String
javascript
Copy code
function createPUTRequest(connToken, jsonObj, dbName, relName) {
    var putRequest = "{\n"
            + "\"token\" : \""
            + connToken
            + "\","
            + "\"dbName\": \""
            + dbName
            + "\",\n" + "\"cmd\" : \"PUT\",\n"
            + "\"rel\" : \""
            + relName + "\","
            + "\"jsonStr\": \n"
            + jsonObj
            + "\n"
            + "}";
    return putRequest;
}
Features
User-Friendly Interface
Fast Response Times
Easy to Use
Tech Stack
Client: HTML, CSS, JavaScript

Server: JSONPowerDB

Author: SonaLi Singh