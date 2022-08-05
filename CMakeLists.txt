cmake_minimum_required(VERSION 3.21)
project(TestCGALProject)

set(CMAKE_PREFIX_PATH "/home/linuxbrew/.linuxbrew/Cellar/qt/6.2.2/lib/cmake/")

find_package(Qt6 COMPONENTS Widgets REQUIRED)

include_directories(/usr/local/include/)
include_directories(/home/linuxbrew/.linuxbrew/include/)
include_directories(/home/linuxbrew/.linuxbrew/Cellar/qt/6.2.2/include/)

link_directories(/usr/local/lib/)
link_directories(/home/linuxbrew/.linuxbrew/Cellar/)

set(CMAKE_CXX_FLAGS "-O3 -fopenmp -Wall -Wextra")
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_BUILD_TYPE "Debug")

add_executable(TestCGALProject main.cpp DrawUsingQt.h CGALComponents.h QuadraticTimeClosestPair.h)

target_link_libraries(TestCGALProject Qt6::Core)
target_link_libraries(TestCGALProject Qt6::Widgets)



// Workable CMake

cmake_minimum_required(VERSION 3.21)
project(FastSparseSpanner)

set(CMAKE_PREFIX_PATH "/home/linuxbrew/.linuxbrew/Cellar/qt/6.3.1/lib/cmake/")

find_package(CGAL)
find_package(Qt6Core REQUIRED)
find_package(Qt6Widgets REQUIRED)
find_package(Qt6Quick REQUIRED)


include_directories(/usr/local/include/)
include_directories(/home/linuxbrew/.linuxbrew/include/)
include_directories(/home/linuxbrew/.linuxbrew/Cellar/qt/6.3.1/include/)

link_directories(/usr/local/lib/)
link_directories(/home/linuxbrew/.linuxbrew/Cellar/)


set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_FLAGS "-O3 -fopenmp -fexceptions -frounding-math -Wall -Wextra -Wno-unused")
#set(CMAKE_CXX_FLAGS "-O3 -fopenmp -Wall -Wextra")
set(CMAKE_BUILD_TYPE "Debug")

add_executable(FastSparseSpanner main.cpp
        PointGenerators.h
        DelaunayL2.h
        StretchFactorExact.h
        StretchFactorExperimental.h
        Utilities.h
        GreedySpanners.h
        ShortestPaths.h
        FSS.h
        PointGenOptions.h
        WSPD.h
        WSPD_TSpanner.h
        quadtreeNeighborFinder.h
        Experiment.h LeafLeaderPointCalculation.h
        StretchFactorCalculator.h
        GreedyShortestPath.h)

target_link_libraries(FastSparseSpanner gmp)
target_link_libraries(FastSparseSpanner mpfr)
target_link_libraries(FastSparseSpanner boost_system)
target_link_libraries(FastSparseSpanner boost_thread)
target_link_libraries(FastSparseSpanner -I/usr/local/include/CGAL)
target_link_libraries(FastSparseSpanner Qt6::Core)
target_link_libraries(FastSparseSpanner Qt6::Widgets)
