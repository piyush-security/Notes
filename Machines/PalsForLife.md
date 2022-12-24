- - -

### OS: 
### Web-Technology: 


#### IP: 

### USERS:

### CREDENTIALS (ANY):

- - -
## My Thinking  ( Attack & Enum Vectors ): 


- - -
## NMAP RESULTS : 
```sh
PORT     STATE    SERVICE     VERSION
22/tcp   filtered ssh
6443/tcp open  ssl/sun-sr-https?
| ssl-cert: Subject: commonName=k3s/organizationName=k3s
| Subject Alternative Name: DNS:kubernetes, DNS:kubernetes.default, DNS:kubernetes.default.svc.cluster.local, DNS:localhost, IP Address:10.10.130.218, IP Address:10.43.0.1, IP Address:127.0.0.1, IP Address:172.30.18.136, IP Address:192.168.1.244
| Not valid before: 2021-05-31T21:56:08
|_Not valid after:  2023-12-17T13:41:11
| fingerprint-strings: 
|   FourOhFourRequest: 
|     HTTP/1.0 401 Unauthorized
|     Cache-Control: no-cache, private
|     Content-Type: application/json
|     Date: Sat, 17 Dec 2022 13:42:06 GMT
|     Content-Length: 129
|     {"kind":"Status","apiVersion":"v1","metadata":{},"status":"Failure","message":"Unauthorized","reason":"Unauthorized","code":401}
|   GenericLines, Help, Kerberos, RTSPRequest, SSLSessionReq, TLSSessionReq, TerminalServerCookie: 
|     HTTP/1.1 400 Bad Request
|     Content-Type: text/plain; charset=utf-8
|     Connection: close
|     Request
|   GetRequest: 
|     HTTP/1.0 401 Unauthorized
|     Cache-Control: no-cache, private
|     Content-Type: application/json
|     Date: Sat, 17 Dec 2022 13:41:25 GMT
|     Content-Length: 129
|     {"kind":"Status","apiVersion":"v1","metadata":{},"status":"Failure","message":"Unauthorized","reason":"Unauthorized","code":401}
|   HTTPOptions: 
|     HTTP/1.0 401 Unauthorized
|     Cache-Control: no-cache, private
|     Content-Type: application/json
|     Date: Sat, 17 Dec 2022 13:41:26 GMT
|     Content-Length: 129
|_    {"kind":"Status","apiVersion":"v1","metadata":{},"status":"Failure","message":"Unauthorized","reason":"Unauthorized","code":401}
```

- - -
## Web Services Enumeration: 


#### NIKTO : 

### Subdomains : 

### WFUZZ  : 

##### FILES: / (Web Root) :

##### DIRECTORIES: / (Web Root)  : 

- - -
## OTHER ENUM :   



- - -
## PRIV-ESC :    


- - -
### Take Away Concepts : 



