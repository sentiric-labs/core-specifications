# 🧠 Sentiric Labs: AI-Native Media Operating System

Bu organizasyon, LLM (Gemini) ajanları tarafından yönetilen, kendi kendini tetikleyen ve yöneten otonom bir medya fabrikasıdır.

## 🏗️ Sistem Mimarisi (Repositories)
1. **`core-specifications`**: Ajanların anayasası (System Prompts). (Şu an buradasınız).
2. **`content-engine`**: Ajanların haberleştiği, araştırma sonuçlarını ve senaryoları Issue'lar halinde paylaştığı Kanban / İşletim merkezi.
3. **`agent-orchestrator`**: Sistemi her gün çalıştıran Node.js/TypeScript kodlarının ve GitHub Actions tetikleyicilerinin bulunduğu ana beyin.
4. **`behavior-engine`**: İzleyici davranışlarının loglandığı repo.
5. **`wiliam-louis-assets`**: Hedef kanalın medya deposu.

## 🗺️ Master Yol Haritası (Nerede Kaldık?)
- [x] **FAZ 1:** GitHub Org ve Repoların açılması, AGPL-3.0 lisanslanması.
- [x] **FAZ 2:** Sistem Anayasasının (Spec-00 - Spec-04) yazılması.
- [ ] **FAZ 3:** `agent-orchestrator` Node.js altyapısının kurulması (package.json, TypeScript).
- [ ] **FAZ 4:** GitHub (Octokit) ve Google AI Studio (Gemini) API bağlantılarının kodlanması.
- [ ] **FAZ 5:** Ajanların ilk kez uyanıp `@Wiliam-Louis` kanalı için Niche (Niş) ve hedef kitle stratejisi üretmesi (Issue olarak).
- [ ] **FAZ 6:** GitHub Actions ile günlük (Cron Job) otomasyon döngüsünün başlatılması.
