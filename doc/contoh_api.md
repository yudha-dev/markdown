# Users API Spec

## Create Users

Endpoint ini digunakan untuk menambah user baru.

### Endpoint

**POST** `/api/user/create`

### Request Headers

| Key           | Value            | Required |
| ------------- | ---------------- | -------- |
| Authorization | `Bearer <token>` | Ya       |

### Request Body

Request Body harus dalam format JSON dan mencakup bidang berikut:

| Field   | Type   | Description | Required |
| ------- | ------ | ----------- | -------- |
| name    | string | Nama        | Ya       |
| address | string | Alamat      | Ya       |
| phone   | string | Nomor Hp    | Ya       |

### Contoh Request

```http
POST /api/user/create
Authorization: Bearer <token>
Content-Type: application/json
```

Request Body

```json
{
  "name": "Bayuda Pradani",
  "address": "Kudus, Jawa Tengah, Indonesia",
  "phone": "081234567890"
}
```

Respons Sukses (201)

```json
{
  "data": {
    "id": "1",
    "name": "Bayuda Pradani",
    "address": "Kudus, Jawa Tengah, Indonesia",
    "phone": "081234567890"
  },
  "message": "Data user berhasil ditambahkan."
}
```

Respons Error (400)

- 400 Bad Request: Jika ada bidang yang wajib diisi tidak lengkap atau tidak valid.

```json
{
  "error": "Bad Request",
  "message": "Bidang name harus diisi."
}
```

Respons Unauthorized (401)

- 401 Unauthorized: Jika token otorisasi tidak valid atau tidak disertakan.

```json
{
  "error": "Unauthorized",
  "message": "Token otorisasi tidak valid atau tidak ditemukan."
}
```

Respons Internal Server Error (500)

- 500 Internal Server Error: Jika terjadi kesalahan di server saat memproses permintaan.

```json
{
  "error": "Internal Server Error",
  "message": "Terjadi kesalahan di server. Silakan coba lagi nanti."
}
```

## Get Users

Endpoint ini mengambil daftar user yang tersedia dari database. Otorisasi diperlukan untuk mengakses endpoint ini.

### Endpoint

**GET** `/api/user`

### Request Header

| Key           | Value            | Required |
| ------------- | ---------------- | -------- |
| Authorization | `Bearer <token>` | Ya       |

### Query Parameters (Optional)

| Parameter | Type   | Description               |
| --------- | ------ | ------------------------- |
| name      | string | Filter berdasarkan nama   |
| address   | string | Filter berdasarkan alamat |
| phone     | string | Filter berdasarkan no_hp  |

### Contoh Request

```http
GET /api/user?name=Basic&price=50000
Authorization: Bearer <token>
```

Respons Sukses (200)

```json
{
  "data": [
    {
      "id": "1",
      "name": "Bayuda Pradani",
      "address": "Kudus, Jawa Tengah, Indonesia",
      "phone": "081234567890"
    },
    {
      "id": "2",
      "name": "Steve Jobs",
      "address": "Kudus, Jawa Tengah, Indonesia",
      "phone": "081234567891"
    }
  ]
}
```

Respons Error (400)

- 400 Bad Request: Jika parameter query tidak valid (misalnya, jika price tidak berupa angka).

```json
{
  "error": "Bad Request",
  "message": "Parameter query tidak valid."
}
```

Respons Unauthorized (401)

- 401 Unauthorized: Jika token otorisasi tidak valid atau tidak disertakan.

```json
{
  "error": "Unauthorized",
  "message": "Token otorisasi tidak valid atau tidak ditemukan."
}
```

Respons Internal Server Error (500)

- 500 Internal Server Error: Jika terjadi kesalahan di server saat memproses permintaan.

```json
{
  "error": "Internal Server Error",
  "message": "Terjadi kesalahan di server. Silakan coba lagi nanti."
}
```

## Update Users

Endpoint ini memungkinkan untuk memperbarui detail user. Otorisasi diperlukan untuk mengakses endpoint ini.

### Endpoint

**PUT** `/api/user/{id}`

### Request Header

| Key           | Value            | Required |
| ------------- | ---------------- | -------- |
| Authorization | `Bearer <token>` | Ya       |

### Request Body

Request body harus dalam format JSON dan mencakup bidang berikut:

| Field   | Type   | Description | Required |
| ------- | ------ | ----------- | -------- |
| name    | string | Nama        | Ya       |
| address | string | Alamat      | Ya       |
| phone   | string | Nomor Hp    | Ya       |

### Contoh Request

```http
PUT /api/user/{id}
Authorization: Bearer <token>
```

Request Body

```json
{
  "name": "Bayuda Pradani",
  "address": "Kudus, Jawa Tengah, Indonesia",
  "phone": "081234567890"
}
```

Respons Sukses (200)

```json
{
  "data": {
    "id": "1",
    "name": "Bayuda Pradani",
    "address": "Kudus, Jawa Tengah, Indonesia",
    "phone": "081234567890"
  },
  "message": "User berhasil di update."
}
```

Respons Error (400)

- 400 Bad Request: Jika ada kesalahan pada parameter atau body permintaan, seperti nama yang tidak valid.

```json
{
  "error": "Bad Request",
  "message": "Invalid input nama."
}
```

Respons Unauthorized (401)

- 401 Unauthorized: Jika token otorisasi tidak valid atau tidak disertakan.

```json
{
  "error": "Unauthorized",
  "message": "Token otorisasi tidak valid atau tidak ditemukan."
}
```

Respons Internal Server Error (500)

- 500 Internal Server Error: Jika terjadi kesalahan di server saat memproses permintaan.

```json
{
  "error": "Internal Server Error",
  "message": "Terjadi kesalahan di server. Silakan coba lagi nanti."
}
```

## Delete users

Endpoint ini memungkinkan superadmin untuk menghapus user yang sudah ada berdasarkan ID. Dibutuhkan otorisasi untuk mengakses endpoint ini.

### Endpoint

**DELETE** `/api/user/{id}`

### Request Header

| Key           | Value            | Required |
| ------------- | ---------------- | -------- |
| Authorization | `Bearer <token>` | Ya       |

### Request Body

Request body harus dalam format JSON dan mencakup bidang berikut:

| Parameter | Type   | Description | Required |
| --------- | ------ | ----------- | -------- |
| id        | string | ID User     | Ya       |

### Contoh Request

```http
DELETE /api/user/{id}
Authorization: Bearer <token>
```

Respons Sukses (200)

```json
{
  "message": "User berhasil dihapus."
}
```

Respons Error (400)

- Jika User dengan ID yang diberikan tidak ditemukan.

```json
{
  "error": "Not Found",
  "message": "User tidak ditemukan."
}
```

Respons Unauthorized (401)

- 401 Unauthorized: Jika token otorisasi tidak valid atau tidak disertakan.

```json
{
  "error": "Unauthorized",
  "message": "Token otorisasi tidak valid atau tidak ditemukan."
}
```

Respons Internal Server Error (500)

- 500 Internal Server Error: Jika terjadi kesalahan di server saat memproses permintaan.

```json
{
  "error": "Internal Server Error",
  "message": "Terjadi kesalahan di server. Silakan coba lagi nanti."
}
```
