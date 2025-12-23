# sahte_para
# 💵 Gerçek–Sahte Banknot Sınıflandırma (HOG + SVM) / Real–Fake Banknote Classification (HOG + SVM)

## 🇹🇷 Türkçe

### Proje Özeti
Bu proje, banknot görüntülerini **Gerçek (Real)** ve **Sahte (Fake)** olarak sınıflandırmak için **HOG (Histogram of Oriented Gradients)** özellik çıkarımı ve **SVM (Support Vector Machine)** tabanlı bir yaklaşım kullanır.  
Model, eğitim sürecinde en iyi hiperparametreleri bulmak için **GridSearchCV** ile optimize edilir ve `joblib` ile tek dosyada kaydedilir.

### Özellikler
- Görüntü ön işleme: **grayscale + resize**
- Özellik çıkarımı: **HOG**
- Sınıflandırma: **SVC (RBF kernel)**
- Dengesiz sınıflara karşı: `class_weight="balanced"`
- Otomatik parametre seçimi: **GridSearchCV (5-fold CV)**
- Model paketleme: `real_fake_model.pkl` (model + HOG parametreleri + img_size)

### Veri Seti Yapısı
Aşağıdaki klasör yapısı beklenir:
dataset/
Fake/
*.jpg | *.png | ...
Real/
*.jpg | *.png | ...

Eğitim

Eğitim akışı genel olarak:

Fake/Real klasörlerinden görselleri oku

HOG feature çıkar

Train/Test split

Pipeline (Scaler + SVC)

GridSearchCV ile en iyi parametreleri bul

Modeli kaydet

Model kaydı örneği:

joblib.dump(
    {"model": best_model, "img_size": IMG_SIZE, "hog_params": HOG_PARAMS},
    "real_fake_model.pkl"
)
Tek Görüntü Tahmini

predict_image() ile tek bir görseli tahmin edebilirsin:

print(predict_image("dataset/Real/sample.jpg"))
print(predict_image("dataset/Fake/sample.jpg"))

Mac’te masaüstünden örnek:

print(predict_image("/Users/bernatutuncu/Desktop/rupi.jpg"))

Hızlı Test (Rastgele Örnekler)
import random, glob

fake_samples = random.sample(glob.glob("dataset/Fake/*"), 10)
real_samples = random.sample(glob.glob("dataset/Real/*"), 10)

print("FAKE testleri:")
for p in fake_samples:
    print(p, "→", predict_image(p))

print("\nREAL testleri:")
for p in real_samples:
    print(p, "→", predict_image(p))

Değerlendirme

Performans ölçümü için:

Accuracy

Confusion Matrix

Classification Report (precision/recall/f1)

Not: Sınıflar dengesizse yalnız accuracy yanıltıcı olabilir; confusion matrix ve f1 skorları daha anlamlı olur.

Proje Notları / İyileştirmeler

Sadece * ile dosya toplamak yerine *.jpg, *.png filtrelenebilir.

Daha fazla veri ve çeşitlilik performansı artırır.

CNN tabanlı bir yaklaşım ile karşılaştırma yapılabilir.

Project Overview

This project classifies banknote images as Real or Fake using a classic computer vision + ML pipeline:

Feature extraction with HOG (Histogram of Oriented Gradients)

Classification with SVM (Support Vector Machine)

Hyperparameter tuning via GridSearchCV

Model packaging & saving with joblib (real_fake_model.pkl)

Features

Preprocessing: grayscale + resize

Feature extraction: HOG

Classifier: SVC (RBF kernel)

Handles class imbalance: class_weight="balanced"

Hyperparameter search: GridSearchCV (5-fold CV)

Saved bundle includes: model + img_size + hog_params

Project Overview

This project classifies banknote images as Real or Fake using a classic computer vision + ML pipeline:

Feature extraction with HOG (Histogram of Oriented Gradients)

Classification with SVM (Support Vector Machine)

Hyperparameter tuning via GridSearchCV

Model packaging & saving with joblib (real_fake_model.pkl)

Features

Preprocessing: grayscale + resize

Feature extraction: HOG

Classifier: SVC (RBF kernel)

Handles class imbalance: class_weight="balanced"

Hyperparameter search: GridSearchCV (5-fold CV)

Saved bundle includes: model + img_size + hog_params

Dataset Structure
Expected directory layout:
dataset/
  Fake/
    *.jpg | *.png | ...
  Real/
    *.jpg | *.png | ...

Installation
Python 3.x recommended.
pip install numpy opencv-python scikit-image scikit-learn joblib

Training
Typical pipeline:


Load images from Fake/Real folders


Extract HOG features


Train/Test split


Pipeline (Scaler + SVC)


GridSearchCV for best params


Save the trained model bundle


Save example:
joblib.dump(
    {"model": best_model, "img_size": IMG_SIZE, "hog_params": HOG_PARAMS},
    "real_fake_model.pkl"
)

Single Image Prediction
Use predict_image() to classify a single image:
print(predict_image("dataset/Real/sample.jpg"))
print(predict_image("dataset/Fake/sample.jpg"))

macOS example:
print(predict_image("/Users/bernatutuncu/Desktop/rupi.jpg"))

Quick Random Tests
import random, glob

fake_samples = random.sample(glob.glob("dataset/Fake/*"), 10)
real_samples = random.sample(glob.glob("dataset/Real/*"), 10)

print("FAKE samples:")
for p in fake_samples:
    print(p, "->", predict_image(p))

print("\nREAL samples:")
for p in real_samples:
    print(p, "->", predict_image(p))

Evaluation
Recommended metrics:


Accuracy


Confusion Matrix


Classification Report (precision/recall/f1)



Note: If classes are imbalanced, accuracy alone may be misleading; check F1 and confusion matrix.

Future Improvements


Filter only image extensions (*.jpg, *.png) when loading data.


Increase dataset size & diversity.


Compare against CNN-based deep learning models.






