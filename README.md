# ESP32_MicroROS_Pio

Test on ESP32, ESP32C3

```config
;ESP32C3
[env:seeed_xiao_esp32c3]
platform = espressif32
board = seeed_xiao_esp32c3
framework = arduino
board_microros_transport = serial
lib_deps = 
	https://github.com/micro-ROS/micro_ros_platformio

;ESP32
[env:esp32dev]
platform = espressif32
board = esp32dev
framework = arduino
board_microros_transport = serial
lib_deps = 
  https://github.com/micro-ROS/micro_ros_platformio

;SAM D21
[env:seeed_xiao]
platform = atmelsam
board = seeed_xiao
framework = arduino
lib_deps = 
	https://github.com/micro-ROS/micro_ros_platformio
```

## Docker run ROS-Agent

- Serial

  seeed_xiao_esp32c3 

  ```bash
  docker run -it --rm -v /dev:/dev -v /dev/shm:/dev/shm --privileged --net=host microros/micro-ros-agent:humble serial --dev /dev/ttyACM0 -v6
  ```

  esp32dev

  ```bash
  docker run -it --rm -v /dev:/dev -v /dev/shm:/dev/shm --privileged --net=host microros/micro-ros-agent:humble serial --dev /dev/ttyUSB0 -v6
  ```

- Wifi
