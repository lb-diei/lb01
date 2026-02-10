# Smart File Organizer (SFO)

License: MIT License - Free to use and modify

Automatically organize your messy folders! Sort files by type, date, or size with automatic renaming support.



## What It Does

| Before (Messy) | After (Organized) |
|----------------|-------------------|
| Downloads/     | organized_files/   |
| photo.jpg      | images/photo.jpg |
| report.pdf     | documents/report.pdf |
| video.mp4      | videos/video.mp4 |
| old_doc.docx   | documents/old_doc.docx |
| backup.zip     | archives/backup.zip |


## Quick Start

`
Organize by type (recommended)
Organize this folder, sort by file type

Organize by date
Organize files by modification date, grouped by month

Sort by size with numbering
Separate large and small files with numbers
`


## Key Features

- Smart Sorting - By type, date, size, or prefix
- Auto Rename - Timestamps, numbers, or keep original
- Safe Mode - Copy by default with conflict handling


## Supported Formats

| Type | Formats |
|------|---------|
| Images | jpg, png, gif, bmp, svg, webp, ico, tiff |
| Documents | pdf, doc, docx, txt, xlsx, csv, rtf, odt |
| Videos | mp4, avi, mkv, mov, webm, wmv, flv |
| Audio | mp3, wav, flac, aac, ogg, m4a, wma |
| Archives | zip, rar, 7z, tar, gz, bz2 |
| Code | py, js, ts, html, java, cpp, go, rs |


## Advanced Usage

| Setting | Options |
|---------|---------|
| Sort by | extension, size, date, prefix |
| Rename | timestamp, number, keep original |
| Action | copy, move |
| Conflict | skip, overwrite, rename, ask |


## File Size Categories

| Category | Size Range |
|----------|-----------|
| Tiny | < 100KB |
| Small | 100KB-1MB |
| Medium | 1MB-10MB |
| Large | 10MB-100MB |
| Huge | > 100MB |


## Safety Features

- Copy mode by default (original files preserved)
- Confirmation before moving
- Multiple conflict handling options


## Examples

Organize by Date:

| Original Path | Organized Path |
|---------------|----------------|
| report.pdf (2026-01) | documents/2026/01/report.pdf |
| notes.txt (2026-01) | documents/2026/01/notes.txt |
| data.xlsx (2026-02) | documents/2026/02/data.xlsx |
| backup.zip (2025-12) | archives/2025/12/backup.zip |


Organize by Size:

| Original Name | Organized Folder | Size |
|--------------|------------------|------|
| icon.png | tiny/ | < 100KB |
| logo.svg | tiny/ | < 100KB |
| photo.jpg | small/ | 100KB-1MB |
| document.pdf | small/ | 100KB-1MB |
| video.mp4 | medium/ | 1MB-10MB |


Rename with Timestamps:

| Original | Renamed To |
|----------|------------|
| report.pdf | report_20260210_143022.pdf |
| photo.jpg | photo_20260210_143023.jpg |
| data.xlsx | data_20260210_143024.xlsx |


## Conflict Resolution

| Action | Result |
|--------|--------|
| Skip | Keep existing file |
| Overwrite | Replace with source |
| Auto-rename | Add _1, _2, _3... |
| Ask | Prompt each time |


## Technical Details

| Feature | Supported |
|---------|----------|
| OS | Windows, Linux, macOS |
| Operations | Bash commands |
| Folders | Nested structures |
| Max Attempts | 1000 renames |


## Configuration

| Option | Description | Default |
|--------|-------------|---------|
| Source | Folder to organize | Current |
| Target | Output folder | organized_files |
| Sort | How to group files | By type |
| Rename | File naming | Keep original |
| Action | Copy or move | Copy |
| Conflict | Handling method | Skip |


## Important Notes

1. Move mode deletes originals - use with caution
2. Overwrite mode permanently replaces files
3. Ensure proper folder permissions
4. Special characters may need auto-rename


## Changelog

### v1.0.1 (2025~2026)
- Initial release
- 4 sorting methods
- 3 rename options
- 4 conflict strategies
- 10 usage examples


## Contributing

Issues and Pull Requests welcome!


## License

MIT License - Free to use and modify


## Author

Created with Claude Code
