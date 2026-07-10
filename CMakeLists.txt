cmake_minimum_required(VERSION 3.20)

project(lingmo-portals VERSION 1.0.0 DESCRIPTION "Lingmo Portals" LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_AUTOMOC ON)

find_package(Qt6 REQUIRED COMPONENTS Core DBus)

add_library(lingmo-portals SHARED
    src/main.cpp
)

target_link_libraries(lingmo-portals PUBLIC
    Qt6::Core
    Qt6::DBus
)

include(GenerateExportHeader)
generate_export_header(lingmo-portals
    EXPORT_MACRO_NAME LINGMO_LINGMO_PORTALS_EXPORT
    EXPORT_FILE_NAME /export.h
)

install(TARGETS lingmo-portals
    EXPORT lingmo-portalsTargets
    LIBRARY DESTINATION 
    ARCHIVE DESTINATION 
)

install(DIRECTORY include/lingmo-portals
    DESTINATION 
)
