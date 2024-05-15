# Template: C++17
This is a template project for creating C++17 projects using CMake, Ninja and vcpkg

## Prerequisites
You must have the following installed on your machine:

- A C++ compiler like clang, gcc, g++
- CMake
- Ninja
- vcpkg

## Running
Generate Ninja build files. This should automatically install `vcpkg` dependencies.

```bash
$ cmake -G Ninja
```

Run Ninja to compile the project.

```bash
$ ninja
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

## Adding and Installing Dependencies
You can use `vcpkg add port ...` to add dependencies.

```bash
$ vcpkg add wxwidgets
```

Then, add the `find_package(...)` and `target_link_libraries` directives to your `CMakeLists.txt` file and run Ninja to compile your program. This should install the dependencies automatically and rebuild the project.

```bash
$ ninja
```

## License
MIT
