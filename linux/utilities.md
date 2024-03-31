##### Create Windows 10 Bootable USB Disk In Ubuntu:
> `$ sudo snap find woeusb`

> `$ sudo snap install --edge woe-usb`

> `$ sudo woe-usb.woeusb --target-filesystem {{filesystem_name}} --device {{source_media_path}} {{device}}`

---

- Check whether the adb server process is running and start it:
> `$ adb start-server`

- Terminate the adb server process:
> `$ adb kill-server`

- Start a remote shell in the target emulator/device instance:
> `$ adb shell`

- Push an Android application to an emulator/device:
> `$ adb install -r {{path/to/file.apk}}`

- Copy a file/directory from the target device:
> `$ adb pull {{path/to/device_file_or_directory}} {{path/to/local_destination_directory}}`

- Copy a file/directory to the target device:
> `$ adb push {{path/to/local_file_or_directory}} {{path/to/device_destination_directory}}`

- Get a list of connected devices:
> `$ adb devices`

---

- Take Snapshot After 5s:
> `$ flameshot gui -d {{nb_seconds}}`

---

- Resizing Image Using ImageMagick:
> `$ convert {{image_filename.ext}} -resize {{resolution}} {{output_filename.ext}}`

- Compress Image Using ImageMagick:
> `$ convert {{image_filename.ext}} -strip -interlace Plane -gaussian-blur 0.05 -quality {{quality}} {{output_filename.ext}}`

- Convert From PNG To JPG Using ImageMagick:
> `$ convert {{input_image_filename.png}} -quality {{quality}} {{output_image_filename.jpg}}`

---

- Convert To Webp Extension:
> `$ wget https://storage.googleapis.com/downloads.webmproject.org/releases/webp/libwebp-1.2.1-linux-x86-64.tar.gz`

> `$ ./cwebp -q {{compression_factor}} {{image_filename.ext}} -o {{output_filename.webp}}`

---

##### Make Backup Of Any Image:
> `$ cp {{filename}}.{{{ext},{{bak}}`

---

##### Use ls command to see file size:
> `$ ls -lh {filename}.ext`

---

##### Using optipng To Compress PNG:
> `$ sudo apt install optipng`

> `$ optipng {{image_filename.png}}`

---

##### To display png image size, type, and compression info, enter:
> `$ sudo apt install pngtools`

> `$ pnginfo -t {{image_filename.png}}`

---

- Download the contents of a URL to a file:
> `$ curl {{http://example.com}} --output {{filename}}`

- Download a file, saving the output under the filename indicated by the URL:
> `$ curl --remote-name {{http://example.com/filename}}`

- Download a file, following location redirects, and automatically continuing (resuming) a previous file transfer and return an error on server error:
> `$ curl --fail --remote-name --location --continue-at - {{http://example.com/filename}}`

- Send form-encoded data (POST request of type application/x-www-form-urlencoded). Use --data @file_name or --data @'-' to read from STDIN:
> `$ curl --data {{'name=bob'}} {{http://example.com/form}}`

- Send a request with an extra header, using a custom HTTP method:
> `$ curl --header {{'X-My-Header: 123'}} --request {{PUT}} {{http://example.com}}`

- Send data in JSON format, specifying the appropriate content-type header:
> `$ curl --data {{'{"name":"bob"}'}} --header {{'Content-Type: application/json'}} {{http://example.com/users/1234}}`

- Pass a username and password for server authentication:
> `$ curl --user myusername:mypassword {{http://example.com}}`

- Pass client certificate and key for a resource, skipping certificate validation:
> `$ curl --cert {{client.pem}} --key {{key.pem}} --insecure {{https://example.com}}`

---

 - Download the contents of a URL to a file (named "foo" in this case):
> `$ wget {{https://example.com/foo}}`

 - Download the contents of a URL to a file (named "bar" in this case):
> `$ wget --output-document {{bar}} {{https://example.com/foo}}`

 - Download a single web page and all its resources with 3-second intervals between requests (scripts, stylesheets, images, etc.):
> `$ wget --page-requisites --convert-links --wait=3 {{https://example.com/somepage.html}}`

 - Download all listed files within a directory and its sub-directories (does not download embedded page elements):
> `$ wget --mirror --no-parent {{https://example.com/somepath/}}`

 - Limit the download speed and the number of connection retries:
> `$ wget --limit-rate={{300k}} --tries={{100}} {{https://example.com/somepath/}}`

 - Download a file from an HTTP server using Basic Auth (also works for FTP):
> `$ wget --user={{username}} --password={{password}} {{https://example.com}}`

 - Continue an incomplete download:
> `$ wget --continue {{https://example.com}}`

 - Download all URLs stored in a text file to a specific directory:
> `$ wget --directory-prefix {{path/to/directory}} --input-file {{URLs.txt}}`

---

- Check out a working copy from a repository:
> `$ svn co {{url/to/repository}}`

- Bring changes from the repository into the working copy:
> `$ svn up`

- Put files and directories under version control, scheduling them for addition to repository. They will be added in next commit:
> `$ svn add {{PATH}}`

- Send changes from your working copy to the repository:
> `$ svn ci -m {{commit_log_message}} [{{PATH}}]`

- Display changes from the last 10 revisions, showing modified files for each revision:
> `$ svn log -vl {{10}}`

- Show detailed help:
> `$ svn help`

---

Determine file type

- Give a description of the type of the specified file. Works fine for files with no file extension:
> `$ file {{filename}}`

- Look inside a zipped file and determine the file type(s) inside:
> `$ file -z {{foo.zip}}`

- Allow file to work with special or device files:
> `$ file -s {{filename}}`

- Don't stop at first file type match; keep going until the end of the file:
> `$ file -k {{filename}}`

- Determine the mime encoding type of a file:
> `$ file -i {{filename}}`

---

> `$ npm install -g tldr`

> `$ tldr curl`

---

> `$ pip install eg`

> `$ eg curl`

---

> `$ pip install cheat`

> `$ cheat curl`

---

> `$ sudo snap install multipass`

> `$ multipass launch --name ubuntu-saifanov`

> `$ multipass stop ubuntu-saifanov`

> `$ multipass start ubuntu-saifanov`

> `$ multipass exec ubuntu-saifanov -- cat /etc/os-release`

> `$ multipass shell ubuntu-saifanov`

> `$ multipass delete ubuntu-saifanov`

> `$ multipass list`

> `$ multipass purge`

> `$ multipass find`

---

> `$ apt install scrcpy`

> `$ adb -a nodaemon server start`

> `$ adb connect 192.168.1.11:5555`

> `$ scrcpy`

---

> `$ git clone https://github.com/wg/wrk.git`

> `$ sudo make`

> `$ ./wrk -t12 -c400 -d30s https://google.com`

---

> `$ pip install -U kb-manager`

```
$ cat <<EOF > ~/.kb_alias
alias kbl="kb list"
alias kbe="kb edit"
alias kba="kb add"
alias kbv="kb view"
alias kbd="kb delete --id"
alias kbg="kb grep"
alias kbt="kb list --tags"
EOF
```

> `$ echo "source ~/.kb_alias" >> ~/.bashrc`

> `$ source ~/.kb_alias`

---

Opens a file or URL in the user's preferred application

- Open the current directory in the default file explorer:
> `$ xdg-open .`

- Open a URL in the default browser:
> `$ xdg-open {{https://example.com}}`

- Open an image in the default image viewer:
> `$ xdg-open {{path/to/image}}`

- Open a PDF in the default PDF viewer:
> `$ xdg-open {{path/to/pdf}}`

---

Execute a command with piped arguments coming from another command, a file, etc.The input is treated as a single block of text and split into separate pieces on spaces, tabs, newlines and end-of-file.

- Run a command using the input data as arguments:
> `$ {{arguments_source}} | xargs {{command}}`

- Run multiple chained commands on the input data:
> `$ {{arguments_source}} | xargs sh -c "{{command1}} && {{command2}} | {{command3}}"`

- Delete all files with a .backup extension (-print0 uses a null character to split file names, and -0 uses it as delimiter):
> `$ find . -name {{'*.backup'}} -print0 | xargs -0 rm -v`

- Execute the command once for each input line, replacing any occurrences of the placeholder (here marked as _) with the input line:
> `$ {{arguments_source}} | xargs -I _ {{command}} _ {{optional_extra_arguments}}`

- Parallel runs of up to max-procs processes at a time; the default is 1. If max-procs is 0, xargs will run as many processes as possible at a time:
> `$ {{arguments_source}} | xargs -P {{max-procs}} {{command}}`

---

Find files or directories under the given directory tree, recursively

 - Find files by extension:
> `$ find {{root_path}} -name '{{*.ext}}'`

 - Find files matching multiple path/name patterns:
> `$ find {{root_path}} -path '{{**/path/**/*.ext}}' -or -name '{{*pattern*}}'`

 - Find directories matching a given name, in case-insensitive mode:
> `$ find {{root_path}} -type d -iname '{{*lib*}}'`

 - Find files matching a given pattern, excluding specific paths:
> `$ find {{root_path}} -name '{{*.py}}' -not -path '{{*/site-packages/*}}'`

 - Find files matching a given size range:
> `$ find {{root_path}} -size {{+500k}} -size {{-10M}}`

 - Run a command for each file (use {} within the command to access the filename):
> `$ find {{root_path}} -name '{{*.ext}}' -exec {{wc -l {} }}\;`

 - Find files modified in the last 7 days and delete them:
> `$ find {{root_path}} -daystart -mtime -{{7}} -delete`

 - Find empty (0 byte) files and delete them:
> `$ find {{root_path}} -type {{f}} -empty -delete`

---

Read from standard input and write to standard output and files (or commands)

- Copy standard input to each file, and also to standard output:
> `$ echo "example" | tee {{path/to/file}}`

- Append to the given files, do not overwrite:
> `$ echo "example" | tee -a {{path/to/file}}`

- Print standard input to the terminal, and also pipe it into another program for further processing:
> `$ echo "example" | tee {{/dev/tty}} | {{xargs printf "[%s]"}}`

- Create a directory called "example", count the number of characters in "example" and write "example" to the terminal:
> `$ echo "example" | tee >(xargs mkdir) >(wc -c)`

---

Python package manager

- Install a package (see pip install for more install examples):
> `$ pip install {{package_name}}`

- Install a package to the user's directory instead of the system-wide default location:
> `$ pip install --user {{package}}`

- Upgrade a package:
> `$ pip install --upgrade {{package_name}}`

- Uninstall a package:
> `$ pip uninstall {{package_name}}`

- Save installed packages to file:
> `$ pip freeze > {{requirements.txt}}`

- Show installed package info:
> `$ pip show {{package_name}}`

----

ompress/uncompress files with gzip compression (LZ77)

- Compress a file, replacing it with a gzipped compressed version:
> `$ gzip {{file.ext}}`

- Decompress a file, replacing it with the original uncompressed version:
> `$ gzip -d {{file.ext}}.gz`

- Compress a file, keeping the original file:
> `$ gzip --keep {{file.ext}}`

- Compress a file specifying the output filename:
> `$ gzip -c {{file.ext}} > {{compressed_file.ext.gz}}`

- Decompress a gzipped file specifying the output filename:
> `$ gzip -c -d {{file.ext}}.gz > {{uncompressed_file.ext}}`

- Specify the compression level. 1=Fastest (Worst), 9=Slowest (Best), Default level is 6:
> `$ gzip -9 -c {{file.ext}} > {{compressed_file.ext.gz}}`

---

Python language interpreter

- Start a REPL (interactive shell):
> `$ python`

- Execute a specific Python file:
> `$ python {{path/to/file.py}}`

- Execute a specific Python file and start a REPL:
> `$ python -i {{path/to/file.py}}`

- Execute a Python expression:
> `$ python -c "{{expression}}"`

- Run the script of the specified library module:
> `$ python -m {{module}} {{arguments}}`

- Install a package using pip:
> `$ python -m {{pip}} install {{package_name}}`

- Interactively debug a Python script:
> `$ python -m {{pdb}} {{path/to/file.py}}`

- Start the built-in HTTP server on port 8000 in the current directory:
> `$ python -m {{http.server}}`

---

Display one-line descriptions from manual pages.

- Display a description from a man page:
> `$ whatis {{command}}`

- Don't cut the description off at the end of the line:
> `$ whatis --long {{command}}`

- Display descriptions for all commands matching a glob:
> `$ whatis --wildcard {{net*}}`

- Search man page descriptions with a regular expression:
> `$ whatis --regex '{{wish[0-9]\.[0-9]}}'`

---
