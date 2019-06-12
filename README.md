# mkbooks

A script that turns your [Mkdocs](http://Mkdocs.org) project into a PDF or EPUB!

## Contents

- [Dependencies](#dependencies)
- [Installation](#installation)
- [Usage](#usage)
- [Troubleshooting](#troubleshooting)
- [License](#license)

## Dependencies

The following software dependencies are required for the script to work:

- [mdpdf](https://github.com/BlueHatbRit/mdpdf)
- [pandoc](https://pandoc.org/)

On Ubuntu 17.10+ systems, those can be obtained the following way:
```
$ sudo apt install npm pandoc
$ sudo npm install -g mdpdf --unsafe-perm=true
```

## Installation

Clone the repository:

```bash
$ git clone https://github.com/CTXz/mkbooks.git
```

From here, the script may be executed directly:
```
$ cd mkbooks
$ bash mkbooks.sh -h
```

Additionally, you may install the script to `/usr/local/bin`!

```
# cp mkbooks.sh /usr/local/bin/
# chmod +x /usr/local/bin/mkbooks.sh
```

## Usage:

To run the script:

```
$ bash mkbooks.sh [-h] <cfg> <out> [extra]
```

### Options/Arguments

|Argument|Description                                                                                               |
|--------|----------------------------------------------------------------------------------------------------------|
|-h      |Display this usage                                                                                        |
|cfg     |Path to the Mkdocs yml configuration file                                                                 |
|out     |Name and type of the output file (Example: Docs.pdf or Docs.epub)                                         |
|extra   |Additional arguments that are passed to mdpdf or pandoc (pdf = mdpdf, pandoc = epub). Use quotation marks!|

### Examples

```
$ bash mkbooks.sh ./mkdocs.yml docs.pdf
$ bash mkbooks.sh ./mkdocs.yml docs.epub
$ bash mkbooks.sh ./mkdocs.yml docs.pdf '--style=styles.css'
```

If no error has occurred, a PDF or EPUB will be generated!

## Troubleshooting:

Should mkbooks complain that mdpdf has not been installed:

```
mkbooks: mdpdf has not been installed!
```

despite mdpdf being installed, mdpdf may be improperly executing. Try to run `mdpdf` and see if an error is being thrown.

Should `mdpdf` return the following error:

```
/usr/bin/env: ‘node\r’: No such file or directory
```

Then the newline formatting of the mdpdf script is set to CRLF. To fix this issue, open the mdpdf script in `/usr/local/bin/mdpdf` with a text editor that can convert from CRLF to LF. Alternatively, you can use the [dos2unix](http://manpages.ubuntu.com/manpages/trusty/man1/dos2unix.1.html) tool.

## License
This project is licensed under the MIT License

```
Copyright (c) 2018 Patrick Pedersen <ctx.xda@gmail.com>=

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```
