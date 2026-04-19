# Kurulum ve GitHub'a Yükleme Rehberi

## 1. Flutter Kurulumu (Eğer yüklü değilse)

### Windows:
1. [Flutter SDK](https://docs.flutter.dev/get-started/install/windows) indirin
2. ZIP dosyasını çıkarın (örn: `C:\src\flutter`)
3. Path'e ekleyin: System Properties > Environment Variables > Path > Edit > New > `C:\src\flutter\bin`
4. Terminalde `flutter doctor` komutunu çalıştırın

### macOS:
```bash
# Homebrew ile
brew install flutter

# Veya manuel kurulum
# https://docs.flutter.dev/get-started/install/macos
```

### Linux:
```bash
# Snap ile
sudo snap install flutter --classic

# Veya manuel kurulum
# https://docs.flutter.dev/get-started/install/linux
```

## 2. Projeyi Çalıştırma

```bash
# Bağımlılıkları yükle
flutter pub get

# Cihazları kontrol et
flutter devices

# Uygulamayı çalıştır
flutter run
```

## 3. Ekran Görüntüleri Alma

1. Uygulamayı çalıştırın
2. Ana sayfada ekran görüntüsü alın → `screenshots/home_page.png` olarak kaydedin
3. Bir ürüne tıklayın, detay sayfasında ekran görüntüsü alın → `screenshots/detail_page.png`
4. "Sepete Ekle" butonuna basın, bildirimi gösterin → `screenshots/cart_notification.png`

## 4. GitHub'a Yükleme

### İlk Kurulum:

```bash
# Git repository başlat
git init

# Dosyaları ekle
git add .

# İlk commit
git commit -m "Initial commit: Mini Katalog Uygulaması"

# GitHub'da yeni repository oluşturun (public)
# Sonra aşağıdaki komutları çalıştırın:

git branch -M main
git remote add origin https://github.com/KULLANICI_ADINIZ/mini-catalog-app.git
git push -u origin main
```

### Ekran Görüntülerini Eklemek:

```bash
# Ekran görüntülerini screenshots klasörüne kopyalayın
# Sonra:

git add screenshots/
git commit -m "Add app screenshots"
git push
```

## 5. Kontrol Listesi

Projeyi teslim etmeden önce kontrol edin:

- [ ] Uygulama çalışıyor mu?
- [ ] Ana sayfa ürünleri gösteriyor mu?
- [ ] Detay sayfasına geçiş yapılabiliyor mu?
- [ ] Sepete ekleme çalışıyor mu?
- [ ] GitHub repository public olarak oluşturuldu mu?
- [ ] README.md dosyası eksiksiz mi?
- [ ] Ekran görüntüleri eklendi mi?
- [ ] Repository linki hazır mı?

## 6. Sorun Giderme

### "flutter: command not found"
- Flutter'ın PATH'e eklendiğinden emin olun
- Terminal'i yeniden başlatın

### "No devices found"
- Android Emulator veya iOS Simulator'ü başlatın
- Veya fiziksel cihazı USB ile bağlayın ve USB debugging açın

### "pub get failed"
- İnternet bağlantınızı kontrol edin
- `flutter clean` sonra `flutter pub get` deneyin

### Görsel yüklenmiyor
- İnternet bağlantınızı kontrol edin
- Mock data'daki URL'lerin geçerli olduğundan emin olun

## 7. İletişim

Sorularınız için:
- Flutter Dokümantasyon: https://docs.flutter.dev
- Flutter Community: https://flutter.dev/community
