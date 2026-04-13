# README - Magnet Runner Sound Pack

Bu klasördeki sesler oyunun temel aksiyonları için kullanılmak üzere yerleştirilmiştir.

- jump.wav: Zıplama sesi
- magnet_on.wav: Mıknatıs duvara yapışma/aktifleşme sesi (elektrik/zzzz)
- magnet_off.wav: Mıknatıs bırakma sesi
- collect_good.wav: Olumlu parça toplama/puan artışı
- collect_bad.wav: Olumsuz parça çarpma/puan kaybı
- death.wav: Ölüm/yanma sesi
- menu_select.wav: Menüde seçim sesi
- shop_buy.wav: Mağazada satın alma sesi

Tüm sesler Creative Commons veya özgün olarak üretilmiş örneklerdir. Kendi seslerinizi bu dosyaların yerine koyabilirsiniz.

Kullanım için:
- `pygame.mixer.Sound('assets/sounds/jump.wav').play()`
- Veya ilgili event fonksiyonlarında doğrudan çağırabilirsiniz.
