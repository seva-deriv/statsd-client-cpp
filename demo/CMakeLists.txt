function (AddTool TOOL)
    add_executable(${TOOL} ${TOOL}.cpp)
    target_link_libraries(${TOOL} StatsdClient)
endfunction ()

if (NOT WIN32)
    AddTool(test_client)
    AddTool(system_monitor)
endif ()
