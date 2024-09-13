cmake_minimum_required(VERSION 3.30)

# Set the project name and specify languages
project(pico-mcp2515 LANGUAGES C CXX)

# Specify the C/C++ standards to be used
set(CMAKE_C_STANDARD 11)
set(CMAKE_CXX_STANDARD 17)

# Create the library from the source files
add_library(pico_mcp2515 STATIC
    src/mcp2515.cpp  
)

# Specify the include directories to expose the headers
target_include_directories(pico_mcp2515 PUBLIC 
    ${CMAKE_CURRENT_LIST_DIR}/include
)

# Link necessary dependencies, such as Pico SDK and SPI hardware
target_link_libraries(pico_mcp2515
    pico_stdlib
    hardware_spi
)
