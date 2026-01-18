# Korean Sidewalk Gazebo Models

본 저장소는 한국 보도(인도) 환경을 모사하기 위한 Gazebo 모델 에셋 모음이다.  
보행로 로봇, 자율주행 로봇 시뮬레이션 및 SLAM / Navigation 실험을 목적으로 사용한다.

---

## Download

```bash
git clone https://github.com/your-id/korean-sidewalk-gazebo-models.git
```

---

## Usage

### 1. Gazebo 모델 경로 설정

모델 디렉토리를 Gazebo 기본 모델 경로에 복사한다.

```bash
cp -r korean-sidewalk-gazebo-models/models/* ~/.gazebo/models/
```

Gazebo는 `~/.gazebo/models/` 경로의 모델을 자동으로 인식한다.

---

### 2. World 파일에서 모델 로드

Gazebo world 파일에서 `<include>` 문법을 사용해 모델을 불러온다.

```xml
<include>
  <uri>model://hedge</uri>
  <pose>0 0 0 0 0 0</pose>
</include>
```

- `uri` : 모델 디렉토리 이름  
- `pose` : `x y z roll pitch yaw`

---

### 3. Gazebo 실행

```bash
gazebo gazebo_test.world
```

ROS2 환경에서는 다음과 같이 실행 가능하다.

```bash
ros2 launch gazebo_ros gazebo.launch.py world:=gazebo_test.world
```

---

## Model Structure

각 모델은 다음 구조를 따른다.

```
model_name/
├── model.sdf
├── model.config
└── preview.png (optional)
```

- `model.sdf` : 형상, 충돌, 재질 정의  
- `model.config` : Gazebo 모델 메타데이터  
- `preview.png` : Gazebo 상 외형 참고 이미지  

---

## Contribution

### 기존 모델 수정
- `model.sdf` 파일 수정

### 신규 모델 추가
- 새 모델 디렉토리 생성
- `model.sdf`, `model.config` 작성
- 가능 시 Gazebo 실행 화면을 `preview.png`로 추가

---

## License

MIT License
