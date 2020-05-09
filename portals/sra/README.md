# Smile Restful APIs
* [Register User](#registeruser)
* [Create Token or Login](#createtoken)

## Register User

An user can register to smile protal using his username or smile voice number. user must be onboarded before the registration.
once user's username or smile voice number is verified he will receive the OTP on his registered mobile number to set password.

### Request

`POST /sra/registerbyotp`

    curl -i -H 'Accept: application/json' -d '{"customerId":10020,"identity":"0688944","key":"499504","newPassword":"test@123","confirmPassword":"test@123"}' https://smile.com.ng/sra/registerbyotp
    
### Response(success)

    HTTP/1.1 200 OK
    {"done":true}
### Response(invalid identity)

    HTTP/1.1 404
    {"SRAError": {"errorDesc": "invalid identity","errorType": "business","errorCode": "SRA-0003"}}
    
*  **URL Params**

   **Required:**
 
   `id=[integer]`

* **Data Params**

  None

* **Success Response:**

  * **Code:** 200 <br />
    **Content:** `{ id : 12, name : "Michael Bloom" }`
 
* **Error Response:**

  * **Code:** 404 NOT FOUND <br />
    **Content:** `{ error : "User doesn't exist" }`

  OR

  * **Code:** 401 UNAUTHORIZED <br />
    **Content:** `{ error : "You are unauthorized to make this request." }`

* **Sample Call:**

  ```javascript
    $.ajax({
      url: "/users/1",
      dataType: "json",
      type : "GET",
      success : function(r) {
        console.log(r);
      }
    });
  ```
    
## Create Token or Login

User must need to have valid token to access Smile portal APIs. provide a vaid username or smile number with your password to receive a token. 
