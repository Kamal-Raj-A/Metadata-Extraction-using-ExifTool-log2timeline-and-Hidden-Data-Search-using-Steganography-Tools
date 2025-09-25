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
<img width="1024" height="1024" alt="Gemini_Generated_Image_egcy3fegcy3fegcy" src="https://github.com/user-attachments/assets/de788213-88f6-4d5c-9d76-148e46335209" />

- **Extract metadata from a file:**
```bash
exiftool image.jpg
```
<img width="1024" height="1024" alt="Gemini_Generated_Image_e1xgtwe1xgtwe1xg" src="https://github.com/user-attachments/assets/a38da102-a6b9-4963-b4b0-e1846e78d4b0" />

- **Batch process a folder:**
  
```bash
exiftool -r /path/to/folder
```

<img width="1024" height="1024" alt="Gemini_Generated_Image_5nt63r5nt63r5nt6" src="https://github.com/user-attachments/assets/ab07eb64-3179-42e4-832f-64ef0cef12d8" />


- **Useful flags:**
  
- ```-G: Show metadata group```
<img width="1024" height="1024" alt="Gemini_Generated_Image_3dvkon3dvkon3dvk" src="https://github.com/user-attachments/assets/372342a2-4df2-4a81-a15f-843f3b8ed17a" />

- ```-time:all: Show only timestamps```
<img width="1024" height="1024" alt="Gemini_Generated_Image_b2zua0b2zua0b2zu" src="https://github.com/user-attachments/assets/ceaef9f5-fd7c-406e-a3ab-166d701a3e02" />

- ```-GPSLatitude -GPSLongitude: Extract GPS data```
<img width="1024" height="1024" alt="Gemini_Generated_Image_mfn3rumfn3rumfn3" src="https://github.com/user-attachments/assets/8fd246cf-288a-4411-b0b6-439d564325a4" />


### install log2timeline
```
sudo apt install plaso -y
```
<img width="1024" height="1024" alt="Gemini_Generated_Image_i0cqb7i0cqb7i0cq" src="https://github.com/user-attachments/assets/f23f966c-8d3a-4d47-b191-d42e0f6f6488" />

```
sudo apt install steghide -y
```
<img width="1024" height="1024" alt="Gemini_Generated_Image_owet0rowet0rowet" src="https://github.com/user-attachments/assets/6a25cd33-a6e5-4b12-9ebc-87abdf258e92" />

- **Embed data**
```
steghide embed -cf /home/kali/Downloads/wallpaper.jpg -ef /home/kali/Downloads/secret.txt
```
<img width="1024" height="1024" alt="Gemini_Generated_Image_zfas1rzfas1rzfas" src="https://github.com/user-attachments/assets/1d015ff0-c984-4fe3-8b6c-b9c415236a98" />

- **Extract hidden data:**
```
steghide extract -sf hidden.jpg
```
<img width="1024" height="1024" alt="Gemini_Generated_Image_s7pywts7pywts7py" src="https://github.com/user-attachments/assets/6e4f16ef-cd6a-4cdf-b311-a9725d392742" />

### Using binwalk – for file analysis
```bash
sudo apt install binwalk -y
binwalk suspicious.jpg
```
<img width="1024" height="1024" alt="Gemini_Generated_Image_tfjprqtfjprqtfjp" src="https://github.com/user-attachments/assets/43e8453f-930f-4e24-acda-85da6e831d7b" />

```bash
binwalk /home/kali/Downloads/wallpaper.jpg
```
<img width="1024" height="1024" alt="Gemini_Generated_Image_o51szvo51szvo51s" src="https://github.com/user-attachments/assets/33b47c36-ce8f-413e-8b70-fc48da8aa464" />


## RESULT:
Metadata was successfully extracted, timeline analysis was completed, and hidden data was identified using steganography tools.
