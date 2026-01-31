# Thai License Plate Detection & Recognition System

ระบบตรวจจับและจดจำป้ายทะเบียนรถไทยด้วย YOLOv8 และ AI for Thai API พร้อม Firebase Database

## Features

- **ตรวจจับป้ายทะเบียน** ด้วย YOLOv8 custom model
- **อ่านข้อความ** ด้วย AIforThai LPR API
- **Firebase Database** สำหรับเก็บข้อมูลการตรวจจับ
- **วิเคราะห์จังหวัด** จากป้ายทะเบียนและ API response
- **Webcam Real-time** detection
- **อัปโหลดไฟล์** รูปภาพ
- **Web Interface** ที่ใช้งานง่าย
- **Dashboard** แสดงข้อมูลการตรวจจับล่าสุดและสถิติจังหวัด

## Project Structure

```
├── app.py                    # Flask web application
├── firebase_config.py        # Firebase configuration & operations
├── province_utils.py         # Province analysis from license plate text
├── api_province_utils.py     # Province extraction from API response
├── best.pt                   # Custom trained YOLOv8 model
├── static/                   # Web assets
│   ├── css/                 # Stylesheets
│   ├── js/                  # JavaScript files
│   └── uploads/             # Uploaded images
├── templates/               # HTML templates
│   ├── index.html          # Main page
│   ├── webcam.html         # Webcam detection
│   ├── dashboard.html      # Real-time dashboard
│   └── history.html        # Detection history
├── requirements.txt         # Python dependencies
└── venv/                   # Virtual environment
│   ├── predict.py          # Prediction utilities
│   └── Train.py            # Training script
├── training_data/          # Training datasets
│   ├── train/              # Training images & labels
│   ├── valid/              # Validation data
│   ├── test/               # Test data
│   └── data.yaml           # Dataset configuration
├── docs/                   # Documentation
└── venv/                   # Python virtual environment
```

## Quick Start

### 1. Setup Environment

```bash
python -m venv venv
source venv/bin/activate  # macOS/Linux
pip install -r requirements.txt
```

### 2. Run Application

```bash
python app.py
```

### 3. Open Browser

```
http://localhost:5000
```

## Usage

### Web Interface

1. **อัปโหลดไฟล์**: เลือกรูปภาพป้ายทะเบียน
2. **Webcam**: ใช้กล้องตรวจจับแบบ Real-time
3. **ประวัติ**: ดูผลการตรวจจับที่ผ่านมา

### Webcam Features

- **Camera Selection**: เลือกกล้องที่ต้องการ
- **Resolution Control**: ปรับความละเอียด
- **Detection Settings**: ปรับ confidence threshold
- **Auto/Manual Mode**: โหมดตรวจจับอัตโนมัติหรือแมนนวล

## Configuration

### API Setup

แก้ไขไฟล์ `app.py` เพื่อใส่ API key:

```python
API_KEY = "your_aiforthai_api_key"
```

### Model Path

ไฟล์ model อยู่ที่ `models/best.pt`

## Documentation

- [Organized Structure](docs/ORGANIZED_STRUCTURE.md)
- [Performance Optimization](docs/PERFORMANCE_OPTIMIZATION.md)
- [Webcam Guide](docs/WEBCAM_GUIDE.md)

## Contributing

1. Fork the project
2. Create feature branch
3. Commit changes
4. Push to branch
5. Open Pull Request

