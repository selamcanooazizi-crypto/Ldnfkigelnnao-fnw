# ZegaAİ — Aşama 1

Kotlin + Jetpack Compose ile yazılmış Android Studio projesi.

## Derleme (APK üretme)

1. Android Studio (Ladybug veya yeni) ile `ZegaAI` klasörünü açın. Gradle senkronizasyonunu bekleyin
   (Android SDK 35 ve internet gerekir; Android Studio eksik SDK'yı kendisi indirmeyi önerir).
2. Telefonu USB ile bağlayıp **Run** deyin; ya da menüden
   **Build > Build Bundle(s) / APK(s) > Build APK(s)** seçin.
3. APK şurada oluşur: `app/build/outputs/apk/debug/app-debug.apk`

> Not: Bu projede `gradlew` yoktur. Android Studio kendi Gradle'ını kullanır. Komut satırı için proje
> klasöründe bir kez `gradle wrapper --gradle-version 8.9` çalıştırın.

## Bu sürümde GERÇEKTEN çalışması hedeflenenler

- Sohbet arayüzü (mesaj alanı, gönder/durdur, yeni sohbet, kenar çubuğunda sohbet geçmişi)
- Sohbet geçmişinin cihazda kalıcı saklanması (JSON dosyası), silme, tümünü silme
- Varsayılan tam siyah tema + Koyu gri, Koyu mavi, Mor, Yeşil, Beyaz, Özel renk
- Varsayılan Türkçe; Türkçe, İngilizce, Almanca, Rusça, Fransızca, İspanyolca, Arapça (RTL), İtalyanca, Portekizce
- ZegaAİ logosu ve uygulama simgesi (vektör, uyarlanabilir)
- Ayarlar: dil, tema, model yönetimi (cihaz RAM/depolama bilgisi), geçmiş, depolama, ses, hakkında
- Modüler yapay zekâ altyapısı: `ai/AiEngine.kt` arayüzü + `EngineRegistry`

## Bu sürümde YOK (henüz entegre edilmedi)

- Yapay zekâ modeli: şu an `NoModelEngine` var; cevap üretmez ve bunu açıkça söyler.
  GGUF / llama.cpp (NDK + JNI), model indirme/seçme/silme sonraki aşamadır.
- Bulut model, internet araması, dosya/fotoğraf/video/APK/ZIP/JAR yükleme ve inceleme
- Görsel/video oluşturma ve düzenleme, sesli sohbet, konuşma↔yazı
- Oyun ve Minecraft mod yardımcı modları (bunlar model + sistem istemi + dosya incelemeye bağlıdır)

## Önemli

Bu proje, Android SDK bulunmayan bir ortamda yazıldı: **hiç derlenmedi ve cihazda denenmedi.**
İlk derlemede küçük hatalar çıkabilir; hata mesajını paylaşırsanız düzeltilir.

## Bilgisayarsız / bulutta derleme (GitHub Actions)

1. github.com'da ücretsiz hesap açın, yeni bir depo (repository) oluşturun.
2. Bu klasörün içeriğini depoya yükleyin (Add file > Upload files). `.github/workflows/build.yml` dosyasının da yüklendiğinden emin olun.
3. Depoda **Actions** sekmesine girin, **Build APK** iş akışının bitmesini bekleyin (birkaç dakika).
4. Biten çalıştırmayı açın, sayfanın altındaki **Artifacts** bölümünden **ZegaAI-debug-apk** dosyasını indirin (ZIP içinde app-debug.apk).
