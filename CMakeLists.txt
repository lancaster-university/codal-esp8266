project(codal-esp8266)

include("${CODAL_UTILS_LOCATION}")

# find sources and headers
RECURSIVE_FIND_DIR(INCLUDE_DIRS "${CMAKE_CURRENT_SOURCE_DIR}/inc" "*.h")
RECURSIVE_FIND_FILE(SOURCE_FILES "${CMAKE_CURRENT_SOURCE_DIR}/source" "*.c")

# add them
include_directories(${INCLUDE_DIRS})

# create our target
add_library(codal-esp8266 ${SOURCE_FILES})

# expose it to parent cmake.
target_include_directories(codal-esp8266 PUBLIC ${INCLUDE_DIRS})
