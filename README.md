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
<img width="900" height="637" alt="436356184-75dc64ee-7af7-4765-9ecf-0ee8eafec4af" src="https://github.com/user-attachments/assets/657c343b-13f1-44f2-98af-7bf4100fff0a" />

- **Extract metadata from a file:**
```bash
exiftool image.jpg
```

- **Batch process a folder:**
```bash
exiftool -r /path/to/folder
```

- **Useful flags:**
  
- ```-G: Show metadata group```

- ```-time:all: Show only timestamps```

- ```-GPSLatitude -GPSLongitude: Extract GPS data```


### install log2timeline
```
sudo apt install plaso -y
```

```
sudo apt install steghide -y
```
- **Embed data**
```
steghide embed -cf /home/kali/Downloads/wallpaper.jpg -ef /home/kali/Downloads/secret.txt
```
<img width="1422" height="249" alt="491853406-4bed1f96-9f5f-41d5-91f7-2126b0c337af" src="https://github.com/user-attachments/assets/d77a08c6-e62e-4493-856c-e7b0eb5c7e7e" />


- **Extract hidden data:**
```
steghide extract -sf hidden.jpg

```
<img width="1920" height="375" alt="491853575-56aafc98-2e5b-40a5-a066-751e87184223" src="https://github.com/user-attachments/assets/5c82031f-4e2d-4835-9038-8518509cd315" />


### Using binwalk – for file analysis
```bash
sudo apt install binwalk -y
binwalk suspicious.jpg
```
```bash
binwalk /home/kali/Downloads/wallpaper.jpg
```
<img width="1572" height="472" alt="491853802-3d14b0c2-b01e-4241-9159-147d1b892735" src="https://github.com/user-attachments/assets/bd8d1974-b2f0-470c-831c-37845e1dd52d" />


## RESULT:
Metadata was successfully extracted, timeline analysis was completed, and hidden data was identified using steganography tools.
