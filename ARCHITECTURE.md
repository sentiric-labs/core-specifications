# 🏛️ SENTIRIC LABS - SYSTEM ARCHITECTURE & STATE MACHINE

Bu belge, Sentiric Labs otonom içerik fabrikasının ana mimarisini ve çalışma prensiplerini tanımlar. Bu organizasyonda çalışan **her insan ve her yapay zeka ajanı** bu kurallara uymak zorundadır.

## 1. REPO HARİTASI (Single Source of Truth)
*   **`core-specifications`**: Sistemin Anayasasıdır. Ajanların karakterleri (Spec 00-05) buradadır.
*   **`agent-orchestrator`**: Sistemin Kalbidir. `daily-run.yml` ile her sabah uyanır ve `index.ts` ile iş akışını ilerletir.
*   **`content-engine`**: Sistemin Fabrika Bandıdır. Ajanlar birbirleriyle SADECE buradaki Issue'lar üzerinden iletişim kurar.
*   **`behavior-engine`**: Sistemin Hafızasıdır. Geçmiş hatalar (Insight) burada tutulur. Ajanlar yeni bir fikre başlamadan önce burayı okur.
*   **`wiliam-louis-assets`**: Hedef kanalın (şu anki sandbox) medya varlıklarıdır.

## 2. İŞ AKIŞI (The State Machine)
Orkestratör uyanır, `content-engine` içindeki **açık** Issue'ların **Etiketlerine (Label)** bakar ve sıradaki ajanı tetikler. Sistemin asla tek seferde tüm işi bitirmesine izin verilmez; her adım izole edilmiştir.

*   **ADIM 1:** Açık Issue yoksa -> `Data Agent` uyanır, yeni proje açar. Etiket: `status: backlog`
*   **ADIM 2:** Etiket `backlog` ise -> `Visual Agent` uyanır, ambalajı tasarlar. Etiket: `status: visual-ready`
*   **ADIM 3:** Etiket `visual-ready` ise -> `Script Agent` uyanır, senaryoyu yazar. Etiket: `status: production`
*   **ADIM 4:** Etiket `production` ise -> AI BEKLER. İnsan operatör kurguyu yapar ve etiketi elle `status: review` yapar.
*   **ADIM 5:** Etiket `review` ise -> `QA Agent` uyanır, denetler. Onaylarsa Etiket: `status: ready-to-publish`

## 3. ALTIN KURALLAR (Golden Rules)
1.  **Düşünme, Uygula:** Operatör (İnsan) sistemi yönetmez, sadece AI'ın verdiği Blueprint'i uygular (Kurgu yapar).
2.  **Öğrenme Döngüsü (Feedback Loop):** `behavior-engine`'de yazan hiçbir hata, yeni bir videoda tekrarlanamaz.
3.  **Stabilizasyon:** Mevcut tek kanallı yapı (William Louis) kusursuz bir şekilde 10 video döngüsünü tamamlamadan Multi-Channel (Çoklu Kanal) mimarisine geçiş yapılamaz.
