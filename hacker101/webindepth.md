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
 
- How Cookies actually works 
  - Cookies added for _.example.com_ can be read by any subdomain of _example.cm_
  - Cookies added to a subdomain can be read by that subdoamin and its subdomains
  - A subdomain can set cookies for its subdomains and its parent
  - A Subdomain CAN NOT SET cookirs for its siblings 
  
