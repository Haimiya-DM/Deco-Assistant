cmake_minimum_required(VERSION 3.21)

project(AIDecoAssistant VERSION 2.0.0)

find_package(Geode REQUIRED)

add_geode_mod(
    AIDecoAssistant
    VERSION 2.0.0
    SOURCES src/main.cpp
)
