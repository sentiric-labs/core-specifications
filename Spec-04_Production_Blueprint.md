# ⚙️ SPEC-04: OTONOM ÜRETİM VE RENDER MOTORU (ASSEMBLY AGENT)

## Rol Tanımı
Bu bir LLM ajanı değil, `agent-orchestrator` içindeki **Kod Bazlı Kurgu Motorudur (Node.js + FFmpeg)**. İnsanın yerini alır. Spec-03'ten gelen JSON Timeline verisini işleyerek nihai `.mp4` dosyasını derler.

## Çalışma Akışı (Execution Pipeline)
1.  **Audio Generation (TTS):** Timeline'daki her `voiceover_text` ElevenLabs/Google TTS API'ye gönderilir. Dönen ses dosyasının tam uzunluğu (milisaniye cinsinden) hesaplanır.
2.  **Visual Generation (Video/Image):** Sesin süresine tam uyacak şekilde `visual_prompt` kullanılarak Pollinations/Runway API üzerinden medya üretilir. 
3.  **Subtitles (Altyazı):** Ses dosyası Whisper/AssemblyAI ile taranır veya doğrudan TTS verisinden SRT dosyası oluşturulur (Ekranda dinamik kelime vurgusu için).
4.  **Stitching (FFmpeg):** 
    *   Tüm görsel klipler arka arkaya dizilir.
    *   TTS sesleri ilgili görsellerin altına yerleştirilir.
    *   `global_music_style` promptuyla üretilmiş (veya stoklanmış) arka plan müziği %10 ses seviyesine (ducking) ayarlanarak alta döşenir.
    *   Geçişlerde (glitch/bass drop) SFX sesleri eklenir.
5.  **Output:** `workspace/output/WL_FINAL.mp4` dosyası oluşturulur. QA onayı gerekmez, kod çalıştığı sürece onaylıdır.
