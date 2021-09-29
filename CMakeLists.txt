cmake_minimum_required(VERSION 3.12)

file(GLOB Blynk_SRC CONFIGURE_DEPENDS "src/*/*.cpp")

add_library (Blynk ${Blynk_SRC})

# add_compile_definitions(NDEBUG)
add_compile_definitions(ARDUINO_ARDUINO_NANO33BLE)


# include_directories(../libraries/Adafruit_BusIO ../libraries/Arduino_vec)

#set_property(TARGET Blynk PROPERTY CXX_STANDARD 11)

# target_link_arduino_libraries (Blynk PUBLIC BlynkLogging "Arduino_vec" Adafruit_AHRS Arduino_LSM9DS1 Adafruit_Unified_Sensor Adafruit_BusIO SPI ArduinoBLE Blynk)
# target_link_arduino_libraries (Blynk PRIVATE core Wire)
#target_link_arduino_libraries(Blynk PRIVATE core Wire Ultrasonic   \
#                                "UDOO Neo Acc-Mag"                 \
#                                "UDOO Neo Gyroscope" Madgwick      \
#                                "Adafruit Motor Shield V2 Library" \
#                                "Adafruit BusIO" RobDisplay)

# target_link_arduino_libraries (Blynk PUBLIC core Wire
# 	Ultrasonic "UDOO Neo Acc-Mag" "UDOO Neo Gyroscope" Madgwick
# 	"Adafruit Motor Shield V2 Library"
# 	"Adafruit BusIO" "Adafruit AHRS" "Adafruit Sensor Calibration"
# 	"Udoo FXAS21002C" "Udoo FXOS8700"
# 	"PID"
# 	)

target_include_directories (Blynk PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})
#target_link_arduino_libraries(Blynk AUTO_PUBLIC)
