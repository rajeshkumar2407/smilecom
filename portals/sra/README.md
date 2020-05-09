# Smile Restful APIs
- [Smile Restful APIs](#crossref-rest-api)
    - [Register User](#registeruser)
    - [Create Token](#createtoken)

## Register User
  Register a new user to the application using OTP.

* **URL**

  /sra/registerbyotp

* **Method:**

  `POST`
    
*  **URL Params**

   None

* **Query Params**

  None
  
* **Request Body:**

  ```
  {
    "customerId":12345,
    "identity":"09876485982", //mobile number used for OTP
    "key":"594432", // OTP Code. Valid for 15 Min
    "newPassword":"test123",
    "confirmPassword":"test123"
  }
  ```

* **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
      ```
      {
      "done" : true
      }
      ```
 
* **Error Response:**

  * **Code:** 400 <br />
    **Content:** 
      ```
      {
      "SRAError":{
      "errorDesc":"identity is missing",
      "errorType":"business",
      "errorCode":"SRA-0003"
      }
      }
      ```
      
  * **Code:** 404 <br />
    **Content:** 
      ```
      {
      "SRAError":{
      "errorDesc":"invalid identity",
      "errorType":"business",
      "errorCode":"SRA-0003"
      }
      }
      ```
      
  * **Code:** 404 <br />
    **Content:** 
      ```
      {
      "SRAError":{
      "errorDesc":"user already regisstered",
      "errorType":"business",
      "errorCode":"SRA-0003"
      }
      }
      ```
   
## Create Token

User must need to have valid token to access Smile portal APIs. provide a vaid username or smile number with your password to receive a token. 
