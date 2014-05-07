cmake_minimum_required(VERSION 2.8)

project(PROJECT)

#Some Paths config
set(PROJECT_SRC ${CMAKE_SOURCE_DIR}/src)

include_directories(${PROJECT_SRC})
# include_directories(${PROJECT_SRC}/lib)
# add_subdirectory(${MODES_SRC}/alglib)
# include_directories(${CMAKE_BINARY_DIR}/config)

set(CMAKE_BUILD_TYPE Release)

# For OpenMP
#find_package(OpenMP REQUIRED)
#if(OPENMP_FOUND)
	#set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} ${OpenMP_C_FLAGS}")
	#set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} ${OpenMP_CXX_FLAGS}")
#endif()

# set additional libraries and linker flags
set(LIBS ${LIBS} mylib -Wl,-O1,--sort-common,--as-needed,-z,relro)

# set compile flags for c++11 and security
add_definitions(-std=c++11 -fstack-protector --param=ssp-buffer-size=4 -D_FORTIFY_SOURCE=2)

# Copy addtional files,examples, etc. and build local includes
#file(COPY examples DESTINATION .)
#configure_file( ${PROJECT_SRC}/sys_config.h.in ${CMAKE_BINARY_DIR}/config/sys_config.h )

#Build program
add_executable(program src/*.cxx)
target_link_libraries(program ${LIBS})
