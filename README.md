# ESP32 Voice Assistant per Home Assistant  
**Episodio 1 – Architettura, Wake Word e Continuous Mode**

Questo progetto mostra come realizzare un **Voice Assistant personalizzato**
basato su **ESP32** e completamente integrato con **Home Assistant**.

In questo primo episodio non ci concentriamo su effetti avanzati o circuiti complessi,
ma sulle **fondamenta**:  
come funziona davvero un assistente vocale,  
come gestire la wake word,  
e come rendere l’interazione naturale grazie alla modalità di ascolto continuo.

---

## 🎯 Obiettivi del progetto
- Creare un voice assistant **locale**, senza cloud di terze parti
- Utilizzare **wake word** per attivare l’ascolto solo quando serve
- Supportare la **modalità continuous** (più comandi senza ripetere la wake word)
- Fornire un **feedback visivo chiaro** tramite LED
- Integrare anche la funzione di **media player**
- Mantenere il progetto **open-source e personalizzabile**

---

## 🧠 Come funziona (in breve)

1. **Standby**
   - Il dispositivo ascolta solo la wake word
   - I LED mostrano un’animazione discreta

2. **Wake word rilevata**
   - Il voice assistant si attiva
   - La wake word viene disabilitata temporaneamente
   - I LED indicano lo stato di ascolto

3. **Modalità Continuous**
   - È possibile fare più richieste consecutive
   - Nessuna ripetizione della wake word

4. **Thinking / Speaking**
   - I LED mostrano chiaramente quando il sistema:
     - ascolta
     - elabora
     - risponde

5. **Uscita**
   - Con la frase **“modalità silenziosa”**
   - Il sistema torna in standby
   - La wake word viene riattivata

---

## 🔊 Audio: I2S, Microfono e Speaker

Il progetto utilizza un **bus I2S condiviso** per:

- **INMP441** – microfono digitale I2S
- **MAX98357A** – amplificatore I2S per speaker

Un **mixer audio** permette di:
- riprodurre musica
- gestire annunci e TTS
- evitare conflitti tra media player e voice assistant

---

## 💡 Feedback visivo con LED

Un anello LED WS2812 mostra lo stato del sistema:

| Stato        | Effetto LED                          |
|-------------|--------------------------------------|
| Standby     | Due LED arancioni che ruotano         |
| Listening   | LED verde su sfondo blu               |
| Thinking    | LED rosso su sfondo blu               |
| Speaking    | LED giallo su sfondo rosso            |
| Error       | LED rosso su sfondo scuro             |

I LED non sono decorativi:  
sono parte integrante dell’interazione.

---

## 🧩 Funzionalità incluse (Episodio 1)

- Wake word locale
- Voice Assistant in modalità continuous
- Media player integrato
- Mixer audio
- LED di stato
- Gestione sessione e uscita controllata

❌ **Non incluso in questo episodio**
- VU meter / RMS
- ADC audio
- Effetti LED reattivi alla musica

Queste parti verranno affrontate in episodi successivi.

---

## 🛠️ Hardware utilizzato

- ESP32-S3 DevKit
- Microfono INMP441 (I2S)
- Amplificatore MAX98357A (I2S)
- Speaker 4–8 Ω
- Anello LED WS2812 (16 LED)

---

## 📁 Struttura del progetto

