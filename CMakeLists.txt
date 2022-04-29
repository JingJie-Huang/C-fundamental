# 設定cmake版本
cmake_minimum_required( VERSION 3.2 )
# 設定專案名稱
project( Basic )

# 設定支援c++ 11標準
set( CMAKE_CXX_FLAGS "-std=c++11" )

# 添加頭文件 library.h
include_directories( ${PROJECT_SOURCE_DIR} )

# 將library.cpp編譯成庫文件
add_library( Lib STATIC library.cpp )
# 設定basic.cpp編譯成執行檔Basic
add_executable( Basic basic.cpp )
# 設定basic_modified.cpp編譯成執行檔Basic_modified
add_executable( Basic_modified basic_modified.cpp )

# 鏈接庫文件 
target_link_libraries( Basic Lib )
target_link_libraries( Basic_modified Lib )

