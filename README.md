# Starter: C++17
This is a starter project for creating C++17 projects using CMake, Ninja and vcpkg

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
$ ./bin/starter_cpp17
Hello, world!

# On Windows
$ .\bin\starter_cpp17.exe
Hello, world!
```

## License
MIT
