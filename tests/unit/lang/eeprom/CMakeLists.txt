# define the test executable
add_executable(language_eeprom_tests
../../../../src/lang/translator.cpp
../../../../src/common/language_eeprom.cpp
../../test_main.cpp
tests.cpp
)

# define required search paths
target_include_directories(language_eeprom_tests PUBLIC . ${CMAKE_SOURCE_DIR}/src/lang)
target_include_directories(language_eeprom_tests PUBLIC . ${CMAKE_SOURCE_DIR}/src/common)

# define custom macros
target_compile_definitions(language_eeprom_tests PUBLIC LANGEEPROM_UNITTEST)

# tell build system about the test case
add_catch_test(language_eeprom_tests)
