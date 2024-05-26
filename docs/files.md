# Files API

## List All Files

**Endpoint**: `GET /files`
**Description**: Retrieve a list of all files in the cloud storage.

**Request**:
```http
GET /files HTTP/1.1
Host: api.cloudfilemanager.com
```
**RESPONSE**:
```
[
  {
    "id": "file123",
    "name": "example.pdf",
    "size": 1024,
    "createdAt": "2024-05-26T12:34:56Z"
  },
  {
    "id": "file124",
    "name": "photo.jpg",
    "size": 2048,
    "createdAt": "2024-05-26T12:45:00Z"
  }
]
```

## Upload a New File

**Endpoint:** `POST /files`
**Description:** Upload a new file to the cloud storage.

**Request:**
```
POST /files HTTP/1.1
Host: api.cloudfilemanager.com
Content-Type: multipart/form-data

--boundary
Content-Disposition: form-data; name="file"; filename="example.pdf"
Content-Type: application/pdf

<file content here>
--boundary--
```
**Response:**
```
{
  "id": "file125",
  "name": "example.pdf",
  "size": 1024,
  "createdAt": "2024-05-26T13:00:00Z"
}
```

## Retrieve a File

**Endpoint:** `GET /files/{fileId}`
**Description:** Retrieve details of a specific file using its ID.

**Request:**
```
GET /files/file123 HTTP/1.1
Host: api.cloudfilemanager.com
```
**Response:**
```
{
  "id": "file123",
  "name": "example.pdf",
  "size": 1024,
  "createdAt": "2024-05-26T12:34:56Z"
}


```
## Delete a File

**Endpoint:** ` DELETE /files/{fileId}`
**Description:** Delete a specific file using its ID.

**Request:**
```
DELETE /files/file123 HTTP/1.1
Host: api.cloudfilemanager.com
```
**Response:**
`204 No Content
`








