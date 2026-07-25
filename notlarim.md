# Kendi Notlarım ve Örneklerim
> Bu repo üzerinden Python öğrenirken her konuyu kendi projelerimden (Coddiom, ÇelikHub, PostByPrompt, FinanceAI Pro) esinlenen örneklerle pekiştiriyorum.

## İçindekiler
1. [Python'a Giriş](#1_python_giris)
2. [Temel Yapılar](#2_python_temel_yapilar)
3. [Döngüler ve Kontrol Yapıları](#3_donguler_kontrol_yapilari)
4. [Fonksiyonlar](#4_fonksiyonlar)
5. [Dosya İşlemleri](#5_dosya_islemleri)
6. [Hata Yönetimi](#6_hata_yonetimi)
7. [Ortam ve Paket Yönetimi](#7_ortam_paket_yonetimi)
8. [NumPy](#8_numpy)
9. [Pandas](#9_pandas)
10. [Matplotlib](#10_matplotlib)
11. [OOP](#11_oop)
12. [Öğrenci Not Analiz Projesi](#12_ogrenci_not_analiz_projesi)

---

## 1_python_giris
Python'a giriş ve temel çıktı işlemleri.

```python
# İlk deneme
print("Yazılım Geliştirici ve Yazılım Mühendisi olarak AI yolculuğum başlıyor")

# Kullanıcıdan girdi alma
proje_adi = input("Şu an üzerinde çalıştığın proje: ")
print(f"{proje_adi} için kodlama başlıyor...")
```

## 2_python_temel_yapilar
Değişken atamaları ve veri tipleri.

```python
meslek = "Yazılım Geliştirici ve Yazılım Mühendisi"
gpa = 3.29
aktif_sporcu = True

print(f"Meslek: {meslek}, Ortalama: {gpa}")

# Liste, tuple, dict, set örnekleri
aktif_projeler = ["ÇelikHub", "PostByPrompt", "FinanceAI Pro"]
proje_sayisi = len(aktif_projeler)
print(f"Şu an {proje_sayisi} aktif proje yürütüyorum: {aktif_projeler}")
```

## 3_donguler_kontrol_yapilari
Şartlı ifadeler ve döngüler.

```python
# Antrenman rutini kontrolü
antrenman_gunleri = ["Pazartesi", "Çarşamba", "Cuma", "Cumartesi"]

for gun in antrenman_gunleri:
    if gun == "Cumartesi":
        print(f"{gun}: Dinlenme günü")
    else:
        print(f"{gun}: Spor yapılıyor")

# while ile deploy kontrolü örneği
build_hatasi = True
deneme = 0
while build_hatasi and deneme < 3:
    deneme += 1
    print(f"Deploy denemesi {deneme}...")
    if deneme == 3:
        build_hatasi = False
        print("Deploy başarılı!")
```

## 4_fonksiyonlar
Tekrar kullanılabilir kod blokları tanımlama.

```python
# Temel otonom agent başlatma simülasyonu
def agent_baslat(agent_adi, gorev):
    return f"{agent_adi} isimli yapay zeka ajanı '{gorev}' göreviyle başlatıldı."

print(agent_baslat("DataAnalyzer", "Veri Ön İşleme"))

# Varsayılan parametre ve *args örneği
def coddiom_rapor(*hizmetler, musteri="Genel"):
    print(f"{musteri} için sunulan hizmetler: {', '.join(hizmetler)}")

coddiom_rapor("Web Otomasyonu", "SaaS Geliştirme", musteri="Coddiom Müşterisi")
```

## 5_dosya_islemleri
Dosyaya veri yazma ve okuma.

```python
# Engineering Efficiency logları
with open("tasarim_log.txt", "w") as f:
    f.write("Sürdürülebilir tasarım prensipleri uygulandı.")

with open("tasarim_log.txt", "r") as f:
    print(f.read())

# Satır satır ekleme (append)
with open("tasarim_log.txt", "a") as f:
    f.write("\nPhase 18 tamamlandı.")
```

## 6_hata_yonetimi
Kodun çökmesini engellemek için try/except blokları.

```python
try:
    sonuc = 10 / 0
except ZeroDivisionError:
    print("Matematiksel hata: Sıfıra bölme işlemi yapılamaz.")
finally:
    print("Otomasyon akışı devam ediyor.")

# Özel exception tanımlama
class GecersizVeriHatasi(Exception):
    pass

def veri_kontrol(deger):
    if deger < 0:
        raise GecersizVeriHatasi("Negatif değer kabul edilmiyor.")
    return deger

try:
    veri_kontrol(-5)
except GecersizVeriHatasi as e:
    print(f"Hata yakalandı: {e}")
```

## 7_ortam_paket_yonetimi
Sanal ortam oluşturma ve kütüphane indirme işlemleri.

```bash
# Terminal komutları
python -m venv .venv
source .venv/bin/activate
pip install numpy pandas matplotlib scikit-learn

# Bağımlılıkları dışa aktarma
pip freeze > requirements.txt
```

## 8_numpy
Matematiksel işlemler ve diziler.

```python
import numpy as np

# Tahminsel algoritmik simülasyon verileri
sensor_harici_veriler = np.array([12.5, 14.2, 11.8, 15.1])
print(f"Ortalama Değer: {sensor_harici_veriler.mean():.2f}")
print(f"Standart Sapma: {sensor_harici_veriler.std():.2f}")

# Matris işlemleri
matris = np.array([[1, 2], [3, 4]])
print(f"Determinant: {np.linalg.det(matris):.2f}")
```

## 9_pandas
Veri setlerini tablo (DataFrame) formatında işleme.

```python
import pandas as pd

projeler = pd.DataFrame({
    "Proje": ["WaterTwin AI", "ÇelikHub", "PostByPrompt", "FinanceAI Pro"],
    "Alan": ["Predictive Software", "Emlak Portalı", "SaaS Otomasyon", "Finansal Asistan"]
})
print(projeler)

# Filtreleme ve gruplama
saas_projeler = projeler[projeler["Alan"].str.contains("SaaS|Asistan")]
print(saas_projeler)
```

## 10_matplotlib
Veri görselleştirme temelleri.

```python
import matplotlib.pyplot as plt

# Örnek bir tahmin modeli performans artışı
haftalar = [1, 2, 3, 4]
dogruluk_orani = [75, 82, 88, 94]

plt.plot(haftalar, dogruluk_orani, marker='o', color='b')
plt.title("Model Doğruluk Oranı (Haftalık)")
plt.xlabel("Hafta")
plt.ylabel("Doğruluk (%)")
plt.grid(True)
plt.show()
```

## 11_oop
Nesne Yönelimli Programlama (Sınıflar ve Nesneler).

```python
class Ogrenci:
    def __init__(self, isim, bolum, gpa):
        self.isim = isim
        self.bolum = bolum
        self.gpa = gpa

    def akademik_durum(self):
        return f"{self.isim} - {self.bolum} (GPA: {self.gpa})"

ben = Ogrenci("Berat", "Yazılım Mühendisliği", 3.29)
print(ben.akademik_durum())

# Kalıtım (inheritance) örneği
class YazilimGelistirici(Ogrenci):
    def __init__(self, isim, bolum, gpa, sirket):
        super().__init__(isim, bolum, gpa)
        self.sirket = sirket

    def mesleki_bilgi(self):
        return f"{self.isim}, {self.sirket} bünyesinde yazılım geliştiriyor."

berat = YazilimGelistirici("Berat", "Yazılım Mühendisliği", 3.29, "Coddiom")
print(berat.mesleki_bilgi())
```

## 12_ogrenci_not_analiz_projesi
Mevcut yapıları birleştiren ufak bir analiz scripti.

```python
# Basit not analizi
notlar = {"Vize": 85, "Proje": 95, "Final": 90}

toplam = sum(notlar.values())
ortalama = toplam / len(notlar)

durum = "Geçti" if ortalama >= 60 else "Kaldı"
print(f"Dönem Ortalaması: {ortalama:.1f} -> Durum: {durum}")

# Birden fazla öğrenci için genişletilmiş versiyon
sinif_notlari = {
    "Berat": {"Vize": 85, "Proje": 95, "Final": 90},
    "Ayşe": {"Vize": 40, "Proje": 55, "Final": 48},
}

for ogrenci, notlar in sinif_notlari.items():
    ort = sum(notlar.values()) / len(notlar)
    durum = "Geçti" if ort >= 60 else "Kaldı"
    print(f"{ogrenci}: {ort:.1f} -> {durum}")
```
