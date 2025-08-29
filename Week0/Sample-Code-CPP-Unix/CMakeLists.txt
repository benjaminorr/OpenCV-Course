# SPECIFY THE MINIMUM VERSION OF CMAKE REQUIRED
cmake_minimum_required(VERSION 3.10)


# SPECIFY YOUR PROJECT NAME
PROJECT(sampleCode)


# Enable C++11
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED TRUE)


# MAKE SURE OPENCV IS INSTALLED CORRECTLY
find_package( OpenCV REQUIRED )


# INCLUDE OPENCV DIRECTORIES
include_directories( ${OpenCV_INCLUDE_DIRS})


# MACRO TO COMPILE CPP FILES
# Do Not Edit
MACRO(add_example name)
  ADD_EXECUTABLE(${name} ${name}.cpp)
  TARGET_LINK_LIBRARIES(${name} ${OpenCV_LIBS} )
ENDMACRO()

# change output dir to same dir as CMakeLists
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_SOURCE_DIR})

# COMPILE CPP FILES USING THIS LINE
######## EDIT THE FILE NAMES ########
add_example(sampleCode)
#add_example(sampleCode2) and so on