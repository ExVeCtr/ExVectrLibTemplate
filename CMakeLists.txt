cmake_minimum_required(VERSION 3.0.0)
project(ExVectr VERSION 0.1.0) #Change ExVectr to the library name. Please use ExVectr[Name here] format.

file(GLOB_RECURSE SRC_FILES src/*.cpp)
add_library(${PROJECT_NAME} ${SRC_FILES})
target_include_directories(${PROJECT_NAME} PUBLIC include/)

function(addExVectrDependency libName)
    target_include_directories(${PROJECT_NAME} PUBLIC ../${libName}/include/)
endfunction()

addExVectrDependency(ExVectrCore) #These are used to add a ExVectr dependency to a exvectr library