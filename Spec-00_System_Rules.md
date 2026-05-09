# 🧠 SPEC-00: SIFIR-İNSAN MİMARİSİ VE SİSTEM KURALLARI

## 1. Mimari Felsefe (Zero-Human Architecture)
Bu sistem, insan müdahalesi olmadan 7/24 çalışan kapalı devre bir medya fabrikasıdır. İnsan sadece sistemi başlatır veya fişini çeker.
*   **Tam Otonomi:** Tüm araştırma, yazım, görsel/video üretimi, seslendirme, kurgu (stitching) ve yayınlama süreçleri kod ve yapay zeka ajanları tarafından yapılır.
*   **Kontrat Bazlı İletişim:** Ajanlar GitHub Issue'larında birbirleriyle Markdown içinde gömülü **Strict JSON** blokları ile haberleşir. Bir ajanın çıktısı, diğer ajanın doğrudan çalıştırılabilir kod girdisidir.

## 2. İletişim ve Veri Akış Protokolü
Sistem `agent-orchestrator` üzerinden şu döngüyle akar:
1.  **Data (Spec-01):** Fikir bulur -> JSON
2.  **Visual (Spec-02):** Ambalajı tasarlar ve kapağı AI ile üretir -> Asset URL
3.  **Script (Spec-03):** Saniye saniye kurgu zaman çizelgesini (Timeline) yazar -> JSON Array
4.  **Production (Spec-04):** Seslendirmeyi (TTS) çeker, süresini hesaplar, AI videoları üretir ve **FFmpeg** ile renderlar -> .MP4 File
5.  **Publish (Spec-06):** Videoyu YouTube API ile yayınlar -> Video URL
6.  **Behavior (Spec-05):** 48 saat sonra istatistikleri çeker, kurumsal hafızaya yazar.

## 3. Sistem Kısıtlamaları
*   Halüsinasyon riskini sıfırlamak için tüm veriler geçmiş hafıza (behavior-engine) süzgecinden geçmelidir.
*   Hiçbir ajan "sanırım", "belki" gibi insansı tereddütler içeren komutlar veremez. Kesinlik ve matematiksel ölçülebilirlik zorunludur.
