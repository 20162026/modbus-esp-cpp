cmake_minimum_required(VERSION 3.5)

set(srcs "pl_modbus_base.cpp" "pl_modbus_memory_area.cpp" "pl_modbus_client.cpp" "pl_modbus_server.cpp")
add_prefix(srcs "${CMAKE_CURRENT_LIST_DIR}/" ${srcs})

idf_component_register( SRCS ${srcs} 
                        INCLUDE_DIRS "include" 
                        REQUIRES pl_common pl_uart pl_network)

target_compile_options(${COMPONENT_LIB} PRIVATE -frtti)