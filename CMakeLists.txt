cmake_minimum_required(VERSION 3.26)
project(LoadandDisplayBVH)

set(CMAKE_CXX_STANDARD 14)

include_directories(src)
include_directories(third)
include_directories(third/freeglut)
include_directories(third/freeglut/include)
include_directories(third/freeglut/include/GL)
include_directories(/usr/include)

find_library(GLUT_LIB glut)
find_library(GL_LIB GL)
find_library(GLU_LIB GLU)

add_executable(LoadandDisplayBVH
        src/BVH.cpp
        src/BVH.h
        src/BVHPlayer.cpp
        third/freeglut/include/GL/freeglut.h
        third/freeglut/include/GL/freeglut_ext.h
        third/freeglut/include/GL/freeglut_std.h
        third/freeglut/include/GL/freeglut_ucall.h
        third/freeglut/include/GL/glut.h
        src/test.cpp)

TARGET_LINK_LIBRARIES(LoadandDisplayBVH ${GLUT_LIB})
TARGET_LINK_LIBRARIES(LoadandDisplayBVH ${GL_LIB})
TARGET_LINK_LIBRARIES(LoadandDisplayBVH ${GLU_LIB})
