cmake_minimum_required(VERSION 3.0.0)
project(VectrLibTemplate VERSION 0.1.0) #Change VectrLibTemplate to the library name. Please use Vectr[Name here] format.

file(GLOB_RECURSE SRC_FILES src/*.cpp)
add_library(${PROJECT_NAME} ${SRC_FILES})
target_include_directories(${PROJECT_NAME} PUBLIC include/)

function(addVectrDependency libName)
    target_include_directories(${PROJECT_NAME} PUBLIC ../${libName}/include/)
endfunction()

addVectrDependency(VectrHAL) #These are used to add a Vectr dependency to a vectr library
addVectrDependency(VectrCore)