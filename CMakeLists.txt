cmake_minimum_required(VERSION 2.6.4)
project(CFS_TO_LAB C)

include_directories(fsw/mission_inc)
include_directories(fsw/platform_inc)
include_directories(${ci_lab_MISSION_DIR}/fsw/platform_inc)
include_directories(${sample_app_MISSION_DIR}/fsw/platform_inc)

include_directories(${MISSION_SOURCE_DIR}/apps/inc)
include_directories(${MISSION_SOURCE_DIR}/apps/cf/fsw/platform_inc)
include_directories(${MISSION_SOURCE_DIR}/apps/sch/fsw/platform_inc)
include_directories(${MISSION_SOURCE_DIR}/apps/hs/fsw/platform_inc)
include_directories(${MISSION_SOURCE_DIR}/apps/hk/fsw/platform_inc)
include_directories(${APPLICATION_PLATFORM_INC_LIST})

include_directories(${MISSION_SOURCE_DIR}/components/hwlib/fsw/public_inc)

aux_source_directory(fsw/src APP_SRC_FILES)

# Create the app module
add_cfe_app(to_lab ${APP_SRC_FILES})

add_cfe_tables(TO_LAB_Subs fsw/tables/to_lab_sub.c)

