# use: ./build/cmake .. -A x64
# Download from: https://www.autodesk.com/content/dam/autodesk/www/adn/fbx/2020-0-1/fbx202001_fbxsdk_linux.tar.gz
# Dependencies:
#	sudo apt-get install libxml2-dev

cmake_minimum_required(VERSION 2.8.9)
project(FBX2OBJ)

set(CMAKE_GENERATOR_PLATFORM x64)

#find_package(LibXml2 REQUIRED)

# include folders
include_directories(src)
include_directories(include)

# library folders
link_directories(lib/gcc/x64/release)

# sources
file(GLOB SOURCES "src/*.cpp")
add_executable(FBX2OBJ ${SOURCES})

# libraries to link
target_link_libraries(FBX2OBJ libfbxsdk.so)
target_link_libraries(FBX2OBJ dl)
target_link_libraries(FBX2OBJ z)
target_link_libraries(FBX2OBJ xml2)
