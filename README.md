[README.md](https://github.com/user-attachments/files/33674661/README.md)
<div align="center">

# BG-FILES

### I tuoi archivi, senza complicazioni.

Apri, esplora ed estrai i tuoi archivi su Windows.<br>
Consulta i rapporti VirusTotal dei file che scegli prima di procedere all’estrazione.

**Windows · Italiano / English / Español · Gratuito · Donazioni facoltative**

[Come iniziare](#come-iniziare) · [VirusTotal](#integrazione-con-virustotal) · [Domande frequenti](#domande-frequenti) · [Sostieni il progetto](#sostieni-il-progetto)

</div>

---

## Cos’è BG-FILES

BG-FILES è un’applicazione per Windows pensata per rendere semplice il passaggio da un archivio compresso ai suoi contenuti. Un’interfaccia essenziale permette di scegliere un file, esplorarlo, impostare la destinazione ed estrarlo in pochi passaggi.

Il motore di estrazione **7-Zip è incluso**: non serve installare separatamente 7-Zip. Il controllo facoltativo con **VirusTotal** aggiunge la possibilità di consultare rapporti già esistenti sui file contenuti nell’archivio.

## Funzionalità

| Funzione | Cosa permette di fare |
|---|---|
| **Esplora prima di estrarre** | Consulta l’elenco dei contenuti dell’archivio. |
| **Estrazione locale** | Scegli la cartella di destinazione e accedi al risultato con **Apri cartella**. |
| **Menu rapido di Windows** | Usa **Apri con BG-FILES**, **Estrai qui** o **Analizza con VirusTotal** da Esplora file. |
| **Controllo VirusTotal facoltativo** | Seleziona i file, consulta i risultati disponibili e decidi se continuare. |
| **Chiave API personale** | Collega o modifica la tua chiave dalle impostazioni. |
| **Tre lingue** | Installer e applicazione disponibili in italiano, inglese e spagnolo. |
| **Associazione ZIP** | Accedi alla scelta dell’app predefinita attraverso le impostazioni di Windows. |

Fra i formati riconosciuti figurano **ZIP, RAR, 7Z, TAR, GZ, BZ2 e XZ**, oltre ad altre estensioni gestite dal motore incluso. Il supporto dipende anche dalle caratteristiche del singolo archivio; la versione 2.12 non gestisce l’inserimento di password per archivi cifrati.

## Stato della versione 2.12

La versione documentata è **BG-FILES 2.12**. I test funzionali eseguiti coprono estrazione, gestione degli errori e interfacce nelle tre lingue; l’integrazione VirusTotal è stata verificata anche con risposte simulate.

> [!IMPORTANT]
> È stato riscontrato un blocco del disinstallatore su un sistema con **Smart App Control** attivo. Applicazione, installer e disinstallatore della 2.12 non sono firmati digitalmente. Questa versione presenta quindi un problema noto di distribuzione su Windows e non va considerata verificata su tutte le configurazioni.

I test automatici non certificano ogni formato, ogni versione di Windows o la disponibilità del servizio VirusTotal. Ulteriori dettagli sono nella sezione [Limiti e problemi noti](#limiti-e-problemi-noti).

## Requisiti

- **Windows con supporto alle applicazioni x64.** L’installer attuale non è destinato a Windows a 32 bit; la compatibilità ARM64 non è stata verificata.
- **.NET Framework 4.5 o successivo.**
- Permessi di amministratore per l’installazione standard.
- Spazio libero sufficiente per i file estratti e gli eventuali file temporanei.
- Connessione Internet e una chiave API personale **solo per il controllo VirusTotal**.

Non è disponibile una versione nativa per macOS o Linux.

## Come iniziare

### Download e installazione

1. Apri la sezione **Releases** di questo repository e consulta le note della versione che vuoi utilizzare.
2. Se disponibile, scarica l’installer allegato alla release. Per la versione descritta qui, il file è **`BG-FILES-Setup-2.12.exe`**.
3. Avvia l’installer e scegli **Italiano**, **English** o **Español**.
4. Completa l’installazione e apri BG-FILES.
5. Alla guida iniziale di VirusTotal puoi collegare una chiave oppure scegliere **Più tardi**.

Gli archivi **Source code** generati da GitHub non sono l’installer dell’applicazione.

Se Windows blocca l’installer, l’app o la disinstallazione, consulta [Windows e firma digitale](#windows-e-firma-digitale) prima di procedere.

### Estrarre un archivio

1. Apri BG-FILES e scegli il tuo archivio, oppure trascinalo nella finestra.
2. Usa **Contenuto** se vuoi vedere l’elenco dei file.
3. Controlla la destinazione nelle impostazioni e premi **Estrai archivio**.
4. Al termine premi **Apri cartella**.

Per un’estrazione rapida, fai clic destro sull’archivio in Esplora file e scegli **Estrai qui**. Su Windows 11 le voci del menu classico possono trovarsi sotto **Mostra altre opzioni**.

### Impostare BG-FILES come app predefinita

Apri le impostazioni di BG-FILES e usa il pulsante dedicato all’app predefinita. Completa la scelta nelle impostazioni di Windows. L’associazione resta una decisione dell’utente e può dipendere dalle regole del computer.

## Integrazione con VirusTotal

### Collegare la propria chiave

1. Crea un account sul [sito ufficiale di VirusTotal](https://www.virustotal.com/).
2. Accedi alla pagina [della tua chiave API](https://www.virustotal.com/gui/my-apikey).
3. Copia la chiave e inseriscila nella guida iniziale di BG-FILES oppure nelle **Impostazioni → Collega VirusTotal**.
4. Per correggerla in seguito, usa **Modifica chiave** nelle impostazioni.

Una chiave salvata viene indicata come collegata. La sua validità presso VirusTotal viene verificata quando effettui una richiesta al servizio.

### Controllare prima di estrarre

1. Scegli **Analizza con VirusTotal** nella finestra principale o nel menu rapido dell’archivio.
2. Seleziona i file che vuoi controllare.
3. Premi **Controlla selezionati**. Durante il controllo puoi annullare l’operazione.
4. Leggi i risultati disponibili. Quando esiste un rapporto utilizzabile, il pulsante centrale diventa **Apri rapporto** per il file evidenziato.
5. Scegli **Annulla estrazione** oppure **Continua estrazione**.

> [!NOTE]
> **Continua estrazione estrae l’intero archivio**, compresi i file che non hai selezionato per il controllo. La selezione decide cosa consultare su VirusTotal, non quali file estrarre.

### Cosa significano i risultati

BG-FILES calcola localmente l’impronta **SHA-256** di ciascun file selezionato e cerca il relativo rapporto su VirusTotal. Questo flusso consulta analisi preesistenti: non avvia una nuova scansione tramite caricamento dei contenuti.

| Risultato | Come interpretarlo |
|---|---|
| **Rilevamenti** | Numero di motori che hanno classificato il file come dannoso nel rapporto disponibile. |
| **Sospetti** | Risultati sospetti, indicati separatamente dai rilevamenti. |
| **Motori senza esito** | Motori che non hanno prodotto un risultato utilizzabile. |
| **File sconosciuto** | Non è disponibile un rapporto per quell’impronta. |
| **Errore o quota raggiunta** | Il controllo non è stato completato; non è un risultato pulito. |
| **Data dell’analisi** | Data del rapporto consultato, che può essere precedente al controllo effettuato nell’app. |

**Zero rilevamenti non garantisce che un file sia sicuro.** I conteggi non sono una percentuale di sicurezza. BG-FILES e questa integrazione non sostituiscono l’antivirus del computer.

### Privacy e conservazione della chiave

- Il controllo invia a VirusTotal le **impronte SHA-256**, senza caricare il contenuto dei file.
- Le richieste includono la chiave API necessaria all’autenticazione e i normali dati di connessione. Un’impronta può identificare un file già noto al servizio.
- I file selezionati non vengono eseguiti durante il controllo.
- La chiave viene salvata nella cartella locale dell’utente Windows, cifrata tramite **Windows DPAPI**.
- Le impostazioni possono essere riutilizzate dopo un aggiornamento: per questo non è normalmente necessario reinserire la chiave a ogni versione.

Non inserire la tua chiave API in segnalazioni GitHub, screenshot o file condivisi.

### Limiti del controllo

| Limite locale | Versione 2.12 |
|---|---|
| Dimensione del singolo file da controllare | 256 MiB |
| Totale dei dati da controllare | 1 GiB per operazione |
| Dimensione dell’archivio | 2 GiB |
| Archivi contenuti in altri archivi | Il loro contenuto non viene analizzato ricorsivamente |

La Public API di VirusTotal prevede quote di utilizzo, indicate nella documentazione ufficiale come **4 richieste al minuto e 500 al giorno**. Le quote appartengono all’account e possono essere consumate anche da altre applicazioni. Controllare molti file può richiedere tempo.

L’utilizzo dell’integrazione è soggetto alle [condizioni e ai limiti di VirusTotal](https://docs.virustotal.com/reference/public-vs-premium-api) e alle [regole d’uso delle API](https://docs.virustotal.com/docs/api-overview), comprese le restrizioni per prodotti commerciali e determinati workflow aziendali. La gratuità di BG-FILES e l’uso di una chiave personale non sostituiscono tali condizioni. Non è stata ottenuta un’approvazione specifica di VirusTotal per questa integrazione.

## Windows e firma digitale

La versione 2.12 non dispone di una firma digitale riconosciuta. Windows può quindi mostrare avvisi o impedire l’avvio di uno dei componenti, a seconda delle protezioni e delle policy attive.

Nel controllo della versione 2.12 è stato riprodotto un blocco di **`unins000.exe`**, il disinstallatore, da parte del controllo applicazioni di Windows. Il problema è ancora aperto.

Se incontri un blocco, conserva il testo dell’avviso e segnala quale file è coinvolto. Non disattivare Defender o Smart App Control per aggirarlo. Scaricare l’app da GitHub non modifica la firma del programma e non elimina automaticamente questi blocchi.

### Verificare il download della 2.12

Impronta SHA-256 dell’installer a cui si riferisce questo README:

```text
137837588b52c845112a107e19f0043dff3035304052a68ed5e417a31b18dc70
```

Da PowerShell, nella cartella che contiene il file:

```powershell
Get-FileHash -LiteralPath '.\BG-FILES-Setup-2.12.exe' -Algorithm SHA256
```

Il valore deve coincidere con quello indicato qui. Il confronto conferma l’identità del file rispetto a questa impronta; non equivale a una firma digitale o a una certificazione di sicurezza. Per altre versioni usa il checksum pubblicato nelle rispettive note di release.

## Limiti e problemi noti

- **Disinstallazione:** possibile blocco con Smart App Control; problema riprodotto sulla 2.12.
- **Richieste simultanee:** nella 2.12 il distanziamento delle richieste VirusTotal è gestito per singolo processo. Più istanze aperte possono raggiungere la quota dell’account prima del previsto.
- **Compatibilità:** non tutte le versioni di Windows, architetture, configurazioni e varianti dei formati sono state verificate.
- **Archivi cifrati:** non è disponibile un flusso per l’inserimento della password.
- **VirusTotal:** rapporti assenti, datati o incompleti e indisponibilità del servizio possono limitare il controllo.

## Domande frequenti

<details>
<summary><strong>Devo installare anche 7-Zip?</strong></summary>

No. BG-FILES include il motore necessario all’estrazione. L’app utilizza tecnologia 7-Zip: il motore di decompressione non è stato sviluppato da zero per BG-FILES.

</details>

<details>
<summary><strong>Posso usare BG-FILES senza Internet o senza chiave API?</strong></summary>

Sì. L’estrazione normale funziona localmente. Internet e la chiave personale servono alla consultazione dei rapporti VirusTotal.

</details>

<details>
<summary><strong>Un file sconosciuto a VirusTotal è sicuro?</strong></summary>

Non è possibile stabilirlo da quel risultato. “Sconosciuto” significa che il servizio non ha restituito un rapporto disponibile per l’impronta cercata.

</details>

<details>
<summary><strong>Come correggo una chiave API errata?</strong></summary>

Apri le impostazioni e premi **Modifica chiave**. La finestra dei risultati VirusTotal è dedicata ai controlli e ai rapporti.

</details>

<details>
<summary><strong>Devo effettuare una donazione per utilizzare l’app?</strong></summary>

No. Le donazioni sono facoltative e non sono necessarie per usare BG-FILES.

</details>

## Segnalazioni e suggerimenti

Per segnalare un problema, usa la sezione **Issues** del repository, se abilitata. Includi:

- versione di BG-FILES e versione di Windows;
- lingua dell’app;
- passaggi necessari per riprodurre il problema;
- risultato atteso e comportamento osservato;
- formato dell’archivio ed eventuale messaggio d’errore.

Rimuovi chiavi API, percorsi personali e altre informazioni riservate dagli allegati. Per problemi con un archivio, usa quando possibile un piccolo esempio privo di dati personali.

## Componenti e licenze

BG-FILES utilizza **7-Zip** per la gestione degli archivi. Il motore è distribuito con i relativi avvisi di licenza; i termini dei componenti di terze parti continuano ad applicarsi.

- [Sito ufficiale 7-Zip](https://www.7-zip.org/)
- [Licenza 7-Zip](https://www.7-zip.org/license.txt)
- [Download e sorgenti 7-Zip](https://www.7-zip.org/download.html)

Questo README non assegna una licenza open source al codice originale di BG-FILES. Le condizioni per modificarlo e ridistribuirlo devono essere definite in una licenza dedicata del progetto.

**BG-FILES è un progetto indipendente, non affiliato né approvato da VirusTotal o dal progetto 7-Zip.** I rispettivi nomi e marchi appartengono ai loro titolari.

## Sostieni il progetto

BG-FILES è gratuito. Se ti è utile e vuoi sostenere il suo sviluppo, puoi effettuare una donazione facoltativa:

### [Dona con PayPal](https://paypal.me/leonardobaggio000)

Puoi contribuire anche segnalando problemi, suggerendo miglioramenti o aiutando a rendere più chiare le traduzioni.

---

<div align="center">

**BG-FILES — Apri. Esplora. Estrai.**

</div>
