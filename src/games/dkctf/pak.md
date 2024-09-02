## [DKC:TF](/formats.md#dkctf) > Archive (PAK)

| Type | Description |
| --- | --- |
| [CFormDescriptor] | [PACK form](#pack-form) |

## PACK Form
| Type | Description |
| --- | --- |
| [CFormDescriptor] | [TOCC form](#tocc-form) (table of contents) |

## TOCC Form
| Type | Description |
| --- | --- |
| [CChunkDescriptor] | [ADIR chunk](#adir-chunk) (asset directory) |
| [CChunkDescriptor] | [META chunk](#meta-chunk) (meta files) |
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
| Uint64 | File offset |
| Uint64 | File size |

### META Chunk
Some file types have a metadata file. These are stored in this chunk with the same file id as their main file.

| Type | Description |
| --- | --- |
| [List]&lt;[CPakFile::SMetaDataOffsetEntry](#cpakfilesmetadataoffsetentry)&gt; | Entries |

#### CPakFile::SMetaDataOffsetEntry
| Type | Description |
| --- | --- |
| [CObjectId] | File id |
| Uint32 | File offset |

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