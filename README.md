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
            "inisial_kurikulum": "string",
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
        "nama_sekolah_kelas": "string",
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
                    "id_jurusan" : "string, unique",
                },
                {
                    "pilihan": "number",
                    "id_jurusan" : "string, unique",
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
        "job_ortu": "string",
         "daftar_produk": [
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
         "isLogin": "boolean",
         "isAktif": "enum", 
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
                    "nama_sekolah_kelas": "string",
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
         "isLogin": "boolean", 
         "isAktif": "enum",
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

## Change Password

Request :
- Method : PUT
- Endpoint : `/api/v1/change-password/{id_user}`
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

# LandingPage


## TOBK Go Nasional

Request :
- Method : GET
- Endpoint : `/api/v1/landing-page/tobk-go-nasional`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data": [
        {
            "title": "string, unique",
            "tanggal_pelaksanaan": "date",
            "soon_date": "string || date", // cnth: Coming Soon 10 Oktober 2023
            "soon_time": "string || date", // cnth: Pukul 09.00 - 12.00 WIB
            "deskripsi": [
                {
                    "content": "string" 
                }
            ],
            "path_router": "string",
        }
    ],

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```


## Top Guru

Request :
- Method : GET
- Endpoint : `/api/v1/landing-page/top-guru`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data": [
        {
            "nama_guru": "string",
            "mata_pelajaran": "string",
            "pengalaman": "string || number",
            "pencapaian": "string",
            "deskripsi": [
                { "content": "string" },
            ],
        },
    ],

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```

## Testimoni Siswa

Request :
- Method : GET
- Endpoint : `/api/v1/landing-page/testimoni-siswa`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data": [
        {
            "nama_siswa": "string",
            "title": "string",
            "description": "string",
            "link_video": "string",
        }
    ],

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
    "data" : [
        {
            "kode_tob" : "string, unique",
            "nama_tob" : "string",
            "sistem_penilaian" : "enum", // cnth : IRT
            "tanggal_selesai": "date",
            "isSolusi": "boolean",
            "info": [
                {
                    "id_kelompok_jurusan":  "string, unique",
                    "nama_kelompok": "string",
                    "universitas": "string",
                    "jurusan": "string",
                    "passing_grade": "number",
                    "nilai_score": "number",
                }
            ],
            "list_nilai": [
                {
                    "nama_subtes":  "string",
                    "nilai_score": "number",
                }
            ],
            "isEPB": "boolean",
            "link_download_epb": "string",
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
    "data" : [
        "pilihan_ptn": [
            {
                "id_kelompok_jurusan": "string, unique",
                "nama_kelompok_jurusan": "string",
                "universitas": "string",
                "jurusan": "string",
                "passing_grade": "number",
                "nilai_score": "number"
            },
        ],
        "nilai_tobk": [
            {
                "kode_soal": "string, unique",
                "nama_kelompok_ujian": "string",
                "inisial_kelompok_ujian": "string",
                "total_benar": "number",
                "total_salah": "number",
                "total_kosong": "number",
                "jumlah_soal": "number",
                "nilai": "number",
                "nilai_max": "number",
            },
        ]
    ],

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
    "data" : [
        {
            "kode_tob" : "string, unique",
            "nama_tob" : "string",
            "sistem_penilaian" : "enum", // cnth : IRT
            "tanggal_selesai": "date",
            "isSolusi": "boolean",
            "info": [
                {
                    "id_kelompok_jurusan":  "string, unique",
                    "nama_kelompok": "string",
                    "universitas": "string",
                    "jurusan": "string",
                    "passing_grade": "number",
                    "nilai_score": "number",
                }
            ],
            "list_nilai": [
                {
                    "nama_subtes":  "string",
                    "nilai_score": "number",
                }
            ],
            "isEPB": "boolean",
            "link_download_epb": "string",
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
    "data" : [
        {
            "kode_tob" : "string, unique",
            "nama_tob" : "string",
            "sistem_penilaian" : "enum", // cnth : IRT
            "tanggal_selesai": "date",
            "isSolusi": "boolean",
            "info": [
                {
                    "id_kelompok_jurusan":  "string, unique",
                    "nama_kelompok": "string",
                    "universitas": "string",
                    "jurusan": "string",
                    "passing_grade": "number",
                    "nilai_score": "number",
                }
            ],
            "list_nilai": [
                {
                    "nama_subtes":  "string",
                    "nilai_score": "number",
                }
            ],
            "isEPB": "boolean",
            "link_download_epb": "string",
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
    "data" : [
        {
            "kode_tob" : "string, unique",
            "nama_tob" : "string",
            "sistem_penilaian" : "enum", // cnth : IRT
            "tanggal_selesai": "date",
            "isSolusi": "boolean",
            "info": [
                {
                    "id_kelompok_jurusan":  "string, unique",
                    "nama_kelompok": "string",
                    "universitas": "string",
                    "jurusan": "string",
                    "passing_grade": "number",
                    "nilai_score": "number",
                }
            ],
            "list_nilai": [
                {
                    "nama_subtes":  "string",
                    "nilai_score": "number",
                }
            ],
            "isEPB": "boolean",
            "link_download_epb": "string",
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
                            "id_mapel": "string, unique",
                            "nama_mapel": "string", // matematika, b,Indo, b.ing, dll
                            "inisial_maple": "string",
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

## Leaderboard

Request :
- Method : GET
- Endpoint : `/api/v1/leaderboard`
- Header : null
Response :

```json 
{
    "data" : [
        {
            "nasional_top_third": [
                {
                    "no_registrasi": "string, unique",
                    "nama_lengkap": "string",
                    "level": "number",
                    "sort": "number",
                    "rank": "number",
                    "total": "number",
                }
            ],
            "rank_position": [
                {
                    "type_rank": "string", //cnth: nasional, kota, cabang, gedung, sekolah

                    // Get My Position Rank dan Get 3 Rank teratas dan 3 Rank terbawah
                    "my_position_rank": [
                        {
                            "no_registrasi": "string, unique",
                            "nama_lengkap": "string",
                            "level": "number",
                            "sort": "number",
                            "rank": "number",
                            "total": "number",
                        }
                    ]
                }
            ]
        },
    ],

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```


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
            "NIS": "string, unique",
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

# Perguruan Tinggi

## Universitas

Request :
- Method : GET
- Endpoint : `/api/v1/universitas`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data" : [
        {
            "id_universitas": "string, unique",
            "nama_universitas": "string",
            "inisial_universitas": "string",
            "jenis": "enum"
        }
    ],

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```

## Jurusan

Request :
- Method : GET
- Endpoint : `/api/v1/universitas/{id_universitas}`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data" : [
        {
            "id_universitas": "string, unique",
            "id_jurusan": "string, unique",
            "nama_jurusan": "string",
            "kelompok_jurusan": "string",
            "rumpun_jurusan": "string",
            "info": {
                "peminat": [
                    {
                        "jumlah": "number",
                        "tahun": "string"
                    }
                ],
                "tampung": [
                    {
                        "jumlah": "number",
                        "tahun": "string"
                    }
                ],
            },
            "passing_grade": "number",
            "lintas_jurusan": "boolean",
            "deskripsi": "string",
            "lapangan_kerja": "string"
        }
    ],

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```

## Jurusan Detail

Request :
- Method : GET
- Endpoint : `/api/v1/universitas/jurusan/{id_jurusan}`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data" : {
        "id_universitas": "string, unique",
        "id_jurusan": "string, unique",
        "nama_jurusan": "string",
        "kelompok_jurusan": "string",
        "rumpun_jurusan": "string",
        "info": {
            "peminat": [
                {
                    "jumlah": "number",
                    "tahun": "string"
                }
            ],
            "tampung": [
                {
                    "jumlah": "number",
                    "tahun": "string"
                }
            ],
        },
        "passing_grade": "number",
        "lintas_jurusan": "boolean",
        "deskripsi": "string",
        "lapangan_kerja": "string"
    },

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```

## Pilihan PTN User

Request :
- Method : GET
- Endpoint : `/api/v1/ptn-pilihan/{id_user}`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data" : [
        "pilihan": [
            {
                "pilihan": "number",
                "id_universitas": "string, unique",
                "nama_universitas": "string",
                "inisial_universitas": "string",
                "id_jurusan" : "string, unique",
                "nama_jurusan": "string",
                "peminat": "number",
                "daya_tampung": "number",
                "created_at": "date",
                "updated_at": "date",
            },
        ],
        "historyPilihan": [
            {
                "pilihan": "number",
                "id_universitas": "string. unique",
                "id_jurusan": "string. unique",
                "nama_universitas": "string",
                "inisial_universitas": "string",
                "nama_jurusan": "string",
                "peminat": "number",
                "daya_tampung": "number",
                "created_at": "date",
            }
        ]
    ],

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```


# Tryout

## Tryout Soal (Get Soal TO)

Request :
- Method : GET
- Endpoint : `/api/v1/tryout`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data" : [
        {
            "id_soal": "string, unique",
            "soal": "string",
            "opsi": [
                {
                    "pilihan": "string, unique", // cnth:  A, B, C, D
                    "text": "string",
                    "isJawaban": "boolean",
                }
            ],
            "id_wacana": "string, unique",
            "id_tipe_soal": "string, unique",
            "tipe_soal": "string",
            "tingkat_kesulitan": "number",
            "wacana": "string",
            "nama_kelompok_ujian": "string",
            "kode_paket": "string, unique",
            "id_bundel": "string, unique",
            "id_kelompok_ujian": "string, unique",
            "id_video": "string, unique",
            "nomor_soal": "number"
        }
    ],

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```

## List Produk Tryout (Get Daftar TOB)

Request :
- Method : GET
- Endpoint : `/api/v1/tryout`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data" : [
        {
            "kode_tob": "string, unique",
            "nama_tob": "string",
            "jenis_tob": "string || enum",
            "tanggal_mulai": "date",
            "tanggal_selesai": "date",
            "jarak_antar_paket": "number",
            "isKurikulumMerdeka": "boolean",
            "isBersyarat": "boolean",
            "jenis": "string",
        }
    ],

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```


## Paket tryout (Get Daftar Paket TO)

Request :
- Method : GET
- Endpoint : `/api/v1/tryout`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data" : [
        {
            "kode_tob": "string, unique",
            "id_kelompok_ujian": "string, unique",
            "id_jenis_produk": "string, unique",
            "id_sekolah_kelas": "string, unique",
            "kode_paket": "string, unique",
            "deskripsi": "string",
            "nomor_urut": "number",
            "isBlockingTime": "boolean",
            "totalWaktu": "time",
            "total_soal": "number",
            "isRandom": "boolean",
            "isSelesai": "boolean",
            "isPernahMengerjakan": "boolean",
            "isOK": "boolean",
            "tanggal_mulai": "date",
            "tanggal_deadline": "date",
            "tanggal_pengumpulan": "date",
            "merk": "Unknown",
            "keterangan": null,
            "pilihan_siswa": null,
            "flag": null,
            "waktu_habis": "boolean",
            "isWajib": "boolean"
        }
    ],

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```

## Kisi-Kisi tryout (Get Kisi-kisi)

Request :
- Method : GET
- Endpoint : `/api/v1/tryout`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data" : [
        {
           "kelompok_ujian": "string",
           "info": [
                {
                    "nama_bab": "string",
                    "kode_bab": "string",
                    "level_teori": "string || enum",
                    "id_mapel": "string",
                    "inisial_mapel": "string"
                },
           ]
        }
    ],

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```

## Cek syarat tryout (Cek Boleh TO)

Request :
- Method : GET
- Endpoint : `/api/v1/tryout`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data": {
            "isLulus": "boolean",
            "isSelesai": "boolean",
            "total_soal": "number",
            "total_benar": "number",
            "total_salah": "number",
            "total_kosong": "number",
            "listEmpati": [
                {
                    "kode_tob": "string, unique",
                    "kode_paket": "string, unique",
                    "total_soal": "number",
                    "total_benar": "number",
                    "total_salah": "number",
                    "isBoleh": "boolean",
                },
            ]
    },

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```

## Get Daftar Soal TO

Request :
- Method : GET
- Endpoint : `/api/v1/tryout`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data": {
        "waktu": "time",
        "data_detail": [
            {
                "wacana": "",
                "id_soal": "string, unique",
                "nomor_soal": "1",
                "id_wacana": "string, unique",
                "id_bundel": "string, unique",
                "id_kelompok_ujian": "string, unique",
                "nama_kelompok_ujian": "string",
                "id_video": "string, unique",
                "soal": "string",
                "opsi": [
                    {
                        "pilihan": "string, unique", // cnth:  A, B, C, D
                        "text": "string",
                        "isJawaban": "boolean",
                    }
                ],
                "tipe_soal": "enum || string",
                "tingkat_kesulitan": "number",
                "kode_paket": "EMWA-754" //cnth: EMWA-754
            }
        ]
    },

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```

## Get Syarat TO (Belum ada diaji)

Request :
- Method : GET
- Endpoint : `/api/v1/tryout`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data" : [
        {
            "kode_tob": "string, unique",
            "nama_tob": "string",
            "jenis_tob": "string || enum",
            "tanggal_mulai": "date",
            "tanggal_selesai": "date",
            "jarak_antar_paket": "number",
            "isKurikulumMerdeka": "boolean",
            "isBersyarat": "boolean",
            "jenis": "string",
        }
    ],

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```

## Get Daftar Paket Basic

Request :
- Method : GET
- Endpoint : `/api/v1/tryout`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data": [
        {
            "kode_tob": "string, unique",
            "kode_paket": "string, unique",
            "deskripsi": "string",
            "isLulus": "boolean",
            "id_jenis_produk": "string, unique",
            "IsBlockingTime": "boolean",
            "id_sekolah_kelas": "41",
            "tanggal_berlaku": "date",
            "tanggal_kedaluwarsa": "date",
            "total_waktu": "time",
            "total_soal": "number",
            "jenis": "string"
        }
    ],

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```

## Get Daftar Paket TO 2

Request :
- Method : GET
- Endpoint : `/api/v1/tryout`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data": [
        {
            "kode_tob": "string, unique",
            "id_kelompok_ujian": "string, unique",
            "id_jenis_produk": "string, unique",
            "id_sekolah_kelas": "string, unique",
            "kode_paket": "string, unique",
            "deskripsi": "string",
            "nomor_urut": "number",
            "isBlockingTime": "boolean",
            "tanggal_berlaku": "date",
            "tanggal_kadaluwarsa": "date",
            "total_waktu": "time",
            "total_soal": "number",
            "jenis": "string",
            "isSelesai": "boolean",
            "isPernahMengerjakan": "boolean",
            "tanggal_mulai": "date",
            "tanggal_deadline": "date",
            "tanggal_pengumpulan": "date",
            "merk": "Unknown",
            "waktu_habis": "boolean"
        }
    ],

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```


## Get Daftar Bundel

Request :
- Method : GET
- Endpoint : `/api/v1/tryout`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data": [
        {
            "id_bundel": "string, unique",
            "kode_tob": "string, unique",
            "kode_paket": "string, unique",
            "deskripsi": "string",
            "id_kelompok_ujian": "string, unique",
            "nama_kelompok_ujian": "string",
            "inisial": "string",
            "waktu_pengerjaan": "time",
            "total_soal": "number",
            "opsi_urut": "string",
            "id_sekolah_kelas": "string, unique",
            "jenis": "string" //cnth: teaser
        }
    ],

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```


## Get Daftar Bab

Request :
- Method : GET
- Endpoint : `/api/v1/tryout`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data": [
        {
            "bab_utama": "string",
            "info": [
                {
                    "nama_bab": "string",
                    "jumlah_soal": "number",
                    "kode_bab": "string, unique",
                    "id_bundel": "string, unique",
                }
            ]
        }
    ],

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```


## Get Soal

Request :
- Method : GET
- Endpoint : `/api/v1/tryout`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :




```json 
{
    "data": [
        {
            "waktu": "time",
            "data_detail": [
                {
                    "id_bundel": "string, unique",
                    "kode_bab": "string, unique",
                    "id_soal": "string, unique",
                    "id_kelompok_ujian": "string, unique",
                    "nama_kelompok_ujian": "string",
                    "soal": "string",
                    "opsi": [
                        {
                            "opsi_detail": [
                                {
                                    "pilihan": "string, unique", // cnth:  A, B, C, D
                                    "text": "string",
                                    "isJawaban": "boolean",
                                }
                            ],
                            "nilai": {
                                "fullcredit": "number",
                                "halfcredit": "number",
                                "zerocredit": "number",
                            }
                        }
                    ],
                    "id_wacana": "string, unique",
                    "tipe_soal": "string || enum",
                    "tingkat_kesulitan": "number",
                    "nomor_soal": "number",
                    "id_video": null,
                    "wacana": "string",
                    "inisial_mapel": "string"
                }
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


# Simulasi

## Get Simulasi Nilai

Request :
- Method : GET
- Endpoint : `/api/v1/simulasi/`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data": [
        {
            "kode_tob": "string, unique",
            "tob": "string",
            "isSelected": "boolean",
            "isFix": "boolean",
            "detail_nilai": {
                "nama_subtes":  "string",
                "nilai_score": "number",
            }
        }
    ],

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```


## Get Simulasi Pilihan

Request :
- Method : GET
- Endpoint : `/api/v1/simulasi/`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data": [
        {
            "prioritas": "number",
            "status": "boolean",
            "universitas": "string",
            "id_jurusan": "string, unique",
            "nama_jurusan": "string",
            "passing_grade": "number",
            "peminat": {
                "total": "number",
                "tahun": "string"
            },
            "tampung": {
                "total": "number",
                "tahun": "string"
            }
        }
    ],

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```


## Get Simulasi Hasil

Request :
- Method : GET
- Endpoint : `/api/v1/simulasi/`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data": [
        {
            "prioritas": "number",
            "status": "boolean",
            "universitas": "string",
            "id_jurusan": "string, unique",
            "nama_jurusan": "string",
            "rumpun": "string || null",
            "passing_grade": "number",
            "peminat": {
                "total": "number",
                "tahun": "string"
            },
            "tampung": {
                "total": "number",
                "tahun": "string"
            },
            "total": "number",
            "saran": "string || null"
        }
    ],

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```

## My Bookmark 

Request :
- Method : GET
- Endpoint : `/api/v1/simulasi/`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data": [
        {
            "icon_mapel": "string",
            "list_bookmark": [
                {
                    "id_soal": "string, unique",
                    "isPaket": "boolean",
                    "kode_bab": "string, unique",
                    "kode_tob": "string, unique",
                    "nama_bab": "string",
                    "id_bundel": "string, unique",
                    "isSimpan": "boolean",
                    "kode_paket": "string, unique",
                    "nomor_soal": "number",
                    "last_update": "date",
                    "id_jenis_produk": "number",
                    "nomor_soal_siswa": "number",
                    "nama_jenis_produk": "string",
                    "tanggal_kadaluwarsa": "date || null"
                },
            ],
            "id_kelompok_ujian": "string, unique",
            "nama_kelompok_ujian": "string",
            "inisial_kelompok_ujian": "string"
        }
    ],

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```


# Pembayaran

## Get Pembayaran

Request :
- Method : GET
- Endpoint : `/api/v1/simulasi/`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data": [
        {
            "id_pembelian": "string, unique",
            "total_harga": "number",
            "total_dibayar": "number",
            "sisa_bayar": "number",
            "status": "enum",
        }
    ],

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```


## Get Pembayaran Detail

Request :
- Method : GET
- Endpoint : `/api/v1/simulasi/`
- Header :
    - Accept: application/json
    - Authorization : "Bearer " + Token
Response :

```json 
{
    "data": [
        {
            "id_pembelian": "string, unique",
            "total_harga": "number",
            "total_dibayar": "number",
            "sisa_bayar": "number",
            "status": "enum",
            "tanggal_jatuhtempo": "Date"
        }
    ],

    "meta" : {
        "code" : "number",
        "message" : "string", 
        "status" : "string",
    }
}
```