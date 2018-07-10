cmake_minimum_required(VERSION 3.7)

project(Shooter)

set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} "${PROJECT_SOURCE_DIR}/cmake")

set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${PROJECT_SOURCE_DIR}/bin)

find_package(SDL2 REQUIRED)
find_package(SDL2_image REQUIRED >=2.0.0)

configure_file(assets/background.bmp bin/assets/background.bmp COPYONLY)
configure_file(assets/bullet.bmp bin/assets/bullet.bmp COPYONLY)
configure_file(assets/player_one.bmp bin/assets/player_one.bmp COPYONLY)
configure_file(assets/running_right.bmp bin/assets/running_right.bmp COPYONLY)

add_executable(
    Shooter
    src/main.cpp
    src/Game.cpp
    src/Character.cpp
    src/Collision.cpp
    src/TextureManager.cpp
    src/GameObject.cpp
    src/Combat.cpp
)

target_link_libraries(Shooter ${SDL2_LIBRARY} ${SDL2_IMAGE_LIBRARY})
