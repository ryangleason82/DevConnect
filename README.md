# DevConnect
MERN Full-Stack Application
Social media site to connect developers. View/create profiles, make posts, authentication, authorization, validation, 

Tools used:
    - Mongo Atlas: DB
    - Mongoose: object data modeling library for mongodb and nodeJS
    - Express: server framework for NodeJS
    - Postman: API development environment simulate client 
    - bcrypt: encrypt passwords 
    - JSON Web Token (JWT): access protected routes with tokens
    - Passport: works with authorization. Allows users to "travel" to different API routes based on permission
    - React
    - Nodejs

How Authentication Works:
    - Create encrypted password by combining salt and password to create hash
    - Hash is stored in db
    - Compare using bcrypt the given password and db password

How Authorization Works:
    - If authenticated, create payload comprised of whatever you want to pass as a part of the token, eg. id, name, avatar. Used as header
    - Token is then created with jwt.sign
    - Use Passport to put the token in header which will send it to server, validate so we can use it in express server when authorized (public vs private)
    - Worth noting: you can use Oauth with passport, not limited to JWT. Just uses a different strategy