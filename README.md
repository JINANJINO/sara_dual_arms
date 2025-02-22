본 프로젝트는 기존의 Open manipulator 개조하여 6DOF manipulator인 Sara 로봇을 2개 사용하여 시각장애인의 식사를 보조하는 로봇을 개발하는 것이 목표이다.

해당 github에 올린 내용은 sara 2개를 gazebo Simulator 환경 상에서 moveit을 활용하여 구동할 수 있도록 만든 것이다.
현재 구현한 환경은 ```Ros Noetic``` 버전이며, ```Ubutu 20.04``` 환경임을 참고 하도록 하자

먼저 워크스페이스를 만들고 open manipulator의 stl 파일을 사용하였으므로 다음 명령어를 통하여 open_manipulator_friends 패키지를 git clone하도록 하자
```
mkdir -p dual_sara/src
cd dual_sara/src
git clone https://github.com/ROBOTIS-GIT/open_manipulator_friends.git
git clone https://github.com/ROBOTIS-JAPAN-GIT/tb3mm_6DoF.git
git clone https://github.com/m-tartari/realsense_gazebo_description.git
git clone https://github.com/k11k22/d435_independent.git
```
이후에 관련 Repositorie들을 git clone 하도록 하자
```
git clone https://github.com/JINANJINO/sara_dual_arms.git
```
추가적으로 해당 launch 파일을 사용하기 위해서는 작성자(JINANJINO)의 moveit config와 관련된 내용을 git clone 하도록 한다.

moveit과 관련하여 내용이 궁금한 사람은 (https://github.com/JINANJINO/sara_dual_arms_moveit.git) 참조하도록 하자.

마지막으로 현재 rviz환경, 로봇의 urdf, gazebo를 구동하도록하는 현재 repo에 있는 내용을 git clone을 한다.
```
https://github.com/JINANJINO/sara_dual_arms_moveit.git
```
참고로 해당 내용은 src 파일에서 모두 진행하도록 하자.
이후 해당 환경을 build 시켜야한다. build는 ~/dual_sara에서 시키도록 한다.
```
cd ~/dual_sara
catkin_make
source devel/setup.bash
```
모두 완료되었고 터미널 창 1개에 아래 명령어를 넣도록 한다.
```
roscore
```
```
roslaunch sara_dual_arms bringup_moveit.launch
```
```
roslaunch sara_dual_arms_moveit_config move_group.launch
```
이후 해당 환경을 실행하면 rviz와 gazebo 환경이 포팅될 것이다.
![Screenshot from 2025-02-20 13-54-43](https://github.com/user-attachments/assets/491f8357-4868-4d37-848c-9d947c71b41e)

Figure1은 포팅된 Gazebo 환경의 모습이다.

![Screenshot from 2025-02-20 13-56-14](https://github.com/user-attachments/assets/547c7bc4-49fa-48c0-8b99-9316b8f6b423)

Figure2는 포팅된 rviz의 모습이다.
이제 rviz의 컴포넌트에서 제어하고 싶은 manipulator를 선택하고 joint에서 원하는 각도를 설정한 후 plan 버튼을 누른 후 Execute 버튼을 누르면 아래와 같이 gazebo 환경에서 로봇이 구동되는 모습을 볼 수 있을 것이다.

![Screenshot from 2025-02-20 13-58-38](https://github.com/user-attachments/assets/61f20837-9bc4-4f39-b96b-2053ff8487c9)

