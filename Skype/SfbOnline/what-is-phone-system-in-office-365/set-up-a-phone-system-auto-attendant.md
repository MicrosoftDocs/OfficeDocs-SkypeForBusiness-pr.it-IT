---
title: Impostare un operatore automatico in Sistema telefonico
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: makolomi
ms.date: 9/1/2018
ms.topic: article
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: "Informazioni su come configurare e testare gli operatori automatici di sistema telefonico in (Cloud PBX) per la gestione dell'organizzazione delle chiamate efficiente. "
ms.openlocfilehash: 41a4f7d3536e3a92104c98eaee057a47a21aeb9e
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/13/2018
ms.locfileid: "26294574"
---
# <a name="set-up-a-phone-system-auto-attendant"></a>Impostare un operatore automatico in Sistema telefonico

Gli operatori automatici di consentono agli utenti che chiamate verso l'organizzazione e passare a un sistema di menu per ottenere informazioni utili per il reparto destro, coda, persona o l'operatore di chiamata. È possibile creare un operatore automatico per l'organizzazione mediante il Skype per l'interfaccia di amministrazione di Business. Per creare un nuovo operatore automatico, accedi a **Instradamento chiamate** nel menu di navigazione a sinistra, quindi seleziona **Operatori automatici** > **Aggiungi nuovo**.

Per ulteriori informazioni sugli operatori automatici, vedere [che cosa sono gli operatori automatici di sistema telefonico?](/microsoftteams/what-are-phone-system-auto-attendants)

## <a name="step-1---getting-started"></a>Fase 1 - Attività iniziali

- Before you can create and set up your auto attendants, you will need to get or transfer your existing toll or toll-free service numbers. Dopo aver ottenuto il numero a tariffa o i numeri verdi servizio, verrà visualizzato nella **Skype per Business admin center** > **vocale** > pagina**i numeri di telefono** . Per ottenere i numeri di servizio, vedere [Getting numeri di telefono del servizio per Skype per le aziende e team di Microsoft](getting-service-phone-numbers.md)o se si desidera trasferimento e il numero di servizio esistente, [trasferire i numeri di telefono a Office 365](/microsoftteams/transfer-phone-numbers-to-office-365). **User (subscriber)** numbers can't be assigned to auto attendants. Se si è fuori degli Stati Uniti, è possibile utilizzare Skype per interfaccia di amministrazione di Business per ottenere numeri di servizio. andare [qui](/microsoftteams/manage-phone-numbers-for-your-organization) invece.

    > [!CAUTION]
    > Per ottenere e utilizzare numeri verdi, è necessario impostare i titoli di coda di comunicazioni. Per eseguire questo vedere [che cosa sono i titoli di coda Communications?](/microsoftteams/what-are-communications-credits) e [impostare i titoli di coda di comunicazione per l'organizzazione](/microsoftteams/set-up-communications-credits-for-your-organization).
  
- L'organizzazione deve disporre (almeno) una licenza Enterprise E3 plus **Sistema telefonico** o una licenza Enterprise E5. Il numero di licenze utente **Sistema telefonico** assegnati influisce sul numero dei numeri di servizio disponibili essere utilizzati per gli operatori automatici. I numeri di operatori automatici, che è possibile avere dipende le licenze numeri **Sistema telefonico** e **Audioconferenza** che sono assegnate all'interno dell'organizzazione. Per ulteriori informazioni sulle licenze, Vai [qui](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).

    > [!TIP]
    > Per reindirizzare le chiamate a un operatore o un'opzione di menu è un utente in linea con una licenza di **Sistema telefonico** , sarà necessario abilitati per Enterprise Voice o assegnarvi tariffe di chiamate in Office 365. Vedi [Assegnare le licenze per i componenti aggiuntivi Skype for Business e Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). Puoi anche utilizzare Windows PowerShell. Ad esempio, eseguire:`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
## <a name="step-2---create-a-new-auto-attendant"></a>Fase 2 - Creare un nuovo operatore automatico

![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **utilizzando Skype per interfaccia di amministrazione di Business**


Nell' **interfaccia di amministrazione di Skype for Business**, fai clic su **Instradamento chiamate** > **Operatori automatici**, poi fai clic su **Aggiungi nuovo**.

### <a name="edit-general-info-page"></a>Pagina Modifica informazioni generali

![New auto attendant page 1.](../images/edacec94-9384-4a87-be0a-5c49a151287e.png)

***
![Numero 1](../images/sfbcallout1.png)<br/>**Nome** Immettere un nome descrittivo per l'operatore automatico. Il nome è obbligatorio e può contenere fino a 64 caratteri, inclusi gli spazi. Sarà elencato nella colonna **Nome** della scheda **Operatori automatici**.
***

![Numero 2](../images/sfbcallout2.png)<br/>**Numero di telefono** Questa impostazione è facoltativa. Se desideri, puoi selezionare un numero di telefono per l'operatore automatico. È possibile scegliere qualsiasi numero a tariffa servizio disponibile o il numero verde che è necessario per l'organizzazione. Se non ci sono numeri di telefono indicati, dovrai ottenere un numero di servizio (a pagamento o numero verde). Vai [qui](getting-service-phone-numbers.md) per ottenere informazioni utili. <br/> <br/>

> [!NOTE]
> **User (subscriber)** numbers can't be assigned to auto attendants.

***
![Numero 3](../images/sfbcallout3.png)<br/>**Fuso orario** È necessario impostare il fuso orario per l'operatore automatico, che non deve necessariamente corrispondere al fuso orario dell'indirizzo principale indicato per l'organizzazione. Ciascun operatore automatico può avere un fuso orario diverso, e l'orario di ufficio fissato per l'operatore automatico verrà impostato in base al fuso orario che selezioni qui.
***
![14](../images/sfbcallout4.png)<br/>**Lingua** Seleziona la lingua che vuoi utilizzare per l'operatore automatico tra una delle lingue disponibili elencate. La lingua impostata qui è la lingua che verrà utilizzato l'operatore automatico per interagire con persone che chiamare questo operatore automatico e tutte le richieste di sistema verranno riprodotto nella lingua selezionata.
***
![Numero 5](../images/sfbcallout5.png)<br/>**Riconoscimento vocale** Riconoscimento vocale è disponibile e se questa opzione è selezionata. Utenti che chiamano in possono utilizzare input vocale nella lingua che è impostata. È possibile disattivare il riconoscimento vocale deselezionando se si desidera solo consentire agli utenti di utilizzare il tastierino numerico del telefono.
***
![Numero 6](../images/sfbcallout6.png)<br/>**Operatore** È un'impostazione facoltativa per l'operatore automatico. Tuttavia, è possibile impostare l'opzione **operatore** per gli utenti che chiamano in siano in grado di abbandonare i menu di parlare a una persona per migliorare la. <br/> <br/> Il tasto 0 viene assegnato automaticamente alla funzione Operatore. <br/> <br/> Se a tale scopo, è necessario anche informare gli altri utenti chiamata in quanto si tratta di un'opzione disponibile nel **menu Opzioni di modifica** nella pagina di **gestione delle chiamate di orari d'ufficio** . Se si imposta un operatore per l'operatore automatico, è necessario immettere il testo del messaggio corrispondente nella casella **i chiamanti possano rispondere** o modificare il file audio per includere questa opzione. Ad esempio: "Per contattare un operatore, premere zero". <br/><br/>  Puoi impostare la funzione Operatore a una delle persone seguenti. 
*    **Persona nell'azienda** con una licenza di **Sistema telefonico** abilitata per Enterprise Voice o con Piani di chiamata di Office 365 assegnati. <br/>

        > [!Note] 
        > Una **Persona nell'azienda** può essere un utente in linea o un utente ospitato in locale con Skype per Business Server 2015 o Lync Server 2013. Lync Server 2010 non è supportato. <br/> 

*    Una **Coda di chiamata** che hai impostato. 
*    Puoi impostarla in modo che la persona che chiama può essere passata alla segreteria. A tale scopo, selezionare **persona nell'azienda** e impostare le chiamate vengano inoltrate direttamente alla segreteria telefonica della persona. 

### <a name="select-hours-of-operation-page"></a>Pagina Seleziona orari di utilizzo

Per impostazione predefinita, orari d'ufficio sono impostato su 24 ore al giorno, 7 giorni alla settimana, quindi tutte le ore sono considerate orari d'ufficio. Tutti gli orari che non sono inclusi nell'orario di ufficio sono considerati orario di chiusura. Se si seleziona l'opzione **personalizzato** e imposta l'orario di ufficio, una nuova pagina viene chiamata **dopo la gestione delle chiamate ore** verrà aggiunta dove è possibile configurare la gestione per dopo l'orario di ufficio per l'operatore automatico delle chiamate.

![New auto attendant Hours of operation.](../images/61769547-cdb4-45c0-af5a-3d6e0731fbc6.png)

***
![Numero 1](../images/sfbcallout1.png)<br/>Seleziona l'opzione **Personalizzato** per selezionare l'orario di ufficio specifico nel calendario. Quando selezioni **Personalizzato**, l'orario di ufficio sarà impostato da lunedì a venerdì, dalle 9:00 alle 17:00, per impostazione predefinita.
***
![Numero 2](../images/sfbcallout2.png)<br/>Per modificare l'orario di ufficio, evidenzia l'orario di ufficio che desideri impostare con il calendario. Calendario consente di selezionare l'orario di ufficio intervalli di 30 minuti e gli orari d'ufficio che selezionare di seguito viene impostati in base il fuso orario impostato nella pagina **informazioni generali** . Per impostare una pausa (ad esempio la pausa pranzo), deseleziona o trascina per deselezionare l'orario in questione sul calendario. È possibile impostare più interruzioni all'interno di orari d'ufficio. 

### <a name="select-business-hours-call-handling-page"></a>Pagina di selezione delle chiamate in orario di ufficio

> [!TIP]
> Se usi un orario di ufficio personalizzato, devi impostare anche la gestione delle chiamate nell'orario di chiusura. Verrà aggiunta una pagina **Gestione delle chiamate in orario di chiusura** per poter configurare queste opzioni, con le stesse opzioni di **Gestione delle chiamate in orario di ufficio**. 

È possibile impostare messaggi di saluto, istruzioni e dei menu di persone che possano rispondere in chiamata al numero di telefono operatore automatico dell'organizzazione durante le ore lavorative.

![Business hours call handling.](../images/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)

***
![Numero 1](../images/sfbcallout1.png)<br/>**Messaggio di saluto aziendale** Il messaggio di saluto in orario di ufficio è facoltativo e può essere impostato su **Nessuno**. In questo caso, il chiamante non udirà alcun messaggio o saluto prima che la chiamata venga gestita da una delle opzioni selezionate. È possibile caricare un file audio (nel formato con estensione wav, mp3 o .wma) o creare un messaggio di saluto personalizzato utilizzando la sintesi vocale.
*    **Nessuno** Nessun messaggio di saluto verrà riprodotto quando le persone chiamano il numero di telefono dell'operatore automatico.
*    **Crea un oggetto personalizzato messaggio di saluto** Se si sceglie questa opzione, immettere il testo che si desidera che il sistema per la lettura (fino a 1000 caratteri). Ad esempio, è possibile immettere "Benvenuti alla Contoso. La tua chiamata è importante per noi." nella casella **I chiamanti udiranno**.
*    **Caricare un file audio** Se si sceglie questa, registrare il messaggio di saluto e quindi caricare i file audio (in formato WAV, MP3 o. wma).
***
![Numero 2](../images/sfbcallout2.png)<br/>È possibile selezionare cosa avviene alle chiamate in arrivo durante l'orario di ufficio. È possibile scegliere tra le opzioni seguenti:
* **Disconnettere** Se selezionata, la persona che chiama verrà disconnessa dopo aver ascoltato una saluto di orario di ufficio.
* **Reindirizzare una chiamata** Ciò consente di inviare automaticamente la chiamata a:
  * **Persona nell'azienda** con una licenza di **Sistema telefonico** abilitata per Enterprise Voice o con Piani di chiamata di Office 365 assegnati. Puoi impostarla in modo che la persona che chiama possa essere passata alla segreteria telefonica. A tale scopo, selezionare **persona nell'azienda** e impostare tale persona per le chiamate inoltrate direttamente alla segreteria telefonica. <br/><br/>   
    > [!Note]
    > Una **Persona nell'azienda** può essere un utente in linea o un utente ospitato in locale con Skype per Business Server 2015 o Lync Server 2013. Lync Server 2010 non è supportato. <br/><br/>

  * **Coda di chiamata** Utilizzando una coda di chiamata puoi trasferire la chiamata a una Coda di chiamata esistente che hai configurato.
  * Un altro **Operatore automatico** Puoi usare un operatore automatico esistente per creare un secondo livello di opzioni del menu contenente un sottomenu. Questi sono denominati operatori automatici innestati.

* **Riprodurre richieste del menu Opzioni** Queste sono anche utilizzabili per consentire la configurazione di una richiesta che si desidera riprodurre.
***
![Numero 3](../images/sfbcallout3.png)<br/>**Messaggio del menu** Per creare il messaggio del menu principale, puoi utilizzare il sintetizzatore vocale o caricare un file audio (.wav, .mp3 o .wma). Puoi digitare il messaggio nella casella **I chiamanti sentiranno** o registrare un file audio e dire, per esempio: "Per assistenza commerciale, premere o pronunciare 1. Per i servizi, premere o pronunciare 2. Per l'assistenza clienti, premere o pronunciare 3. Per contattare un operatore, premere o pronunciare 0. Per ascoltare di nuovo questo menu, premere il tasto asterisco o pronunciare Ripeti". **Crea un messaggio personalizzato** Se scegli questa opzione, devi inserire il testo che vuoi fare leggere al sistema (fino a 1000 caratteri). **Carica un file audio** Se scegli questa opzione, dovrai registrare il messaggio di saluto e poi caricare il file audio (in formato .wav, .mp3 o .wma).
***
![Numero 4](../images/sfbcallout4.png)<br/>**Accesso esterno in base al nome** Se si sceglie questa opzione, in questo modo gli utenti che chiamare nella ricerca di utenti all'interno dell'organizzazione con ricerca nella Directory. Puoi selezionare quali persone saranno elencate come disponibili o non disponibili per Chiamata per nome definendo queste opzioni nella pagina **Ambito chiamata**. Tutti gli utenti in linea con una licenza di **Sistema telefonico** o tutti gli utenti ospitati in locale con Skype per Business Server 2015 o Lync Server 2013 possono essere trovati con Chiamata per nome.<br/><br/>  

> [!WARNING]
> Gli utenti ospitati in locale con Lync 2010 **non sono raggiungibili** con Chiamata per nome.
> ***

![Numero 5](../images/sfbcallout5.png)<br/>**Modifica opzioni di menu** Le opzioni del menu possono essere aggiunte o rimosse utilizzando i tasti della tastiera. Per aggiungere un'opzione di menu, premi il tasto corrispondente sulla tastiera. I tasti in uso cambieranno colore e sotto di essi apparirà la fila di opzioni corrispondente. Per eliminare una voce di menu, scegliere semplicemente la chiave corrispondente del controllo utilizzando il tastierino numerico per deselezionare questa chiave. La riga di mapping dei tasti verrà rimossa.<br/><br/>  **Suggerimento:** È necessario aggiornare il testo di richieste di menu o registrare l'audio separatamente, quando si aggiunge alla rimozione di opzioni in quanto non verranno eseguita automaticamente per il prompt dei comandi di menu esistenti.  <br/><br/>  Qualsiasi opzione di menu può essere aggiunte o rimosse in qualsiasi ordine e il mapping dei tasti non è necessario essere continuo. È possibile, ad esempio, per creare un menu con i tasti 0, 1 e 3 mappati alle opzioni, mentre non viene utilizzata la chiave di 2.<br/><br/> 

> [!NOTE]
> I tasti * (Ripeti) e # (Indietro) sono riservati al sistema e non possono essere riassegnati. Se è abilitato il riconoscimento vocale, premere * corrisponderà con "Ripeti" e # corrisponderà con i comandi vocali "Nuovo".


Per configurare le opzioni di menu, dopo aver selezionato dei tasti, è necessario: 
- **Immettere il nome dell'opzione** Questo può contenere un massimo di 64 caratteri e può contenere più parole come "Servizio clienti" o "operazioni e motivi". Se è abilitato il riconoscimento vocale, verrà riconosciuto automaticamente il nome e la persona chiamata sarà in grado di premere 3, dire "tre" oppure "Servizio clienti" per selezionare l'opzione mappata al tasto 3. 
- Il passaggio successivo consiste nel selezionare dove la chiamata verrà inviata se viene premuto il tasto corrispondente o se l'opzione selezionata utilizza il riconoscimento vocale. La chiamata può essere inviata a: 
    - **Operatore** Se l'operatore è già stato configurato, viene automaticamente mappato al tasto 0, ma può anche essere eliminato o riassegnato a un tasto diverso. Se l'operatore non è impostato su nessun tasto, anche il comando vocale "Operatore" verrà disabilitato. 
    - Una **Persona nell'azienda** con una licenza di **Sistema telefonico** abilitata per Enterprise Voice o con Piani di chiamata di Office 365 assegnati. Puoi impostarla in modo che la persona che chiama possa essere passata alla segreteria telefonica. A tale scopo, selezionare **persona nell'azienda** e impostare tale persona per le chiamate inoltrate direttamente alla segreteria telefonica.<br/><br/> 

        > [!Note] 
        > Una **Persona nell'azienda** può essere un utente in linea o un utente ospitato in locale con Skype per Business Server 2015 o Lync Server 2013. Lync Server 2010 non è supportato. <br/><br/>

    - **Coda di chiamata** Utilizzando una coda di chiamata puoi trasferire la chiamata a una Coda di chiamata esistente che hai configurato. 
    - **Operatore automatico** Puoi usare un operatore automatico esistente per creare un secondo livello di opzioni del menu contenente un sottomenu. Questi sono denominati operatori automatici innestati.<br/><br/>

        > [!Note]
        > Gli **Orari d'ufficio** degli operatori automatici innestati (o di secondo livello) verranno inoltre utilizzate, incluso per le chiamate inviate da altri operatori automatici che sono stati configurati.         

### <a name="select-holidays-page"></a>Pagina selezione festività 

È possibile aggiungere fino a 20 giorni festivi pianificati per ogni operatore automatico.

![Impostazione di festività per operatore automatico](../images/50a5ce88-7f39-4210-808a-da7ced969854.png)

***
![Numero 1](../images/sfbcallout1.png)<br/>**Aggiungere una festività** Immettere un nome per la nuova festività nel campo **Nome della festività**.<br/><br/> I nomi delle festività possono essere formati da un massimo di 64 caratteri e devono essere univoci per l'operatore automatico stesso. Ad esempio, è possibile avere due festività denominate "Giorno del ringraziamento" nello stesso operatore automatico.  
***
![Numero 2](../images/sfbcallout2.png)<br/>**Messaggio di saluto festività** Il messaggio di saluto festività è facoltativo e può essere impostata su **Nessuno**. In questo caso, il chiamante non udirà alcun messaggio o saluto prima che la chiamata venga gestita da una delle opzioni selezionate. È possibile caricare un file audio (nel formato con estensione wav, mp3 o .wma) o creare un messaggio di saluto personalizzato utilizzando la sintesi vocale.
*    **Nessuno** Nessun messaggio di saluto verrà riprodotto quando le persone chiamano il numero di telefono dell'operatore automatico.
*    **Crea un oggetto personalizzato messaggio di saluto** Se si sceglie questa opzione, immettere il testo che si desidera che il sistema per la lettura (fino a 1000 caratteri). Ad esempio, è possibile immettere "Buon anno! I nostri uffici sono chiusi." nella casella **I chiamanti udiranno**.
*    **Caricare un file audio** Se si sceglie questa, registrare il saluto festività e quindi caricare i file audio (in formato WAV, MP3 o. wma).  
***
![Numero 3](../images/sfbcallout3.png)<br/>**Cosa succede alle chiamate dopo il messaggio di saluto?** È possibile selezionare cosa succede alle chiamate in arrivo durante una festività. È possibile scegliere tra le opzioni seguenti:
* **Disconnettere**  La persona chiamata verrà disconnessa dopo aver ascoltato il messaggio di saluto di festività.
* **Reindirizzare una chiamata** Ciò consente di inviare automaticamente la chiamata a:
  * Una **Persona nell'azienda** con una licenza di **Sistema telefonico** abilitata per Enterprise Voice o con Piani di chiamata di Office 365 assegnati. Puoi impostarla in modo che la persona che chiama possa essere passata alla segreteria telefonica. A tale scopo, selezionare **persona nell'azienda**e impostare tale persona per le chiamate inoltrate direttamente alla segreteria telefonica. <br/><br/> 

    > [!Note] 
    > Una **Persona nell'azienda** può essere un utente in linea o un utente ospitato in locale con Skype per Business Server 2015 o Lync Server 2013. Lync Server 2010 non è supportato.<br/><br/>

  * Una **Coda di chiamata** per trasferire la chiamata a una coda esistente di chiamata che è stata configurata.
  * Un altro **Oeratore automatico**, per creare un secondo livello delle opzioni di menu che contiene un sottomenu. Questi sono denominati operatori automatici innestati. <br/><br/>

    > [!Note]
    > Per impostazione predefinita, per tutte le chiamate in arrivo per un periodo di festività impostate per essere disconnesse dopo il messaggio di saluto (se esistenti), è necessario specificare un reindirizzamento se non si desidera un comportamento diverso.

***
![Numero 4](../images/sfbcallout4.png)<br/>**Se si desidera iniziare e terminare la festività?** Immetti la data di inizio festività nel formato gg/mm/aaaa e quindi seleziona un'ora di inizio, data di fine e ora di fine, come richiesto nella tabella intervallo date.<br/><br/>È possibile specificare fino a 10 diversi intervalli di date per una festività. Ad esempio, è possibile aggiungere gli intervalli di date per le festività di Natale fino a 10 anni. Una festività può estendersi su più giorni.<br/><br/>Per aggiungere ulteriori intervalli di date alle festività (ad esempio, per l'anno successivo), fai clic su **Aggiungi un altro**e quindi immetti una nuova serie di date di inizio e fine della festività.<br/><br/>Sono inoltre supportate le festività innestate. Ad esempio, è possibile innestare più festività all'interno di un intervallo di tempo "interruzione festività": 
*    **Dal 24 dicembre tal 3 gennaio:** "Buone feste! I nostri uffici sono chiusi. Riapriremo il 4 gennaio."
*    **25 dicembre:** "Buon Natale! I nostri uffici sono chiusi. Riapriremo il 4 gennaio."
*    **Il 1° gennaio:** "Buon anno! I nostri uffici sono chiusi. Riapriremo il 4 gennaio."

Dopo aver salvato l'operatore automatico, le festività vengono visualizzate nella scheda **Festività**, in cui è possibile editare, aggiungere o modificare le impostazioni di festività.

### <a name="select-dial-scope-page"></a>Pagina Seleziona ambito di chiamata

In questa pagina, è possibile impostare gli utenti nell'organizzazione sarà elencato nella directory e disponibili per l'accesso esterno in base al nome quando una persona che chiama nell'organizzazione.

![Dial scope for searching with dial by name.](../images/1bcb185c-00db-43a7-b5c4-9b021c0627f7.png)

***
![Numero 1](../images/sfbcallout1.png)<br/>Quando usi l'opzione **Includi** hai a disposizione due opzioni:
* **Tutti gli utenti online** Questa opzione permette di includere tutte le persone dell'organizzazione nella ricerca in elenco. Tutti gli utenti in linea con una licenza di **Sistema telefonico**, nonché gli utenti ospitati in locale con Skype per Business Server 2015 o Lync Server 2013 che dispongono di piani di chiamata in Office 365, verranno elencati. 
* **Personalizzato** Se utilizzi questa opzione, puoi cercare un Gruppo di Office 365, una lista di distribuzione o un gruppo di protezione che è stata creato all'interno dell'organizzazione e gli utenti aggiunti a questo Gruppo di Office 365, lista di distribuzione o gruppo di sicurezza che sono entrambi **Utenti in linea con una licenza di Sistema telefonico** o ospitati in locale con Skype per Business Server 2015 o Lync Server 2013. È possibile aggiungere più gruppi di Office 365, liste di distribuzione e gruppi di sicurezza. <br/><br/> 

  > [!Caution]
  > Gli utenti locali di distribuzioni di Lync Server 2010 non è incluso quando un utente cerca nella directory con accesso esterno in base al nome. 
***
![Numero 2](../images/sfbcallout2.png)<br/>Utilizzo dell'opzione **escludere** , sono disponibili due opzioni:
* **Nessuno** Questa opzione indica che nessun utente online sarà escluso dalla ricerca in elenco. 
* **Personalizzato** Se si utilizza questa opzione, è possibile cercare un gruppo di Office 365, lista di distribuzione o gruppo di protezione che è stata creata nella propria organizzazione e tutti gli utenti aggiunti a questo gruppo di Office 365, lista di distribuzione o gruppi di protezione vengono esclusi dalla ricerca di directory. È possibile aggiungere più gruppi di Office 365, liste di distribuzione e gruppi di sicurezza. <br/><br/> 

  > [!Caution]
  > Gli utenti locali di distribuzioni di Lync Server 2010 non è incluso quando un utente cerca nella directory con accesso esterno in base al nome.          

> [!NOTE]
> Potrebbe richiedere fino a 36 ore a un nuovo utente a con il nome nell'elenco nella directory quando un utente utilizza Dial per nome da riconoscimento vocale. 

Dopo aver immesso tutti i campi obbligatori e impostare le opzioni di menu e di gestione delle chiamate, fare clic su **Salva**.

## <a name="editing-and-testing-auto-attendants"></a>Modifica e testare gli operatori automatici

Dopo aver salvato il tuo operatore automatico, verrà elencato nella pagina **Operatori automatici**. In questo modo è possibile visualizzare rapidamente alcune opzioni sono state impostate, inclusi il nome, numero di telefono, lingua e lo stato.

Se si desidera apportare modifiche a un operatore automatico, selezionare l'operatore automatico e quindi nel riquadro azioni fare clic su **Modifica**.

È possibile effettuare anche rapidamente una chiamata di prova per l'operatore automatico con il pulsante **Test** nel riquadro azioni.

## <a name="want-to-know-more"></a>Per saperne di più

Puoi anche utilizzare Windows PowerShell per creare e configurare gli operatori automatici.

### <a name="auto-attendant-cmdlets"></a>Cmdlet dell'operatore automatico

Questi sono i cmdlet necessari per gestire un operatore automatico.


|                                                                                                                                                               |                                                                                                                                                               |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                   [New-CsOrganizationalAutoAttendant](https://technet.microsoft.com/library/mt796493.aspx)                                    |                                [New-CsOrganizationalAutoAttendantPrompt](https://technet.microsoft.com/library/mt796484.aspx)                                 |
|                                   [Set-CsOrganizationalAutoAttendant](https://technet.microsoft.com/library/mt796486.aspx)                                    |                              [New-CsOrganizationalAutoAttendantMenuOption](https://technet.microsoft.com/library/mt796485.aspx)                               |
|                                   [Get-CsOrganizationalAutoAttendant](https://technet.microsoft.com/library/mt796482.aspx)                                    |    [Get-CsOrganizationalAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/get-csorganizationalautoattendantholidays?view=skype-ps)    |
|                                  [Remove-CsOrganizationalAutoAttendant](https://technet.microsoft.com/library/mt796492.aspx)                                  |                                 [New-CsOrganizationalAutoAttendantMenu](https://technet.microsoft.com/library/mt796488.aspx)                                  |
|                                         [New- CsOnlineAudioFile](https://technet.microsoft.com/library/mt796479.aspx)                                         |                               [New-CsOrganizationalAutoAttendantCallFlow](https://technet.microsoft.com/library/mt796489.aspx)                                |
| [Export-CsOrganizationalAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/export-csorganizationalautoattendantholidays?view=skype-ps) |                                         [New-CsOnlineTimeRange](https://technet.microsoft.com/library/mt796491.aspx)                                          |
|                    [New-CsOnlineDateTimeRange](https://docs.microsoft.com/powershell/module/skype/new-csonlinedatetimerange?view=skype-ps)                    |                                          [New-CsOnlineSchedule](https://technet.microsoft.com/library/mt796490.aspx)                                          |
|                           [Get-CsOrganizationalAutoAttendantSupportedTimeZone](https://technet.microsoft.com/library/mt796483.aspx)                           |                        [New-CsOrganizationalAutoAttendantCallHandlingAssociation](https://technet.microsoft.com/library/mt796487.aspx)                        |
|                           [Get-CsOrganizationalAutoAttendantSupportedLanguage](https://technet.microsoft.com/library/mt796481.aspx)                           | [Import-CsOrganizationalAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/import-csorganizationalautoattendantholidays?view=skype-ps) |
|                            [New-CsOrganizationalAutoAttendantCallableEntity](https://technet.microsoft.com/library/mt796480.aspx)                             |                                                                                                                                                               |

### <a name="more-about-windows-powershell"></a>Altre informazioni su Windows PowerShell

- Windows PowerShell is all about managing users and what users are allowed or not allowed to do. È possibile gestire Office 365 e Skype for Business online da un'unica risorsa di amministrazione, semplificando il lavoro quotidiano se si hanno molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedere questi argomenti:

  - [Introduzione a Windows PowerShell e Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [Sei motivi per utilizzare Windows PowerShell per gestire Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)

- Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso della sola interfaccia di amministrazione di Office 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, vedere gli argomenti seguenti:

  - [Gestire Office 365 con Windows PowerShell nel modo migliore](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [Usare Windows PowerShell per gestire Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>See also
[Ecco cosa offre il Sistema telefonico in Office 365](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[Ottenere numeri di servizio per Skype for Business e Microsoft Teams](getting-service-phone-numbers.md)

[Disponibilità di Audioconferenza e Piani per chiamate per paese e area geografica](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

[Cosa sono gli operatori automatici in Sistema telefonico](/MicrosoftTeams/what-are-phone-system-auto-attendants.md)

[Esempio di piccole e medie imprese - configurazione di un operatore automatico](tutorial-org-aa.yml)  
