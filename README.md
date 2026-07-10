# 🌅 Singularity v9 – "Beyaz Şafak"
## Türkçe AI Platform | Tüm API'lere Açık | Sade Beyaz Arayüz

![Version](https://img.shields.io/badge/version-9.0.0-blue)
![License](https://img.shields.io/badge/license-MIT-green)
![Language](https://img.shields.io/badge/language-Türkçe-red)

---

## 📋 Genel Bakış

**Singularity v9**, bembeyaz, minimal bir arayüzün arkasında güçlü yapay zeka teknolojileriyle:
- 🤖 **Kendi kendini iyileştiren AI** (Self-Health monitoring)
- 🔌 **Tüm API'lere bağlantı** (REST, GraphQL, SOAP, WebSocket, gRPC)
- ☁️ **Sanal bilgisayarlar** (Ubuntu/Windows)
- 🎮 **Minecraft yönetimi**
- 🌐 **Web hosting** (Nginx, Node, Python, PHP)
- 📦 **Çoklu dil derleme** (Java, JavaScript, APK)
- 🔄 **CI/CD ve Kubernetes**
- 🎤 **Sesli komutlar**
- 👥 **Çoklu kullanıcı işbirliği**
- 🧠 **Kendi prompt'larını yazma ve geliştirme**

---

## 🚀 Hızlı Başlangıç

### Sistem Gereksinimleri
- Docker & Docker Compose
- 4GB+ RAM
- 20GB+ Disk
- Linux/macOS/Windows (WSL2)

### Kurulum

```bash
# Repository'yi klonla
git clone https://github.com/ahmetmerk779-png/asmp.git
cd asmp

# Docker Compose ile başlat
docker-compose up -d

# Bekleme süresi: ~2-3 dakika
sleep 120

# Tarayıcıda aç
open http://localhost:3000
# veya
xdg-open http://localhost:3000
```

### İlk Kullanım

1. **Beyaz ekran açılır** → "Bugün ne yapmamı istersiniz?" sorusu görülür
2. **Komut gir** → Örn: "Bana bir Ubuntu VM aç"
3. **API Ekle** (Opsiyonel) → Dashboard → API Yönetimi
4. **AI ile Konuş** → Sade kartlarda sonuçlar

---

## 📁 Proje Yapısı

```
asmp/
├── docker-compose.yml          # Tüm servislerin orkestrasyonu
├── README.md
├── LICENSE
├── .env.example
│
├── frontend/                   # React 18 + Tailwind (Beyaz Tema)
│   ├── package.json
│   ├── tsconfig.json
│   ├── public/
│   │   ├── index.html
│   │   └── favicon.ico
│   ├── src/
│   │   ├── index.tsx
│   │   ├── App.tsx
│   │   ├── components/
│   │   │   ├── ChatInterface.tsx
│   │   │   ├── Dashboard.tsx
│   │   │   ├── APIManager.tsx
│   │   │   ├── HealthMonitor.tsx
│   │   │   ├── VirtualDesktop.tsx
│   │   │   └── Terminal.tsx
│   │   ├── pages/
│   │   │   ├── Home.tsx
│   │   │   ├── Settings.tsx
│   │   │   └── NotFound.tsx
│   │   ├── services/
│   │   │   ├── api.ts
│   │   │   ├── websocket.ts
│   │   │   └── auth.ts
│   │   ├── hooks/
│   │   │   ├── useChat.ts
│   │   │   ├── useAPI.ts
│   │   │   └── useWebSocket.ts
│   │   ├── types/
│   │   │   ├── index.ts
│   │   │   ├── api.ts
│   │   │   └── models.ts
│   │   ├── i18n/
│   │   │   ├── tr.json
│   │   │   ├── en.json
│   │   │   └── index.ts
│   │   ├── styles/
│   │   │   ├── tailwind.css
│   │   │   └── globals.css
│   │   └── utils/
│   │       ├── formatters.ts
│   │       ├── validators.ts
│   │       └── helpers.ts
│   └── Dockerfile
│
├── backend/                    # Python FastAPI
│   ├── requirements.txt
│   ├── main.py                 # FastAPI app entry
│   ├── config.py
│   ├── Dockerfile
│   │
│   ├── app/
│   │   ├── __init__.py
│   │   ├── core/
│   │   │   ├── config.py
│   │   │   ├── security.py
│   │   │   └── logging.py
│   │   ├── api/
│   │   │   ├── v1/
│   │   │   │   ├── __init__.py
│   │   │   │   ├── router.py
│   │   │   │   ├── endpoints/
│   │   │   │   │   ├── chat.py
│   │   │   │   │   ├── api_management.py
│   │   │   │   │   ├── vm.py
│   │   │   │   │   ├── health.py
│   │   │   │   │   ├── files.py
│   │   │   │   │   ├── github.py
│   │   │   │   │   ├── kubernetes.py
│   │   │   │   │   ├── database.py
│   │   │   │   │   └── voice.py
│   │   │   │   └── dependencies.py
│   │   │   └── websocket/
│   │   │       ├── manager.py
│   │   │       └── handlers.py
│   │   ├── models/
│   │   │   ├── __init__.py
│   │   │   ├── user.py
│   │   │   ├── api.py
│   │   │   ├── chat.py
│   │   │   ├── vm.py
│   │   │   └── health.py
│   │   ├── schemas/
│   │   │   ├── __init__.py
│   │   │   ├── user.py
│   │   │   ├── chat.py
│   │   │   ├── api.py
│   │   │   └── responses.py
│   │   ├── services/
│   │   │   ├── __init__.py
│   │   │   ├── ai_service.py         # LLM çağrıları, prompt yönetimi
│   │   │   ├── api_integrator.py     # Dış API bağlantısı ve keşif
│   │   │   ├── vm_service.py
│   │   │   ├── health_service.py     # Kendi kendini iyileştirme
│   │   │   ├── prompt_optimizer.py   # Prompt geliştirme
│   │   │   ├── kubernetes_service.py
│   │   │   ├── git_service.py
│   │   │   ├── voice_service.py
│   │   │   └── database_service.py
│   │   ├── tasks/
│   │   │   ├── __init__.py
│   │   │   ├── celery_app.py
│   │   │   ├── ai_tasks.py
│   │   │   ├── vm_tasks.py
│   │   │   ├── health_tasks.py
│   │   │   └── cleanup_tasks.py
│   │   ├── db/
│   │   │   ├── __init__.py
│   │   │   ├── session.py
│   │   │   ├── base.py
│   │   │   └── migrations/
│   │   ├── utils/
│   │   │   ├── __init__.py
│   │   │   ├── openapi_reader.py     # Swagger/OpenAPI analizi
│   │   │   ├── llm_client.py         # LLM API çağrıları
│   │   │   ├── validators.py
│   │   │   └── helpers.py
│   │   └── exceptions/
│   │       └── __init__.py
│   └── tests/
│       ├── __init__.py
│       ├── test_api_integrator.py
│       ├── test_ai_service.py
│       └── test_health_service.py
│
├── nginx/
│   ├── Dockerfile
│   ├── nginx.conf
│   └── ssl/
│       └── .gitkeep
│
├── postgres/
│   ├── Dockerfile
│   ├── init.sql
│   └── backups/
│       └── .gitkeep
│
├── redis/
│   ├── Dockerfile
│   └── redis.conf
│
├── docs/
│   ├── TR/
│   │   ├── KURULUM.md
│   │   ├── KULLANICI_KILAVUZU.md
│   │   ├── API_ENTEGRASYONU.md
│   │   ├── MIMARIFIK_DETAYLARI.md
│   │   └── SORUN_GIDERME.md
│   ├── EN/
│   │   └── README.md
│   ├── ARCHITECTURE.md
│   └── API.md
│
└── scripts/
    ├── setup.sh
    ├── migrate_db.sh
    ├── backup.sh
    └── health_check.sh
```

---

## 🔌 API Entegratörü – Nasıl Çalışır?

### 1. API Ekle (Dashboard)
```
Dashboard → API Yönetimi → Yeni API
├─ Ad: "Hava Durumu"
├─ Endpoint: "https://api.openweathermap.org/data/2.5/"
├─ Anahtar: "abc123xyz..."
└─ Dokümantasyon: "https://openweathermap.org/api"
```

### 2. AI Tarafından Otomatik Keşif
```
AI → OpenAPI Dökümanı Oku → Endpoint'leri Analiz Et
→ Parametreleri Anla → Yanıt Formatını Öğren
```

### 3. Sohbette Kullan
```
Kullanıcı: "İstanbul'da hava nasıl?"
↓
AI: Hava Durumu API'sini kullan
↓
API Çağrı: GET /weather?city=Istanbul&units=metric
↓
Yanıt İşle: JSON → Türkçe Kart
↓
Ekranda: ☀️ 28°C, Açık, Nem %45
```

---

## 🧠 Kendi Kendini İyileştirme (Self-Health)

### Monitoring
- ✅ CPU, RAM, Disk kullanımı
- ✅ Docker container durumları
- ✅ API yanıt süreleri
- ✅ Veritabanı bağlantıları
- ✅ Hata oranları

### Otomatik Aksiyon
```
Sorun Tespit Et
↓
Uyarı Gönder (Türkçe)
↓
Otomatik Düzelt (Mümkünse)
↓
Log Kaydet
↓
Kullanıcıya Rapor Sunut
```

---

## 🤖 Prompt Optimizasyonu (Self-Prompt)

Sistem, kendi kullandığı prompt'ları:
- 📊 **Başarı metriklerine göre sırala**
- 🔄 **A/B test yap**
- ✨ **En iyisini seç ve genelleştir**
- 📈 **Kullanıcı feedback'ini dahil et**

```python
# Örnek mekanizması
prompt_v1 = "Kullanıcının isteğini al ve bunu 3 adımda yap..."
prompt_v2 = "Önce konteksti anla, sonra adım adım çöz..."

# Testler: 100 soruda hangisi daha iyi sonuç verdi?
# prompt_v2 → %87 başarı, kullan ve geliştir
```

---

## 🛠️ Teknoloji Stack

| Katman | Teknoloji |
|--------|-----------|
| **Frontend** | React 18, TypeScript, Tailwind CSS, Socket.IO |
| **Backend** | Python 3.11, FastAPI, SQLAlchemy, Celery |
| **Database** | PostgreSQL 15, Redis 7, ChromaDB (Vector) |
| **Sanallaştırma** | Docker, QEMU/KVM, noVNC |
| **İş Kuyrukları** | Celery + Redis |
| **Orchestration** | Kubernetes Client, Docker SDK |
| **LLM** | OpenAI API, Local LLaMA (opsiyonel) |
| **Security** | JWT, OAuth2, ClamAV |
| **Logging** | Structured Logging + ELK (opsiyonel) |

---

## 📚 Temel Özellikler

### ✅ Yapılmış
- [x] Beyaz, minimal React arayüzü
- [x] Türkçe i18n desteği
- [x] FastAPI arka ucuyla WebSocket bağlantısı
- [x] Docker Compose setup
- [x] PostgreSQL + Redis
- [x] JWT authentication
- [x] Temel chat arayüzü
- [x] API Yönetimi CRUD'u
- [x] OpenAPI reader
- [x] Health monitoring başlangıcı
- [x] Prompt optimizer framework
- [x] Celery task queue
- [x] Virtual Machine başlatma
- [x] Terminal emülatörü
- [x] Dosya yükleme/indirme
- [x] GitHub entegrasyonu
- [x] Kubernetes client
- [x] Ses komutları (frontend)
- [x] Çoklu kullanıcı desteği
- [x] Veritabanı yönetimi

---

## 🚀 Gelecek Aşamalar

- [ ] Advanced prompt chaining
- [ ] Multi-modal input (resim, ses, video)
- [ ] Graph database entegrasyonu
- [ ] Real-time collaboration (CRDT)
- [ ] Custom LLM fine-tuning
- [ ] Mobile app (React Native)

---

## 📖 Dokümantasyon

- 📘 [Türkçe Kurulum Kılavuzu](docs/TR/KURULUM.md)
- 📗 [Kullanıcı Rehberi](docs/TR/KULLANICI_KILAVUZU.md)
- 📕 [API Entegrasyonu](docs/TR/API_ENTEGRASYONU.md)
- 📙 [Mimari Detayları](docs/TR/MIMARIFIK_DETAYLARI.md)

---

## 🤝 Katkıda Bulunma

```bash
git checkout -b feature/yeni-ozellik
git commit -m "Add: yeni özellik açıklaması"
git push origin feature/yeni-ozellik
# PR aç
```

---

## 📄 Lisans

MIT License – Özgürce kullan, değiştir ve dağıt.

---

## 👨‍💻 İletişim

- 📧 Email: ahmetmerk779-png@example.com
- 🐛 Issues: https://github.com/ahmetmerk779-png/asmp/issues
- 💬 Discussions: https://github.com/ahmetmerk779-png/asmp/discussions

---

**"Beyaz ekranın arkasında sonsuz güç."** ✨
