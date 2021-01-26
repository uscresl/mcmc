cmake_minimum_required(VERSION 3.16.0)
set(CMAKE_CXX_STANDARD 11)
project(MCMC CXX)

find_package(Armadillo REQUIRED)

add_library(MCMC src/aees.cpp src/de.cpp src/hmc.cpp src/mala.cpp src/rmhmc.cpp src/rwmh.cpp)

target_include_directories(MCMC PUBLIC ${ARMADILLO_INCLUDE_DIRS})
target_include_directories(MCMC PUBLIC (${CMAKE_CURRENT_LIST_DIR}/include) ${ARMADILLO_INCLUDE_DIRS})
target_link_libraries(MCMC PUBLIC ${ARMADILLO_LIBRARIES} openblas)