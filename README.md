# GPS_PathPlanning
---
이 레포지토리는 MORAI simulator 환경에서 GPS만을 사용하여 Path를 만들고 PathPlanning을 구현한 프로젝트입니다.<br>

### 사용 운영체제
- Ubuntu 18.04LTS
- ROS melodic

### 사용 시뮬레이션 환경
- MORAI simulator
    - scout-mini 모델 사용

### 실행 전 작업
- MORAI simulator 실행
    - map 선택 및 scout-mini 모델 선택
    - GPS, IMU 설치
- ros-bridge 실행
```
$ roslaunch rosbridge_server rosbridge_websocket.launch
```
### 1. Path_Making
MORAI simulator에서 publish하는 gps값 subsscribe해서 path 폴더에 좌표 값 넣은 txt 파일 생성
```
$ roslaunch scout_ros path_maker.launch
```
![gps_pathmaker_render](https://github.com/Choi0914/GPS_PathPlanning/assets/121415776/b3ecce11-921f-40cb-ad5c-804b20eeb147)

- 완성된 path

![path](https://github.com/Choi0914/GPS_PathPlanning/assets/121415776/156702ab-7dbe-4139-90ea-3835a41bb021)


### 2. Path_Planning
앞서 기록한 txt파일의 좌표와 주변 환경을 탐색한 정보를 바탕으로 미리 정한 개수만큼 path를 만들고 그 중 상황에 맞는 path를 선택해 주행

```
$ roslaunch scout_ros planner.launch
```
![gps_pathplanner_render](https://github.com/Choi0914/GPS_PathPlanning/assets/121415776/49134d75-6e0e-4027-b59d-dbaa3a3626a4)
