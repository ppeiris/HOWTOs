### Web Request

- HTTP Request 
```
VERB /resource/locator HTTP 1.1
HEADER 1
HEADER 2
```

- Auth header
```
Authentication BASIC base64(username:password)
```

- Cookies 
  - key:value pairs
  - Cookies has domain pattern that is apply and pass via each request 
  - **Cookies that apply to root domain is a security issue because this allow to set cookies on any subdomain**
  - **If you can set cookies on domains that you are not suppose to, this is a security issue** 
 


