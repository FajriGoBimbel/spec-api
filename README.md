# API Spec

## Registrasi Akun

Request :
- Method : POST
- Endpoint : `/api/v1/register`
- Header : null
- Body :

```json 
{
    "username" : "string",
    "nohp": "number",
    "email" : "string",
    "password" : "string",
    "password_confirm" : "string"
}
```

Response :

```json 
{
    "data" : {
         "id" : "string, unique",
         "name" : "string",
         "username" : "string",
         "nohp": "number",
         "email" : "string",
         "createdAt" : "date",
         "updatedAt" : "date"
    },

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```

## Login

Request :
- Method : POST
- Endpoint : `/api/v1/login`
- Header : null
- Body :

```json 
{
    "username" : "string",
    "password" : "string",
}
```

Response :

```json 
{
    "data" : {
         "id" : "string, unique",
         "name" : "string",
         "username" : "string",
         "nohp" : "number",
         "email" : "string",
         "token" : "string", 
         "createdAt" : "date",
         "updatedAt" : "date"
    },

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```

## Lupa Password

Request :
- Method : POST
- Endpoint : `/api/v1/lupa-password`
- Header : null
- Body :

```json 
{
    "email" : "string",
}
```

Response :

```json 
{
    "data" : {
         "id" : "string, unique",
         "name" : "string",
         "username" : "string",
         "nohp" : "number",
         "email" : "string",
         "token" : "string", 
         "createdAt" : "date",
         "updatedAt" : "date"
    },

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```

## Reset Password Pilihan 1

Request :
- Method : PUT
- Endpoint : `/api/v1/reset-password`
- Header : null
- Body :

```json 
{
    "id_user" : "string, unique",
    "new_password" : "string",
    "password_confirm" : "string",
}
```

Response :

```json 
{
    "data" : {
         "id" : "string, unique",
         "name" : "string",
         "username" : "string",
         "nohp" : "number",
         "email" : "string",
         "token" : "string", 
         "createdAt" : "date",
         "updatedAt" : "date"
    },

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```

## Reset Password Pilihan 2

Request :
- Method : PUT
- Endpoint : `/api/v1/reset-password/{id_user}`
- Header : null
- Body :

```json 
{
    "new_password" : "string",
    "password_confirm" : "string",
}
```

Response :

```json 
{
    "data" : {
         "id" : "string, unique",
         "name" : "string",
         "username" : "string",
         "nohp" : "number",
         "email" : "string",
         "token" : "string", 
         "createdAt" : "date",
         "updatedAt" : "date"
    },

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```

## Send OTP Via WhatsApp

Request :
- Method : POST
- Endpoint : `/api/v1/auth/otp-wa`
- Header : null
- Body :

```json 
{
    "nohp" : "string",
    "id_device" : "string, unique",
}
```

Response :

```json 
{
    "data" : {
         "id" : "string, unique",
         "name" : "string",
         "username" : "string",
         "nohp" : "number",
         "email" : "string",
         "token" : "string", 
         "createdAt" : "date",
         "updatedAt" : "date"
    },

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```

## Send OTP Via SMS

Request :
- Method : POST
- Endpoint : `/api/v1/auth/otp-sms`
- Header : null
- Body :

```json 
{
    "nohp" : "string",
    "id_device" : "string, unique",
}
```

Response :

```json 
{
    "data" : {
         "id" : "string, unique",
         "name" : "string",
         "username" : "string",
         "nohp" : "number",
         "email" : "string",
         "token" : "string", 
         "createdAt" : "date",
         "updatedAt" : "date"
    },

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```

## Send Email Verification Mobile App

Request :
- Method : POST
- Endpoint : `/api/v1/auth/otp-email`
- Header : null
- Body :

```json 
{
    "email" : "string",
    "id_device" : "string, unique",
}
```

Response :

```json 
{
    "data" : {
         "id" : "string, unique",
         "name" : "string",
         "username" : "string",
         "nohp" : "number",
         "email" : "string",
         "token" : "string", 
         "createdAt" : "date",
         "updatedAt" : "date"
    },

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```

## Send Email Verification Website Client

Request :
- Method : POST
- Endpoint : `/api/v1/auth/email`
- Header : null
- Body :

```json 
{
    "email" : "string",
}
```

Response :

```json 
{
    "data" : {
         "id" : "string, unique",
         "name" : "string",
         "username" : "string",
         "nohp" : "number",
         "email" : "string",
         "token" : "string", 
         "createdAt" : "date",
         "updatedAt" : "date"
    },

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```


## Create Product

Request :
- Method : POST
- Endpoint : `/api/v1/products`
- Header :
    - Content-Type: application/json
    - Authorization : "Bearer " + Token
- Body :

```json 
{
    "id" : "string, unique",
    "name" : "string",
    "price" : "long",
    "komar" : "number"
}
```

Response :

```json 
{
    "data" : {
         "id" : "string, unique",
         "name" : "string",
         "price" : "long",
         "komar" : "string",
         "createdAt" : "date",
         "updatedAt" : "date"
    },

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```

## Get Product Komar

Request :
- Method : GET
- Endpoint : `/api/v1/products/{id_komar}`
- Header :
    - Accept: application/json

Response :

```json 
{
    "data" : {
         "id" : "string, unique",
         "name" : "string",
         "price" : "long",
         "komar" : "string",
         "createdAt" : "date",
         "updatedAt" : "date"
    },

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```

## Get Product Detail

Request :
- Method : GET
- Endpoint : `/api/v1/products/{id_product}`
- Header :
    - Accept: application/json

Response :

```json 
{
    "data" : {
         "id" : "string, unique",
         "name" : "string",
         "price" : "long",
         "komar" : "string",
         "createdAt" : "date",
         "updatedAt" : "date"
    },

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```

## Update Product

Request :
- Method : PUT
- Endpoint : `/api/v1/products/{id_product}`
- Header :
    - Content-Type: application/json
    - Accept: application/json
- Body :

```json 
{
    "name" : "string",
    "price" : "long",
    "komar" : "string"
}
```

Response :

```json 
{
    "data" : {
         "id" : "string, unique",
         "name" : "string",
         "price" : "long",
         "komar" : "string",
         "createdAt" : "date",
         "updatedAt" : "date"
    },

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```

## List Product Pilihan 1

Request :
- Method : GET
- Endpoint : `/api/v1/products`
- Header :
    - Accept: application/json
- Query Param :
    - size : number,
    - search: string,
    - page : number

Response :

```json 
{
    "data" : [
        {
             "id" : "string, unique",
             "name" : "string",
             "price" : "long",
             "komar" : "string",
             "createdAt" : "date",
             "updatedAt" : "date"
        },
        {
             "id" : "string, unique",
             "name" : "string",
             "price" : "long",
             "komar" : "string",
             "createdAt" : "date",
             "updatedAt" : "date"
         }
    ],

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```

## List Product Pilihan 2

Request :
- Method : POST
- Endpoint : `/api/v1/products`
- Header :
    - Accept: application/json
- Body :

```json 
{
    "size" : "number",
    "search" : "string",
    "page" : "number"
}
```

Response :

```json 
{
    "data" : [
        {
             "id" : "string, unique",
             "name" : "string",
             "price" : "long",
             "quantity" : "integer",
             "createdAt" : "date",
             "updatedAt" : "date"
        },
        {
             "id" : "string, unique",
             "name" : "string",
             "price" : "long",
             "quantity" : "integer",
             "createdAt" : "date",
             "updatedAt" : "date"
         }
    ],

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```

## Delete Product

Request :
- Method : DELETE
- Endpoint : `/api/v1/products/{id_product}`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "code" : "number",
    "message" : "string",
    "status" : "string"
}
```