# cmake_utils
Useful bits for CMake

## FetchContent_MakeAvailable_ExcludeFromAll

The `ExcludeFromAll` option to add_directory is super useful, but `FetchContent` does not support this until 3.28.  This cmake file provides a function based on
> [https://stackoverflow.com/questions/65527126/disable-install-for-fetchcontent](https://stackoverflow.com/questions/65527126/disable-install-for-fetchcontent)

This allows the `FetchContent` to pull in the project without adding all its builds to the `all` target.

```cmake
# Used to provide
#  FetchContent_MakeAvailable_ExcludeFromAll
FetchContent_Declare(
    cmake_utils
    GIT_REPOSITORY https://github.com/mjp41/cmake_utils
    GIT_TAG [[FILL THIS IN]]  
    GIT_SHALLOW FALSE
)

FetchContent_MakeAvailable(cmake_utils)
```

Replace `[[FILL THIS IS]]` with a SHA for the latest commit.  You should review what the CMake does.
