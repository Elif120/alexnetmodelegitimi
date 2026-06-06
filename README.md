#  AlexNet ile Intel Görüntü Sınıflandırma Projesi

Bu proje, bilgisayarlı görü (computer vision) alanında devrim yaratan derin öğrenme mimarilerinden **AlexNet** kullanılarak, doğal ve kentsel ortamlara ait manzaraları sınıflandırmak amacıyla geliştirilmiştir. Projede uçtan uca veri önişleme, model mimarisi kurulumu, eğitim ve performans analizi adımları uygulanmıştır.

---

##  Proje Özellikleri

* **Mimari:** AlexNet (Evrişimli Sinir Ağı - CNN)
* **Framework / Kütüphaneler:** PyTorch, Torchvision, NumPy, Matplotlib
* **Veri Seti:** Intel Image Classification (Kaggle)
* **Geliştirme Ortamı:** Kaggle Notebook / VS Code
* **Sınıf Sayısı:** 6 Farklı Doğal/Kentsel Mekan sınıfı

---

##  Veri Seti Hakkında

Projede kullanılan **Intel Image Classification** veri seti, dünyanın dört bir yanından toplanmış yaklaşık 25.000 adet yüksek kaliteli yer manzarası görselini içermektedir. Veri seti 6 ana sınıfa ayrılmıştır:

1. 🏢 **Buildings (Binalar)**
2. 🌲 **Forest (Orman)**
3. 🏔️ **Glacier (Buzdağı)**
4. ⛰️ **Mountain (Dağ)**
5. 🌊 **Sea (Deniz)**
6. 🛣️ **Street (Sokak)**

*Tüm görseller, AlexNet mimarisinin standart girdi boyutu olan **224x224** piksel boyutuna yeniden ölçeklendirilmiş ve normalize edilmiştir.*

---

## 🧠 Model Mimarisi: AlexNet

Bu projede uygulanan AlexNet modeli, büyük ölçekli görsel tanıma problemlerinde derin öğrenmenin gücünü kanıtlamış 8 katmanlı güçlü bir CNN yapısıdır:

* **Evrişim Katmanları (Convolutional Layers):** Görsellerdeki kenar, köşe ve doku gibi düşük ve yüksek seviyeli özellikleri çıkarmak için $11 \times 11$, $5 \times 5$ ve $3 \times 3$ boyutlarında filtreler kullanılmıştır.
* **Aktivasyon Fonksiyonu:** Modelin hızlı yakınsaması (convergence) için tüm gizli katmanlarda **ReLU** ($f(x) = \max(0, x)$) tercih edilmiştir.
* **Ortaklama Katmanları (Max-Pooling):** Özellik haritalarının boyutunu azaltırken en belirgin özellikleri korumak için kullanılmıştır.
* **Aşırı Öğrenmeyi Önleme (Regularization):** Modelin ezberlemesini (overfitting) engellemek amacıyla Tam Bağlantılı (Fully Connected) katmanlarda %50 oranında **Dropout** uygulanmıştır.

---

## 🛠️ Kurulum ve Çalıştırma

Projeyi yerel bilgisayarınızda veya kendi Kaggle ortamınızda çalıştırmak için aşağıdaki adımları takip edebilirsiniz.

### 1. Depoyu Klonlayın
```bash
git clone [https://github.com/Elif120/transformerveagent.git](https://github.com/Elif120/transformerveagent.git)
cd transformerveagent
