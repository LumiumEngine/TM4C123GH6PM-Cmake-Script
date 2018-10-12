cmake_minimum_required(VERSION 3.8.2)
project(linux_blinky)

#Toolchain file
include(tm4c123g.cmake)

#Tivaware files
set(TIVAWARE_PATH "C:/ti/TivaWare_C_Series-2.1.4.178")
include_directories(${TIVAWARE_PATH})

#Source files
add_executable(${CMAKE_PROJECT_NAME}.axf "src/startup.c"
"src/blinky.cpp"

)

target_link_libraries(${CMAKE_PROJECT_NAME}.axf 
    ${TIVAWARE_PATH}/usblib/gcc/libusb.a
    ${TIVAWARE_PATH}/driverlib/gcc/libdriver.a
)