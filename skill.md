# File Organizer Skill

## Overview
Help users organize and categorize files, create structured folders, and rename files while preserving original files.

## Trigger Conditions
When the user needs to:
- Organize messy file directories
- Categorize files by type, date, or size
- Rename files with timestamps or numbers
- Create file backups with organization

## Input Parameters

### Required Parameters
- **Source Directory**: Folder to organize (from user input or current directory)
- **Target Directory**: Output folder for organized files (default: "organized_files")

### Optional Parameters
- **Sort Method**:
  - By extension (default)
  - By file size (tiny/small/medium/large/huge)
  - By modification date (monthly or yearly)
  - By custom prefix
  
- **Rename Method**:
  - Add timestamp: `filename_YYYYMMDD_HHMMSS.ext`
  - Add sequence number: `filename_001.ext`
  - Keep original name
  
- **Action**: copy (default) or move
  
- **Conflict Resolution**:
  - skip (default)
  - overwrite
  - auto-rename
  - ask user

## Execution Steps

### 1. Validate Parameters
```
Input parameters:
- Source directory: [from user or current directory]
- Target directory: [from user or default "organized_files"]
- Sort method: [from user or default "by extension"]
- Rename method: [from user or default "keep original"]
- Action: [from user or default "copy"]
- Conflict handling: [from user or default "skip"]
```

### 2. Validate Source Directory
Use `ls` command to verify source directory exists:
```bash
ls -la [source directory]
```

### 3. Create Target Structure
Create subdirectories based on chosen sort method:
```bash
mkdir -p [target]/[category1]
mkdir -p [target]/[category2]
...
```

### 4. Process and Organize Files
Scan files and organize based on rules:

**By Extension:**
- Images: `images/` - jpg, jpeg, png, gif, bmp, svg, webp, ico, tiff
- Documents: `documents/` - pdf, doc, docx, txt, rtf, odt, xls, xlsx, ppt, pptx, csv
- Videos: `videos/` - mp4, avi, mkv, mov, wmv, flv, webm, m4v
- Audio: `audio/` - mp3, wav, flac, aac, ogg, m4a, wma
- Archives: `archives/` - zip, rar, 7z, tar, gz, bz2
- Code: `code/` - py, js, ts, html, css, java, cpp, c, h, php, rb, go, rs, json, xml, yaml, sql
- Others: `others/` - files not in above categories

**By Size:**
- Tiny (<100KB): `tiny/`
- Small (100KB-1MB): `small/`
- Medium (1MB-10MB): `medium/`
- Large (10MB-100MB): `large/`
- Huge (>100MB): `huge/`

**By Date:**
- Monthly: `YYYY/MM/` format
- Yearly: `YYYY/` format
- Quarterly: `YYYY/Q1`, `YYYY/Q2`, etc.

### 5. Handle File Conflicts
When target file exists:

**Option 1: Skip (default)**
```
Skip "images/photo_001.jpg" - file already exists
```

**Option 2: Overwrite**
```
Overwrite "images/photo_001.jpg" - file replaced
```

**Option 3: Auto-rename**
```
Auto-rename "images/photo.jpg" to "images/photo_1.jpg"
Auto-rename "images/photo_1.jpg" to "images/photo_2.jpg"
```

**Option 4: Ask User**
```
File "images/photo.jpg" already exists.
Choose:
1) Skip
2) Overwrite
3) Auto-rename
4) Ask for each
```

### 6. Verify Results
Display summary:
```
File organization complete!

Source: /path/to/source
Target: /path/to/target

Results:
- 15 files organized
- 3 subdirectories created
- Files copied to [target directory]
```

## Error Handling

### Common Issues
1. **Source directory doesn't exist**: Confirm path and re-enter
2. **Target directory already exists**: Ask user whether to overwrite or use new name
3. **Filename conflicts**: Use selected conflict resolution method
4. **Permission issues**: Inform user of permission problems

### Filename Conflict Resolution Logic
```python
def handle_conflict(target_path, method):
    if method == "skip":
        return None  # Skip this file
    elif method == "overwrite":
        return target_path  # Replace existing file
    elif method == "auto_rename":
        counter = 1
        base = get_base_name(target_path)
        ext = get_extension(target_path)
        while os.path.exists(target_path):
            target_path = f"{base}_{counter}{ext}"
            counter += 1
            if counter > 1000:
                raise Error("Cannot generate unique filename after 1000 attempts")
        return target_path
    elif method == "ask":
        return ask_user(target_path)  # Prompt user for action
```

## Output Results

### Success
- Display organized directory structure
- List all created subdirectories and file counts
- Provide operation summary

### Example Output
```
File organization complete!

Source: /path/to/source
Target: organized_files

Results:
- 15 files organized
- 3 subdirectories created
- Files copied to organized_files

Breakdown:
- 5 files -> images/
- 8 files -> documents/
- 2 files -> others/
```

## Usage Examples

### Example 1: Organize by Extension (Keep Original Names)
```
User: Organize files in this folder by extension
Execution:
1. Create images/, documents/, videos/, audio/, archives/, code/, others/
2. Copy .jpg/.png/.gif -> images/
3. Copy .pdf/.docx/.txt -> documents/
4. Copy .mp4/.avi -> videos/
5. Copy .mp3/.wav -> audio/
6. Copy .zip/.rar -> archives/
7. Copy .py/.js/.html -> code/
8. Copy remaining -> others/
```

### Example 2: Organize by Date (Monthly)
```
User: Organize files by modification date, grouped by month
Execution:
1. Check file modification dates
2. Create 2024/01/, 2024/02/, etc.
3. Copy files:
   - report.pdf (modified 2024-01-15) -> 2024/01/
   - photo.jpg (modified 2023-12-20) -> 2023/12/
```

### Example 3: Rename with Timestamps
```
User: Organize files and add modification timestamps
Execution:
1. Get file modification time: report.pdf (2024-01-15 14:30:22)
2. Create organized_files directory
3. Rename to: report_20240115_143022.pdf
```
