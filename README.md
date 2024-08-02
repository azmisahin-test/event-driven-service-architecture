# Event-Driven Service Architecture [ Prototype ]

## Proje Tanımı

Event-Driven Service Architecture, mikro servis mimarisi kullanarak olay odaklı bir sistem geliştirmeyi hedefleyen bir projedir. Bu proje, çeşitli bileşenlerin entegre olduğu, olay bazlı iletişim sağlayan ve kullanıcıların çeşitli senaryolarda veri yönetimini yapabilen bir platform sunar.

`Not: Gerçek projeleriniz için proje katmanlarını farklı depo adreslerine dağıtmalısınız. Bu bir prototiptir.`

Proje, aşağıdaki bileşenleri içerir:

* API Servisleri: RESTful API'ler ile olay yönetimi ve veri işlemleri.
* Masaüstü Uygulaması: Electron ile geliştirilen, farklı işletim sistemlerinde çalışabilen masaüstü uygulaması.
* Mobil Uygulama: React Native veya Expo ile geliştirilmiş mobil uygulama.
* Çekirdek Servisler ve Olay Servisi: Kafka ile olay yönetimi ve işleme mantığı.
* Veritabanı: PostgreSQL ile veri yönetimi ve depolama.
* Dış API Servisleri: Çeşitli üçüncü taraf API'lerle entegrasyon.
* Sistem Paneli: Yönetim ve izleme paneli.

## Özellikler

* Olay Odaklı Mimari: Apache Kafka kullanılarak olay tabanlı veri akışı ve işleme.
* Veri Yönetimi: PostgreSQL ile kullanıcılar, organizasyonlar, belgeler ve loglar gibi verilerin yönetimi.
* Masaüstü ve Mobil Uygulama: Electron ve React Native ile çeşitli platformlarda çalışabilen uygulamalar.
* API Servisleri: Kullanıcı yetkilendirme, belge işlemleri ve otomatik güncellemeler gibi işlevler sunan API'ler.
* Dış API Entegrasyonları: Çeşitli harici API'lerle veri alışverişi ve entegrasyon.

## Teknolojiler

* Node.js: Sunucu tarafı uygulamalar için.
* Docker: Konteyner yönetimi ve dağıtım için.
* Electron: Masaüstü uygulamaları için.
* React Native / Expo: Mobil uygulamalar için.
* PostgreSQL: İlişkisel veritabanı yönetimi için.
* Apache Kafka: Olay yönetimi ve mesajlaşma için.

## Kurulum ve Başlangıç

## Gereksinimler

* Node.js (LTS sürüm)
* Docker
* PostgreSQL
* Apache Kafka
* Git

## Projeyi Klonlama

Öncelikle, projeyi GitHub'dan klonlayın:

```
git clone https://github.com/azmisahin-test/event-driven-service-architecture.git
cd event-driven-service-architecture
```

## Docker ile Çalışma

Proje, Docker kullanarak çalıştırılabilir. Docker ve Docker Compose ile gerekli servisleri başlatmak için:

```
docker-compose up --build
```

## Veritabanı Kurulumu

PostgreSQL veritabanını kurun ve şemayı oluşturun:

1. PostgreSQL’i kurun.
2. Veritabanı yapılandırmasını database dizininde bulunan SQL dosyalarını kullanarak yapın.

## Uygulama Geliştirme

### Node.js API Servisleri:

* API servislerini api/ dizininde geliştirin.
* API'leri başlatmak için:

```
cd api
npm install
npm start
```

### Electron Masaüstü Uygulaması:

Electron uygulamasını electron-app/ dizininde geliştirin.
Uygulamayı başlatmak için:

```
cd electron-app
npm install
npm start
```

### Mobil Uygulama:

Mobil uygulamayı mobile-app/ dizininde geliştirin.
Uygulamayı başlatmak için:

```
cd mobile-app
npm install
npm start
```

### Sistem Paneli:

Sistem panelini system-panel/ dizininde geliştirin.
Sistemi başlatmak için:

```
cd system-panel
npm install
npm start
```

## API Dokümantasyonu

API'ler ve uç noktalar hakkında detaylı bilgi için API Dokümantasyonu sayfasına göz atın.

## Testler

Testler, birim ve entegrasyon testlerini içerir. Testleri çalıştırmak için:

```
npm test
```

## Katkıda Bulunma

Katkıda bulunmak isterseniz, lütfen bir çekme isteği (pull request) gönderin veya bir sorun (issue) açın. Katkılarınız için şimdiden teşekkür ederiz!

## Lisans
Bu proje MIT lisansı ile lisanslanmıştır. Daha fazla bilgi için LICENSE dosyasına bakabilirsiniz.