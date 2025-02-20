본 프로젝트는 기존의 Open manipulator 개조하여 6DOF manipulator인 Sara 로봇을 2개 사용하여 시각장애인의 식사를 보조하는 로봇을 개발하는 것이 목표이다.
해당 github에 올린 내용은 sara 2개를 gazebo Simulator 환경 상에서 moveit을 활용하여 구동할 수 있도록 만든 것이다.
현재 구현한 환경은 Ros Noetic 버전이며, Ubutu 20.04 환경임을 참고 하도록 하자
먼저 워크스페이스를 만들고 open manipulator의 stl 파일을 사용하였으므로 다음 명령어를 통하여 open_manipulator_friends 패키지를 git clone하도록 하자
```
mkdir -p dual_sara src
git clone https://github.com/ROBOTIS-GIT/open_manipulator_friends.git
git clone https://github.com/ROBOTIS-JAPAN-GIT/tb3mm_6DoF.git
git clone https://github.com/m-tartari/realsense_gazebo_description.git
git clone https://github.com/k11k22/d435_independent.git
```
이후에 해당 Repositories git clone 하도록 하자
```
git clone https://github.com/JINANJINO/sara_dual_arms.git
```
추가적으로 해당 launch 파일을 사용하기 위해서는 작성자(JINANJINO)의 moveit config와 관련된 내용을 git clone 하도록 한다.
```

```
