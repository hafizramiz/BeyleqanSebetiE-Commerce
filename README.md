# 🛒 ASP.NET Core 9.0 ve PostgreSQL ile Ogani E-Ticaret Sitesi

Bu repository, M&Y Yazılım Akademi kapsamındaki on altıncı proje olan Ogani E-Ticaret Sitesi uygulamasını içerir. Proje ASP.NET Core 9.0 (MVC) ve PostgreSQL ile geliştirilmiş, sade ve okunabilir tek katmanlı bir mimari ile tasarlanmıştır.

---

## 🚀 Özellikler

- 🧩 Veritabanı: Category, Product, Customer, Order ve Log tabloları (PostgreSQL)
- 🐘 PostgreSQL entegrasyonu ve güvenli CRUD işlemleri
- 🍎 Ürün verisi: AI destekli 250+ yiyecek ürünü insert ile eklendi
- 👤 Müşteri verisi: 500+ Türkçe müşteri kaydı
- 📦 Sipariş verisi: 100.000 sipariş CSV’den içeri aktarıldı
- 🧠 Admin Paneli: Modern CRUD arayüzü
- 📊 Dashboard & Analitik: Widget, istatistik kartları, grafikler
- 🍳 Yemek öneri özelliği: RapidAPI üzerinden AI destekli öneriler
- 💬 WhatsApp entegrasyonu: Ana sayfadan WhatsApp Web ile iletişim
- 📈 Sipariş tahmini: ML.NET ile 2026 ilk 3 ay, şehir bazlı tahmin
- 🥇 Müşteri segmentasyonu:
  - Altın: 210+ sipariş
  - Gümüş: 180–209 sipariş
  - Bronz: 179 veya altı
  Pie chart ile gösterim
- 🗺️ Harita entegrasyonu: Leaflet ile Türkiye şehir bazlı heatmap, toplam sipariş, ortalama tutar ve en çok tercih edilen kategori
- 🧾 Loglama: CRUD işlemlerinin Log tablosuna kaydı (LogId, UserName, ActionType, Entity, Description, Date)

---

## 🧱 Mimari ve Teknolojiler

- 💻 ASP.NET Core 9.0 (MVC)
- 🐘 PostgreSQL
- 💎 Entity Framework Core (ORM)
- 🔄 AutoMapper (Entity ↔ DTO)
- 🤖 ML.NET (tahminleme)
- 🌐 RapidAPI (AI entegrasyonu)
- 🧱 Tek katmanlı mimari, temiz kod ve folder structure prensipleri
- 🧩 ViewComponent
- 🎨 HTML5, CSS3, Bootstrap, JavaScript

Proje yapısı örneği:

```
15PC2_ECommerce.sln
15PC2_ECommerce/
  Program.cs
  appsettings.json
  Context/
  Controllers/
  DTOs/
  Entities/
  Mapping/
  Services/
  ViewComponents/
  Views/
  wwwroot/
```

---

## 🧭 Modüller

### 🏠 Ana Sayfa
- Ürünleri kategori bazında listeleme
- Fiyat ve kategori filtreleri
- Ürün detayları
- Bize Ulaşın formu

### 🧮 Admin Paneli
- Category, Product, Customer, Order için CRUD
- ML.NET ile sipariş tahmini
- Leaflet ile şehir bazlı sipariş yoğunluğu
- RapidAPI ile malzemeye göre yemek önerileri
- Log kayıtları ve “Yapılan İşlemler” listesi

---

## ⚙️ Kurulum ve Çalıştırma

1. PostgreSQL veritabanını oluşturun ve bağlantı bilgisini `appsettings.json` dosyasına girin:
   ```json
   {
     "ConnectionStrings": {
       "DefaultConnection": "Host=localhost;Port=5432;Database=OganiDb;Username=postgres;Password=your_password"
     }
   }
   ```
2. Gerekli NuGet paketlerini yükleyin:
   - Microsoft.EntityFrameworkCore
   - Npgsql.EntityFrameworkCore.PostgreSQL
   - AutoMapper.Extensions.Microsoft.DependencyInjection
   - Microsoft.ML
3. Migration ve veritabanı güncellemelerini uygulayın:
   - dotnet tool restore
   - dotnet ef migrations add InitialCreate
   - dotnet ef database update
4. Uygulamayı çalıştırın:
   - dotnet run

Not: Kurulum adımları proje yapılandırmanıza göre değişebilir. `Program.cs` ve `Context/AppDbContext.cs` içinde gerekli servis ve context konfigürasyonlarını kontrol edin.

---

## 🔄 Veri Hazırlığı

- Ürün ve müşteri verileri AI destekli olarak üretilmiştir.
- 100.000 sipariş CSV dosyası ETL ile sisteme yüklenmiştir.
- ML.NET modelleri 2025 verileri ile eğitilerek 2026 ilk 3 ay için şehir bazlı tahmin üretir.

---

## 📊 Dashboard ve Analitik

- Müşteri segmentasyonu (Altın/Gümüş/Bronz) pie chart
- Şehir seçimine göre toplam sipariş, ortalama tutar, en popüler kategori
- Heatmap ile yoğunluk haritası (Leaflet)

---

## 🧾 Loglama

- Admin panelindeki her CRUD işlemi Log tablosuna kayıt edilir.
- Son işlemler panelde listelenir.

---

## 📁 Önemli Dizimler ve Dosyalar

- `Context/AppDbContext.cs`: EF Core DbContext ve PostgreSQL konfigürasyonu
- `Controllers/*Controller.cs`: MVC controller’ları
- `Entities/*.cs`: Temel domain entity’leri
- `DTOs/*`: Veri transfer nesneleri
- `Mapping/MappingProfile.cs`: AutoMapper profilleri
- `Services/*`: İş mantığı servisleri
- `Views/*`: Razor view’lar
- `wwwroot/*`: Statik dosyalar

---

## 🔐 Ortam Değişkenleri ve Ayarlar

- `appsettings.json` ve `appsettings.Development.json` içinde:
  - ConnectionStrings
  - Logging
  - RapidAPI anahtarı (güvenlik için gizli tutun ve kullanıcı gizliliğini koruyun)

---

## 🧪 Test ve Doğrulama

- Controller ve service katmanı için birim testleri önerilir.
- Veri migrasyonları sonrası temel CRUD ve tahmin akışını doğrulayın.

---

## 📸 Ekran Görüntüleri

`ss/` ve `ss2/` klasörlerinde örnek ekran görüntüleri mevcuttur.

---

## 📄 Lisans

Bu proje eğitim amaçlıdır. Ticari kullanım öncesi gerekli düzenlemeleri yapınız.

---

## 🙏 Teşekkür

Eğitim sürecindeki katkıları için Murat Yücedağ’a teşekkürler.
