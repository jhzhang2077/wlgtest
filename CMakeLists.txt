
    cmake_minimum_required(VERSION 3.6)
    
    include_directories(googletest/include)



    project(mygtest)
    add_executable(mygtest sample1_unittest.cc)
    add_library(sample1 sample1.cc)
    target_link_libraries(mygtest sample1 
                                   ../googletest/lib/gtestd
                                   ../googletest/lib/gtest_maind
                                   )
    

    #这个必须放在project的后面
    IF(MSVC)
        message("run here")
        set(CMAKE_CXX_FLAGS_RELEASE "${CMAKE_CXX_FLAGS_RELEASE} /MT")
        set(CMAKE_CXX_FLAGS_DEBUG "${CMAKE_CXX_FLAGS_DEBUG} /MTd")
    endif()
     