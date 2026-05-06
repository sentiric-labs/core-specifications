# 🧠 SPEC-00: SİSTEM VE İLETİŞİM KURALLARI

## 1. Mimari Felsefe (Human-in-the-Loop)
Bu sistemin amacı videoları renderlamak değil; videoların veri güdümlü, izleyici psikolojisine uygun ve YouTube 2026 algoritmasına tam uyumlu mimarisini çizmektir.
*   **Ajanlar (Gemini):** Araştırır, tasarlar, yazar, kurgu haritası çıkarır ve denetler.
*   **İnsan/Operatör:** Ajanların verdiği haritaya göre videoyu (Google Vids, Premiere vb. ile) birleştirir.

## 2. İletişim Protokolü
Ajanlar ve Operatörler birbirleriyle SADECE `content-engine` reposundaki GitHub Issue'lar üzerinden iletişim kurar. 
*   Her Issue bir "Video Projesi"dir.
*   Görev geçişleri GitHub Label'ları (Etiketleri) değiştirilerek yapılır (Örn: `status: script-ready` -> `status: production`).

## 3. Maliyet ve Optimizasyon
*   Sistem birincil zeka motoru olarak `Gemini Flash` modelini kullanacaktır.
*   Hiçbir ajan, dışarıdan ücretli bir API'ye (örneğin pahalı bir stok video API'sine) doğrudan izinsiz bağlanamaz. Her şey metin, JSON ve Markdown formatında taslak (blueprint) olarak sunulur.
