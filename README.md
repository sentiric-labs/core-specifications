# 🧠 Sentiric Labs: AI-Native Media Operating System

Bu organizasyon, LLM (Gemini) ajanları tarafından yönetilen, kendi kendini tetikleyen ve yöneten otonom bir medya fabrikasıdır.

## 🏗️ Sistem Mimarisi (Repositories)
1. **`core-specifications`**: Ajanların anayasası (System Prompts). 
2. **`content-engine`**: Ajanların haberleştiği, araştırma sonuçlarını ve senaryoları Issue'lar halinde paylaştığı Kanban / İşletim merkezi.
3. **`agent-orchestrator`**: Sistemi her gün çalıştıran Node.js/TypeScript kodlarının ve GitHub Actions tetikleyicilerinin bulunduğu ana beyin.
4. **`behavior-engine`**: İzleyici davranışlarının loglandığı repo. (Gelecek Faz)
5. **`wiliam-louis-assets`**: Hedef kanalın medya deposu.

## 🗺️ Master Yol Haritası ve Durum
- [x] **FAZ 1:** GitHub Org ve Repoların açılması.
- [x] **FAZ 2:** Sistem Anayasasının (Spec-00 - Spec-04) yazılması.
- [x] **FAZ 3:** `agent-orchestrator` Node.js altyapısının kurulması.
- [x] **FAZ 4:** GitHub ve Google AI Studio (Gemini 3 Flash) API bağlantılarının kodlanması.
- [x] **FAZ 5:** Ajanların ilk kez uyanıp `@Wiliam-Louis` kanalı için Niche ve ilk video stratejisini üretmesi.
- [x] **FAZ 6:** GitHub Actions ile otonom döngünün (Fabrika Bandı) başlatılması.
- [x] **FAZ 7:** Multi-Agent State Machine mimarisinin (Ajanların birbirine etiketler ile görev devretmesi) tamamlanması ve ilk "ONAYLANDI" QA testinin geçilmesi! 🎉

## 🔮 GELECEK VİZYONU (Bir Sonraki Geliştirme Oturumu İçin Notlar)
Sistem başarıyla kuruldu ve insan döngüsü (Human-in-the-Loop) kanıtlandı. Sistemin gelecekteki modülleri şunlar olacaktır:
1. **Behavioral Feedback (Geri Besleme Modülü):** YouTube API bağlanacak. Yayınlanan videonun 48 saatlik Retention (Elde tutma) ve CTR (Tıklanma) verileri çekilecek. Gemini, bu verilere bakarak Spec-01'deki stratejisini otomatik güncelleyecek.
2. **Repurposing (Yeniden Paketleme):** Onaylanan uzun videolar, otomatik olarak Shorts/Reels/TikTok formatlarına bölünecek yeni bir ajan (Spec-05) devreye alınacak.
