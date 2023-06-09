# Spring Security JWT

Spring Security has built-in support for JWTs using oAuth2 Resource Server. 
In this example you are going to learn how to secure your APIs using JSON Web Tokens (JWT) with Spring Security.



## Commands to check the application

- http POST :8080/token --auth username:password -v  # to get the token
- http  :8080  'Authorization: Bearer TOKEN'         # to get the response on the "resource server: oauth2Resourceservr filter chain "



### Considerations

We forced to access the /token API with basic authentication and all the other resources 
with the token as if we were an Oauth2ResourceServer.

Note that to accomplish the above conditions we defined 2 different security filter chains.

### Remarks
When I generate new tokens for the same user, all these tokens are valid to access the oauth2 resource server,
only if I restart the server these tokens are not valid anymore. The encoder and the decoder have in common the "NimbusJwt-Encoder/Decoder" 
class.


#### References

- [Blog Post](https://www.danvega.dev/blog/2022/09/06/spring-security-jwt/)
- [YouTube](https://youtu.be/KYNR5js2cXE)