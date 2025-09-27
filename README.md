# Metadata-Extraction-using-ExifTool-log2timeline-and-Hidden-Data-Search-using-Steganography-Tools
## AIM:
To extract metadata, perform timeline analysis, and search for hidden data using forensic tools like ExifTool, log2timeline, and steganography detection tools.
## REQUIREMENTS
- **Operating System:** Kali Linux (preferred) or any Linux distro with forensic tools
- **Tools:**
     -  ExifTool – For metadata extraction
     -  plaso/log2timeline – For timeline analysis
- **Steganography tools:** steghide, zsteg, binwalk
- **Test Data:** Image, video, and document files (some with embedded hidden data)
## ARCHITECTURE DIAGRAM
```mermaid
flowchart TD
    A[Sample Files - Images, Videos, Documents] --> B[Metadata Extraction with ExifTool]
    B --> C[Event Timeline Creation with log2timeline]
    C --> D[Hidden Data Search with Steganography Tools]
    D --> E[Evidence Analysis and Documentation]
```
## DESIGN STEPS:
### Step 1:
Use exiftool to extract metadata from files such as images, documents, and videos.

### Step 2:
Use log2timeline and plaso to create and analyze event timelines from system logs and file metadata.

### Step 3:
Apply steganography detection tools like steghide, zsteg, or binwalk to uncover hidden data in media files.

## PROGRAM:
| Step | Action                  | Tool                 | Output                           |
| ---- | ----------------------- | -------------------- | -------------------------------- |
| 1    | Extract file metadata   | ExifTool             | Metadata fields, GPS, timestamps |
| 2    | Generate event timeline | log2timeline / plaso | CSV/HTML timeline                |
| 3    | Search for hidden data  | steghide / binwalk   | Extracted hidden files           |
| 4    | Document findings       | Manual report        | Investigation record             |


## OUTPUT:
### A. Using ExifTool – for file metadata
- **Install:**
```bash
sudo apt update
sudo apt install exiftool -y
```
<img width="846" height="786" alt="image" src="https://github.com/user-attachments/assets/de8a8b6a-21f8-4cd9-b428-0f5e1c69edf9" />

- **Extract metadata from a file:**
```bash
exiftool image.jpg
```
<img width="897" height="622" alt="image" src="https://github.com/user-attachments/assets/89e64efa-738e-4718-8ce1-180073c8b214" />

- **Batch process a folder:**
  
```bash
exiftool -r /path/to/folder
```
<img width="899" height="652" alt="image" src="https://github.com/user-attachments/assets/a37c4e58-951a-401a-9e0f-658f52d89b58" />

- **Useful flags:**
  
- ```-G: Show metadata group```

- ```-time:all: Show only timestamps```

- ```-GPSLatitude -GPSLongitude: Extract GPS data```
<img width="898" height="636" alt="image" src="https://github.com/user-attachments/assets/f001616c-2bec-46ad-84c6-4e937ba151bc" />


### install log2timeline
```
sudo apt install plaso -y
```
<img width="905" height="651" alt="image" src="https://github.com/user-attachments/assets/e0d9c437-3706-4272-9d6c-8e3b02e240ea" />

```
sudo apt install steghide -y
```
<img width="899" height="525" alt="image" src="https://github.com/user-attachments/assets/2a0043cc-8982-4db3-9492-9ecf61ceaa9d" />

- **Embed data**
```
steghide embed -cf /home/kali/Downloads/wallpaper.jpg -ef /home/kali/Downloads/secret.txt
```
<img width="892" height="774" alt="image" src="https://github.com/user-attachments/assets/5d79399b-03e5-4e70-a667-372473216ec7" />

- **Extract hidden data:**
```
steghide extract -sf hidden.jpg
```
<img width="894" height="753" alt="image" src="https://github.com/user-attachments/assets/8b2ea77e-109a-4c6d-a8d2-f7a9e00c4e9e" />

### Using binwalk – for file analysis
```bash
sudo apt install binwalk -y
binwalk suspicious.jpg
```
<img width="897" height="486" alt="image" src="https://github.com/user-attachments/assets/e1253890-eb8a-4cfe-9eee-3de2e79c4ec4" />

```bash
binwalk /home/kali/Downloads/wallpaper.jpg
```


## RESULT:
Metadata was successfully extracted, timeline analysis was completed, and hidden data was identified using steganography tools.
