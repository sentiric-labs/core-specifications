# 🏛️ SENTIRIC LABS - MASTER INSTRUCTION (V2.0 ENTERPRISE)

## 1. MİMARİ FELSEFE: HİBRİT VE SIFIR-İNSAN SİSTEM
Bu organizasyon, içerik üretimini "İnsan-Döngülü" (Human-in-the-Loop) modelden çıkarıp, tam otonom "Karanlık Fabrika" (Dark Factory) modeline geçirmiştir. Sistem, sıfır maliyetle çalışacak ve her yeni kanal için klonlanabilir standartta olacaktır.

Sistem 3 temel düzlemden (Plane) oluşur:
1.  **Control Plane (Beyin):** `agent-orchestrator` (GitHub Actions). Gemini LLM API çağrılarını yapar, kararları alır ve GitHub Issue'larını günceller.
2.  **Data Plane (Hafıza):** `content-engine` (İş akışı Kanbanı) ve `behavior-engine` (72+ saatlik gecikmeli YouTube Analitikleri).
3.  **Execution Node (Kas):** `editly` GİBİ HANTAL YAPILAR YASAKTIR. Kurgu, sadece **FFmpeg** komutlarıyla çalışan saf Node.js betikleriyle lokal makinede (veya ücretsiz VPS'te) çalıştırılır.

## 2. KÖTÜYE KULLANIM VE RİSK YÖNETİMİ (FALLBACK PROTOKOLÜ)
Ücretsiz servisler (Freemium/Open Source) doğası gereği kırılgandır. Bu yüzden sistem her modülde bir **Adaptör / Yedekleme** kullanmak ZORUNDADIR:
*   **Ses Üretimi (TTS):** Birincil: `edge-tts`. Başarısız olursa -> İkincil: `Google/Azure Free Tier`.
*   **Görsel Üretimi:** Birincil: `pollinations.ai`. Başarısız olursa -> İkincil: `HuggingFace Inference API`.
*   **Veri Formatlama:** Tüm ajanlar çıktılarını **KATI JSON (Strict JSON)** olarak vermek zorundadır. Markdown içi JSON parse edilemezse, Orkestratör işlemi durdurup Zod ile validasyon hatası fırlatacaktır.

## 3. ZAMANLAMA VE VERİ AKIŞI
*   YouTube algoritmaları veriyi anında vermez. Analitik ajanları (Spec-05), veri çekmek için videonun yayınlanmasının üzerinden **en az 72 saat** geçmesini beklemek zorundadır.
*   Sistem, tek bir kanalın otomasyonunu %100 stabilize edip (örneğin 10 video üst üste hatasız renderlanıp yayınlandığında) diğer kanallara (Multi-Channel) geçiş yapacaktır.
