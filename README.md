# API Spec

## Registrasi Akun

Request :
- Method : POST
- Endpoint : `/api/v1/register`
- Header : null
- Body :

```json 
{
    "nama_lengkap" : "string",
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
         "nama_lengkap" : "string",
         "nohp": "number",
         "email" : "string",
         "id_sekolah_kelas": "number",
         "id_kurikulum": "number",
         "status": "enum",
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
    "email" : "string",
    "password" : "string",
}
```

Response :

```json 
{
    "data" : {
         "id" : "string, unique",
         "nama_lengkap" : "string",
         "nohp": "number",
         "email" : "string",
         "id_sekolah_kelas": "number",
         "kelas_detail": {
            "id": "string, unique",
            "tingkat_kelas": "string",
            "jurusan": "string",
            "kelompok_sekolah": "string", 
         },
         "id_kurikulum": "number",
         "kurikulum_detail": {
            "id": "string, unique",
            "nama_kurilkulum": "string",
            "singkatan_kurikulum": "string",
            "tahun_terbit": "number"
         },
         "status": "enum",
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
         "nama_lengkap" : "string",
         "nohp": "number",
         "email" : "string",
         "id_sekolah_kelas": "number",
         "id_kurikulum": "number",
         "status": "enum",
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
         "nama_lengkap" : "string",
         "nohp": "number",
         "email" : "string",
         "id_sekolah_kelas": "number",
         "id_kurikulum": "number",
         "status": "enum",
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
         "nama_lengkap" : "string",
         "nohp": "number",
         "email" : "string",
         "id_sekolah_kelas": "number",
         "id_kurikulum": "number",
         "status": "enum",
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
         "nama_lengkap" : "string",
         "nohp": "number",
         "email" : "string",
         "id_sekolah_kelas": "number",
         "id_kurikulum": "number",
         "status": "enum",
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
    "nohp" : "number",
    "id_device" : "string, unique",
}
```

Response :

```json 
{
    "data" : {
         "id" : "string, unique",
         "nama_lengkap" : "string",
         "nohp": "number",
         "email" : "string",
         "id_sekolah_kelas": "number",
         "id_kurikulum": "number",
         "status": "enum",
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
         "nama_lengkap" : "string",
         "nohp": "number",
         "email" : "string",
         "id_sekolah_kelas": "number",
         "id_kurikulum": "number",
         "status": "enum",
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
         "nama_lengkap" : "string",
         "nohp": "number",
         "email" : "string",
         "id_sekolah_kelas": "number",
         "id_kurikulum": "number",
         "status": "enum",
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

## Get Product

Request :
- Method : POST
- Endpoint : `/api/v1/products`
- Header : null
- Body :

```json 
{
    "kota" : "string",
    "outlet" : "string",
    "kelas" : "string",
}
```
       
Response :

```json 
{
    "data" : {
         "id" : "string, unique",
         "name_product" : "string",
         "price" : "number",
         "jenis_layanan" : "string",
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
         "name_product" : "string",
         "price" : "number",
         "jenis_layanan" : "string",
         "product_detail": [
            {
                "icon": "string",
                "program_name": "string",
            }
         ],
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

# Laporan


## Laporan TOBK

Request :
- Method : GET
- Endpoint : `/api/v1/laporan/tobk/{id_user}`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data" : {
         "id" : "string, unique",
         "name" : "string",
         "hasil" : "number",
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

## Laporan Tes VAK

Request :
- Method : GET
- Endpoint : `/api/v1/laporan/vak/{id_user}`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data" : {
         "id" : "string, unique",
         "name" : "string",
         "hasil" : "number",
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

## Laporan Tes Kuis

Request :
- Method : GET
- Endpoint : `/api/v1/laporan/kuis/{id_user}`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data" : {
         "id" : "string, unique",
         "name" : "string",
         "hasil" : "number",
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

## Laporan Presensi Kegiatan Belajar Mengajar (KBM)

Request :
- Method : GET
- Endpoint : `/api/v1/laporan/presensi-kbm/{id_user}`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data" : {
         "id" : "string, unique",
         "name" : "string",
         "hasil" : "number",
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

## Laporan Aktivitas Belajar Siswa (ABS)

Request :
- Method : GET
- Endpoint : `/api/v1/laporan/abs/{id_user}`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data" : {
         "id" : "string, unique",
         "name" : "string",
         "hasil" : "number",
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

## Laporan Buku Sakti

Request :
- Method : GET
- Endpoint : `/api/v1/laporan/buku-sakti/{id_user}`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data" : [
        {
            "id" : "string, unique",
            "name" : "string",
            "jumlah_target_soal" : "number",
            "target_soal_dikerjakan": "number",
            "total_score": "number",
            "total_benar": "number",
            "total_salah": "number",
            "detail_target_soal": [
               {
                   "level_soal": "number", // cnth: level soal 1,2,3,4,5
                   "total_jawaban": {
                       "salah": "number",
                       "benar": "number"
                   }
   
               },
            ],
            "rank_nasional": "number",
            "rank_kota": "number",
            "rank_cabang": "number",
            "rank_gedung": "number",
            "rank_sekolah": "number",
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

## Laporan Progress Hasil Latihan Buku Sakti

Request :
- Method : GET
- Endpoint : `/api/v1/laporan/buku-sakti/progress/{id_user}`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data" : [
        {
            "progress": "string", // cnth : hari ini, minggu ini, bulan ini
            "kategori": [
                {
                    "nama_kategori": "string", // cnth: Literasi Bahasa, penalaran
                    "mapel": [
                        {
                            "id_mapel": "string",
                            "nama_mapel": "string", // matematika, b,Indo, b.ing, dll
                            "singkatan_maple": "string",
                            "benar": "number",
                            "salah": "number",
                            "total_target": "number",
                            "progress_target": "number"
                        },
                    ],
                },
            ],
        }
    ],

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```


# Leaderboard


## Leaderboard First Rank

Request :
- Method : GET
- Endpoint : `/api/v1/leaderboard/first-rank`
- Header : null
Response :

```json 
{
    "data" : [
        {
            "NIS": "string",
            "total": "number",
            "tipe": "string", // Nasional, Kota, cabang, gedung, sekolah
            "no_registrasi": "string",
            "score": "number",
            "nama_lengkap": "string",
            "url_profile": "string"
        },
    ],

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```


# TOBK

## TOBK

Request :
- Method : GET
- Endpoint : `/api/v1/tobk`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data" : [
        {
            "kode_tobk": "string",
            "id_sekolah_kelas": "number",
            "tahap_tobk": "string", // cnth : tobk1, tobk2, tobk3, dll
            "date_mulai_tobk": "date",
            "jam_mulai_tobk": "datetime",
            "durasi_tobk": "time",
            "status_pembayaran": "enum", // cnth: belum lunas, cicilan, lunas
            "type_tobk": "enum", // cnth: Online, Offline
        }
    ],

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```
