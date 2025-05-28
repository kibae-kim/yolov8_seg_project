
# YOLOv8 Segmentation Project

이 프로젝트는 Ultralytics YOLOv8의 인스턴스 세그멘테이션 기능을 활용하여 비디오 파일에 대해 세그멘테이션을 수행하는 예제입니다. Jupyter Notebook을 통해 손쉽게 실행할 수 있도록 구성되어 있습니다.

---

## 📁 프로젝트 구조

```
yolov8_seg_project/
├── environment.yml         # Conda 환경 정의 파일
├── input/                  # 원본 데이터 폴더
│   └── input.mp4           # 세그멘테이션을 수행할 비디오 파일
├── notebooks/              # Jupyter 노트북 저장 폴더
│   └── segmentation.ipynb  # 세그멘테이션 실행 노트북
├── outputs/                # 결과 저장 폴더
│   └── runs/segment/predict/
│       ├── input.mp4       # 세그멘테이션된 합성 비디오
│       └── frames/         # 프레임별 PNG 이미지
└── README.md               # 프로젝트 소개 및 실행 방법
```

---

## 🚀 환경 설정 (Environment Setup)

1. Conda 설치를 먼저 완료합니다. ([https://docs.conda.io/en/latest/miniconda.html](https://docs.conda.io/en/latest/miniconda.html))

2. 프로젝트 루트 디렉토리로 이동 후, 아래 명령으로 환경을 생성합니다:

   ```bash
   cd yolov8_seg_project
   conda env create -f environment.yml
   ```

3. 환경 활성화:

   ```bash
   conda activate yolov8_seg
   ```

4. (이미 환경을 생성한 상태라면 업데이트):

   ```bash
   conda env update -f environment.yml
   ```

---

## 🖥️ Jupyter Notebook 실행

1. Conda 환경이 활성화된 상태에서, 아래 명령으로 Jupyter Notebook을 실행합니다:

   ```bash
   jupyter notebook notebooks/segmentation.ipynb
   ```

2. 또는 Anaconda Navigator에서 `yolov8_seg` 환경을 선택한 후, **Jupyter Notebook** 또는 **JupyterLab**을 실행하고 `segmentation.ipynb` 파일을 엽니다.

---

## 📊 노트북 사용 방법

1. **라이브러리 로드** 셀을 실행하여 의존성 모듈을 임포트합니다.
2. **경로 설정** 셀에서 `input/input.mp4` 경로를 확인하고, 필요 시 수정합니다.
3. **모델 불러오기** 셀에서 원하는 세그멘테이션 모델(`yolov8s-seg.pt`, `yolov8m-seg.pt` 등)을 지정합니다.
4. **예측 실행** 셀을 실행하면, 결과가 `outputs/runs/segment/predict/` 디렉토리에 저장됩니다.
5. (선택) **프레임 분리** 셀로 합성 비디오에서 개별 프레임 이미지를 추출할 수 있습니다.

---

## 🔧 환경 정의 (`environment.yml`)

```yaml
name: yolov8_seg          # 환경 이름
channels:
  - conda-forge
  - defaults
dependencies:
  - python=3.9
  - pip
  - ipython
  - ipykernel
  - notebook
  - jupyterlab
  - pip:
      - ultralytics>=8.0.20    # YOLOv8 (Segmentation 포함)
      - torch>=1.13            # PyTorch
      - torchvision>=0.14
      - opencv-python>=4.5     # 비디오 입출력
      - matplotlib             # 결과 시각화
      - ipywidgets             # 인터랙티브 위젯 (선택)
      - tqdm                   # 진행바
```

---

## 🎓 참고 자료

* Ultralytics YOLOv8 GitHub: [https://github.com/ultralytics/ultralytics](https://github.com/ultralytics/ultralytics)
* YOLOv8 문서: [https://docs.ultralytics.com/](https://docs.ultralytics.com/)
* OpenCV 비디오 처리: [https://docs.opencv.org/](https://docs.opencv.org/)

---

