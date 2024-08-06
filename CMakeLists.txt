cmake_minimum_required(VERSION 3.10)

# プロジェクト名とバージョンを設定
project(HelloWorld VERSION 1.0)

# ソースディレクトリを指定
set(SOURCE_DIR "${PROJECT_SOURCE_DIR}/src")

# 実行可能ファイルを指定
add_executable(hello_world ${SOURCE_DIR}/main.cpp)

# Visual Studio用の設定
if(MSVC)
    set_target_properties(hello_world PROPERTIES
        RUNTIME_OUTPUT_DIRECTORY_DEBUG ${PROJECT_SOURCE_DIR}/build/windows
        RUNTIME_OUTPUT_DIRECTORY_RELEASE ${PROJECT_SOURCE_DIR}/build/windows
    )
else()
    set_target_properties(hello_world PROPERTIES
        RUNTIME_OUTPUT_DIRECTORY ${PROJECT_SOURCE_DIR}/build/linux
    )
endif()
