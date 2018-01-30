cmake_minimum_required(VERSION 2.8)

add_subdirectory(json-jsmn)

add_library(json-parser-object OBJECT mqttc_json.c
                                            $<TARGET_OBJECTS:json-jsmn-object>)

add_library(json-parser-static STATIC mqttc_json.c
                                            $<TARGET_OBJECTS:json-jsmn-object>)

include_directories(${CMAKE_CURRENT_LIST_DIR})
