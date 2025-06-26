# 🧐 YOLO11 — Panduan Training & Deploy

> 📺 **Tutorial Lengkap (YouTube)**
> [Klik di sini untuk menonton](https://youtu.be/r0RspiLG260?si=CkzempiIklxxesqy)
> Cocok untuk pemula, dijelaskan langkah demi langkah.

---

## 🚀 Quick Start

### 🔧 1. Training Model

#### ✅ **Opsi 1: Google Colab (Direkomendasikan)**

* Gratis & siap pakai
* Upload dataset → jalankan beberapa blok kode

📎 [Buka Google Colab](https://colab.research.google.com/github/EdjeElectronics/Train-and-Deploy-YOLO-Models/blob/main/Train_YOLO_Models.ipynb)

#### 💻 **Opsi 2: Di Komputer Sendiri**

* Cocok untuk PC dengan GPU NVIDIA
  📖 [Panduan Lengkap](https://www.ejtech.io/learn/train-yolo-models)

---

## ⚙️ Deploy Model (Deteksi Objek)

### 1. Masuk ke Environment

```bash
conda activate yolo-env1
```

### 2. Masuk ke Folder Project (contoh)

```bash
cd C:\Users\Farel\OneDrive\Attachments\Documents\YOLO\my_model
```

### 3. Download Script Deteksi (jika belum ada)

```bash
curl -O https://raw.githubusercontent.com/EdjeElectronics/Train-and-Deploy-YOLO-Models/refs/heads/main/yolo_detect.py
```

### 4. Jalankan Inference

```bash
python yolo_detect.py --model my_model.pt --source usb0 --resolution 640x480
```

---

## 💻 Command Line Arguments

| Argumen        | Keterangan                                                        | Contoh             |
| -------------- | ----------------------------------------------------------------- | ------------------ |
| `--model`      | Path ke file model `.pt`                                          | `yolo11n.pt`       |
| `--source`     | Input: gambar, folder, video, atau kamera                         | `test.jpg`, `usb0` |
| `--thresh`     | Nilai minimum confidence (default: `0.5`)                         | `0.4`              |
| `--resolution` | Resolusi output dalam format `WxH`                                | `1280x720`         |
| `--record`     | Rekam hasil output jadi video `.avi` (harus pakai `--resolution`) | *(flag saja)*      |

---

## 🎥 Tipe Input (Source)

* 📷 **Gambar**: `test.jpg`
* 📂 **Folder gambar**: `images/`
* 🎞️ **Video**: `video.mp4`
* 🔌 **USB Camera**: `usb0`, `usb1`
* 🍓 **Pi Camera (Raspberry Pi)**: `picamera0`

---

## ✨ Contoh Perintah

```bash
# Deteksi objek di gambar
python yolo_detect.py --model yolo11n.pt --source test.jpg

# Proses video dengan hasil direkam
python yolo_detect.py --model yolo11n.pt --source video.mp4 --resolution 1280x720 --record

# Real-time kamera dengan threshold
python yolo_detect.py --model yolo11n.pt --source usb0 --thresh 0.6
```

---

## ⌨️ Kontrol Saat Menjalankan

| Tombol | Fungsi                                         |
| ------ | ---------------------------------------------- |
| `q`    | Keluar dari program                            |
| `s`    | Pause sementara                                |
| `p`    | Screenshot frame hasil deteksi (`capture.png`) |

---

## 🧐 Tips & Catatan

### Pilihan Model

* `nano` ➔ Ringan, cocok untuk CPU
* `small`, `medium`, `large` ➔ Butuh GPU, akurasi lebih tinggi

### Optimasi Performa

* Gunakan `--thresh` yang sesuai dengan kebutuhan
* Resolusi kecil seperti `640x480` lebih ringan untuk real-time
* Model `nano` sudah cukup untuk banyak kasus penggunaan sederhana

### Dependencies

Otomatis terinstal lewat:

```bash
pip install ultralytics
```

Termasuk:

* PyTorch, OpenCV, NumPy, Pillow
* Matplotlib, tqdm, PyYAML, requests
* ONNX, TensorFlow Lite (opsional untuk export)

---

## Kalau masih bingung

📺 **Tonton tutorial lengkap di YouTube** untuk penjelasan lebih detail.
Link:[https://youtu.be/r0RspiLG260?si=CkzempiIklxxesqy]
