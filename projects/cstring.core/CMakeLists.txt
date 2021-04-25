
SET (CORE_SRC_DIR ../../src)

FILE (GLOB CORE_SRCS
    ${CORE_SRC_DIR}/cs*.c
)

add_library(cstring ${CORE_SRCS})

target_compile_options(cstring PRIVATE
    $<$<OR:$<CXX_COMPILER_ID:Clang>,$<CXX_COMPILER_ID:AppleClang>,$<CXX_COMPILER_ID:GNU>>:
		-Werror -Wall -Wextra -pedantic
	>
    $<$<CXX_COMPILER_ID:MSVC>:
		/WX /W4
	>
)

