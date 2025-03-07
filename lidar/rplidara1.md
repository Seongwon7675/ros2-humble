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

# 실행 파일을 어딘가에 넣어서 실행할 때에는
1. colcon build가 필요
cd (디렉토리) 후에
colcon build --install 이런식으로
2. 빌드 후 ros2 환결설정이 필요
source install/setup.bash
(이 때 매번 source하기 귀찮으면 자동으로 source하게끔 가능, but 정확하지 않음. 찾아보자.)
echo "source ~/디렉토리/install/setup.bash" >> ~/.bashrc
source ~/.bashrc
이후 위처럼 rp lidar a1을 실행하면 자동실행됨.
