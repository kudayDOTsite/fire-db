# Finansal Özgürlük Ses Kütüphanesi

Finansal özgürlükle alakalı kapsamlı bir Türkçe kaynak ve içerikler üretmek için oluşturulmuş public bir veritabanı.

## 🛠️ Know-How: Ses Dosyası Optimizasyonu

### M4A → Opus Dönüştürme (32k - Önerilen)

Ses dosyalarını %87 boyut tasarrufu ile optimize etmek için:

```bash
# FFmpeg kurulumu
brew install ffmpeg

# Tek dosya dönüştürme
ffmpeg -i input.m4a -c:a libopus -b:a 32k output.opus

# Toplu dönüştürme
for file in *.m4a; do
    ffmpeg -i "$file" -c:a libopus -b:a 32k "${file%.m4a}.opus"
done
```

**Örnek kullanım:**
```bash
# 1.m4a dosyasını 1.opus olarak dönüştür
ffmpeg -i sesler/mmm/1.m4a -c:a libopus -b:a 32k sesler/mmm/1.opus
```

**Sonuç:** 39MB → 5.1MB (%87 tasarruf)
