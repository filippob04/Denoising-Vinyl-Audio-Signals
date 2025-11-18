# 🎵 Progetto FESI - FESI 25-26

💻 Computer Science - UniGe 🇮🇹

Questo progetto si fissa l'obbiettivo di esplorare diversi metodi, in Python, per la riduzione del rumore (de-noising) da registrazioni audio, con un focus specifico sulla rimozione di un rumore elettrico che affligge il mio giradischi.

## 🚀 Funzionalità

- **🎤 Acquisizione e Analisi:** Carica file audio `.wav` ed esegue un'analisi nel dominio tempo-frequenza utilizzando la **Short-Time Fourier Transform (STFT)**.
- **🎶 Profilazione Calibrata:** Implementa un metodo robusto che "impara" il profilo del rumore da una sezione di audio specificata (es. gli ultimi `N` secondi del brano), garantendo una perfetta calibrazione del livello di gain tra il rumore e il segnale (`percentile`).
- **💿 Sogliatura, Sottrazione Spettrale e Filtro di Wiener:** Applica diverse tipologie di filtraggi e confronta i risultati ottenuti.
- **🖼️ Verifica e Output:** Genera plot di confronto (profili spettrali e spettrogrammi) per analizzare visivamente il segnale e l'efficacia della pulizia, salvando l'output come file `.wav` a 24-bit.

## 📦 Dipendenze

Le principali librerie Python utilizzate sono:

- [**Librosa**](https://librosa.org/): Per l'analisi audio, la STFT, e la conversione (es. Mel, dB).
- [**NumPy**](https://numpy.org/): Per il calcolo numerico e la manipolazione delle matrici.
- [**SoundFile**](https://pysoundfile.readthedocs.io/): Per l'esportazione robusta di file audio in formato `.wav` a 24-bit.
- [**Matplotlib**](https://matplotlib.org/): Per la generazione di tutti i grafici e spettrogrammi.
- [**IPython**](https://ipython.org/): Per l'embedding di player audio direttamente nel notebook.
- [**SciPy**](https://scipy.org/): Usato inizialmente per la lettura dei file `.wav`.

## ⚙️ Come Eseguire:

```bash
# 1. Clona il repository (se applicabile)
# git clone ...

# 2. Installa le dipendenze
pip install librosa numpy soundfile matplotlib ipython scipy

# 3. Avvia Jupyter Notebook
jupyter notebook
```

## 🧰 Configurazione

Prima di eseguire il programma, assicurarsi di configurare le costanti principali del notebook:

- `FS = 48000`: Frequenza di campionamento desiderata per tutti i file audio.
- `NOISE_SECTION = 4`: I secondi di rumore puro alla fine del file audio da usare per la calibrazione.
- `N_FFT = 2048`: Dimensione della finestra FFT per la STFT.
- `HL = 512`: Hop length (passo di sovrapposizione) per la STFT.
- `track_wav`: Percorso al file `.wav` di **input** da pulire (es. `../dataSet/nomeBrano.wav`).
- `OUTPUT`: Percorso completo per il file `.wav` di **output** pulito (es. `../dataSet/output.wav`).

## ▶️ Esecuzione

1.  Assicurarsi che tutti i file `.wav` di input si trovino nel percorso specificato (es. `../dataSet/`).
2.  Aprire il file `.ipynb` (es. `project.ipynb`) in Jupyter.
3.  Configurare le costanti come descritto sopra.
4.  Eseguire tutte le celle del notebook in ordine (es. _Kernel > Restart & Run All_).
5.  Il notebook eseguirà l'analisi, la profilazione calibrata, la sottrazione spettrale e la verifica.
6.  Il file audio pulito sarà disponibile nel percorso specificato dalla variabile `OUTPUT`.

### 📄 Note

✉️ [Email](mailto:6393212@studenti.unige.it) <br>
🔗 [Aulaweb](https://2025.aulaweb.unige.it/mod/page/view.php?id=64900)
