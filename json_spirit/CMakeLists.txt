set(JSON_SPIRIT_SRCS
json_spirit_reader.cpp json_spirit_reader.h
json_spirit_value.cpp json_spirit_value.h
json_spirit_writer.cpp json_spirit_writer.h
json_spirit.h
json_spirit_error_position.h
json_spirit_reader_template.h
json_spirit_stream_reader.h
json_spirit_utils.h
json_spirit_writer_options.h
json_spirit_writer_template.h )
 
find_package(Boost 1.34 REQUIRED)
include_directories(${Boost_INCLUDE_DIR})

if(MSVC)
    set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} /bigobj")
endif()
add_library(json_spirit STATIC ${JSON_SPIRIT_SRCS})

install(
  FILES
  ${CMAKE_BINARY_DIR}/json_spirit/libjson_spirit.a
  DESTINATION lib)