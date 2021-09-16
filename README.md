# Whatsapp_API
This code is in no way affiliated with, authorized, maintained, sponsored or endorsed by WhatsApp or any of its affiliates or subsidiaries. This is an independent and unofficial software. Use at your own risk. **Commercial use of this code/repo is strictly prohibited.**

# This api won't work with whatsapp Beta Upcoming Update May resolve this issue.

## Available Scripts

In the project directory, you can run:

### `npm install --force`

### How to RUN Applicaion

### `npm start`
First open [http://localhost:5000/auth/getqr](http://localhost:5000/auth/getqr)
> - scan the code with your whatsapp.
> - Then check Auth [http://localhost:5000/auth/checkauth](http://localhost:5000/auth/checkauth)
> - IF every thing work great. Continue testing your api.

## For testing api

- open index.js and edit the ph number in post method and message in editor
> Request Body
>   axios.post('http://localhost:5000/chat/sendmessage/91123456789', {// ph number wih your country code.91 here indicates for india
<hr>

   > message: 'hello world from heroku docker',})
<hr>

### DOCKER heroku deploy commands
# Download and install Docker better follow official document.

- heroku container:login
- heroku create app_name
- heroku container:push web -a app_name
- heroku container:release web -a app_name
- heroku open -a app_name

# API Doc
## Auth
<u>Getting QR Code</u>
 ``GET : /auth/getqr``
> Used to get a QR Code to Log into Whatsapp Web
	- If not logged in, returns a **QR Code**
	- If logged in, returns a "Authenticated" message.

## Chat
<u>Sending Messages</u>
``POST : /chat/sendmessage/<phone_number>``
> Request Body
> - message - contains the message to be sent
<hr>

<u>Sending Images</u>
``POST : /chat/sendimage/<phone_number>``
> Request Body
> - image - contains the base64 encoded / URL of image to be sent
> - caption - (optional) - contains caption for the message
<hr>

<u>Sending PDF</u>
``POST : /chat/sendpdf/<phone_number>``
> Request Body
> - pdf - contains the base64 encoded / URL of pdf to be sent
<hr>

<u>Sending Locations</u>
``POST : /chat/sendlocation/<phone_number>``
> Request Body
> - latitude - contains the string of latitude
> - longitude - contains the string of longitude
> - description - (optional) - contains description for the location
<hr>

<u>Get Chat By Id</u>
``GET : /chat/getchatbyid/<phone_number>``
>Returns a Chat

<hr>

<u>Get Chats</u>
``GET : /chat/getchats``
>Returns an Array of all Chats


## Group Chat
<u>Sending Messages to Group</u>
``POST : /group/sendmessage/<Group_Name>``
> Request Body
> - message - contains the message to be sent
<hr>

<u>Sending Images</u>
``POST : /group/sendimage/<Group_Name>``
> Request Body
> - image - contains the base64 encoded / URL of image to be sent
> - caption - (optional) - contains caption for the message
<hr>

<u>Sending PDF</u>
``POST : /group/sendpdf/<Group_Name>``
> Request Body
> - pdf - contains the base64 encoded / URL of pdf to be sent
<hr>

<u>Sending Locations</u>
``POST : /group/sendlocation/<Group_Name>``
> Request Body
> - latitude - contains the string of latitude
> - longitude - contains the string of longitude
> - description - (optional) - contains description for the location
<hr>


## Contact
<u>Get Contacts</u>
``GET : /contact/getcontacts``
>Returns an Array of Contacts of the Current Instance

<hr>

<u>Get Contact</u>
``GET : /contact/getcontact/<phone_number>``
>Returns a Contact

<hr>

<u>Get Profile Pic</u>
``GET : /contact/getprofilepic/<phone_number>``
>Returns a URL of the User's Profile Picture if Privacy Settings allow it

<hr>

<u>Is Registered User</u>
``GET : /contact/isregistereduser/<phone_number>``
>Returns if a given User is registered on Whatsapp
