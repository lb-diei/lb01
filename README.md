# Smart File Organizer

License: MIT License - Free to use and modify

Automatically organize your messy folders! Sort files by type, date, or size with automatic renaming support.


## One-Click Organization

Before vs After:

`
Downloads/              organized_files/
photo.jpg            images/
report.pdf           photo1.jpg
video.mp4            screenshot.gif
old_doc.docx         documents/
backup.zip           report.pdf
                      report_20260210.pdf
                      videos/
                      video.mp4
                      archives/
                          backup.zip
`


## Quick Start

`
# Organize by type (recommended)
Organize this folder, sort by file type

# Organize by date
Organize files by modification date, grouped by month

# Sort by size with numbering
Separate large and small files with numbers
`


## Key Features

| Feature       | Description                       | Use Case          |
|---------------|-----------------------------------|-------------------|
| Smart Sorting | By type/date/size/prefix          | Clean up Downloads|
| Auto Rename   | Timestamps, numbers, keep original| Too many files?  |
| Safe Mode     | Copy by default, conflict handling | Protect your files|


## Supported Formats

| Type       | Formats                                              |
|------------|------------------------------------------------------|
| Images     | jpg, png, gif, bmp, svg, webp, ico, tiff            |
| Documents  | pdf, doc, docx, txt, xlsx, csv, rtf, odt            |
| Videos     | mp4, avi, mkv, mov, webm, wmv, flv                  |
| Audio      | mp3, wav, flac, aac, ogg, m4a, wma                  |
| Archives   | zip, rar, 7z, tar, gz, bz2                          |
| Code       | py, js, ts, html, java, cpp, go, rs                 |


## Advanced Usage

Specify custom rules:

`
Organize files:
- Sort by: file extension
- Rename: add timestamp
- Action: copy
- Conflict: auto-rename
`


## File Size Categories

| Category | Size Range   |
|----------|--------------|
| Tiny     | < 100KB      |
| Small    | 100KB - 1MB  |
| Medium   | 1MB - 10MB   |
| Large    | 10MB - 100MB |
| Huge     | > 100MB      |


## Safety Features

- Copy mode by default (original files preserved)
- Confirmation before moving
- Multiple conflict strategies (skip/overwrite/rename/ask)


## Examples

### Example 1: Sort by Type

`
images/
  photo1.jpg
  screenshot.gif

documents/
  report.pdf
  notes.txt

videos/
  video.mp4
`


### Example 2: Sort by Date

`
2026/
  01/
    report.pdf
    notes.txt

  02/
    data.xlsx
`


### Example 3: Rename with Timestamps

`
report_20260210_143022.pdf
photo_20260210_143023.jpg
data_20260210_143024.xlsx
`


## Conflict Resolution

When target file exists:

- Skip (default) - Keep existing file
- Overwrite - Replace with source file
- Auto-rename - Add suffix _1, _2, _3...
- Ask user - Prompt for each conflict


## Technical Details

- Windows, Linux, macOS support
- Bash-based file operations
- Nested directory support
- Max 1000 rename attempts


## Configuration Options

| Parameter     | Description                   | Default         |
|---------------|------------------------------|-----------------|
| Source path   | Directory to organize        | -               |
| Target path   | Output directory             | organized_files |
| Sort method   | extension/size/date/prefix  | extension       |
| Rename method | timestamp/number/keep        | keep original   |
| Action        | copy/move                   | copy            |
| Conflict      | skip/overwrite/rename/ask    | skip            |


## Important Notes

1. Move mode - Deletes original files, use with caution
2. Overwrite mode - Permanently replaces existing files
3. Permissions - Ensure read/write access to directories
4. Special characters - Auto-rename recommended


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
