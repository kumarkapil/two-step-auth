# two-step-auth

This is a npm package that helps in verifying an Email address by sending OTP

## Installation

```bash
npm i --save two-step-auth
```
## What It Does
For people developing login sections they must know if the email Id the end user provides is valid, thus this package takes in the Email ID they provide and returns you a data OTP to verify them, and sends the client one via Email, Thus making sure only verified Emails are encouraged.

## Usage

**Kindly Provide a Company Name so the mail will be treated as important, but you can continue without it also**,
Usually the server responds within seconds ~ =< 2 seconds, incase the server is inactive it might take upto ~ <= 10 seconds, 
And you can handle the Time you need the OTP for your project in your script and do the necessary :)

```node.js
const {Auth} = require('two-step-auth');

async function login(emailId){
    const res = await Auth(emailId);
    // You can follw the above approach, But we recommend you to follow the one below, as the mails will be treated as important
    const res = await Auth(emailId, "Company Name");
    console.log(res);
    console.log(res.mail);
    console.log(res.OTP);
    console.log(res.success);
}

login("YourEmail@anyDomain.com")

```

## Output Format
The output will be a Javascript JSON object, making it easy to work

```node.js
{ mail: 'YourEmail@anyDomain.com', OTP: 141129, success: true }
YourEmail@anyDomain.com
141129
true

```
## Email Sample
![](images/result-screen.png)

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

## License
[MIT](https://choosealicense.com/licenses/mit/)
