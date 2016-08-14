cmake_minimum_required (VERSION 2.8)

set(CMAKE_MODULE_PATH "${CMAKE_CURRENT_SOURCE_DIR}/cmake-modules")

project (SkeletalAnimationLibrary)
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++14 -Wall -Wextra -Wno-unused-parameter")

if(APPLE)
    link_directories(/usr/local/lib)
endif()

find_package(SFML 2.1 COMPONENTS system window graphics REQUIRED)
include_directories(${SFML_INCLUDE_DIR})

set(ASSIMP_DIR "${CMAKE_CURRENT_SOURCE_DIR}/cmake-modules")
find_package(ASSIMP 3 REQUIRED)
include_directories(${ASSIMP_INCLUDE_DIR})

find_package(OpenGL REQUIRED)
include_directories(${OPENGL_INCLUDE_DIR})

find_package(Threads REQUIRED)

add_executable(sfml_examples sfml_examples.cpp)

if(UNIX)
    find_package(X11 REQUIRED)
    include_directories(${X11_INCLUDE_DIR})
    target_link_libraries(sfml_examples ${X11_LIBRARIES})
endif()

target_link_libraries(sfml_examples ${CMAKE_THREAD_LIBS_INIT})
target_link_libraries(sfml_examples ${SFML_LIBRARIES})
target_link_libraries(sfml_examples ${ASSIMP_LIBRARIES})
target_link_libraries(sfml_examples ${OPENGL_LIBRARIES})
