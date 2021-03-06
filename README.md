# Skidloader ![Build Badge](https://img.shields.io/badge/build-passing-success.svg) ![Dependency Badge](https://img.shields.io/badge/dependencies-up%20to%20date-success.svg)
Tool for importing the Collection #1 data breach into MongoDB. 

Given any archive file as input, Skidloader will extract it, recursively search the archive for `.txt` file files that have an `email:password` format, and then load them into a single JSON file for easy importing into MongoDB. Archive formats such as `.zip, .gz, .bz2, .tar, tar.gz, tar.bz2, .tgz, and .tbz2` are all supported.


## Usage
`$ skidloader <archive_file> <output_file.json>`

Then, you can import them into your MongoDB instance like this:

`$ mongoimport -d <database> -c <collection> --type json <output_file.json>`


## Output Format
Skidloader outputs results in the JSON format of {email, password}. Here is an example of what the output file looks like.
```
{email: "bezos@amazon.com", password: "smallpeen"}
{email: "xqc@schnoze.com", password: "Pepega123"}
{email: "trump@whitehouse.gov", password: "BUILDTHEWALL24"}
...
```


## Download
You can download pre-built binaries for Skidloader [here](https://github.com/petercunha/skidloader/releases)

- Mac: https://github.com/petercunha/skidloader/releases/download/1.0/skidloader-macos
- Windows: https://github.com/petercunha/skidloader/releases/download/1.0/skidloader-win.exe
- Linux: https://github.com/petercunha/skidloader/releases/download/1.0/skidloader-linux


## Running From Source
To run from source code instead of using the pre-built binaries, you can set up the project like this:

```
git clone https://github.com/petercunha/skidloader.git
cd skidloader
npm i
node skidloader.js <archive_file> <output_file.json>
```


## Demo
[![asciicast](https://asciinema.org/a/238918.svg)](https://asciinema.org/a/238918)
