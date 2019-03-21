# Useful Cookies

## JWT Debugger

Need [jtw.io][1] to help with the cookie.

## Admin cookie

```
access_token_cookie=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VyX2NsYWltcyI6eyJyb2xlIjoiYWRtaW4ifSwianRpIjoiMzg0MzRhYWItNDdiYS00YWJmLWFiZDYtZjlhMDlkMDQzOTVmIiwiZXhwIjoxNTUzNzc4MjY1LCJmcmVzaCI6ZmFsc2UsImlhdCI6MTU1MzE3MzQ2NSwidHlwZSI6ImFjY2VzcyIsIm5iZiI6MTU1MzE3MzQ2NSwiaWRlbnRpdHkiOiJhZG1pbiJ9.sPWMCPJdOF6J2tGgfWWM6n1FlCHWzy7IDc4ZylFY-ow
```

### Decoded

```json
//header
{
  "alg": "HS256",
  "typ": "JWT"
}
//payload
{
  "user_claims": {
    "role": "admin"
  },
  "jti": "38434aab-47ba-4abf-abd6-f9a09d04395f",
  "exp": 1553778265,
  "fresh": false,
  "iat": 1553173465,
  "type": "access",
  "nbf": 1553173465,
  "identity": "admin"
}
//verify signature
```

### Anonymous Cookie

```
access_token_cookie=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VyX2NsYWltcyI6eyJyb2xlIjoiYW5vbnltb3VzIn0sImp0aSI6IjM4ODBmZmUzLWY2MDktNDE1ZS1hMTI0LTY3MzZmYzM3YWJiYiIsImV4cCI6MTU1Mzc3ODg0NiwiZnJlc2giOmZhbHNlLCJpYXQiOjE1NTMxNzQwNDYsInR5cGUiOiJhY2Nlc3MiLCJuYmYiOjE1NTMxNzQwNDYsImlkZW50aXR5IjoiYW5vbnltb3VzIn0.tFY1EE5-ik5Rtj6pq4QQ6_46lZdbvZkNvAuzSJMvgJc
```

### Decoded

```json
//header
{
  "alg": "HS256",
  "typ": "JWT"
}
//payload
{
  "user_claims": {
    "role": "anonymous"
  },
  "jti": "3880ffe3-f609-415e-a124-6736fc37abbb",
  "exp": 1553778846,
  "fresh": false,
  "iat": 1553174046,
  "type": "access",
  "nbf": 1553174046,
  "identity": "anonymous"
}
//verify signature
```

## Error

```
session=eyJfZmxhc2hlcyI6W3siIHQiOlt7IiBiIjoiWkdGdVoyVnkifSwiPGI-RXJyb3I8L2I-OiBVc2VyIDEyMyBkb2Vzbid0IGV4aXN0Il19XX0.XJOOjQ.DsBqwfR415cN1NQ2k44lw5XGghM
```

### Decoded

```json
{
  "_flashes": [
    {
      " t": [
        {
          " b": "ZGFuZ2Vy"
        },
        "<b>Error</b>: User 123 doesn't exist"
      ]
    }
  ]
}
```

Also, [ZGFuZ2Vy][2] can be decoded to **danger**.

## XSS Session

```
session=.eJyrVopPy0kszkgtVrKKrlZSKIFQSUpWSlHubqVRRmGVSrU6SjZJdq5FRflFNvpJdlYKocWpRQo2xclFmQUldok5qUUlCRXFxQk2-lAhhZT81OI89RKF1IrM4hKl2NrYWgDnZiNH.XJOLPA.6s7VcpXmZNJWHEINC1B2U8kXHkM
```

[1]: https://jwt.io/
[2]: https://www.base64decode.org/