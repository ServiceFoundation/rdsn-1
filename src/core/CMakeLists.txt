add_definitions(-DDSN_IN_CORE)
set(DSN_IN_CORE "TRUE")
add_subdirectory(core)
add_subdirectory(perf_counter)
add_subdirectory(tools)
add_subdirectory(tests)

add_library(dsn_runtime STATIC
        $<TARGET_OBJECTS:dsn.core>
        $<TARGET_OBJECTS:dsn.perf_counter>
        $<TARGET_OBJECTS:dsn.tools.common>
        $<TARGET_OBJECTS:dsn.tools.hpc>
        $<TARGET_OBJECTS:dsn.tools.simulator>
        $<TARGET_OBJECTS:dsn.tools.http>
        )
install(TARGETS dsn_runtime DESTINATION "lib")
