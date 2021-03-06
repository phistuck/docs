﻿#Commands : UploadAsync

**UploadAsync** is used to insert a new file or update content of an existing one in a file system.

## Syntax

{CODE upload_1@FileSystem\ClientApi\Commands\Files.cs /}

| Parameters | | |
| ------------- | ------------- | ----- |
| **filename** | string | The name of the uploaded file (full path) |
| **source** | Stream | The file content |
| **metadata** | RavenJObject | The file metadata (default: `null`) |
| **size** | long? | The file size. It is sent in `RavenFS-Size` header to validate number of bytes received on the server side (default: `null` - then `source.Length` value is used). If there is a mismatch between the size reported in the header and the number read bytes on the server side, then `BadRequestException` is thrown |

| Return Value | |
| ------------- | ------------- |
| **Task** | A task that represents the asynchronous upload operation |

## Example

{CODE upload_2@FileSystem\ClientApi\Commands\Files.cs /}