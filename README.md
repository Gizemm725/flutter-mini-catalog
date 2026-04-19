# Mini Katalog Uygulaması

Flutter ile geliştirilmiş modern bir ürün katalog uygulaması. Kullanıcılar ürünleri görüntüleyebilir, detaylarını inceleyebilir ve sepete ekleyebilir.

## 📱 Özellikler

- ✅ Ürün listesi (GridView ile kart tabanlı tasarım)
- ✅ Ürün detay sayfası
- ✅ Navigator ile sayfa geçişleri
- ✅ Route Arguments ile veri aktarımı
- ✅ Sepet simülasyonu (state yönetimi)
- ✅ Hero animasyonları
- ✅ Pull-to-refresh özelliği
- ✅ Responsive tasarım

## 🛠️ Kullanılan Teknolojiler

- **Flutter SDK**: 3.0.0 veya üzeri
- **Dart**: 3.0.0 veya üzeri
- **Material Design 3**
- Harici paket kullanılmamıştır (sadece Flutter SDK)

## 📦 Kurulum

### Gereksinimler

- Flutter SDK yüklü olmalı ([Flutter Kurulum Rehberi](https://docs.flutter.dev/get-started/install))
- Android Studio veya VS Code
- Android Emulator veya iOS Simulator (ya da fiziksel cihaz)

### Adımlar

1. Projeyi klonlayın:
```bash
git clone <repository-url>
cd mini_catalog_app
```

2. Bağımlılıkları yükleyin:
```bash
flutter pub get
```

3. Uygulamayı çalıştırın:
```bash
flutter run
```

## 📂 Proje Yapısı

```
lib/
├── main.dart                 # Uygulama giriş noktası
├── models/
│   └── product.dart         # Product ve Rating model sınıfları
├── services/
│   └── api_service.dart     # API servisi (mock data)
├── screens/
│   ├── home_page.dart       # Ana sayfa (ürün listesi)
│   └── product_detail_page.dart  # Ürün detay sayfası
└── widgets/
    └── product_card.dart    # Ürün kartı widget'ı
```

## 🎯 Özellik Detayları

### 1. Veri Modeli
- `Product` sınıfı: id, title, price, description, category, image, rating
- `Rating` sınıfı: rate, count
- `fromJson` ve `toJson` metodları ile JSON dönüşümü

### 2. Ana Sayfa (HomePage)
- GridView ile 2 sütunlu ürün listesi
- Her ürün Card widget'ı içinde gösterilir
- Sepet ikonu ve ürün sayacı
- Pull-to-refresh özelliği
- Loading state yönetimi

### 3. Detay Sayfası (ProductDetailPage)
- Ürün görseli (Hero animasyonu ile)
- Ürün başlığı, kategorisi, fiyatı
- Yıldız puanı ve değerlendirme sayısı
- Detaylı açıklama
- "Sepete Ekle" butonu
- State güncellemesi ile sepet simülasyonu

### 4. Navigasyon
- `Navigator.push` ile sayfa geçişi
- Route Arguments ile Product nesnesi aktarımı
- Geri dönüş değeri ile sepet durumu güncelleme

## 📸 Ekran Görüntüleri

### Ana Sayfa
![Ana Sayfa](screenshots/home_page.png)

*GridView ile ürün listesi, her ürün kart içinde gösterilir. Sağ üstte sepet ikonu ve ürün sayacı bulunur.*

### Ürün Detay Sayfası
![Detay Sayfası](screenshots/detail_page.png)

*Ürün görseli, başlık, kategori, fiyat, yıldız puanı ve detaylı açıklama. Alt kısımda "Sepete Ekle" butonu.*

### Sepet Bildirimi
![Sepet Bildirimi](screenshots/cart_notification.png)

*Ürün sepete eklendiğinde gösterilen SnackBar bildirimi.*

> **Not:** Ekran görüntülerini almak için uygulamayı çalıştırın ve `screenshots` klasörüne ekleyin. Detaylı talimatlar için `screenshots/README.md` dosyasına bakın.

## 🚀 Kullanım

1. Uygulama açıldığında ana sayfada ürün listesi görüntülenir
2. Bir ürüne tıklayarak detay sayfasına gidin
3. Detay sayfasında "Sepete Ekle" butonuna basın
4. Ana sayfaya döndüğünüzde sepet sayacının arttığını göreceksiniz
5. Sepet ikonuna tıklayarak sepetteki ürün sayısını görebilirsiniz

## 🔄 API Entegrasyonu

Proje şu anda mock data kullanmaktadır. Gerçek API entegrasyonu için:

1. `pubspec.yaml` dosyasına `http` paketini ekleyin
2. `lib/services/api_service.dart` dosyasındaki `fetchProducts` metodunu güncelleyin:

```dart
import 'package:http/http.dart' as http;

static Future<List<Product>> fetchProducts() async {
  final response = await http.get(
    Uri.parse('https://fakestoreapi.com/products'),
  );
  
  if (response.statusCode == 200) {
    final List<dynamic> jsonList = json.decode(response.body);
    return jsonList.map((json) => Product.fromJson(json)).toList();
  } else {
    throw Exception('Failed to load products');
  }
}
```

## 📝 Notlar

- Proje harici paket kullanmadan geliştirilmiştir
- Mock data Fake Store API formatındadır
- Material Design 3 kullanılmıştır
- Responsive tasarım için GridView kullanılmıştır
- State yönetimi StatefulWidget ile yapılmıştır

## 👨‍💻 Geliştirici

Bu proje Flutter eğitimi kapsamında geliştirilmiştir.

## 📄 Lisans

Bu proje eğitim amaçlıdır ve serbestçe kullanılabilir.
