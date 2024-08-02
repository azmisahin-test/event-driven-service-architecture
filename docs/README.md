## Teknoloji Seçimi ve Veritabanı

- Node.js: Sunucu tarafı uygulamalar için
- Docker: Konteyner yönetimi için
- Electron: Masaüstü uygulaması için
- Apache Kafka: Olay odaklı mimari için
- PostgreSQL: Güçlü, açık kaynaklı bir ilişkisel veritabanı olarak önerilir

## Veritabanı Seçimi ve Modeli: PostgreSQL

Neden PostgreSQL?

- PostgreSQL, güçlü bir açık kaynak ilişkisel veritabanıdır.
- ACID uyumluluğu ve zengin özellikleri ile karmaşık sorguları ve veri ilişkilerini iyi yönetir.
- JSON ve JSONB türleri sayesinde yapılandırılmamış verileri de yönetebilir, bu da olay verilerini ve log kayıtlarını saklamak için yararlıdır.

## Dizin Yapısı ve Model Tanımı

Dizin Yapısı:

```
event-driven-service-architecture/
├── api/
│   ├── controllers/
│   ├── routes/
│   ├── services/
│   ├── middlewares/
│   └── index.js
├── core/
│   ├── eventProcessor.js
│   └── messageBroker.js
├── database/
│   ├── migrations/
│   ├── seeds/
│   ├── models/
│   └── index.js
├── electron-app/
│   ├── src/
│   ├── public/
│   ├── main.js
│   └── package.json
├── mobile-app/
│   ├── src/
│   ├── components/
│   └── package.json
├── external-apis/
│   ├── service1/
│   ├── service2/
│   └── index.js
├── system-panel/
│   ├── src/
│   ├── components/
│   └── package.json
├── docker/
│   ├── Dockerfile
│   ├── docker-compose.yml
│   └── scripts/
├── .gitignore
├── README.md
```

## Veritabanı Modelleri

1. Kullanıcı Tablosu:

```
CREATE TABLE users (
    id SERIAL PRIMARY KEY,
    username VARCHAR(255) UNIQUE NOT NULL,
    password_hash TEXT NOT NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

2. Organizasyon Tablosu:

```
CREATE TABLE organizations (
    id SERIAL PRIMARY KEY,
    name VARCHAR(255) UNIQUE NOT NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

3. Organizasyon Kullanıcısı Tablosu:

```
CREATE TABLE organization_users (
    id SERIAL PRIMARY KEY,
    user_id INTEGER REFERENCES users(id),
    organization_id INTEGER REFERENCES organizations(id),
    role VARCHAR(50),
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

4. Loglar Tablosu:

```
CREATE TABLE logs (
    id SERIAL PRIMARY KEY,
    level VARCHAR(50),
    message TEXT,
    timestamp TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    meta JSONB
);
```

5. Belgeler Tablosu:

```
CREATE TABLE documents (
    id SERIAL PRIMARY KEY,
    user_id INTEGER REFERENCES users(id),
    device_id VARCHAR(255),
    device_type VARCHAR(50),
    document_type VARCHAR(50),
    document_content JSONB,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

## Proje Yönetimi

GitHub Repository:

- Yeni bir GitHub deposu oluşturun ve yukarıdaki dizin yapısını kullanarak projeyi yapılandırın.
- Projeye uygun bir README.md dosyası ekleyin.

Dökümantasyon:

- Her bileşenin nasıl çalıştığını açıklayan dökümantasyon ekleyin.
- API dökümantasyonunu Swagger veya başka bir araçla oluşturun.

Build ve Yayınlama:

- Docker kullanarak uygulamaları konteynerler içinde build edin ve çalıştırın.
- Electron uygulamasını farklı işletim sistemleri için build edin ve yayınlayın.
- Mobil uygulamayı gerekli platformlarda test edin ve dağıtım yapın.

GitHub Project ve Issue Yönetimi:

- GitHub Project kullanarak proje planlamasını ve görev takibini yapın.
- İşle ilgili konuları ve talepleri GitHub Issues bölümünde yönetin.
