# Smile Restful APIs
* [Register User](#registeruser)
* [Create Token or Login](#createtoken)

## Register User

An user can register to smile protal using his username or smile voice number. user must be onboarded before the registration.
once user's username or smile voice number is verified he will receive the OTP on his registered mobile number to set password.

### Request

`POST /sra/registerbyotp`

    curl -i -H 'Accept: application/json' -d '{"customerId":10020,"identity":"0688944","key":"499504","newPassword":"test@123","confirmPassword":"test@123"}' https://smile.com.ng/sra/registerbyotp

## Create Token or Login

User must need to have valid token to access Smile portal APIs. provide a vaid username or smile number with your password to receive a token. 
