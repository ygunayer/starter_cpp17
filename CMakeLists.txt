cmake_minimum_required(VERSION 3.16)

set(CMAKE_TOOLCHAIN_FILE "$ENV{VCPKG_ROOT}/scripts/buildsystems/vcpkg.cmake")

project(template_cpp17 LANGUAGES CXX)

set(CXX_STANDARD 17)
set(EXECUTABLE_OUTPUT_PATH ${PROJECT_SOURCE_DIR}/bin)

add_executable(template_cpp17 src/main.cpp)

find_package(fmt CONFIG REQUIRED)
target_link_libraries(template_cpp17 PRIVATE fmt::fmt)
