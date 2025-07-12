add_library(logger SHARED logger.c)
target_include_directories(logger PUBLIC
  $<BUILD_INTERFACE:${PROJECT_SOURCE_DIR}/include>
  $<INSTALL_INTERFACE:include>)

target_compile_features(logger INTERFACE c_std_99)

install(TARGETS logger
  RUNTIME DESTINATION bin
  LIBRARY DESTINATION lib
  ARCHIVE DESTINATION lib/c-logger)

install(FILES ${PROJECT_SOURCE_DIR}/include/logger.h
  DESTINATION include)
