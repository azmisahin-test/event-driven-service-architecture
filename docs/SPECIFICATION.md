### 1. Veri Tabanı Servisi

**Temel Veri Tabanları ve Tablolar:**

- **Kullanıcı Tablosu:**
    - `id` (int, PK)
    - `username` (varchar)
    - `password` (varchar, hashed)
- **Organizasyon Tablosu:**
    - `id` (int, PK)
    - `name` (varchar)
- **Organizasyon Kullanıcısı Tablosu:**
    - `id` (int, PK)
    - `kullanici_id` (int, FK)
    - `organizasyon_id` (int, FK)

**Loglama Standartları:**

- **Düzgün Seviye Belirleme:** Logları `info`, `warn`, `error`, `critical` seviyelerinde kaydedin.
- **Gizlilik ve Güvenlik:** Kişisel veya hassas bilgileri içermemelidir.
- **Yapılandırılmış Veri:** JSON formatında loglama yapılmalıdır.
- **Zaman Damgası:** Her log girişi bir zaman damgası içermelidir.
- **Log Döndürme:** Log döndürme ve arşivleme stratejileri uygulanmalıdır.
- **Görselleştirme ve Analiz:** Basit görselleştirme ve analiz araçları kullanın.

### 2. API Servisleri

**Temel Standartlar:**

- API versiyonlaması ve endpoint gruplama: `api.domain.com/v1/endpoint`

**Temel İşlevler:**

- **Yetkilendirme Servisleri:**
    - `/v1/account/login-with-username`
    - `/v1/account/login-with-organization`
    - `/v1/account/login-with-email`
- **Doğrulama Adresleri:**
    - `/v1/sms/validation`
    - `/v1/email/validation`
- **Otomatik Güncelleme Servisi:**
    - `/v1/device/check-version`
- **Belge Ekleme/Güncelleme:**
    - `/v1/document/add`

### 3. Uygulama Geliştirme

**Masaüstü ve Mobil Uygulama:**

- **Yetkilendirme:** Kullanıcıların farklı mekanizmalar ile oturum açabilmesi.
- **Arka Plan Aktifliği:** Arka planda aktif olarak çalışabilme ve komut yürütebilme.
- **Obje/Resim Tarama ve Algılama:** Temel obje ve metin algılama işlevleri.

### 4. Çekirdek Servis

**Fonksiyonlar:**

- Olay servisinden gelen sinyalleri dinler ve ilgili servislere iletir.
- İç API isteklerini işleyebilir ve dış API servislerine yönlendirebilir.

### 5. Dış API Servisleri

**Sorgulama API'si:**

- Key-value listesi şeklinde parametreleri iletebilir.

### 6. Sistem Paneli

**Temel İşlevler:**

- Kullanıcılar farklı mekanizmalar ile oturum açabilmeli.
- Dahili sinyal servisleri ile belgeleri listeleyebilme.

Bu şartname, prototip aşamasında gerekli işlevlerin belirlenmesine ve sistemin minimum gereksinimlerini karşılamasına yardımcı olacaktır. Tam kapsamlı proje için bu prototipin üzerine daha fazla özellik ve fonksiyon eklenebilir.