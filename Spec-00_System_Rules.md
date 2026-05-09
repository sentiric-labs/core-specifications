# 🧠 SPEC-00: SIFIR-İNSAN VE İLETİŞİM PROTOKOLÜ

## 1. İletişim Standartları
Ajanlar (Spec-01'den Spec-06'ya kadar) birbirleriyle SADECE `content-engine` reposundaki Issue yorumları üzerinden iletişim kurar. 
Serbest metin (Free text) yasaktır. Ajanların çıktıları, bir sonraki ajanın çalıştırılabilir kod girdisi olacağı için sadece **JSON** formatında olmak zorundadır.

## 2. JSON Kontratları (Strict Contracts)
*   Sistemin `agent-orchestrator` tarafı, Gemini modeline `response_mime_type: "application/json"` parametresi göndererek halüsinasyonları önleyecektir.
*   Hiçbir ajan "sanırım", "belki" diyemez. Süreler milisaniye (ms), metinler kesin, görsel promptlar sadece İngilizce olacaktır.
