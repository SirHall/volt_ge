cmake_minimum_required(VERSION 3.7)

include(${CMAKE_CURRENT_SOURCE_DIR}/cmake/volt_hunt.cmake)

# set(CMAKE_INSTALL_PREFIX "${CMAKE_CURRENT_BINARY_DIR}/inst/") # For testing

project(volt_ge VERSION 0.0.1)

### ------ Packages ------ ###

# Boost
hunter_add_package(Boost COMPONENTS system filesystem)
find_package(Boost CONFIG REQUIRED system filesystem)
# volt_event
hunter_add_package(volt_event)
find_package(volt_event CONFIG REQUIRED)
# volt_gfx
hunter_add_package(volt_gfx)
find_package(volt_gfx CONFIG REQUIRED)
# volt_net
hunter_add_package(volt_net)
find_package(volt_net CONFIG REQUIRED)
# glm
hunter_add_package(glm)
find_package(glm CONFIG REQUIRED)
# glew
hunter_add_package(glew)
find_package(glew CONFIG REQUIRED)
# glfw
hunter_add_package(glfw)
find_package(glfw3 CONFIG REQUIRED)
# bullet
hunter_add_package(bullet)
find_package(bullet CONFIG REQUIRED)
# entt
hunter_add_package(volt_entt)
find_package(volt_entt CONFIG REQUIRED)
# stb
hunter_add_package(stb)
find_package(stb CONFIG REQUIRED)
# Lua
hunter_add_package(Lua)
find_package(Lua CONFIG REQUIRED)

set(VOLT_GE_LINK_LIBS
    glm
    Boost::boost
    Boost::system
    Boost::filesystem
    glew::glew
    glfw
    volt_event
    volt_gfx
    volt_net
    bullet::Bullet3Common
    bullet::BulletCollision
    bullet::BulletDynamics
    bullet::BulletInverseDynamics
    bullet::BulletSoftBody
    bullet::LinearMath
    # EnTT::EnTT
    stb::stb
    Lua::lua_lib
)

add_subdirectory(${CMAKE_CURRENT_SOURCE_DIR}/volt_ge)