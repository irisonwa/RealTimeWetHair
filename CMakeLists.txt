cmake_minimum_required(VERSION 3.25.0)
project(My3DTemplate VERSION 0.1.0 LANGUAGES C CXX)
set(CMAKE_CXX_STANDARD 23)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_FLAGS "-O0 -ggdb")
set(CMAKE_CXX_FLAGS_DEBUG "-O0 -ggdb")
set(_SOURCE_DIR ./src)

set(INCLUDE_DIRS C:/msys64/mingw64/include)
set(LIBRARIES -LC:/msys64/mingw64/lib)
include_directories(${INCLUDE_DIRS} ${_SOURCE_DIR})
file(GLOB_RECURSE SOURCE_FILES ${_SOURCE_DIR}/*.cpp)
file(GLOB_RECURSE INCLUDE_FILES ${_SOURCE_DIR}/*.h ${_SOURCE_DIR}/*.hpp)
link_libraries(-lglfw3 -lglew32 -lgdi32 -lassimp -lopengl32 -lwinmm)
add_executable(main ${SOURCE_FILES} ${INCLUDE_FILES})

add_compile_options("-fdiagnostics-color=always" "-fsanitize=null" "-ggdb" "-Wall" "-Wno-unknown-pragmas" "-Wno-sign-compare" "-O0" )

target_link_libraries(main ${LIBRARIES})
