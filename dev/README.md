# 4_18 에어심 컨테이너 조용하 수정내용

## 1. 전북대 pub_depth 패키지 추가
- 기능 : 전북대 신경망 실행에 필요한 Depth 이미지를 Airsim에서 topic형태로 변환 및 전송
- ROS_2_PUB_depth.py는 전북대에서 제공한 소스코드임
	- 변경 사항 depth_img_in_meters의 전북대 최초 제공 값은 84*84(하드코딩) 였으나 현 Airsim Depth카메라는 480,640으로 주므로 크기값 변경

## 2. entrypoint 수정
- 시뮬레이션 실행부 하단 source ~/ros_ws/install/setup.bash 적용 및 pub_depth 노드 실행 코드 추가 

## 3. Dockerfile 수정
- /home/ue4/ros_ws/src 생성 및 pub_depth 소스코드 Copy
- colcon build 추가 

- jociiiii/airsim:dev-1.8.2로 빌드 