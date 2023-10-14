# = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = =

# - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
# PROJECT
# - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -

project("HexagonEX.Core" VERSION ${HEXAGON_EX_VERSION})

# - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
# CONSTANTS
# - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -

set(HEXAGON_EX_CORE_DIR ${CMAKE_CURRENT_SOURCE_DIR})

# - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
# SOURCES
# - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -

set(HEXAGON_EX_CORE_PRIVATE_DIR "${HEXAGON_EX_CORE_DIR}/private/hexagonex/core/")
set(HEXAGON_EX_CORE_SOURCES
  "${HEXAGON_EX_CORE_PRIVATE_DIR}game/HexagonEX.cpp"
)

# - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
# BUILD
# - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -

# Add STATIC Library Object
add_library(hexagonex_core ${HEXAGON_EX_CORE_SOURCES})

# Configure STATIC Library Object
set_target_properties(hexagonex_core PROPERTIES
  ARCHIVE_OUTPUT_DIRECTORY "${HEXAGON_EX_OUTPUT_DIR}"
)

# - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
# LINK
# - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -

# Link with HexagonEX.Core Interface
set(HEXAGON_EX_CORE_PRIVATE_HEADERS_DIR "${HEXAGON_EX_CORE_DIR}/private")
target_include_directories(hexagonex_core PRIVATE ${HEXAGON_EX_CORE_PRIVATE_HEADERS_DIR})

# = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = =
