# Skidloader
Tool for importing Collection #1 data breach into MongoDB. 

Given any archive file as input, Skidloader will extract it, recursively search the archive for text file files that have an `email:password` format, and then load them into a single JSON file for easy importing into MongoDB.


## Usage
`$ skidloader <archive_file> <output_file.json>`

Then, you can import them into your MongoDB instance like this:

`$ mongoimport -d <database> -c <collection> --type json <output_file.json>`


## Download
You can download prebuilt binaries for Skidloader [here](https://github.com/petercunha/skidloader/releases).

- Mac: https://github.com/petercunha/skidloader/releases/download/1.0/skidloader-macos
- Windows: https://github.com/petercunha/skidloader/releases/download/1.0/skidloader-win.exe
- Linux: https://github.com/petercunha/skidloader/releases/download/1.0/skidloader-linux


## Building From Source
```bash
git clone https://github.com/petercunha/skidloader.git
cd skidloader
npm i
node skidloader.js <archive_file> <output_file.json>
```
