
# 🧐 YOLO11 — Panduan Training & Deploy Model Deteksi Objek

> 📺 **Tutorial Lengkap di YouTube**  
> (https://youtu.be/r0RspiLG260?si=CkzempiIklxxesqy)

---

## 🚀 Quick Start

### 🔧 1. Training Model

#### ✅ **Opsi 1: Google Colab (Direkomendasikan)**
- Gratis & siap pakai
- Upload dataset → jalankan beberapa blok kode

📎 [Buka Google Colab](https://colab.research.google.com/github/EdjeElectronics/Train-and-Deploy-YOLO-Models/blob/main/Train_YOLO_Models.ipynb)

#### 💻 **Opsi 2: Di Komputer Sendiri**
- Cocok untuk PC dengan GPU NVIDIA  
📖 [Panduan Lengkap](https://www.ejtech.io/learn/train-yolo-models)

---

## ⚙️ Deploy Model (Deteksi Objek)

### Langkah-Langkah

1. **Aktifkan environment Anaconda**  
```bash
conda activate yolo-env1
```

2. **Masuk ke folder project (contoh)**  
```bash
cd C:\Users\Farel\OneDrive\Attachments\Documents\YOLO\my_model
```

3. **Download script deteksi (jika belum ada)**  
```bash
curl -O https://raw.githubusercontent.com/EdjeElectronics/Train-and-Deploy-YOLO-Models/refs/heads/main/yolo_detect.py
```

4. **Jalankan inference (deteksi objek)**  
```bash
python yolo_detect.py --model my_model.pt --source usb0 --resolution 640x480
```

---

## 💻 Command Line Arguments

| Argumen        | Keterangan                                                        | Contoh             |
|----------------|--------------------------------------------------------------------|--------------------|
| `--model`      | Path ke file model `.pt`                                           | `yolo11n.pt`       |
| `--source`     | Input: gambar, folder, video, atau kamera                          | `test.jpg`, `usb0` |
| `--thresh`     | Confidence minimum (default: `0.5`)                                | `0.4`              |
| `--resolution` | Resolusi output (`WxH`)                                            | `1280x720`         |
| `--record`     | Rekam hasil jadi video `.avi` (harus pakai `--resolution`)         | *(flag saja)*      |

---

## 🎥 Tipe Input (Source)

- 📷 **Gambar**: `test.jpg`
- 📂 **Folder gambar**: `images/`
- 🎞️ **Video**: `video.mp4`
- 🔌 **USB Camera**: `usb0`, `usb1`
- 🍓 **Pi Camera (Raspberry Pi)**: `picamera0`

---

## ✨ Contoh Perintah

```bash
# Deteksi objek pada gambar
python yolo_detect.py --model yolo11n.pt --source test.jpg

# Proses video dengan hasil direkam
python yolo_detect.py --model yolo11n.pt --source video.mp4 --resolution 1280x720 --record

# Deteksi objek dari kamera real-time
python yolo_detect.py --model yolo11n.pt --source usb0 --thresh 0.6
```

---

## ⌨️ Kontrol Keyboard Selama Deteksi

| Tombol | Fungsi                                               |
|--------|------------------------------------------------------|
| `q`    | Keluar dari program                                  |
| `s`    | Pause (jeda) sementara                               |
| `p`    | Screenshot frame saat ini (tersimpan sebagai `capture.png`) |

---

## 📦 Download File Besar (Model, Dataset, dll)

Karena GitHub membatasi ukuran file, file `.pt` model dan dataset **tidak disertakan** di repository ini.

Silakan download file lengkap dari Google Drive berikut:

🔗 [📥 Google Drive Folder (YOLO11 Files)](https://drive.google.com/drive/folders/YOUR_FOLDER_ID_HERE)

Isi folder:
- ✅ Trained model (.pt)
- ✅ Dataset contoh
- ✅ Gambar uji coba
- ✅ Script `.py` dan file lainnya

---

## 🧠 Tips & Catatan

### Pilihan Model
| Model     | Cocok untuk | Keterangan              |
|-----------|-------------|--------------------------|
| `nano`    | CPU         | Ringan, kecepatan tinggi |
| `small`   | GPU         | Lebih akurat             |
| `medium`  | GPU         | Keseimbangan bagus       |
| `large`   | GPU         | Akurasi tinggi           |

### Optimasi Performa
- Gunakan resolusi kecil seperti `640x480` untuk real-time
- Sesuaikan nilai `--thresh` sesuai kebutuhan
- Model `nano` cukup untuk sebagian besar kasus sederhana

---

## 🧰 Dependencies

Semua dependensi otomatis terinstall dengan:

```bash
pip install ultralytics
```

Termasuk:
- PyTorch, OpenCV, NumPy, Pillow
- Matplotlib, tqdm, requests, PyYAML
- ONNX, TensorFlow Lite *(untuk export)*

---

## Kalau masih bingung

📺 **Tonton tutorial lengkap di YouTube**:  
(https://youtu.be/r0RspiLG260?si=CkzempiIklxxesqy)
