cmake_minimum_required(VERSION 3.5)

# Set some default values
set(INCLUDE_DIR ${CMAKE_CURRENT_SOURCE_DIR}/include/)
set(SOURCE_DIR ${CMAKE_CURRENT_SOURCE_DIR}/src)
set(CMAKE_CXX_STANDARD 17)

# Setup and include libraries
# We use Boost.asio so we can later transition more easily to the C++ Networking TS library.
# find_package(Boost COMPONENTS system filesystem REQUIRED)
# include_directories(${Boost_INCLUDE_DIR})

# Find all source files
file(GLOB_RECURSE SRCS
    "src/*.cpp"
    RELATIVE_PATH
)

find_package (Threads)

add_library(volt_ge ${SRCS})
target_include_directories(volt_ge PUBLIC ${INCLUDE_DIR})
target_link_libraries(volt_ge ${CMAKE_THREAD_LIBS_INIT})
target_link_libraries(volt_ge ${CONAN_LIBS})

# endif()