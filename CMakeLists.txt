cmake_minimum_required(VERSION 2.8.6)

project(rttlua_completion)

find_package(Lua51 REQUIRED)

include_directories(${LUA_INCLUDE_DIR})
message(STATUS "lua dir: ${LUA_INCLUDE_DIR}")
add_library(readline SHARED readline.c)
set_target_properties(readline PROPERTIES PREFIX "")

install(FILES complete.lua DESTINATION share/lua/5.1)
install(TARGETS readline LIBRARY DESTINATION lib/lua/5.1)
