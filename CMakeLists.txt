
cmake_minimum_required(VERSION 3.23)
project(Course_project)

set(CMAKE_CXX_STANDARD 23)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

set(SOURCE_FILES
        src/main.cpp
        src/data_structure/ThreadPool.cpp
        src/data_structure/ThreadPool.h
        src/data_structure/TaskQueue.h
        src/data_structure/TaskQueue.tpp
        src/data_structure/ThreadSafeHashMap.h
        src/data_structure/ThreadSafeHashMap.tpp
        src/data_structure/InvertedIndex.cpp
        src/data_structure/InvertedIndex.h
        src/FileStorageManager.cpp
        src/FileStorageManager.h
        src/utils/Request.h
        src/utils/Response.h
        src/utils/RequestType.h
        src/test/InvertedIndexTest.cpp
        src/test/InvertedIndexTest.h
        src/test/ThreadPoolTest.cpp
        src/test/ThreadPoolTest.h
        src/test/TestSuite.cpp
        src/test/TestSuite.h
        src/test/TaskQueueTest.cpp
        src/test/TaskQueueTest.h
        src/test/ThreadSafeHashMapTest.cpp
        src/test/ThreadSafeHashMapTest.h
        src/Scheduler.cpp
        src/Scheduler.h)
if(WIN32)
    message(STATUS "Win")
    list(APPEND SOURCE_FILES ${CMAKE_SOURCE_DIR}/src/Server_win.h)
    list(APPEND SOURCE_FILES ${CMAKE_SOURCE_DIR}/src/Server_win.cpp)
else()
    message(STATUS "Linux")
    list(APPEND SOURCE_FILES src/Server_linux.h)
    list(APPEND SOURCE_FILES src/Server_linux.cpp)
endif()

add_executable(Course_project ${SOURCE_FILES})

if(WIN32)
    target_link_libraries(Course_project PRIVATE ws2_32 dbghelp)
    target_link_libraries(Course_project PRIVATE stdc++fs)
else()
    target_link_libraries(Course_project PRIVATE stdc++fs)
endif()

