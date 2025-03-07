# rp lidar a1 드라이버 설치
sudo apt update
sudo apt install ros-humble-rplidar-ros

# 포트 연결 확인 / 여러 개의 포트가 연결되어 있을 수 있음. USB0 USB1 등등
ls /dev/ttyUSB*

# 포트 권한 설정 / 포트 권한이 없을 수 있음.
sudo chmod 666 /dev/ttyUSB0

# rp lidar a1 실행 -> 자동으로 rviz2까지 실행됨.
ros2 launch rplidar_ros view_rplidar_a1_launch.py

![Screenshot from 2025-03-07 13-46-24](https://github.com/user-attachments/assets/b5a33463-3b86-49c5-a8ae-fee89cde013c)
