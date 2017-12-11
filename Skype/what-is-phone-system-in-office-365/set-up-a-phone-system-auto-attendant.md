---
title: "Impostare un operatore automatico di sistema telefonico"
ms.author: tonysmit
author: tonysmit
ms.date: 11/15/2017
ms.audience: ITPro
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.custom: Strat_SB_PSTN
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c

description: "Learn how to set up and test Phone System (Cloud PBX) auto attendents for efficient call handling for your organization. "
---

# Impostare un operatore automatico di sistema telefonico

> [!IMPORTANT]
> Il presente articolo è stato tradotto automaticamente, vedere la [dichiarazione di non responsabilità](6fc2687c-0abf-43b8-aa54-7c3b2a84b67c.md#MT_Footer). Per visualizzare la versione inglese dell'articolo, [fare clic qui](https://support.office.com/en-us/article/6fc2687c-0abf-43b8-aa54-7c3b2a84b67c). 
  
Gli operatori automatici sono molto utili e permettono alle persone che chiamano la tua organizzazione di navigare in un sistema di menu per farli collegare al reparto, alla coda di chiamata o alla persona che cercano oppure a un operatore. Puoi creare un operatore automatico per la tua organizzazione utilizzando l'interfaccia di amministrazione Skype for Business. Per creare un nuovo operatore automatico, accedi a **Instradamento chiamate** nel menu di navigazione a sinistra, quindi seleziona **Operatori automatici** > **Aggiungi nuovo**.
  
Per ulteriori informazioni sugli operatori automatici, vedere [Quali sono gli operatori automatici di sistema telefonico?](what-are-phone-system-auto-attendants.md).
  
## Fase 1 - Attività iniziali

- Prima di creare e configurare gli operatori automatici, è necessario ottenere o trasferire i numeri di servizio esistenti (a pagamento o numeri verdi). Una volta ottenuti i numeri di servizio, a pagamento o numeri verdi, verranno visualizzati nell' **interfaccia di amministrazione Skype for Business** > **Voce** > scheda **Numeri di telefono**, e il **Tipo di numero** indicato sarà elencato come **Servizio - Numero verde**. Per avere i numeri di servizio, consulta [Recupero di numeri di telefono di servizio Skype for Business](getting-service-phone-numbers-for-skype-for-business-and-microsoft-teams.md) oppure, se desideri trasferire un numero di servizio esistente, consulta[Trasferire i numeri di telefono a Office 365](../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md). I numeri **utente (abbonato)** non possono essere assegnati agli operatori automatici. Se sei al di fuori degli Stati Uniti, non è possibile utilizzare l'interfaccia di amministrazione Skype for Business per ottenere i numeri di servizio. Procedi[Gestire i numeri di telefono per la propria organizzazione](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) per sapere cosa fare fuori dagli Stati Uniti.
    
    > [!CAUTION]
    > Per accedere e utilizzare i numeri di telefono verde, è necessario configurare le comunicazioni crediti. Per eseguire questo vedere [Cosa sono i Crediti comunicazioni?](../skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits.md) e[Configurare i Crediti comunicazioni per la propria organizzazione](../skype-for-business-and-microsoft-teams-add-on-licensing/set-up-communications-credits-for-your-organization.md). 
  
- L'organizzazione deve avere (almeno) una licenza Enterprise E3 più **Sistema telefonico** o una licenza E5 Enterprise. Il numero di licenze utente **Sistema telefonico** assegnati impatto il numero del servizio di numeri che è disponibile da utilizzare per gli operatori automatici. I numeri di operatori automatici che è possibile creare dipende dalla licenze **Sistema telefonico** e **Conferenze Audio** numerare assegnato all'interno dell'organizzazione. Per ulteriori informazioni sulle licenze, passare[Skype for Business e Teams Microsoft componente aggiuntivo per le licenze](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
    > [!TIP]
    > Per reindirizzare le chiamate a un operatore o un'opzione di menu che è un utente in linea con una licenza di **Sistema telefonico**, sarà necessario abilitarle per Enterprise Voice o assegnarvi chiamata plan di messaggistica unificata in Office 365. Vedere [Assegnare le licenze per i componenti aggiuntivi Skype for Business e Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). È anche possibile utilizzare Windows PowerShell. Ad esempio eseguire:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
## Fase 2 - Creare un nuovo operatore automatico

Nell' **interfaccia di amministrazione di Skype for Business**, fai clic su **Instradamento chiamate** > **Operatori automatici**, poi fai clic su **Aggiungi nuovo**.
  
### Pagina Modifica informazioni generali

Nella pagina Modifica informazioni generali, immetti o seleziona quanto segue:
  
![New auto attendant page 1.](../images/edacec94-9384-4a87-be0a-5c49a151287e.png)
  
|||
|:-----|:-----|
|**1** <br/> |**Nome** Immetti un nome visualizzato descrittivo per l'operatore automatico. Il nome è obbligatorio e può contenere fino a 64 caratteri, inclusi gli spazi. Sarà elencato nella colonna **Nome** della scheda **Operatori automatici**.  <br/> |
|**2** <br/> |**Numero di telefono** Questa impostazione è facoltativa. Se si preferisce, è possibile selezionare un numero di telefono per l'operatore automatico. È possibile scegliere qualsiasi a pagamento servizi disponibili o il numero verde disponibili per l'organizzazione. Se sono non presenti elencati i numeri di telefono, è necessario procurarsi un numero a pagamento servizio o verde numero. Passare[Recupero di numeri di telefono di servizio Skype for Business](getting-service-phone-numbers-for-skype-for-business-and-microsoft-teams.md) ottenerli. <br/> > [!NOTE]> I numeri **utente (abbonato)** non possono essere assegnati agli operatori automatici.          |
|**3** <br/> |**Fuso orario** È necessario impostare il fuso orario per l'operatore automatico, che non deve necessariamente corrispondere al fuso orario dell'indirizzo principale indicato per l'organizzazione. Ciascun operatore automatico può avere un fuso orario diverso, e l'orario di ufficio fissato per l'operatore automatico verrà impostato in base al fuso orario che selezioni qui. <br/> |
|**4** <br/> |**Lingua** Seleziona la lingua che vuoi utilizzare per l'operatore automatico tra una delle lingue disponibili elencate. La lingua impostata qui è la lingua che l'assistente automatico utilizzerà per interagire con le persone che chiamano questo operatore automatico e tutti i messaggi di sistema verranno riprodotti in questa lingua. <br/> |
|**5** <br/> |**Riconoscimento vocale** Se il riconoscimento vocale è disponibile e questa opzione è selezionata, le persone che chiamano potranno usare i comandi vocali nella lingua impostata. Puoi disattivare il riconoscimento vocale deselezionandolo, se desideri che i chiamanti usino solo la tastiera del telefono. <br/> |
|**6** <br/> |**Operatore** È un'impostazione facoltativa per l'operatore automatico. Tuttavia, puoi impostare l'opzione **Operatore** per consentire alle persone che chiamano di uscire dai menu e parlare con una persona per aiutarli. <br/>  Il tasto 0 viene assegnato automaticamente alla funzione Operatore. <br/>  Se imposti questa funzione, dovrai anche comunicare ai chiamanti che questa opzione è disponibile in **Modifica opzioni di menu** nella pagina **Gestione chiamate in orario di ufficio**. Se imposti l'opzione Operatore per l'operatore automatico, dovrai inserire testo corrispondente nella casella **I chiamanti sentiranno** o modificare il file audio in modo che includa questa opzione. Ad esempio: "Per contattare un operatore, premere zero". <br/>  Puoi impostare la funzione Operatore a una delle persone seguenti. <br/>  Una **persona nella società** con una licenza di **Sistema telefonico** che è abilitata per VoIP aziendale o assegnata la chiamata plan di messaggistica unificata in Office 365. <br/> > [!NOTE]> **Persona della società** possono essere un utente in linea o un utente ospitato locale con Skype for Business Server 2015 o Lync Server 2013. Lync Server 2010 non è supportata.           Una **Coda di chiamata** che hai impostato. <br/>  Puoi impostarla in modo che la persona che chiama può essere passata alla segreteria. Per fare questo, scegli una **Persona nell'azienda** e questa persona riceverà le chiamate inoltrate direttamente alla segreteria telefonica. <br/> |
   
### Pagina Seleziona orari di utilizzo

Per impostazione predefinita, l'orario di ufficio è impostato per 24 ore al giorno, 7 giorni a settimana, perciò qualsiasi orario è considerato orario di ufficio. Tutti gli orari che non sono inclusi nell'orario di ufficio sono considerati orario di chiusura. Se selezioni l'opzione **Personalizzato** e imposti l'orario di ufficio, verrà aggiunta una nuova pagina chiamata **Gestione delle chiamate in orario di chiusura** e dovrai configurare la gestione delle chiamate all'operatore automatico fuori dall'orario di ufficio.
  
![New auto attendant Hours of operation.](../images/61769547-cdb4-45c0-af5a-3d6e0731fbc6.png)
  
|||
|:-----|:-----|
|**1** <br/> |Seleziona l'opzione **Personalizzato** per selezionare l'orario di ufficio specifico nel calendario. Quando selezioni **Personalizzato**, l'orario di ufficio sarà impostato da lunedì a venerdì, dalle 9:00 alle 17:00, per impostazione predefinita.  <br/> |
|**2** <br/> |Per modificare l'orario di ufficio, evidenzia l'orario di ufficio che desideri impostare con il calendario. Il calendario consente di selezionare l'orario di ufficio a intervalli di 30 minuti, e l'orario di ufficio che selezioni qui sarà impostato in base al fuso orario impostato nella pagina **Informazioni generali**. Per impostare una pausa (ad esempio la pausa pranzo), deseleziona o trascina per deselezionare l'orario in questione sul calendario. Puoi anche definire più pause all'interno dell'orario di ufficio.  <br/> |
   
### Pagina di gestione di chiamata selezionare orario di ufficio

> [!TIP]
> Se usi un orario di ufficio personalizzato, devi impostare anche la gestione delle chiamate nell'orario di chiusura. Verrà aggiunta una pagina **Gestione delle chiamate in orario di chiusura** per poter configurare queste opzioni, con le stesse opzioni di **Gestione delle chiamate in orario di ufficio**. 
  
È possibile impostare i messaggi di saluto, prompt e i menu per gli utenti ascolteranno chiamata nel numero di telefono operatore automatico dell'organizzazione durante le ore di lavoro.
  
![Business hours call handling.](../images/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)
  
|||
|:-----|:-----|
|**1**|**Saluto aziendale** Il saluto in orario di ufficio è opzionale e può essere impostato su **Nessuno**. In questo caso, il chiamante non sente nessun messaggio o saluto prima che la chiamata venga gestita da una delle opzioni selezionate. Puoi anche caricare un file audio (in formato .wav, .wma o .mp3), o creare un messaggio di saluto personalizzato utilizzando il sintetizzatore vocale. **Nessuno** Nessun messaggio di saluto verrà riprodotto quando persone chiamare il numero di telefono operatore automatico. **Messaggio di saluto crea una personalizzata** Se si sceglie questa opzione, immettere il testo che si desidera che il sistema di leggere (fino a 1000 caratteri). Ad esempio, è possibile immettere "Introduzione a Contoso. La chiamata è importante."nella casella **i chiamanti ascolteranno**. **Caricare un file audio** Se si sceglie questa, registrare il messaggio di saluto e quindi caricare il file audio (in un formato WAV, MP3 o WMA).|
|**2**| È possibile selezionare cosa accade alle chiamate in arrivo durante le ore lavorative. È possibile scegliere una delle opzioni seguenti: **Disconnetti** Se selezioni questa opzione, il chiamante sarà disconnesso dopo aver ricevuto il saluto selezionato per l'orario di ufficio. **Reindirizza chiamata** Puoi usare questa opzione per trasferire automaticamente la chiamata a uno di questi destinatari: **Persona della società** con una licenza di **Sistema telefonico** che è abilitata per VoIP aziendale o assegnata la chiamata plan di messaggistica unificata in Office 365. È possibile impostare il in modo che la persona chiamata in può essere inviata alla segreteria telefonica. A tale scopo, selezionare **persone della società** e impostare questa persona abbia loro le chiamate vengano inoltrate direttamente alla segreteria telefonica.> [!NOTE]> **Persona della società** possono essere un utente in linea o un utente ospitato locale con Skype for Business Server 2015 o Lync Server 2013. Lync Server 2010 non è supportata.           Una **Coda di chiamata** L'uso dell'opzione Coda di chiamata consente di trasferire la chiamata a una coda di chiamata esistente che hai già impostato. Un altro **Operatore automatico** Puoi utilizzare un operatore automatico esistente per creare un secondo livello di opzioni di menu che contengono un sottomenu. Viene chiamato operatore automatico nidificato. **Riproduci messaggio opzioni di menu** Questa opzione può essere utilizzata anche per impostare un messaggio che si desidera riprodurre.|
|**3**|**Messaggio del menu** Per creare il messaggio del menu principale, puoi utilizzare il sintetizzatore vocale o caricare un file audio (.wav, .mp3 o .wma). Puoi digitare il messaggio nella casella **I chiamanti sentiranno** o registrare un file audio e dire, per esempio: "Per assistenza commerciale, premere o pronunciare 1. Per i servizi, premere o pronunciare 2. Per l'assistenza clienti, premere o pronunciare 3. Per contattare un operatore, premere o pronunciare 0. Per ascoltare di nuovo questo menu, premere il tasto asterisco o pronunciare Ripeti". **Crea un messaggio personalizzato** Se scegli questa opzione, devi inserire il testo che vuoi fare leggere al sistema (fino a 1000 caratteri). **Carica un file audio** Se scegli questa opzione, dovrai registrare il messaggio di saluto e poi caricare il file audio (in formato .wav, .mp3 o .wma).|
|**4**|**Connessione in base al nome** Se si sceglie questa opzione, in questo modo le persone che accedono tramite telefono per cercare persone dell'organizzazione tramite ricerca nella Directory. È possibile selezionare quali persone sarà elencato come disponibile o non è disponibile per telefono in base al nome installando e configurando le opzioni nella pagina **comporre ambito**. Qualsiasi utente in linea con una licenza di **Sistema telefonico** o qualsiasi utente ospitato locale con Skype for Business Server 2015 o Lync Server 2013, sono disponibili con accesso esterno per nome.> [!CAUTION]> Gli utenti ospitati locale utilizzando Lync 2010 **non può essere raggiunto** con accesso esterno per nome.          |
|**5**|**Modifica opzioni di menu** Le opzioni del menu possono essere aggiunte o rimosse utilizzando i tasti della tastiera. Per aggiungere un'opzione di menu, premi il tasto corrispondente sulla tastiera. I tasti in ​​uso cambieranno colore e sotto di essi apparirà la fila di opzioni corrispondente. Per eliminare un'opzione di menu, è sufficiente fare clic sul tasto corrispondente sul controllo a tastiera in modo da deselezionarlo. La riga di mappatura del tasto verrà rimosso.> [!TIP]> Dovrai aggiornare i testi dei messaggi del menu o registrare di nuovo l'audio separatamente quando aggiungi o rimuovi opzioni, l'operazione non avverrà automaticamente per il messaggio del menu esistente.           Qualsiasi opzione di menu può essere aggiunta o rimossa in qualsiasi ordine e la mappatura dei tasti non deve necessariamente essere continua. È possibile, per esempio, creare un menu con i tasti 0, 1 e 3 mappati su opzioni mentre il tasto 2 non è utilizzato.> [!NOTE]> I tasti * (Ripeti) e # (Indietro) sono riservati per il sistema e non possono essere riassegnati. Se il riconoscimento vocale è abilitato, premere * corrisponde al comando vocale "Ripeti" e # a "Indietro".           |
|| Per impostare le opzioni di menu, dopo aver selezionato i tasti, è necessario quanto segue. **Inserisci il nome dell'opzione** Può contenere fino a 64 caratteri e può contenere più parole come "Assistenza clienti" oppure "Operazioni e sedi". Se il riconoscimento vocale è abilitato, il nome verrà automaticamente riconosciuto e il chiamante potrà premere 3, dire "Tre" o dire "Assistenza clienti" per selezionare l'opzione mappata al tasto 3. La fase successiva è selezionare dove deve essere inoltrata la chiamata se viene premuto il tasto corrispondente o viene selezionata l'opzione utilizzando il riconoscimento vocale. La chiamata può essere inviata a una di queste destinazioni: **Operatore** Se l'operatore è già configurato, viene mappato automaticamente al tasto 0, ma può anche essere eliminato o riassegnato a un tasto diverso. Se l'operatore non è impostato su nessun tasto, sarà disattivato anche il comando vocale "Operatore". Una **persona nella società** con una licenza di **Sistema telefonico** che è abilitata per VoIP aziendale o assegnata un piano di chiamata in Office 365. È possibile impostare il in modo che la persona chiamata in può essere inviata alla segreteria telefonica. A tale scopo, selezionare **persone della società** e impostare questa persona abbia loro le chiamate vengano inoltrate direttamente alla segreteria telefonica.> [!NOTE]> **Persona della società** possono essere un utente in linea o un utente ospitato locale con Skype for Business Server 2015 o Lync Server 2013. Lync Server 2010 non è supportata.          **Coda di chiamata** L'uso dell'opzione coda di chiamata consente di trasferire la chiamata a una coda di chiamata esistente che hai già impostato. **Operatore automatico** Puoi utilizzare un operatore automatico esistente per creare un secondo livello di opzioni di menu che contengono un sottomenu. Viene chiamato operatore automatico nidificato.> [!NOTE]>  L' **Orario di ufficio** degli operatori automatici nidificati (o di secondo livello) saranno utilizzati anche per le chiamate inviate dagli altri operatori automatici configurati.          |
   
### Selezionare la pagina di festività (disponibile a esclusivamente ai clienti di anteprima)

È possibile aggiungere fino a 20 festività programmata per ogni operatore automatico.
  
![Setting up Holidays in auto attendant](../images/50a5ce88-7f39-4210-808a-da7ced969854.png)
  
|||
|:-----|:-----|
|**1**|**Aggiungere una festività** Immettere un nome per la nuova festività nel campo **Nome festività**.I nomi delle festività possono essere costituito da un massimo di 64 caratteri e devono essere univoci per l'operatore automatico stesso. Ad esempio, è possibile assegnare due giorni festivi denominate "Ringraziamento" nell'operatore automatico stesso.|
|**2**|**Messaggio di saluto per le festività** La formula di apertura per le festività è facoltativa e può essere impostato su **Nessuno**. In questo caso, il chiamante non ascolteranno Nessun messaggio o un messaggio di saluto prima che la chiamata viene gestita da una delle opzioni selezionate. È possibile caricare un file audio (in formato WAV, mp3 o WMA) o creare un messaggio di saluto personalizzato utilizzando sintesi vocale da testo. **Nessuno** Nessun messaggio di saluto verrà riprodotto quando persone chiamare il numero di telefono operatore automatico. **Messaggio di saluto crea una personalizzata** Se si sceglie questa opzione, immettere il testo che si desidera che il sistema di leggere (fino a 1000 caratteri). Ad esempio, è possibile immettere "buon anno! Uffici sono attualmente chiuso."nella casella **i chiamanti ascolteranno**. **Caricare un file audio** Se si sceglie questa, registrare il saluto per le festività e quindi caricare il file audio (in un formato WAV, MP3 o WMA).|
|**3**|**Cosa accade alle chiamate dopo il messaggio di saluto?** È possibile selezionare cosa accade alle chiamate in arrivo durante questo festività. È possibile scegliere una delle opzioni seguenti: **Disconnessione** La persona chiamata in verrà disconnessi dopo ascoltare il messaggio di saluto per le festività. **Reindirizza chiamata** Puoi usare questa opzione per trasferire automaticamente la chiamata a uno di questi destinatari: Una **persona nella società** con una licenza di **Sistema telefonico** che è abilitata per VoIP aziendale o assegnata la chiamata plan di messaggistica unificata in Office 365. È possibile impostare il in modo che la persona chiamata in può essere inviata alla segreteria telefonica. Per eseguire questa operazione, selezionare **persone della società** e impostare questa persona abbia loro le chiamate vengano inoltrate direttamente alla segreteria telefonica.> [!NOTE]> **Persona della società** possono essere un utente in linea o un utente ospitato locale con Skype for Business Server 2015 o Lync Server 2013. Lync Server 2010 non è supportata.           Una **Chiamata coda** trasferire la chiamata a una coda di chiamare esistente che è stata configurata Un altro **operatore automatico**, per creare un secondo livello di opzioni del menu contenente un sottomenu. Si tratta di operatori automatici annidate. > [!NOTE]>  Per impostazione predefinita, tutte le chiamate in arrivo per un periodo per le festività sono disconnettere dopo il messaggio di saluto (se presente), è necessario specificare un reindirizzamento se non si desidera un comportamento diverso.          |
|**4**|**Quando si desidera per le festività per iniziare e finire?** Immettere la data di inizio per le festività nel formato gg/mm/aaaa e quindi selezionare un'ora di inizio, data di fine e ora di fine, come richiesto descritti nella tabella di intervallo di date.È possibile specificare fino a 10 diversi intervalli di date per una festività. Ad esempio, è possibile aggiungere gli intervalli di date per le festività Natale per fino a 10 anni. Un giorno festivo interessare più giorni.Per aggiungere ulteriori data festività intervalli (ad esempio, per l'anno successivo), fare clic su **Aggiungi un altro** e quindi immettere un nuovo set di date di inizio e fine per le festività.Sono supportate anche festività annidate. Ad esempio, è possibile nidificare più giorni di vacanza all'interno di un intervallo di tempo "interruzione festività": **· 24 dicembre tramite 3 gennaio:** "buon festività! Uffici sono chiuso. Si verrà riaperta in 4 ° gennaio." **· 25 dicembre:** "Buon Natale! Uffici sono chiuso. Si verrà riaperta in 4 ° gennaio." **· 1 ° gennaio:** "buon anno! Uffici sono chiuso. Si verrà riaperta in 4 ° gennaio."|
   
Dopo aver salvato l'operatore automatico, le festività vengono visualizzati nella scheda **festività**, in cui è possibile modificare, aggiungere o modificare le impostazioni per le festività.
  
### Pagina Seleziona ambito di chiamata

In questa pagina puoi impostare quali utenti dell'organizzazione saranno presenti nell'elenco e disponibili per Chiamata per nome quando una persona chiama l'organizzazione.
  
![Dial scope for searching with dial by name.](../images/1bcb185c-00db-43a7-b5c4-9b021c0627f7.png)
  
|||
|:-----|:-----|
|**1** <br/> | Quando usi l'opzione **Includi** hai a disposizione due opzioni: <br/> **Utenti tutti Online** Questa opzione consente di tutti gli utenti dell'organizzazione da includere nella ricerca nella directory. Tutti gli utenti in linea con una licenza di **Sistema telefonico**, come gli utenti ospitati locale con Skype for Business Server 2015 o Lync Server 2013, hanno la chiamata plan di messaggistica unificata in Office 365 sarà elencato.  <br/> **Personalizzato** Se si utilizza questa opzione, è possibile cercare un gruppo di Office 365, una lista di distribuzione o gruppo di sicurezza creato all'interno dell'organizzazione e le persone aggiungono a questo gruppo di Office 365, una lista di distribuzione o gruppo di sicurezza che hanno uno dei due **utenti in linea con un Licenza del sistema telefonico** o locale ospitati utilizzano Skype per Business Server 2015 o Lync Server 2013 verrà incluso nella ricerca directory. È possibile aggiungere più gruppi di Office 365, liste di distribuzione e i gruppi di sicurezza. <br/> > [!CAUTION]>  Gli utenti locali le distribuzioni di Lync Server 2010 non sarà disponibile quando un utente esegue la ricerca nella directory con accesso esterno in base al nome.          |
|**2** <br/> | Quando usi l'opzione **Escludi** hai a disposizione due opzioni: <br/> **Nessuno** Questa opzione indica che nessun utente online sarà escluso dalla ricerca in elenco. <br/> **Personalizzato** Se si utilizza questa opzione, è possibile cercare un gruppo di Office 365, gruppo di sicurezza o elenco di distribuzione che è stata creata nell'organizzazione e tutte le persone aggiunte a questo gruppo di Office 365, i gruppi di sicurezza o elenco di distribuzione verranno esclusi dalla ricerca nella directory. È possibile aggiungere più gruppi di Office 365, liste di distribuzione e i gruppi di sicurezza. <br/> > [!CAUTION]>  Gli utenti locali le distribuzioni di Skype for Business 2015 o Lync Server 2013 e 2010 non sarà disponibile quando un utente esegue la ricerca nella directory con accesso esterno in base al nome.          |
   
> [!NOTE]
> Possono occorrere fino a 36 ore perché un nuovo utente abbia il nome in elenco quando qualcuno usa Chiamata per nome con il riconoscimento vocale. 
  
Dopo aver compilato tutti i campi obbligatori e impostato la gestione menu e le opzioni di chiamata, fai clic su **Salva**.
  
## Modifica e prova degli operatori automatici

Dopo aver salvato il tuo operatore automatico, verrà elencato nella pagina **Operatori automatici**. Questo ti permetterà di vedere rapidamente alcune delle opzioni impostate, tra cui nome, numero di telefono, lingua e stato.
  
Se vuoi apportare modifiche a un operatore automatico, fai clic per evidenziare l'operatore automatico; nel pannello laterale, potrai fare clic su **Modifica**.
  
Puoi anche effettuare una rapida chiamata di prova al tuo operatore automatico utilizzando il pulsante **Test** nel pannello laterale.
  
## Per saperne di più

Puoi anche utilizzare Windows PowerShell per creare e configurare gli operatori automatici.
  
### Cmdlet dell'operatore automatico

Questi sono i cmdlet necessari per gestire un operatore automatico.
  
||||
|:-----|:-----|:-----|
|[New-CsOrganizationalAutoAttendant](https://technet.microsoft.com/en-us/library/mt796493.aspx) <br/> |[Get-CsOrganizationalAutoAttendantSupportedTimeZone]( https://technet.microsoft.com/en-us/library/mt796483.aspx) <br/> |[New-CsOrganizationalAutoAttendantMenu](https://technet.microsoft.com/en-us/library/mt796488.aspx ) <br/> |
|[Set-CsOrganizationalAutoAttendant](https://technet.microsoft.com/en-us/library/mt796486.aspx) <br/> |[Get-CsOrganizationalAutoAttendantSupportedLanguage](https://technet.microsoft.com/en-us/library/mt796481.aspx) <br/> |[New-CsOrganizationalAutoAttendantCallFlow](https://technet.microsoft.com/en-us/library/mt796489.aspx) <br/> |
|[Get-CsOrganizationalAutoAttendant](https://technet.microsoft.com/en-us/library/mt796482.aspx ) <br/> |[New-CsOrganizationalAutoAttendantCallableEntity](https://technet.microsoft.com/en-us/library/mt796480.aspx) <br/> |[New-CsOnlineTimeRange](https://technet.microsoft.com/en-us/library/mt796491.aspx ) <br/> |
|[Remove-CsOrganizationalAutoAttendant](https://technet.microsoft.com/en-us/library/mt796492.aspx) <br/> |[New-CsOrganizationalAutoAttendantPrompt](https://technet.microsoft.com/en-us/library/mt796484.aspx ) <br/> |[New-CsOnlineSchedule](https://technet.microsoft.com/en-us/library/mt796490.aspx) <br/> |
|[New- CsOnlineAudioFile](https://technet.microsoft.com/en-us/library/mt796479.aspx) <br/> |[New-CsOrganizationalAutoAttendantMenuOption](https://technet.microsoft.com/en-us/library/mt796485.aspx ) <br/> |[New-CsOrganizationalAutoAttendantCallHandlingAssociation](https://technet.microsoft.com/en-us/library/mt796487.aspx ) <br/> |
|[Esportazione-CsOrganizationalAutoAttendantHolidays (solo per i clienti di anteprima)](https://docs.microsoft.com/en-us/powershell/module/skype/export-csorganizationalautoattendantholidays?view=skype-ps) <br/> |[Get-CsOrganizationalAutoAttendantHolidays (solo per i clienti di anteprima)](https://docs.microsoft.com/en-us/powershell/module/skype/get-csorganizationalautoattendantholidays?view=skype-ps) <br/> |[Importa-CsOrganizationalAutoAttendantHolidays (solo per i clienti di anteprima)](https://docs.microsoft.com/en-us/powershell/module/skype/import-csorganizationalautoattendantholidays?view=skype-ps) <br/> |
|[New-CsOnlineDateTimeRange (solo per i clienti di anteprima)](https://docs.microsoft.com/en-us/powershell/module/skype/new-csonlinedatetimerange?view=skype-ps) <br/> |||
   
### Altre informazioni su Windows PowerShell

- Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire. È possibile gestire Office 365 e Skype for Business online da un'unica risorsa di amministrazione, semplificando il lavoro quotidiano se si hanno molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedere questi argomenti:
    
  - [Introduzione a Windows PowerShell e Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Sei motivi per cui è consigliabile usare Windows PowerShell per gestire Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso della sola interfaccia di amministrazione di Office 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, vedere gli argomenti seguenti:
    
  - [Gestire Office 365 con Windows PowerShell nel modo migliore](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usare Windows PowerShell per gestire Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usare Windows PowerShell per svolgere comuni attività di gestione di Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Dichiarazione di non responsabilità per la traduzione automatica**: Il presente articolo è stato tradotto tramite un software di traduzione automatica e non da una persona. Microsoft offre le traduzioni automatiche per consentire a coloro che non conoscono la lingua inglese di leggere gli articoli sui prodotti, sui servizi e sulle tecnologie Microsoft. Dal momento che l'articolo è stato tradotto automaticamente, potrebbe contenere errori di sintassi, di grammatica o di utilizzo dei vocaboli. 
  

