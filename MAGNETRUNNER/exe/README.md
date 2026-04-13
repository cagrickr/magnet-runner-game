# Magnet Runner Platform

Pygame ile geliştirilmiş 2D platform oyunu.  
Oyuncu skorları SQLite veritabanında saklanır ve leaderboard sistemi vardır.

## Özellikler

- 2D auto-scroll platform oynanış
- Magnet kutup sistemi (Q/E ile polarite değiştirme)
- Enerji, dash ve long jump mekanikleri
- Checkpoint ve level sistemi
- SQLite veritabanı ile skor ve profil kaydı
- Leaderboard ekranı
- Profil yönetimi (silme, sıfırlama, yeniden adlandırma)

## Çalıştırma

### 1) EXE ile
`MagnetRunner.exe` dosyasını çift tıklamanız yeterlidir.

### 2) Kaynak Kod ile
```bash
pip install -r requirements.txt
python main.py

## Kontroller

**Menü:**
- SPACE: Oyunu başlat
- L: Leaderboard göster
- ESC: Çıkış

**Oynanış:**
- A/D: Hareket et (sol/sağ)
- SPACE: Zıpla
- SHIFT: Magnet aç (enerji gerekli)
- Q: Kutup N (çek)
- E: Kutup S (it)
- ESC: Menüye dön

**Game Over / Win:**
- ENTER: Tekrar oyna
- N: İsim kaydet ve leaderboard
- L: Leaderboard göster
- ESC: Menü

## Oyun Mekanikleri

- **Platform Fiziği:** Yerçekimi, zıplama, yatay hareket
- **Kamera:** Auto-scroll sağa; oyuncu kamerayı geride bırakırsa can/ölüm
- **Magnet:** SHIFT ile aktif, Q/E kutup değişimi, enerji sistemi
- **Objeler:** Metal (skor+enerji), Gold Metal (nadir, yüksek puan), Dangerous Metal (riskli)
- **Checkpoint:** 3 checkpoint'i tamamlayınca level bitmiş say

## Veritabanı

SQLite ile skor kaydı: `data/magnet_runner.db`

### DB Bakım ve Yedekleme

Proje içinde basit bir migration/backup aracı bulunur: `tools/db_migrations.py`.

- `python tools/db_migrations.py init` — DB meta tablosunu oluşturur ve WAL modunu açar.
- `python tools/db_migrations.py backup` — `data/backups/` dizinine zaman damgalı bir yedek oluşturur.
- `python tools/db_migrations.py migrate` — gelecekte eklenecek migration'ları çalıştırır.

Yedekler ve WAL modu, yerel çalıştırma sırasında DB güvenliği ve performansı için önerilir.
