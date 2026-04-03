# 🌊 Akıllı Deniz Filosu Telemetri ve Yönetim Sistemi (SaaS)

Endüstriyel IoT altyapısı ile geliştirilmiş bu sistem; yat, tekne ve jetski gibi deniz araçlarının **gerçek zamanlı takibi**, **uzaktan kontrolü** ve **anahtarsız kiralama yönetimi** için tasarlanmıştır.

---

## 🚀 Genel Bakış

Bu platform sayesinde:

- Araçlar canlı olarak harita üzerinden izlenir
- NFC ile anahtarsız kiralama yapılır (Apple Wallet / Google Wallet)
- Motor uzaktan kontrol edilir
- Hırsızlık ve izinsiz kullanım engellenir
- Şirketlere özel SaaS panel sunulur

Sistem; **donanım + firmware + bulut + panel** olarak uçtan uca çalışır.

---

## 🧱 Sistem Mimarisi

[ IoT Cihazı ] ↓ MQTT (TLS) 
[ MQTT Broker ] ↓ 
[ Backend API ] ↓ 
[ Veritabanı ] ↓ 
[ Web Panel ]

---

# 🔧 1. Donanım Mimarisi

Deniz ortamına özel olarak tasarlanmıştır:

- IP68 su geçirmez yapı
- Yüksek titreşim dayanımı
- Voltaj sıçramalarına karşı koruma (Load Dump)

---

## 🧠 İşlemci ve Güvenlik

- STM32L4 (ARM Cortex-M4)
  - Düşük güç tüketimi
  - Yüksek performans

- ATECC608B Secure Element
  - Donanımsal anahtar saklama
  - Klonlanamaz cihaz kimliği

---

## 📡 Haberleşme ve Konum

- u-blox SARA-R5 (LTE-M / NB-IoT)
- ST4SIM-200M (eSIM)
- u-blox NEO-M9N (GNSS)

Özellikler:
- Global bağlantı
- Düşük enerji tüketimi
- ~1.5 metre konum hassasiyeti

---

## 🔐 NFC Anahtarsız Sistem

- NXP PN7150

Özellikler:
- Apple Wallet / Google Wallet entegrasyonu
- Telefona dokundur → motor aç
- Dijital kiralama yönetimi

---

## ⚡ Güç ve Koruma

- TVS Diyot (SMAJ33A) → voltaj sıçraması koruması
- Optokuplör (PC817) → izolasyon
- LM5164 → stabil voltaj dönüşümü
- Li-Po batarya → güç kesilse bile çalışma

---

# 💻 2. Yazılım Mimarisi

---

## 🔁 Firmware

- FreeRTOS
- C / C++

Özellikler:
- Aynı anda GPS + modem + NFC çalışır
- Kilitlenme olmaz

---

## 📡 Veri İletişimi

- MQTT (TLS 1.2)

Avantajlar:
- %80 daha az veri kullanımı
- Zayıf çekimde bile stabil iletişim

---

## 🔄 OTA Güncelleme

- Uzaktan firmware güncelleme
- Sahaya gitmeden cihaz yönetimi

---

# ☁️ 3. Backend ve Sunucu

---

## 📩 MQTT Broker

- EMQX / Mosquitto

---

## 🗄️ Veritabanı

### PostgreSQL
- Kullanıcılar
- Şirketler
- Faturalandırma

### TimescaleDB / InfluxDB
- GPS verileri
- Hız kayıtları
- Telemetri

---

## ⚙️ Backend

- Node.js (NestJS) veya Go

Özellikler:
- Mikroservis mimarisi
- WebSocket desteği
- Gerçek zamanlı veri

---

# 🖥️ 4. Kullanıcı Arayüzü

---

## 🌐 Web Panel

- React / Vue

Özellikler:
- Canlı araç takibi
- Kontrol paneli
- Raporlama

---

## 🗺️ Harita

- Google Maps / Mapbox

- Canlı izleme
- Geofence çizimi

---

## 📱 PWA

- Mobil uyumlu
- Uygulama gibi çalışır

---

# 🏢 5. Multi-Tenant Sistem

---

## 👑 Süper Admin

- Şirket ekleme
- Cihaz yönetimi
- OTA kontrolü
- Faturalandırma

---

## 🏢 Şirket (Tenant)

- Kendi araçlarını görür
- Geofence oluşturur
- Kiralama süresi belirler

---

## 👤 Kullanıcı

- Dijital anahtar kullanır
- NFC ile aracı başlatır

---

# ⚙️ 6. Temel Özellikler

- 📍 Canlı konum takibi
- 🔐 NFC anahtarsız giriş
- 🚫 Uzaktan motor kapatma
- 🧭 Geofence sistemi
- 🚨 Sabotaj algılama
- 🔋 Akü takibi

---

# 🎯 Proje Amacı

Deniz araçları için:

- Güvenliği artırmak
- Kiralama süreçlerini dijitalleştirmek
- Operasyonları otomatikleştirmek
- Yeni nesil SaaS altyapısı sunmak

---

# 📌 Sonuç

Bu sistem:

- Donanım + yazılım + bulut birleşimi
- Ölçeklenebilir SaaS modeli
- Global pazara uygun

🚀 Profesyonel bir IoT girişimi olarak konumlandırılmıştır.