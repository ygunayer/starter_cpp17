# Template: C++17
This is a template project for creating C++17 projects using CMake and vcpkg

## Prerequisites
You must have the following installed on your machine:

- A C++ compiler like clang, gcc, g++
- CMake
- vcpkg

## Building
### Generator Setup
To compile the code you must first generate the build files for your favorite build tool using CMake.

You can run the following command to see which build tool options are available.
```bash
$ cmake -G
CMake Error: No generator specified for -G

Generators
* Unix Makefiles               = Generates standard UNIX makefiles.
  Ninja                        = Generates build.ninja files.
  Ninja Multi-Config           = Generates build-<Config>.ninja files.
  Watcom WMake                 = Generates Watcom WMake makefiles.
  Xcode                        = Generate Xcode project files.
  CodeBlocks - Ninja           = Generates CodeBlocks project files
                                 (deprecated).
  CodeBlocks - Unix Makefiles  = Generates CodeBlocks project files
                                 (deprecated).
  CodeLite - Ninja             = Generates CodeLite project files
                                 (deprecated).
  CodeLite - Unix Makefiles    = Generates CodeLite project files
                                 (deprecated).
  Eclipse CDT4 - Ninja         = Generates Eclipse CDT 4.0 project files
                                 (deprecated).
  Eclipse CDT4 - Unix Makefiles= Generates Eclipse CDT 4.0 project files
                                 (deprecated).
  Kate - Ninja                 = Generates Kate project files (deprecated).
  Kate - Ninja Multi-Config    = Generates Kate project files (deprecated).
  Kate - Unix Makefiles        = Generates Kate project files (deprecated).
  Sublime Text 2 - Ninja       = Generates Sublime Text 2 project files
                                 (deprecated).
  Sublime Text 2 - Unix Makefiles
                               = Generates Sublime Text 2 project files
                                 (deprecated).
```

From this list you can choose whichever generator you prefer and run CMake again. In this example I used Ninja
```bash
$ cmake -G Ninja -B build
```

> **Note:** It's a good convention to use `-B build` to specify the folder for build artifacts because it helps keep the project root clean.

> This is additionally useful if you use Microsoft's CMake extension pack with Visual Studio Code because it also uses `build/` as the root folder for build artifacts. This way your CLI commands will not interfere with the CMake extension's behavior or vice-versa.

> Despite this, the `.gitignore` files contain directives to ignore most of these files if placed at the root folder (and of course, the `build/` folder as well).

### Compiling the Code
Once the build files are generated, you can now run CMake again with the `--build` flag so it compiles the code with the generator you've selected.

```bash
$ cmake --build build/
```

You can now run the compiled binary.

```bash
# On UNIX
$ ./bin/template_cpp17
Hello, world!

# On Windows
$ .\bin\template_cpp17.exe
Hello, world!
```

As you make more changes on the code or the CMake configuration you can keep using the `cmake --build build/` command to rebuild your program. This will even install or uninstall the relevant `vcpkg` dependencies automatically if you've added or removed some of them.

## Adding and Installing Dependencies
You can use `vcpkg add port ...` to add dependencies.

```bash
$ vcpkg add wxwidgets
```

Then, add the `find_package(...)` and `target_link_libraries` directives to your `CMakeLists.txt` file and run Ninja to compile your program. This should install the dependencies automatically and rebuild the project.

```bash
$ ninja
```

## Additional Notes
This example uses the `fmt` package as a dependency to demonstrate how dependencies can be added and installed automatically using regular CMake commands. Feel free to remove it and add more depending on your use case.

## License
MIT
