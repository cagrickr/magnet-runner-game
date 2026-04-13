Kısa build talimatları (Windows)

1) Sanal ortamınızı etkinleştirin veya aşağıdaki betiği kullanın.

PowerShell (önerilen):

```
.\.venv\Scripts\Activate.ps1
```

cmd.exe veya çift tıklama ile kullanma: doğrudan `build_exe.bat` dosyasını proje kökünde çalıştırın.

2) `build_exe.bat` betiği şu adımları yapar:
- `.venv` içindeki Python ile `pyinstaller` kurar
- `main.py` için tek dosya (`--onefile`) exe üretir
- `assets` klasörünü exe'ye paketler (`--add-data "assets;assets"`)
- Çıktı: `dist\MagnetRunner.exe`

3) Notlar ve sorun giderme:
- Eğer `pyinstaller` önceden yüklüyse, kurulum hızlı geçilir.
- Oyun Pygame kullanıyor; bazı veri/medya dosyaları PyInstaller ile paketlenirken yol sorunları olabilir. Eğer exe çalışmazsa, `--add-data` ile eksik dosyaları ekleyebiliriz.
- `--windowed` kullanıldığı için konsol penceresi gizlenecektir. Hata ayıklamak isterseniz bu bayrağı kaldırın.

4) Build'i şimdi çalıştırmamı isterseniz onay verin; betik `pyinstaller` kuracak ve birkaç dakika sürebilir.
