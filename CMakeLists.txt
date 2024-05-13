cmake_minimum_required(VERSION 3.14.0)

include(FetchContent)

function (FetchContent_MakeAvailable_ExcludeFromAll target)
  FetchContent_GetProperties(${target})
  if(NOT ${target}_POPULATED)
    FetchContent_Populate(${target})
    add_subdirectory(${${target}_SOURCE_DIR} ${${target}_BINARY_DIR} EXCLUDE_FROM_ALL)
  endif()
endfunction()
