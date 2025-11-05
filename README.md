# 03_Kademeli_Surede_LED_Yakma

Bu proje, **STM32F407-Discovery** kartı üzerinde 1 adet LED kullanarak, LED'in yanma süresini kademeli olarak artıran bir uygulamadır.

Projenin amacı, bir `for` döngüsü ve `HAL_Delay()` fonksiyonu kullanarak dinamik bekleme sürelerinin nasıl oluşturulacağını göstermektir. LED'in yanma süresi her döngüde 1 saniye artar ve 8 saniyeye ulaştıktan sonra tekrar 1 saniyeden başlar.

---

### 🎯 Proje Senaryosu

Animasyon, tek bir LED üzerinde artan bekleme süreleri ile çalışır:

1.  LED 1 saniye yanar, 1 saniye söner.
2.  LED 2 saniye yanar, 1 saniye söner.
3.  LED 3 saniye yanar, 1 saniye söner.
4.  ...
5.  LED 8 saniye yanar, 1 saniye söner.
6.  Döngü `while(1)` sayesinde başa döner (1 saniyeden tekrar başlar).

**Zamanlama:**
* **LED Yanma Süresi:** Kademeli olarak 1 saniyeden 8 saniyeye artar (1000ms, 2000ms, ... 8000ms).
* **LED Sönme Süresi:** Her zaman sabit 1 saniyedir (1000ms).

---

### 🛠️ Gerekli Donanım

* **1x** STM32F407-Discovery Geliştirme Kartı
* **1x** Tercih edilen renkte LED
* **1x** 220 Ohm (veya 330 Ohm) Direnç
* Breadboard ve Jumper kablolar

---

### 🔌 Devre Şeması

LED'in anot (uzun) bacağı STM32 pinine, katot (kısa) bacağı ise direnç üzerinden GND hattına bağlanmalıdır.

| LED | Direnç | STM32 Pini |
| :--- | :--- | :--- |
| LED 1 | 220 Ohm | `PA1` |
| (Tümü) | - | `GND` |

<img width="439" height="377" alt="033" src="https://github.com/user-attachments/assets/999a80a5-807e-4261-9d44-b4e371c8c2bc" />

### Kod Bloğu

<img width="1182" height="424" alt="03" src="https://github.com/user-attachments/assets/0709db3b-95d1-4c84-9e08-1494f32b5f05" />

---

### 🚀 Nasıl Kullanılır?

1.  Bu depoyu klonlayın (`git clone ...`).
2.  STM32CubeIDE yazılımını açın.
3.  `File > Open Projects from File System...` seçeneği ile proje klasörünü seçin.
4.  Proje içindeki `.ioc` dosyasını açarak pin yapılandırmasını inceleyebilirsiniz.
5.  Derleyin (Build) ve ST-Link V2 üzerinden kartınıza yükleyin (Run).
