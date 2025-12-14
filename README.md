# 📧 Flusso Automatico: Creazione Cartelle Drive via Email

Un workflow di automazione costruito con **n8n** che trasforma un comando ricevuto via email in un'azione fisica nel tuo Google Drive. Questo flusso permette di creare e rinominare cartelle da remoto, ricevendo una notifica di conferma istantanea su Slack.

## ✨ Caratteristiche & Funzionalità

* **Controllo Remoto:** 📧 Avvia l'azione semplicemente inviando un'email all'account configurato.
* **Estrazione Intelligente:** 🧩 Il nodo "Estrae nome" utilizza una RegEx (espressione regolare) per leggere il testo dell'email e ricavare il nome desiderato per la nuova cartella (cercando la sintassi: `Crea cartella: [Nome Desiderato]`).
* **Notifica Completa:** 🔔 Dopo la creazione, invia un messaggio su Slack che include il nome della cartella e un **link diretto** per aprirla immediatamente su Google Drive.

## 🚀 Struttura del Flusso

Il flusso è composto dai seguenti nodi:

1.  **Gmail Trigger:** ✉️ Avvia il flusso all'arrivo di una nuova email.
2.  **Get a message:** 📥 Recupera il contenuto completo dell'email, necessario per l'analisi.
3.  **Estrae nome (Code):** 🛠️ Nodo cruciale che analizza il corpo del messaggio per estrarre il comando e il nome della cartella.
4.  **Create folder (Google Drive):** 📂 Esegue l'azione, creando la cartella con il nome estratto.
5.  **Send a message (Slack):** 💬 Invia la conferma finale con il link alla cartella.

## 📺 Video di Spiegazione

Per una spiegazione dettagliata del funzionamento, della logica e della configurazione dei nodi, specialmente l'utilizzo della RegEx nel nodo Code, guarda il video qui sotto:

[Spiegazione dettagliata del flusso su YouTube](https://youtu.be/OMxUVSNWkok)

## 🛠️ Requisiti

Per poter utilizzare questo flusso, dovrai configurare le credenziali per i seguenti servizi:

* **Gmail Account** (utilizzato sia come trigger che per recuperare il messaggio).
* **Google Drive Account**
* **Slack Account**
