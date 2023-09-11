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

### Login Tamu

Request :
- Method : POST
- Endpoint : `/api/v1/login-tamu`
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
         "daftar_produk_teaser": [
            {
                "id_komponent_produk": "string, unique",
                "id_bundling": "string, unique",
                "nama_bundling": "string",
                "nama_produk": "string",
                "id_jenis_produk": "string, unique",,
                "nama_jenis_produk": "string",
                "tanggal_awal": "date",
                "tanggal_akhir": "date",
                "id_sekolah_kelas": "string, unique",
            },
        ],
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

### Login Siswa

Request :
- Method : POST
- Endpoint : `/api/v1/login-siswa`
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
        "no_registrasi": "string, unique",
        "nama_lengkap": "string",
        "id_sekolah_kelas": "string, unique",
        "nama_sekolah_kelas": "12 SMA IPS",
        "token": "string, unique",
        "id_kelas_go": "string, unique",
        "nama_kelas_go": "tring",
        "id_jenis_layanan_go": "string, unique",
        "jenis_layanan_go": "string",
        "id_gedung_go": "string, unique",
        "nama_gedung_go": "string",
        "id_kota_go": "string, unique",
        "nama_kota_go": "string",
        "id_sekolah": "string, unique",
        "nama_sekolah": "string",
        "tahun_ajaran": "string",
        "status_bayar": "enum",
        "email": "string, unique",
        "email_ortu": "string, unique",
        "nomor_hp": "number, unique",
        "nomor_hp_ortu": "number, unique",
        "pilihan_ptn": [
            "pilihan": [
                {
                    "pilihan": "number",
                    "jurusan_id" : "string, unique",
                },
                {
                    "pilihan": "number",
                    "jurusan_id" : "string, unique",
                }
            ],
            "historyPilihan": [
                {
                    "pilihan": "number",
                    "id_jurusan": "string. unique",
                    "created_at": "date",
                }
            ]
        ],
        "jobOrtu": "string",
        "daftarAnak": "array",
         "daftarProduk": [
            {
                "id_komponent_produk": "string, unique",
                "id_bundling": "string, unique",
                "nama_bundling": "string",
                "nama_produk": "string",
                "id_jenis_produk": "string, unique",,
                "nama_jenis_produk": "string",
                "tanggal_awal": "date",
                "tanggal_akhir": "date",
                "id_sekolah_kelas": "string, unique",
            },
        ],
         "is_login": "boolean",
         "is_aktif": "enum", 
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

### Login Orang Tua

Request :
- Method : POST
- Endpoint : `/api/v1/login-ortu`
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
        "id_device": "string, unique",
        "token": "string, unique",
        "email_ortu": "string, unique",
        "nomor_hp_ortu": "number, unique",
        "job_ortu": "string",
        "daftarAnak": [
            {
                "no_registrasi": "string. unique",
                "data": {
                    "nama_lengkap": "string",
                    "id_sekolah_kelas": "string, unique",
                    "nama_sekolah_kelas": "12 SMA IPS",
                    "token": "string, unique",
                    "id_kelas_go": "string, unique",
                    "nama_kelas_go": "tring",
                    "id_jenis_layanan_go": "string, unique",
                    "jenis_layanan_go": "string",
                    "id_gedung_go": "string, unique",
                    "nama_gedung_go": "string",
                    "id_kota_go": "string, unique",
                    "nama_kota_go": "string",
                    "id_sekolah": "string, unique",
                    "nama_sekolah": "string",
                    "tahun_ajaran": "string",
                    "status_bayar": "enum",
                    "email": "string, unique",
                    "email_ortu": "string, unique",
                    "nomor_hp": "number, unique",
                    "nomor_hp_ortu": "number, unique",
                    "pilihan_ptn": [
                        "pilihan": [
                            {
                                "pilihan": "number",
                                "jurusan_id" : "string, unique",
                            },
                            {
                                "pilihan": "number",
                                "jurusan_id" : "string, unique",
                            }
                        ],
                        "historyPilihan": [
                            {
                                "pilihan": "number",
                                "id_jurusan": "string. unique",
                                "created_at": "date",
                            }
                        ]
                    ],
                    "daftarProduk": [
                        {
                            "id_komponent_produk": "string, unique",
                            "id_bundling": "string, unique",
                            "nama_bundling": "string",
                            "nama_produk": "string",
                            "id_jenis_produk": "string, unique",,
                            "nama_jenis_produk": "string",
                            "tanggal_awal": "date",
                            "tanggal_akhir": "date",
                            "id_sekolah_kelas": "string, unique",
                        },
                    ],
                }
            },
        ],
         "is_login": "boolean", 
         "is_aktif": "enum",
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


## Laporan TOBK UTBK

Request :
- Method : GET
- Endpoint : `/api/v1/laporan/tobk-utbk/{id_user}`
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

## Laporan TOBK UTBK Detail

Request :
- Method : GET
- Endpoint : `/api/v1/laporan/tobk-utbk/detail/{kode_tob}`
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

## Laporan TOBK ANBK

Request :
- Method : GET
- Endpoint : `/api/v1/laporan/tobk-anbk/{id_user}`
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

## Laporan TOBK STAN

Request :
- Method : GET
- Endpoint : `/api/v1/laporan/tobk-stan/{id_user}`
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

## Laporan TOBK UjianSekolah

Request :
- Method : GET
- Endpoint : `/api/v1/laporan/tobk-ujian-sekolah/{id_user}`
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
         "no_registrasi" : "string, unique",
         "visual" : "number",
         "auditory" : "number",
         "kinestetik" : "number",
         "dominan": [
            {
                "type": "string", // cnth: Visual, Auditory, Kinestetik
                "judul": "string",
                "deskripsi": "string"
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
    "data" : [
        {
            "id" : "string, unique",
            "kode_kuis" : "string, unique",
            "nama_kuis" : "string",
            "kuis_detail" : [
                {
                    "level_soal": "number", // cnth: 1, 2, 3, 4, 5
                    "total_benar": "number",
                    "total_salah": "number",
                }
            ],
            "createdAt" : "date",
            "updatedAt" : "date"
        },   
    ],

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
         {
             "date" : "date",
             "list_presensi": [
                {
                    "id" : "string, unique",
                    "kelas_go": "string, unique",
                    "nama_kelas_go": "string",
                    "waktu_presensi": "datetime",
                    "flag": "boolean", // apakah produk kelas sama dengan kelas go
                    "id_guru": "string, unique",
                    "nama_guru": "string",
                    "jadwal_mulai": "date",
                    "jadwal_selesai": "date",
                    "nama_gedung": "string",
                    "aktifitas": "string",
                    "pertemuan": "number",
                    "mata_pelajaran": "string",
                    "isFeedback": "boolean",
                    "feedbackPermission": "boolean",
                }
            ],
            "createdAt" : "date",
            "updatedAt" : "date"
         },
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
    "data" : [
        {
            "id": "string, unique", // cnth: id Buku teori, dll
            "menu": "string",
            "detail": "string",
            "masuk": "date",
            "keluar": "date"
        }
    ],

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
