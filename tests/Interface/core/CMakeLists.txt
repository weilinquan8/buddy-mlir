_add_test_executable(buddy-container-test
  ContainerTest.cpp
)

if(BUDDY_ENABLE_OPENCV)
  find_package(OpenCV REQUIRED CONFIG)
  include_directories(${OpenCV_INCLUDE_DIRS})
endif()

set(DIP_LIBS ${JPEG_LIBRARY} ${PNG_LIBRARY})

_add_test_executable(buddy-image-container-test
  ImageContainerTest.cpp
  LINK_LIBS
    ${OpenCV_LIBS}
    ${DIP_LIBS}
)

_add_test_executable(buddy-audio-container-test
  AudioContainerTest.cpp
)

_add_test_executable(buddy-text-container-test
  TextContainerTest.cpp
)