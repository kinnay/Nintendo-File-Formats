## [DKC:TF](../../formats.md#dkctf) > Archive (PAK)

| Type | Description |
| --- | --- |
| [CFormDescriptor] | [PACK form](#pack-form) |

## PACK Form
Version 0:

| Type | Description |
| --- | --- |
| [CFormDescriptor] | [TOCC form](#tocc-form) (table of contents) |
| | File contents |

## TOCC Form
Version 1:

| Type | Description |
| --- | --- |
| [CChunkDescriptor] | [ADIR chunk](#adir-chunk) (asset directory) |
| [CChunkDescriptor] | [META chunk](#meta-chunk) (meta files) (optional) |
| [CChunkDescriptor] | [STRG chunk](#strg-chunk) (filenames) |

### ADIR Chunk
| Type | Description |
| --- | --- |
| [List]&lt;[CPakFile::SAssetDirectoryEntry](#cpakfilesassetdirectoryentry)&gt; | Entries |

#### CPakFile::SAssetDirectoryEntry
| Type | Description |
| --- | --- |
| [CFourCC] | File type |
| [CObjectId] | File id |
| Uint64 | File offset (absolute) |
| Uint64 | File size |

### META Chunk
Version: 1

Some file types have a metadata file. These are stored in this chunk with the same file id as their main file.

This chunk is absent when no file with metadata is present.

| Type | Description |
| --- | --- |
| [List]&lt;[CPakFile::SMetaDataOffsetEntry](#cpakfilesmetadataoffsetentry)&gt; | Entries |

#### CPakFile::SMetaDataOffsetEntry
The offset is relative to the offset field itself.

| Type | Description |
| --- | --- |
| [CObjectId] | File id |
| Uint32 | File offset |

The metadata is prefixed by a 32-bit integer that indicates its size.

### STRG Chunk
This chunk contains filenames. Most files in the archive are referenced by object id and don't have a filename however.

| Type | Description |
| --- | --- |
| [List]&lt;[IResourceCollection::CNameTagEntry](#iresourcecollectioncnametagentry)&gt; | 

#### IResourceCollection::CNameTagEntry
| Type | Description |
| --- | --- |
| [CObjectTag] | Object tag |
| [CString] | Filename |

[CFormDescriptor]: types.md#cformdescriptor
[CChunkDescriptor]: types.md#cchunkdescriptor
[CFourCC]: types.md#cfourcc
[CObjectId]: types.md#cobjectid
[CObjectTag]: types.md#cobjecttag
[List]: types.md#list
[CString]: types.md#cstring