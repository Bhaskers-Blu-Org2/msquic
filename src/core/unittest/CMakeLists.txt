# Copyright (c) Microsoft Corporation.
# Licensed under the MIT License.

include_directories(${PROJECT_SOURCE_DIR}/src/core)
include_directories(${PROJECT_SOURCE_DIR}/submodules/googletest/googletest/include)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} ${QUIC_CXX_FLAGS}")

set(SOURCES
    main.cpp
    FrameTest.cpp
    PacketNumberTest.cpp
    RangeTest.cpp
    SpinFrame.cpp
    TransportParamTest.cpp
    VarIntTest.cpp
)

add_executable(msquiccoretest ${SOURCES})

set_property(TARGET msquiccoretest PROPERTY FOLDER "tests")

target_link_libraries(msquiccoretest msquic core platform gtest)

add_test(msquiccoretest msquiccoretest)
