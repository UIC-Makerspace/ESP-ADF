execute_process(COMMAND git describe --always --tags --dirty
                OUTPUT_VARIABLE ADF_VER
                OUTPUT_STRIP_TRAILING_WHITESPACE)
add_definitions(-DADF_VER=\"${ADF_VER}\")

if(!IDF_PATH)
set(ENV{IDF_PATH} "$ENV{ADF_PATH}/esp-idf/")
endif()
set(EXTRA_COMPONENT_DIRS $ENV{ADF_PATH}/components)
