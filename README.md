# CRUD-API
This a Lib. build to do basic crud Operations with nothing more than Node JS. The API allows you to create tokens and users to save with CRUD operations to any database.You can Create Users, and Manage tokens all with this API.No Packages, Only Native Node.Passwords are hashed with SHA 256 Encryption.Built in API With Https and Http Test Servers.No Need to Install anything just clone the repo CD into CRUD-API and Run Node Index.js.  Can Be installed through NPM as Lib.  Build with Simplicity,Speed, and security in mind.To Run File Cd into Index.js Directory and run "node index.js". This Will Start Server, With Options for Http/ and Https. Can Create Users, Tokens and  store users and Data from API. Request Routes Below. 
Data Is converted to JSON for File Saving and transfer. 



Arguments and functions to use for Crud Operations if you want to write your own. Saves as JSON Data and JSON token. 




Example Usage  of Crud Operations API Routes and required Headers Below Crud Operations file. 

Frist Import variable from ./lib/data       

ex-    var _data = require('./lib/data'); //Uses FS Native Node Module


The Arguments for Each Function must be provided to read and Write Data. 

to Create a file  must provide 4 arguments (dir, file, data, callback) 

example-    var _data = require('./lib/data');

 _data.create('users',phone,userObject,function(err){
            if(!err){
              callback(200);
            } else {
              console.log(err);
              callback(500,{'Error' : 'Could not create the new user'});
            }
          });
 
 Read
          example-    var _data = require('./lib/data');
          
to Read a file  must provide 3 arguments (dir, file, callback) 

_data.read('users',phone,function(err,data){
      if(!err && data){
        // do something and callback 200 when done;
        //return read Data Etc then 200 Status Code 
        callback(200,data);
      } else {
        callback(404);
      }
    });



Update A File  example-    var _data = require('./lib/data');
   to Update a a file  must provide 3 arguments (dir, file,DataToUpdate, callback); 
Example 
// Store the new updates
          _data.update('users',phone,userData,function(err){
            if(!err){
              callback(200);
            } else {
              console.log(err);
              callback(500,{'Error' : 'Could not update the user.'});
            }
          });

Delete Example 
      var _data = require('./lib/data');

delete = function(dir,file,callback) As Arguments 


 _data.delete('users',phone,function(err){
          if(!err){
          //Remove Some File and Return 200 to know the process worked. 
            callback(200);
          } else {
            callback(500,{'Error' : 'Could not delete the specified user'});
          }


Routes For API- To Create/ Remove/ Delete/ Add Users to Data Base ( some Routes MUST have JSON TOKEN) from Token Route

/ping- Returns code 200 if running correctly
/users- acceptableMethods = ['post','get','put','delete']) 
 /Tokens 
  acceptableMethods = ['post','get','put','delete'];

           Users - post (to Create)
             // Required data on Headers: firstName, lastName, phone, password, tosAgreement
           Users - get 
             // Required data on Headers : phone (Must have token to request user for auth) 
             
          Users - Delete 
            //  Requires Token From Tokens Route to Remove a User
            
         Users - Put 
             // Must Have Token to Update User Information 
            //Required data: phone
            // Optional data: firstName, lastName, password (at least one must be specified)
            
            
       
 /Tokens 
  acceptableMethods = ['post','get','put','delete'];
  Tokens - post
// Required data: phone, password
// Optional data: none
handlers._tokens.post = function(data,callback)


// Tokens - get
// Required data: id
// Optional data: none
handlers._tokens.get
  
  
Tokens - put
// Required data: id, extend
// Optional data: none
            
          

// Tokens - delete
// Required data: id
// Optional data: none
handlers
  // Check that id is valid
  //then Can Delete 


  
If there are any questions on using this API or anyone would like to contribute please send me an email or message 
joshuaaguilar20@gmail.com 







