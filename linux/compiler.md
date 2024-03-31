Portable GNU assembler.

- Assemble a file, writing the output to a.out:
> `$ as {{file.s}}`

- Assemble the output to a given file:
> `$ as {{file.s}} -o {{out.o}}`

- Generate output faster by skipping whitespace and comment preprocessing. (Should only be used for trusted compilers):
> `$ as -f {{file.s}}`

- Include a given path to the list of directories to search for files specified in .include directives:
> `$ as -I {{path/to/directory}} {{file.s}}`

---

The Netwide Assembler, a portable 80x86 assembler

- Assemble source.asm into a binary file source, in the (default) raw binary format:
> `$ nasm {{source.asm}}`

- Assemble source.asm into a binary file output_file, in the specified format:
> `$ nasm -f {{format}} {{source.asm}} -o {{output_file}}`

- List valid output formats (along with basic nasm help):
> `$ nasm -hf`

- Assemble and generate an assembly listing file:
> `$ nasm -l {{list_file}} {{source.asm}}`

- Add a directory (must be written with trailing slash) to the include file search path before assembling:
> `$ nasm -i {{path/to/include_dir/}} {{source.asm}}`

---

GNU Debugger

- Debug an executable:
> `$ gdb {{executable}}`

- Attach a process to gdb:
> `$ gdb -p {{procID}}`

- Debug with a core file:
> `$ gdb -c {{core}} {{executable}}`

- Execute given GDB commands upon start:
> `$ gdb -ex "{{commands}}" {{executable}}`

- Start gdb and pass arguments to the executable:
> `$ gdb --args {{executable}} {{argument1}} {{argument2}}`


---

GNU C compiler

- Preprocess only; do not compile, assemble or link
> `$ gcc -E {{source.c}}`

- Compile only; do not assemble or link:
> `$ gcc -S {{source.c}}`

- Compile and assemble, but do not link:
> `$ gcc -c {{source.c}}`

- Compile a file using the GNU compiler (default executable output is a.out):
> `$ gcc {{source.c}}`

- compile source code into an outfile file main.o
> `$ gcc {{source.c}} -o main.o`

- Compile multiple source files into executable:
> `$ gcc {{source1.c}} {{source2.c}} --output {{executable}}`

- Create a shared library
> `$ gcc -shared {{source.c}}`

- compile source code and enable all warnings
> `$ gcc -Wall {{source.c}}`

- Allow warnings, debug symbols in output:
> `$ gcc {{source.c}} -Wall -Og --output {{executable}}`

- Include libraries from a different path:
> `$ gcc {{source.c}} --output {{executable}} -I{{header_path}} -L{{library_path}} -l{{library_name}}`

---

Utility for directing compilation

- Call the first target specified in the Makefile (usually named "all"):
> `$ make`

- Call a specific target:
> `$ make {{target}}`

- Call a specific target, executing 4 jobs at a time in parallel:
> `$ make -j{{4}} {{target}}`

- Use a specific Makefile:
> `$ make --file {{file}}`

- Execute make from another directory:
> `$ make --directory {{directory}}`

- Force making of a target, even if source files are unchanged:
> `$ make --always-make {{target}}`

- Override variables defined in the Makefile by the environment:
> `$ make --environment-overrides {{target}}`

---

Manage compile and link flags for libraries

- Get the list of libraries and their dependencies:
> `$ pkg-config --libs {{library1 library2 ...}}`

- Get the list of libraries, their dependencies, and proper cflags for gcc:
> `$ pkg-config --cflags --libs {{library1 library2 ...}}`

- Compile your code with libgtk-3, libwebkit2gtk-4.0 and all their dependencies:
> `$ c++ example.cpp $(pkg-config --cflags --libs gtk+-3.0 webkit2gtk-4.0) -o example`

---

GNU stream editor for filtering/transforming text

- Replace the first occurrence of a regular expression in each line of a file, and print the result:
> `$ sed 's/{{regular_expression}}/{{replace}}/' {{filename}}`

- Replace all occurrences of an extended regular expression in a file, and print the result:
> `$ sed -r 's/{{regular_expression}}/{{replace}}/g' {{filename}}`

- Replace all occurrences of a string in a file, overwriting the file (i.e. in-place):
> `$ sed -i 's/{{find}}/{{replace}}/g' {{filename}}`

- Replace only on lines matching the line pattern:
> `$ sed '/{{line_pattern}}/s/{{find}}/{{replace}}/' {{filename}}`

- Delete lines matching the line pattern:
> `$ sed '/{{line_pattern}}/d' {{filename}}`

- Print the first 11 lines of a file:
> `$ sed 11q {{filename}}`

- Apply multiple find-replace expressions to a file:
> `$ sed -e 's/{{find}}/{{replace}}/' -e 's/{{find}}/{{replace}}/' {{filename}}`

- Replace separator / by any other character not used in the find or replace patterns, e.g. #:
> `$ sed 's#{{find}}#{{replace}}#' {{filename}}`

---

Compiles C++ source files

- Compile a source code file into an executable binary:
> `$ g++ {{source.cpp}} -o {{output_executable}}`

- Display (almost) all errors and warnings:
> `$ g++ {{source.cpp}} -Wall -o {{output_executable}}`

- Choose a language standard to compile for(C++98/C++11/C++14/C++17):
> `$ g++ {{source.cpp}} -std={{language_standard}} -o {{output_executable}}`

- Include libraries located at a different path than the source file:
> `$ g++ {{source.cpp}} -o {{output_executable}} -I{{header_path}} -L{{library_path}} -l{{library_name}}`

---

Compiler for C, C++, and Objective-C source files.

- Compile a source code file into an executable binary:
> `$ clang {{input_source.c}} -o {{output_executable}}`

- Activate output of all errors and warnings:
> `$ clang {{input_source.c}} -Wall -o {{output_executable}}`

- Include libraries located at a different path than the source file:
> `$ clang {{input_source.c}} -o {{output_executable}} -I{{header_path}} -L{{library_path}} -l{{library_name}}`

- Compile source code into LLVM Intermediate Representation (IR):
> `$ clang -S -emit-llvm {{file.c}} -o {{file.ll}}`

-Compile source code without linking:
> `$ clang -c {{input_source.c}}`

---

Compiles C++ source files

- Compile a source code file into an executable binary:
> `$ clang++ {{path/to/source.cpp}} -o {{path/to/output_executable}}`

- Display (almost) all errors and warnings:
> `$ clang++ {{path/to/source.cpp}} -Wall -o {{path/to/output_executable}}`

- Choose a language standard to compile with:
> `$ clang++ {{path/to/source.cpp}} -std={{c++20}} -o {{path/to/output_executable}}`

- Include libraries located at a different path than the source file:
> `$ clang++ {{path/to/source.cpp}} -o {{path/to/output_executable}} -I{{path/to/header_path}} -L{{path/to/library_path}} -l{{path/to/library_name}}`

- Compile source code into LLVM Intermediate Representation (IR):
> `$ clang++ -S -emit-llvm {{path/to/source.cpp}} -o {{path/to/output.ll}}`

---

View information about object files

- Display the file header information:
> `$ objdump -f {{binary}}`

- Display the dis-assembled output of executable sections:
> `$ objdump -d {{binary}}`

- Display a complete binary hex dump of all sections:
> `$ objdump -s {{binary}}`

---

Displays information about ELF

- Display all information about the ELF file:
> `$ readelf -all {{path/to/binary}}`

- Display all the headers present in the ELF file:
> `$ readelf --headers {{path/to/binary}}`

- Display the entries in symbol table section of the ELF file, if it has one:
> `$ readelf --symbols {{path/to/binary}}`

- Display the information contained in the ELF header at the start of the file:
> `$ readelf --file-header {{path/to/binary}}`

---

Display dynamic library calls of a process

- Print (trace) library calls of a program binary:
> `$ ltrace ./{{program}}`

- Count library calls. Print a handy summary at the bottom:
> `$ ltrace -c {{path/to/program}}`

- Trace calls to malloc and free, omit those done by libc:
> `$ ltrace -e malloc+free-@libc.so* {{path/to/program}}`

- Write to file instead of terminal:
> `$ ltrace -o {{file}} {{path/to/program}}`

---

Troubleshooting tool for tracing system calls

- Start tracing a specific process by its PID:
> `$ strace -p {{pid}}`

- Trace a process and filter output by system call:
> `$ strace -p {{pid}} -e {{system_call_name}}`

- Count time, calls, and errors for each system call and report a summary on program exit:
> `$ strace -p {{pid}} -c`

- Show the time spent in every system call:
> `$ strace -p {{pid}} -T`

- Start tracing a program by executing it:
> `$ strace {{program}}`

- Start tracing file operations of a program:
> `$ strace -e trace=file {{program}}`

---

Display shared library dependencies.

- Display shared library dependencies of a binary:
> `$ ldd {{path/to/binary}}`

- Display unused direct dependencies:
> `$ ldd -u {{path/to/binary}}`

---

GNU parser generator

- Compile a bison definition file:
> `$ bison {{path/to/file.y}}`

- Compile in debug mode, which causes the resulting parser to write additional information to the standard output:
> `$ bison --debug {{path/to/file.y}}`

- Specify the output filename:
> `$ bison --output {{path/to/output.c}} {{path/to/file.y}}`

- Be verbose when compiling:
> `$ bison --verbose`

---

Macro processor

- Process macros in a file:
> `$ m4 {{path/to/file}}`

- Define a macro before processing files:
> `$ m4 -D{{macro_name}}={{macro_value}} {{path/to/file}}`

---

Lexical analyser generator (Based on lex)

- Generate an analyser from a flex file:
> `$ flex {{analyser.l}}`

- Specify the output file:
> `$ flex --outfile {{analyser.c}} {{analyser.l}}`

- Compile a C file generated by flex:
> `$ cc {{path/to/lex.yy.c}} --output {{executable}}`

---

autoconf
: /usr/bin/autoconf

Generate configuration scripts

- Basic Usage
> `$ autoconf`

---

C Preprocessor
: /usr/bin/cpp



---

automake
: /usr/bin/automake

---

.a, .lib : static Libraries
.so, .dll : shared libraries
.s: assembly code
.i, .ii: include header, expand macro
.c: c source code file
.cpp: C++ source code file
.h: header file
.o, .obj: object code file
.exe: executable machine code

---

List symbol names in object files

- List global (extern) functions in a file (prefixed with T):
> `$ nm -g {{path/to/file.o}}`

- List only undefined symbols in a file:
> `$ nm -u {{path/to/file.o}}`

- List all symbols, even debugging symbols:
> `$ nm -a {{path/to/file.o}}`

- Demangle C++ symbols (make them readable):
> `$ nm --demangle {{path/to/file.o}}`

---

Cross-platform build automation system, that generates recipes for native build systems

- Generate a build recipe in the current directory with CMakeLists.txt from a project directory:
> `$ cmake {{path/to/project_directory}}`

- Generate a build recipe, with build type set to Release with CMake variable:
> `$ cmake {{path/to/project_directory}} -D {{CMAKE_BUILD_TYPE=Release}}`

- Use a generated recipe in a given directory to build artifacts:
> `$ cmake --build {{path/to/build_directory}}`

- Install the build artifacts into /usr/local/ and strip debugging symbols:
> `$ cmake --install {{path/to/build_directory}} --strip`

- Install the build artifacts using the custom prefix for paths:
> `$ cmake --install {{path/to/build_directory}} --strip --prefix {{path/to/directory}}`

- Run a custom build target:
> `$ cmake --build {{path/to/build_directory}} --target {{target_name}}`

---
