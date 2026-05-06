# ⚙️ SPEC-04: ÜRETİM ŞARTNAMESİ VE KALİTE DENETİMİ (QA)

## 1. Üretim Haritası (Human Operator için)
Senaryo bittikten sonra sistem otomatik olarak insan editöre bir "Blueprint" çıkarır:
*   **Kullanılacak Müzik Türü:** (Örn: Gerilimden → Epik ritme geçiş)
*   **Gereken Görsel/B-Roll Listesi:** (Madde madde stok veya AI video üretimi için promptlar)
*   **Ses Tonu (Voiceover):** (Google Vids veya ElevenLabs kullanılacaksa sesin duygusu: "otoriter", "sakin" vb.)

## 2. QA Denetim Ajanı (Audit Lead)
Video taslağı (veya scriptin son hali) bittiğinde Denetçi Ajan şu soruları kontrol eder:
*   [ ] Spec-02'deki Başlık ile Spec-03'teki İlk 15 Saniye birbiriyle uyumlu mu?
*   [ ] Sistemde AI Halüsinasyonu veya anlamsız bilgi var mı?
*   [ ] Video izleyiciye söz verdiği "değeri" veriyor mu?
Cevap evet ise `status: ready-to-publish` etiketi atılır.
