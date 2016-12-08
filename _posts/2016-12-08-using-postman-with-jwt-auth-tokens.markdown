---
published: false
title: Using Postman with JWT Auth Tokens
layout: post
---
## What is JWT?
In the last couple of years I have been writing API's for mobile applications and web clients. When I first started writing APIs I had no idea about JWT or what it was, but once I started using it the benefits became clear as to why I should never go back to session based application architecture again - one word _scalability_. If there was only one reason I could give for trying to sell JWT tokens to someone it would be this, although there are plenty more (you can find out more on the [jwt.io](jwt.io) site which is a great resource). The reason JWT tokens scale so well is that you can generate the token on any device however I generally only generate the token on my servers which securely hold my `secret key`. Once the server generates the key it can be distributed via headers (my preference) or in the response body or however you like. The 'claims' are sent embedded in the token and can be seen by anyone that knows how to decode a JWT token so it is advisable not to put sensitive data in the token's claims. 

The key to securing JWT token's is in the secret key or private/public key. Whichever implementation you use is fine as long as the secret is kept secret, and this is why a JWT token can be used in the public domain because if it is tampered with in anyway the token's signature is then invalid and authentication will fail.

Anyway that is not the real reason for this post, and if you want to learn more about the suitability of using JWT tokens for you project there are plenty of resources available out there.

The real reason for this post is to help with testing your JWT authenticated APIs in Postman. So here goes.

## Testing your APIs with JWT authentication tokens
