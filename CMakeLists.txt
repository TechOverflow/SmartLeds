cmake_minimum_required(VERSION 3.10)

set(SRCS
    "src/Color.cpp"
    "src/RmtDriver4.cpp"
    "src/RmtDriver5.cpp"
    "src/SmartLeds.cpp"
)

# IDF >= 5.3 split the drivers into esp_driver_* components; IDF 6 no longer
# re-exports them through `driver`, so depend on them directly.
set(REQS driver)
if(IDF_VERSION_MAJOR GREATER 5 OR (IDF_VERSION_MAJOR EQUAL 5 AND IDF_VERSION_MINOR GREATER_EQUAL 3))
    list(APPEND REQS esp_driver_rmt esp_driver_spi esp_driver_gpio)
endif()

idf_component_register(
    SRCS ${SRCS}
    INCLUDE_DIRS "./src"
    REQUIRES ${REQS}
)
