set(CLICKHOUSE_COPIER_SOURCES
        ${CMAKE_CURRENT_SOURCE_DIR}/ClusterCopierApp.cpp
        ${CMAKE_CURRENT_SOURCE_DIR}/ClusterCopier.cpp
        ${CMAKE_CURRENT_SOURCE_DIR}/Internals.cpp)

set(CLICKHOUSE_COPIER_LINK PRIVATE
        clickhouse_common_zookeeper
        clickhouse_parsers
        clickhouse_functions
        clickhouse_table_functions
        clickhouse_aggregate_functions
        clickhouse_dictionaries
        string_utils ${Poco_XML_LIBRARY} PUBLIC daemon)

set(CLICKHOUSE_COPIER_INCLUDE SYSTEM PRIVATE ${PCG_RANDOM_INCLUDE_DIR} ${CMAKE_CURRENT_SOURCE_DIR})

clickhouse_program_add(copier)
