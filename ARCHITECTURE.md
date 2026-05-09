# 🏛️ SENTIRIC LABS - SİSTEM MİMARİSİ VE DURUM MAKİNESİ (V2.0 ZERO-HUMAN)

Bu belge, Sentiric Labs Otonom İçerik Fabrikasının temel mimarisini tanımlar. Bu sistemde İNSAN YOKTUR (Zero-Human Architecture). İnsan sadece sistemi başlatır veya durdurur.

## 1. REPO HARİTASI VE MİMARİ DÜZLEMLER (The 3 Planes)
Sistem birbirinden izole edilmiş, ancak sıkı JSON kontratlarıyla haberleşen 3 düzlemden oluşur:

*   **1. KONTROL DÜZLEMİ (Control Plane - The Brain):**
    *   `core-specifications`: Sistemin anayasası ve Ajan promptları.
    *   `agent-orchestrator`: Sistemi GitHub Actions üzerinden her gün uyandıran Node.js/TypeScript tabanlı Orkestratör. (Sadece API istekleri yapar, ağır işlem yapmaz).

*   **2. VERİ DÜZLEMİ (Data Plane - The Memory):**
    *   `content-engine`: Ajanların Kanban panosu. İletişim SADECE bu repodaki GitHub Issue'ları üzerinden, Strict JSON formatında gerçekleşir.
    *   `behavior-engine`: 72 saatlik YouTube Analitik gecikmesiyle (Lag) çalışan, sistemin kurumsal hafızası ve hata kayıt (Insight) merkezi.

*   **3. ÇALIŞTIRMA DÜĞÜMÜ (Execution Node - The Muscle):**
    *   Lokal Makine veya Ücretsiz VPS üzerinde çalışan, Orkestratörden aldığı JSON'u okuyup `FFmpeg`, `edge-tts` ve `pollinations.ai` kullanarak MP4 video renderlayan fiziksel/sanal motor.

## 2. İŞ AKIŞI (The Autonomous State Machine)
İşlem sırası asenkron çalışır ve etiketler (Labels) üzerinden ilerler:
*   **Aşama 1 (Data):** Fikir, kitle analizi ve "Pattern Interrupt" kuralları belirlenir. -> JSON
*   **Aşama 2 (Visual):** Başlık ve AI görsel promptları üretilir. -> JSON
*   **Aşama 3 (Script):** Senaryo saniyelik zaman çizelgelerine (Timeline) bölünür. Her sahnenin promptu ve metni yazılır. -> JSON Array
*   **Aşama 4 (Production/Assembly):** Execution Node devreye girer. Sesleri sentezler, resimleri çeker, FFmpeg ile birleştirir. İnsan kurgucu yoktur. -> .MP4
*   **Aşama 5 (Publishing):** Video YouTube API ile kanala yüklenir. Döngü kapanır.
*   **Aşama 6 (Behavior):** 72 saat sonra sistem kendi videosunu denetler ve Data (Aşama 1) ajanı için yeni kurallar belirler.

## 3. ALTIN KURALLAR VE RİSK YÖNETİMİ
1.  **JSON Katılığı:** Markdown içindeki serbest metinler asla koda dökülmez. Tüm ajan iletişimleri JSON formatında valide edilir (Zod/Regex).
2.  **Fallback (Yedekleme) Prensibi:** `edge-tts` çökerse Google/Azure TTS'e geçilir. `pollinations` çökerse HF Spaces'e geçilir. Sistem durmaz.
3.  **Optimizasyon:** GitHub Actions içinde ASLA video renderlanmaz (Hesap ban riski). Sadece hafif API çağrıları yapılır.
