cmake_minimum_required(VERSION 3.29)
project(untitled C)

set(CMAKE_C_STANDARD 11)

add_executable(untitled main.c
)
cmake_minimum_required(VERSION 3.10)
project(untitled C)

# GTK için pkg-config ayarlarını yapın
find_package(PkgConfig REQUIRED)
pkg_check_modules(GTK REQUIRED gtk+-3.0)

# GTK'nin gerekli dosyalarını projeye dahil edin
include_directories(${GTK_INCLUDE_DIRS})
link_directories(${GTK_LIBRARY_DIRS})
add_definitions(${GTK_CFLAGS_OTHER})



# GTK kütüphanelerini linkleyin
target_link_libraries(untitled ${GTK_LIBRARIES})
