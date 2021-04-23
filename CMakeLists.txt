cmake_minimum_required(VERSION 3.17)
project(godwoken_scripts C)

set(CMAKE_C_STANDARD 11)

add_compile_options(-Wno-incompatible-pointer-types)

include_directories(c)
include_directories(c/deps/ckb-c-stdlib)
#include_directories(c/deps/deps/ckb-c-stdlib/libc)
include_directories(c/deps/molecule)
include_directories(c/build)
include_directories(c/deps/ckb-c-stdlib/)
include_directories(.)

add_executable(sudt-validator sim/sudt_sim.c)
target_compile_definitions(sudt-validator PUBLIC -DGW_VALIDATOR)

add_executable(sudt-generator sim/sudt_sim.c)
target_compile_definitions(sudt-generator PUBLIC -DGW_GENERATOR)

# contracts/meta_contract.c
add_executable(meta-contract-validator sim/meta_contract_sim.c)
target_compile_definitions(meta-contract-validator PUBLIC -DGW_VALIDATOR)

add_executable(meta-contract-generator sim/meta_contract_sim.c)
target_compile_definitions(meta-contract-generator PUBLIC -DGW_GENERATOR)


