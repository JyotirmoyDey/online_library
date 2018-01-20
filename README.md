# online_library

## This application uses jwt to generate web tokens which can be used for logging in to the application.

End point urls:
For regular user:
http://localhost:3000/library/v1/books/ HTTP GET <br>
http://localhost:3000/library/v1/book/2 HTP GET <br>
more routes available in index.js file under routes folder <br>

For admin:
http://localhost:3000/library/v1/admin/users  HTTP GET <br>
http://localhost:3000/library/v1/admin/user/2 HTTP GET <br>

=======================================================================
There is no validation implemented for logging in to the application, however to view book details or user details validated user is required. <br>
login URL: http://localhost:3000/login HTTP POST <br>
sample payload:
{
"username" : "jyo@innovify.com",
"password" : "pass123"
}
Once sent, a sync reponse will be generated with a token url.

To view books
URL: http://localhost:3000/library/v1/books HTTP GET
request headers:
x-access-token : the token generated during login
x-key          : the userId.

=======================================================================
To check admin access urls proper functioning:
change routes/auth.js  line 45 from role: admin to user. We will get a 403 Not Authorized error.





