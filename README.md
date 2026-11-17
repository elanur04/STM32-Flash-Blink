# STM32 · Zamanlayıcı ve Flash ile LED Kontrolü

STM32F103C8T6 üzerinde TIM2 kesmeleri, GPIO buton girişi ve dahili flash bellekte kalıcı ayar saklama uygulaması.

## Davranış

- LED yanıp sönme sayısı flash bellekten okunur; geçerli aralık 4–7'dir.
- Başlangıçta buton 3 saniye basılı tutulduğunda varsayılan 4 değerine dönülür.
- Yanıp sönme ve bekleme akışı TIM2 üzerinden yönetilir.

## İnceleme ve derleme

Uygulama mantığı `Core/Src/main.c`, pin/zamanlayıcı ayarları `Odev3.ioc`, flash yerleşimi `STM32F103C8TX_FLASH.ld` dosyasındadır. STM32CubeIDE ile projeyi açın; uygun ARM araç zinciri ve ST-Link bağlantısı gerekir. Pin bağlantılarını kod ve `.ioc` yapılandırmasına göre kontrol edin.

## Geliştirme notları

Kalıcı ayar adresi `0x0800FC00` olarak tanımlıdır. Kod büyüdükçe uygulama bölümünün bu sayfaya taşmadığı linker haritasından doğrulanmalıdır. Flash silme/yazma dönüş değerlerinin ele alınması ve donanım üzerinde yeniden başlatma testleri sonraki iyileştirme alanlarıdır.
