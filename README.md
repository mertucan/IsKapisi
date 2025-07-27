# İş Kapısı - İş Bulma Platformu

İş Kapısı, iş arayanlar ve işverenleri bir araya getiren masaüstü iş bulma platformudur. C# .NET 6.0 Windows Forms teknolojisi ile geliştirilmiş bu uygulama, modern bir kullanıcı arayüzü ve kapsamlı özellikler sunar.

## 📖 Proje Hakkında

Bu proje, **Veri Tabanı ve Yönetim Sistemleri Final Projesi** kapsamında geliştirilmiştir. İşsizlik sorununa çözüm bulmak amacıyla tasarlanan bu iş kapısı uygulaması, veritabanı yönetimi ve sistem tasarımı prensiplerini uygulayan kapsamlı bir platformdur. Platform, iki farklı kullanıcı tipi için optimize edilmiş özellikler sunar:

- **Adaylar**: İş arayan kişiler
- **İşverenler**: İş ilanı veren şirketler ve kişiler

## 🛠️ Teknoloji Stack

- **Framework**: .NET 6.0
- **UI Framework**: Windows Forms
- **Veritabanı**: SQL Server
- **Dil**: C#
- **Hedef Platform**: Windows

## 📋 Özellikler

### 👥 Genel Özellikler
- Kullanıcı kayıt ve giriş sistemi
- İki farklı kullanıcı tipi desteği (Aday/İşveren)
- Güvenli şifre yönetimi
- Kullanıcı profil yönetimi
- Hesap ayarları

### 👨‍💼 Aday Özellikleri
- **Profil Yönetimi**: Kişisel bilgilerin düzenlenmesi
- **Özgeçmiş Oluşturma**: Detaylı CV hazırlama
- **İş Arama**: Mevcut iş ilanlarını görüntüleme
- **Başvuru Takibi**: Yapılan başvuruların durumunu izleme
- **Hesap Ayarları**: Kişisel tercihlerin düzenlenmesi

### 🏢 İşveren Özellikleri
- **Şirket Profili**: İşveren bilgilerinin yönetimi
- **İlan Oluşturma**: Yeni iş ilanları yayınlama
- **İlan Yönetimi**: Mevcut ilanların düzenlenmesi
- **Başvuru Değerlendirme**: Gelen başvuruları inceleme
- **Yayınlanan İlanlar**: Aktif ilanların listesi

## 🏗️ Proje Yapısı

### Ana Dosyalar
```
IsKapisi_Odev/
├── Program.cs                 # Ana giriş noktası
├── IsKapisi_Odev.csproj      # Proje konfigürasyonu
├── Properties/               # Proje kaynakları
│   ├── Resources.Designer.cs
│   └── Resources.resx
```

### Formlar
```
├── FrmGiris.cs               # Ana giriş ekranı
├── FrmKayit.cs               # Kullanıcı kayıt ekranı
├── FrmAday.cs                # Aday ana paneli
├── FrmIsveren.cs             # İşveren ana paneli
├── FrmAdayProfil.cs          # Aday profil yönetimi
├── FrmIsverenProfil.cs       # İşveren profil yönetimi
├── FrmOzgecmis.cs            # Özgeçmiş oluşturma
├── FrmIlan.cs                # İş ilanı oluşturma
├── FrmBasvurularim.cs        # Başvuru takibi
├── FrmGelenBasvuru.cs        # Gelen başvurular (İşveren)
├── FrmIlanlarim.cs           # İşveren ilanları
├── FrmYayinlanan.cs          # Yayınlanan ilanlar
├── FrmAdayAyarlar.cs         # Aday hesap ayarları
└── FrmIsverenAyarlar.cs      # İşveren hesap ayarları
```

## 🔧 Kurulum

### Gereksinimler
- Windows 10/11
- .NET 6.0 Runtime
- SQL Server (LocalDB destekli)
- Visual Studio 2022 (geliştirme için)

### Kurulum Adımları

1. **Projeyi klonlayın:**
   ```bash
   git clone [repository-url]
   cd IsKapisi_Odev
   ```

2. **Veritabanını hazırlayın:**
   - SQL Server'da `IsKapisi` adında bir veritabanı oluşturun
   - Gerekli tabloları oluşturun:
     - `Aday` tablosu (AdayID, Isim, Soyad, Email, Sifre, Yas, Telefon)
     - `Isveren` tablosu (IsverenID, Ad, Soyad, Email, Sifre, Yas, Telefon)
     - `Ilan` tablosu (IlanID, IsverenID, Gereksinimler)

3. **Bağlantı dizisini güncelleyin:**
   - `FrmGiris.cs` ve `FrmKayit.cs` gibi dosyalardaki bağlantı dizisini kendi SQL Server ayarlarınıza göre düzenleyin

4. **Projeyi derleyin ve çalıştırın:**
   ```bash
   dotnet build
   dotnet run
   ```

## 📷 Uygulama Görselleri

### Giriş Ekranı
Uygulama, modern ve kullanıcı dostu bir giriş ekranı ile başlar. Bu ekranda:
- **İş Kapısı** logosu ve "Geleceğe Açılan Kapınız" sloganı
- E-posta ve şifre girişi alanları
- Kullanıcı tipi seçimi (Aday/İşveren)
- Şifre görünürlük toggle özelliği
- Kayıt olmak için geçiş butonu

<img width="697" height="969" alt="Ekran görüntüsü 2025-07-27 210300" src="https://github.com/user-attachments/assets/9e953958-273c-4529-b123-da2c749ab008" />

### Aday Ana Ekranı
Aday girişi yaptıktan sonra karşılaşılan ana panel şunları içerir:
- **Sol Navigasyon Menüsü**:
  - Profilim
  - Özgeçmiş
  - İş İlanları
  - Başvurularım
  - Ayarlar
  - Girişe Dön
- **Ana İçerik Alanı**: Seçilen menü öğesine göre ilgili formların açıldığı dinamik panel

<img width="1710" height="670" alt="Ekran görüntüsü 2025-07-27 210509" src="https://github.com/user-attachments/assets/2eea12ef-7f4d-4014-9157-4c3cd623dd88" />

### Panel Yapısı
Proje, modern bir panel sistemi kullanır:
- Ana formlar içerisinde `Panel` kontrolları kullanılır
- Her menü seçiminde ilgili alt form (`TopLevel = false`) ana panelin içerisinde açılır
- Bu yaklaşım sayesinde tek pencere içerisinde çoklu sayfa deneyimi sağlanır
- Her form `BringToFront()` ve `Show()` metodları ile dinamik olarak yüklenir

## 🎯 Kullanım

### İlk Kullanım
1. Uygulamayı başlatın
2. "Kayıt Ol" sekmesinden hesap oluşturun
3. Kullanıcı tipinizi seçin (Aday/İşveren)
4. Gerekli bilgileri doldurun
5. Giriş yaparak platform özelliklerini kullanmaya başlayın

### Aday Kullanımı
1. Profil bilgilerinizi tamamlayın
2. Özgeçmişinizi oluşturun
3. İş ilanlarını inceleyin
4. İlgilendiğiniz pozisyonlara başvurun
5. Başvuru durumlarınızı takip edin

### İşveren Kullanımı
1. Şirket profilinizi oluşturun
2. İş ilanı yayınlayın
3. Gelen başvuruları değerlendirin
4. İlanlarınızı yönetin

## 🔒 Güvenlik

- Şifreler güvenli şekilde saklanır
- SQL enjeksiyon koruması (parameterized queries)
- Kullanıcı kimlik doğrulama sistemi
- Rol tabanlı erişim kontrolü

## 📄 Lisans

Bu proje eğitim amaçlı geliştirilmiştir.

## 📞 İletişim

Proje ile ilgili sorularınız için issue açabilir veya doğrudan iletişime geçebilirsiniz.

