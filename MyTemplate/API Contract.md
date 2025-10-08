
### **GET /api/auth/verify**

```json
//Request Header
{
	Authorization: Bearer <JWT_TOKEN>
}
//Request Body is empty
```

```json
//Responce
{
  "success": true,
  "user": {
    "id": 12345678,
    "name": "Raju",
    "role": "user",
    "plan": "free"
  }
}

//Error
{
  "success": false,
  "message": "Token invalid or expired"
}
```



### **POST /api/auth/login**

```json
//Request
{
  "email": "raju6pro@gmail.com",
  "password": "abcxyz123"
}
```

```json
//Responce
{
  "success": true,
  "message": "Login successful",
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...",
  "user": {
    "id": 12345678,
    "name": "Raju",
    "role": "user",
    "plan": "free"
  }
}
//Error
{
  "success": false,
  "message": "Invalid email or password"
}
```


### **POST /api/auth/register**

```json
//Request
{
  "name": "Raju",
  "email": "raju6pro@gmail.com",
  "password": "abcxyz123"
}
```

```json
//Responce
{
  "success": true,
  "message": "User registered successfully. Please login."
}
//Error
{
  "success": false,
  "message": "Email already in use"
}
```
