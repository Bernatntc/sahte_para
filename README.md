# Fake Currency Detection (Image Classification)
## 🇬🇧 English


A computer vision project that classifies banknote images as **Real** or **Fake** using a classic ML pipeline:
**HOG (Histogram of Oriented Gradients) feature extraction + SVM (Support Vector Machine)**.

The workflow is implemented in a Jupyter Notebook (`.ipynb`) and focuses on a clean, reproducible setup.

---

## What this project does
- Loads images from two classes: `Real` and `Fake`
- Preprocesses images (resize, feature extraction)
- Extracts **HOG** features
- Trains an **SVM** model (optionally with `GridSearchCV`)
- Evaluates performance (accuracy, confusion matrix, classification report)
- Saves the trained model with `joblib` (if enabled in the notebook)

---

## Tech Stack
- Python
- OpenCV (`cv2`)
- NumPy
- scikit-image (HOG)
- scikit-learn (SVM, Pipeline, GridSearchCV, metrics)
- Jupyter Notebook
- joblib

---

## Project Structure 
fake_currency_project/
├─ sahte_para.ipynb
├─ dataset/
│  ├─ Real/
│  └─ Fake/
└─ outputs/              

# Sahte Para Tespiti (Görüntü Sınıflandırma)
##🇹🇷 Türkçe

Klasik bir makine öğrenmesi hattı kullanarak banknot görüntülerini **Gerçek** veya **Sahte** olarak sınıflandıran bir bilgisayarlı görü projesi:
**HOG (Yönelimli Gradyan Histogramı) öznitelik çıkarımı + SVM (Destek Vektör Makineleri)**.

Çalışma akışı bir Jupyter Notebook (`.ipynb`) içinde uygulanmıştır ve temiz/tekrarlanabilir bir kurulum hedefler.

---

## Proje ne yapıyor?
- Görüntüleri iki sınıftan yükler: `Real` ve `Fake`
- Ön işleme uygular (yeniden boyutlandırma, öznitelik çıkarımı)
- **HOG** özniteliklerini çıkarır
- **SVM** modeli eğitir (isteğe bağlı `GridSearchCV` ile)
- Performansı değerlendirir (accuracy, confusion matrix, classification report)
- (Notebook’ta açıksa) modeli `joblib` ile kaydeder

---

## Teknolojiler
- Python
- OpenCV (`cv2`)
- NumPy
- scikit-image (HOG)
- scikit-learn (SVM, Pipeline, GridSearchCV, metrikler)
- Jupyter Notebook
- joblib

---

## Proje Yapısı 

fake_currency_project/
├─ sahte_para.ipynb
├─ dataset/
│  ├─ Real/
│  └─ Fake/
└─ outputs/             

