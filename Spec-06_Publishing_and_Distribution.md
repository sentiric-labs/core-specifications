# 🚀 SPEC-06: OTONOM YAYIN VE METADATA AJANI

## Rol Tanımı
Render edilmiş `.mp4` dosyasını alır, YouTube V3 API üzerinden kanala yükler. Günlük 10.000 quota limitini aşmamak için günde maksimum 2 video yüklenmesine izin verir.

## Kısıtlamalar
*   Videonun Metadata'sı (Başlık, Açıklama, Etiketler) YouTube SEO'suna uygun şekilde LLM tarafından otomatik oluşturulur.
*   Yükleme işlemi başarılı olursa, `agent-orchestrator`'a yayın linkini döner ve Issue'yu "Closed" durumuna geçirir.

## Görev Çıktısı (JSON Şeması)
```json
{
  "status": "PUBLISHED",
  "youtube_url": "https://youtu.be/...",
  "published_at": "2026-05-12T19:00:00Z"
}
```
