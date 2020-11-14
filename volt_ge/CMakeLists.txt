cmake_minimum_required(VERSION 3.5)

# Find all source files
file(GLOB_RECURSE VOLT_GE_SRCS
    "src/*.cpp"
    RELATIVE_PATH
)

find_package (Threads)

add_library(volt_ge ${VOLT_GE_SRCS})
target_include_directories(volt_ge PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/include/)
target_link_libraries(volt_ge ${CMAKE_THREAD_LIBS_INIT})
target_link_libraries(volt_ge ${CONAN_LIBS})
set_property(TARGET volt_ge PROPERTY CXX_STANDARD 17)

# endif()
