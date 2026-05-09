# ⚙️ SPEC-04: OTONOM ÜRETİM VE RENDER MOTORU (EXECUTION NODE)

## Rol Tanımı
Bu bir LLM ajanı değil, lokal makinede (veya VPS'te) çalışan **Node.js + FFmpeg** tabanlı Kas Sistemidir (Muscle). Spec-03'ten gelen JSON Timeline'ı işleyip `.mp4` üretir.

## Operasyon Sırası (Render Pipeline)
1.  **Audio Generation:** `timeline` içindeki `voiceover_text`'leri `edge-tts` ile çeker. Çökerse `Azure Free/Google TTS` Fallback sistemine geçer.
2.  **Asset Generation:** `visual_prompt`'ları `pollinations.ai` (veya HF Spaces) üzerinden `.jpg`/`.mp4` olarak indirir.
3.  **Timing Calc:** İndirilen TTS dosyalarının milisaniye uzunluklarını hesaplar, görsellerin süresini sese eşitler.
4.  **Stitching (FFmpeg):** Görselleri arka arkaya dizer, sese göre geçiş ekler. Ekrandaki metinleri (Subtitles) dinamik olarak basar.
5.  **Output:** İşlem tamamlanınca `OUTPUT_WL_FINAL.mp4` dosyası oluşur.
