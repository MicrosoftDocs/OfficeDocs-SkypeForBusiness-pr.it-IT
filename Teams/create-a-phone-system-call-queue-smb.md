---
title: Creare una coda di chiamata di Microsoft Teams
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callqueues.overview"
- Phone System - seo-marvel-apr2020
description: Informazioni su come configurare le code di chiamata in Microsoft Teams. Le code di chiamata forniscono un messaggio di saluto, tengono musica, reindirizzamento chiamate e altre funzionalità.
ms.openlocfilehash: 93bb13b5f2f34f79bc319b96969a6efc53bf8285
ms.sourcegitcommit: ae687f530d5505b96df7cb7ef4da3a36bd9afd29
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/10/2023
ms.locfileid: "69763687"
---
# <a name="create-a-microsoft-teams-call-queue"></a>Creare una coda di chiamata di Microsoft Teams 

Le code di chiamata instradano i chiamanti a persone dell'organizzazione che possono fornire assistenza per un particolare problema o domanda. Le chiamate vengono distribuite una alla volta alle persone in coda, che sono note come *agenti*.

Le code di chiamata forniscono:

- Messaggio di saluto.
- Musica mentre le persone sono in attesa in coda.
- Instradamento chiamate - nell'ordine *First In, First Out* (FIFO) - agli agenti.
- Gestione delle opzioni per overflow e timeout della coda.

Prima di seguire le procedure descritte in questo articolo, assicurarsi di aver letto [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md) e di seguire i [passaggi introduttivi](plan-auto-attendant-call-queue.md#getting-started).

## <a name="whats-new-for-call-queues-in-the-past-six-months"></a>Novità per le code di chiamata degli ultimi sei mesi

- Agosto
  - **L'aggiunta di un messaggio di saluto** (sintesi vocale) è ora supportata per il messaggio di saluto principale della coda di chiamata.
  - I controlli per **ignorare** i messaggi di sistema della segreteria telefonica vengono ora esposti durante il routing alla segreteria telefonica condivisa, che si applica anche all'aggiunta di **messaggi di saluto**.

## <a name="steps-to-create-a-call-queue"></a>Procedura per creare una coda di chiamata

La procedura per configurare una coda di chiamata include:

1. Configurare le informazioni generali
1. Impostare il saluto e la musica
1. Configurare la risposta alle chiamate
1. Scegliere e assegnare agenti
1. Impostare la gestione dell'overflow di chiamata
1. Impostare la gestione dei timeout di chiamata

I passaggi descritti in questo articolo per la creazione di code di chiamata usano l'interfaccia di amministrazione di Teams. Per istruzioni su come creare code di chiamata con PowerShell, vedere [Creazione di code di chiamata con i cmdlet di PowerShell](create-a-phone-system-call-queue-via-cmdlets.md).

## <a name="follow-these-steps-to-set-up-your-call-queue"></a>Segui questi passaggi per configurare la coda di chiamata

# <a name="step-1-general-info"></a>[Passaggio 1: Informazioni generali](#tab/general-info)

## <a name="step-1-set-up-general-information"></a>Passaggio 1: Configurare le informazioni generali

Per configurare una coda di chiamata, [nell'interfaccia di amministrazione di Teams](https://go.microsoft.com/fwlink/p/?linkid=2066851) espandere **Voce**, selezionare **Code di chiamata** e quindi selezionare **Aggiungi**.

Digitare un nome per la coda di chiamata nella casella in alto.

### <a name="add-a-resource-account"></a>Aggiungere un account della risorsa

Per aggiungere un account di risorse esistente:

1. In **Account delle risorse** selezionare il pulsante **Aggiungi** per aggiungere un account di risorsa per questa coda di chiamata.
1. Nel riquadro **Aggiungi account** cercare l'account della risorsa da aggiungere.
1. Selezionare il pulsante **Aggiungi** accanto all'account della risorsa da assegnare a questa coda di chiamata.
1. Nella parte inferiore del riquadro selezionare il pulsante **Aggiungi** .

Se è necessario creare un account di risorsa:

1. In **Account delle risorse** selezionare il pulsante **Aggiungi** per aggiungere un account di risorsa per questa coda di chiamata.
1. Nel riquadro **Aggiungi account** cercare un set di lettere per visualizzare l'elenco a discesa dei risultati.
1. Selezionare il pulsante **+ Aggiungi un account risorsa** nella parte inferiore dei risultati.
1. Nel riquadro **Aggiungi account risorse** :
    1. Digitare un **nome visualizzato** descrittivo, che sarà visibile agli agenti.
    1. Digitare un **nome utente** descrittivo per l'account della risorsa.
    1. Selezionare l'elenco a discesa **Tipo di account risorsa** e selezionare **Coda di chiamata**.
1. Nella parte inferiore del riquadro selezionare il pulsante **Salva** .
1. Nel riquadro **Account risorse** selezionare il pulsante **Aggiungi** .

Gli agenti vedranno il nome dell'account della risorsa quando ricevono una chiamata in arrivo.

Per altre informazioni, vedere [Gestire gli account delle risorse di Teams](manage-resource-accounts.md).

### <a name="assign-a-calling-id-optional"></a>Assegnare un ID chiamata (facoltativo)

**Disponibile per gli utenti desktop delle chiamate per canale/collaborazione di Teams e per gli utenti dei client mobili di Teams con code di chiamata standard.**

Assegnare numeri di ID chiamante in uscita agli agenti specificando uno o più account delle risorse con un numero di telefono. Gli agenti possono selezionare il numero ID chiamante in uscita da usare con ogni chiamata in uscita effettuata. All'interno dell'app Chiamate, gli agenti possono utilizzare il proprio numero di coda di chiamata (CQ) / Operatore automatico (AA) o il proprio direct inward dial personale (DID).

> [!NOTE]
> L'account della risorsa usato per gli scopi dell'ID chiamante deve avere una licenza **account di Telefono di Microsoft Teams risorsa** e una delle seguenti assegnazioni:
>
> - Una licenza per un Piano per chiamate e un numero di telefono assegnato
> - Numero di telefono Operator Connect assegnato
> - Un criterio di routing vocale online (l'assegnazione del numero di telefono è facoltativa quando si usa l'instradamento diretto)

1. In **Assegna ID chiamante** seleziona il pulsante **Aggiungi** .
1. Nel riquadro **Aggiungi account** cercare gli account della risorsa da consentire agli agenti di usare per scopi di ID chiamante in uscita.
1. Selezionare il pulsante **Aggiungi** accanto all'account della risorsa con un numero di telefono assegnato.
1. Selezionare il pulsante **Aggiungi** nella parte inferiore del riquadro.

Se non si ha un account della risorsa con un numero di telefono assegnato:

1. In **Account risorse** selezionare il pulsante **Aggiungi** per aggiungere un account di risorsa.
1. Nel riquadro **Aggiungi account** cercare un set di lettere per visualizzare l'elenco a discesa dei risultati.
1. Selezionare il pulsante **+ Aggiungi un account risorsa** nella parte inferiore dei risultati.
1. Nel riquadro **Aggiungi account risorse** :
    1. Digitare un **nome visualizzato** descrittivo, che sarà visibile ai destinatari della chiamata.
    1. Digitare un **nome utente** descrittivo per l'account della risorsa.
    1. Selezionare l'elenco a discesa **Tipo di account risorsa** e selezionare **Coda di chiamata**.
1. Nella parte inferiore del riquadro selezionare il pulsante **Salva** .
1. Nel riquadro **Account risorse** selezionare il pulsante **Aggiungi** .

Dopo aver creato questo nuovo account della risorsa per l'ID chiamante, sarà comunque necessario:

- Assegnare una [licenza Telefono di Microsoft Teams Account risorse di sistema](manage-resource-accounts.md#assign-a-license).
- Assegna una licenza per un piano per chiamate Microsoft, assegna un numero di telefono Operator Connect o assegna un criterio di routing vocale online per il routing diretto.
- Assegna il [numero di telefono all'account della risorsa](manage-resource-accounts.md#assign-a-phone-number), se usi il Piano per chiamate Microsoft.

### <a name="set-the-call-queue-language"></a>Impostare la lingua della coda di chiamata

Scegliere una [lingua supportata](create-a-phone-system-call-queue-languages.md).

Questa lingua verrà utilizzata per i comandi vocali generati dal sistema e per la trascrizione della segreteria telefonica, se abilitati.

Dopo aver selezionato una lingua, seleziona il pulsante **Avanti** nella parte inferiore della pagina **Aggiungi una coda di chiamata** .

# <a name="step-2-greeting-and-music"></a>[Passaggio 2: Saluto e musica](#tab/greeting-music)

## <a name="step-2-add-a-greeting-and-on-hold-music"></a>Passaggio 2: Aggiungere un messaggio di saluto e musica in attesa

*Nuovo: **l'aggiunta di un messaggio di saluto** (sintesi vocale) è ora supportata per il messaggio di saluto principale della coda di chiamata.*

Specificare se si vuole riprodurre un *messaggio di saluto* ai chiamanti quando arrivano in coda.

- Se si seleziona **Riproduci file audio**, è necessario caricare un file MP3, WAV o WMA contenente il messaggio di saluto da riprodurre. La registrazione caricata non può avere dimensioni superiori a 5 MB.

- Se selezioni **Digita un messaggio di saluto**, il sistema leggerà il testo digitato (fino a 1000 caratteri) quando la coda di chiamata risponde a una chiamata.

Teams fornisce musica predefinita ai chiamanti mentre sono *in attesa in coda*.

- La musica predefinita fornita nelle code di chiamata di Teams è gratuita di eventuali royalties pagabili dalla tua organizzazione.
- Se si vuole riprodurre un file audio specifico, scegliere **Riproduci file audio** e caricare un file MP3, WAV o WMA.

> [!NOTE]
> L'utente è responsabile in modo indipendente della cancellazione e della protezione di tutti i diritti e le autorizzazioni necessari per l'uso di musica o file audio con il servizio Microsoft Teams, che può includere la proprietà intellettuale e altri diritti in qualsiasi musica, effetti audio, audio, marchi, nomi e altri contenuti nel file audio da tutti i titolari dei diritti pertinenti, che possono includere artisti,  attori, artisti, musicisti, cantautori, compositori, etichette discografica, editori musicali, unioni, gilde, società per i diritti, organizzazioni di gestione collettiva e qualsiasi altra parte che possiede, controlla o concede in licenza i copyright musicali, gli effetti sonori, l'audio e altri diritti di proprietà intellettuale.

Dopo aver selezionato un messaggio di saluto e la musica in attesa, seleziona il pulsante **Avanti** nella parte inferiore della pagina **Aggiungi una coda di chiamata** .

# <a name="step-3-call-answering"></a>[Passaggio 3: Risposta alle chiamate](#tab/call-answering)

## <a name="step-3-set-up-who-will-answer-incoming-calls"></a>Passaggio 3: Configurare chi risponderà alle chiamate in arrivo

Esaminare i [prerequisiti per l'aggiunta di agenti a una coda di chiamata](plan-auto-attendant-call-queue.md#prerequisites).

### <a name="teams-channel"></a>Canale di Teams

È possibile aggiungere fino a 200 agenti tramite un canale di Teams. Devi essere un membro del team o il creatore o il proprietario del canale per aggiungere un canale alla coda.

Per [usare un canale di Teams per gestire la coda](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e):

1. Seleziona il pulsante **di opzione Scegli un team** e seleziona **Aggiungi un canale**.
1. Cerca il team che vuoi usare, selezionalo e seleziona **Aggiungi**.
1. Selezionare il canale da usare (sono supportati solo i canali standard o privati) e selezionare **Applica**.

I client seguenti sono supportati quando si usa un canale di Teams per le code di chiamata:

- Client Windows di Microsoft Teams
- Client Microsoft Teams Mac

> [!NOTE]
> Se si usa questa opzione, possono essere richieste fino a 24 ore prima che la coda di chiamata sia pienamente operativa.
>
> Se ci sono più di 200 membri nel team, solo i primi 200 membri, in ordine alfabetico, verranno aggiunti come agenti alla coda di chiamata.
> 
> Le chiamate verranno distribuite a tutti i membri del team anche se il canale privato ha solo un sottoinsieme di membri del team.

### <a name="users-and-groups"></a>Utenti e gruppi

È possibile aggiungere fino a 20 agenti singolarmente e fino a 200 agenti tramite gruppi.

Per aggiungere singoli utenti o gruppi alla coda:

1. Selezionare il pulsante di opzione **Scegli utenti e gruppi** .

Per **aggiungere un utente** alla coda:

1. Seleziona **Aggiungi utenti**, cerca l'utente, seleziona **Aggiungi** e quindi seleziona **Aggiungi**.

Per **aggiungere un gruppo** alla coda:

1. Seleziona **Aggiungi gruppi**, cerca il gruppo, seleziona **Aggiungi** e quindi seleziona **Aggiungi**. 
    1. È possibile usare liste di distribuzione, gruppi di sicurezza e gruppi di Microsoft 365 o team di Microsoft Teams.

> [!NOTE]
> I nuovi utenti aggiunti a un gruppo possono richiedere fino a otto ore per l'arrivo della prima chiamata.
>
> Se ci sono più di 200 membri nel gruppo, solo i primi 200 membri, in ordine alfabetico, verranno aggiunti come agenti alla coda di chiamata.

### <a name="conference-mode"></a>Modalità conferenza

**La modalità conferenza** riduce la quantità di tempo necessaria per la connessione di un chiamante a un agente dopo che l'agente accetta la chiamata. Per il funzionamento della modalità conferenza, gli agenti nella coda di chiamata devono utilizzare uno dei client seguenti:

- L'ultima versione del client desktop di Microsoft Teams, dell'app Android o dell'app iOS.
- Telefono di Microsoft Teams Versione di sistema 1449/1.0.94.2020051601 o successiva.
  
Gli account di Teams degli agenti devono essere impostati sulla `TeamsOnly` modalità. Gli agenti che non soddisfano i requisiti non sono inclusi nell'elenco di routing delle chiamate. È consigliabile abilitare la modalità conferenza per le code di chiamata se gli agenti usano client compatibili.

> [!TIP]
> L'impostazione consigliata è impostare la **modalità conferenza** su **Attivato** .

> [!NOTE]
> La modalità conferenza non è supportata per le chiamate indirizzate alla coda da un gateway di routing diretto abilitato per il routing Location-Based.
>
> La modalità conferenza non è supportata per le chiamate indirizzate alla coda da Skype for Business Server.
> 
> La modalità conferenza è necessaria se gli utenti di Teams devono consultare/trasferire chiamate con code di chiamata.
>
> Gli agenti possono sentire la musica configurata in attesa in coda per un massimo di 2 secondi quando si partecipa per la prima volta alla chiamata.
>  
> Se la [registrazione di conformità](teams-recording-policy.md) è abilitata per gli agenti, la combinazione di modalità conferenza e instradamento dell'operatore non è supportata. Se devi usare la modalità Conferenza, seleziona **Routing seriale**, **Round robin** o **Long idle** come **metodo routing**. Se devi usare il routing Attendant, imposta La modalità conferenza su **Disattivato**.

Dopo aver selezionato le opzioni di risposta alle chiamate, seleziona il pulsante **Avanti** nella parte inferiore della pagina **Aggiungi una coda di chiamata** .

# <a name="step-4-agent-selection"></a>[Passaggio 4: selezione dell'agente](#tab/agent-selection)

## <a name="step-4-select-your-agent-routing-options"></a>Passaggio 4: Selezionare le opzioni di routing dell'agente

**Il metodo di routing** determina l'ordine in cui gli agenti ricevono chiamate dalla coda.

Scegliere una delle opzioni seguenti:

- **L'instradamento dell'operatore** squilla tutti gli agenti in coda contemporaneamente. Il primo agente di chiamata che risponde alla chiamata riceve la chiamata.

- **Il routing seriale** squilla tutti gli agenti di chiamata uno alla uno nell'ordine specificato nell'elenco **Agenti di chiamata** . Se un agente chiude o non risponde a una chiamata, la chiamata squillerà all'agente successivo. Questa operazione si ripeterà fino al momento in cui la chiamata non viene ripresa o eseguita in timeout.

- **Round robin** bilancia il routing delle chiamate in arrivo in modo che ogni agente di chiamata riceva lo stesso numero di chiamate dalla coda. Questo metodo di routing può essere auspicabile in un ambiente di vendita in ingresso per assicurare pari opportunità tra tutti gli agenti di chiamata.

- **L'inattività più lunga** indirizza ogni chiamata all'agente che è rimasto inattivo più a lungo. Un agente viene considerato inattivo se lo stato presenza è Disponibile. Gli agenti il cui stato presenza non è Disponibile non saranno idonei a ricevere chiamate fino a quando non cambieranno la presenza su Disponibile.

> [!TIP]
> L'impostazione consigliata è Impostare **routing Method** su **Round robin** o **Longest idle** .

> [!NOTE]
> Se la [registrazione di conformità](teams-recording-policy.md) è abilitata per gli agenti, la combinazione di **modalità conferenza** e **instradamento dell'operatore** non è supportata. Se devi usare la **modalità Conferenza**, seleziona **Routing seriale**, **Round robin** o **Long idle** come **metodo routing**. Se devi usare **il routing Attendant**, imposta **La modalità conferenza su** **Disattivato**.
>
> Quando si utilizza **Long idle** e quando ci sono meno chiamate in coda rispetto agli agenti disponibili, solo i primi due agenti inattivi più lunghi verranno presentati con chiamate dalla coda.
>
> Quando si usa **l'inattività più lunga**, a volte un agente riceve una chiamata dalla coda poco dopo la non disponibilità o un breve ritardo nella ricezione di una chiamata dalla coda dopo essere diventato disponibile.
>
> La presentazione delle chiamate in coda di chiamata agli agenti potrebbe essere in conflitto con le restrizioni di routing basato sulla posizione. In questo caso, l'agente riceverà un avviso popup di chiamata, ma non sarà in grado di rispondere alla chiamata. Questa condizione continuerà fino a quando un altro agente non sarà disponibile a rispondere alla chiamata, il chiamante si disconnette o si verifica la condizione di timeout della coda di chiamata.  

### <a name="presence-based-call-routing"></a>Routing delle chiamate basato sulla presenza

**Il routing delle chiamate basato sulla presenza** usa lo stato di disponibilità degli agenti di chiamata per determinare se un agente deve essere incluso nell'elenco di instradamento delle chiamate per il metodo di routing selezionato.

Gli agenti di chiamata il cui stato di disponibilità è impostato su **Disponibile** sono inclusi nell'elenco di instradamento chiamate e possono ricevere chiamate. Gli agenti il cui stato di disponibilità è impostato su qualsiasi altro stato vengono esclusi dall'elenco di routing delle chiamate e non riceveranno chiamate finché lo stato di disponibilità non torna a **Disponibile**.

È possibile abilitare **il routing delle chiamate basato sulla presenza** con uno qualsiasi dei metodi di routing.

Se un agente rifiuta esplicitamente di ricevere chiamate, non verrà incluso nell'elenco di routing delle chiamate, indipendentemente dallo stato di disponibilità impostato.

> [!TIP]
> L'impostazione consigliata è impostare il **routing basato sulla presenza su** **Attivato** .

> [!NOTE]
> Quando l'opzione **Inattività più lunga** è selezionata come metodo di routing, il routing basato sulla presenza è obbligatorio e abilitato automaticamente anche se l'interruttore routing basato sulla presenza sarà **disattivato** e disattivato.
>
> Se il routing basato sulla presenza non è abilitato e sono presenti più chiamate in coda, il sistema presenterà contemporaneamente queste chiamate agli agenti indipendentemente dal loro stato presenza. Questa azione genererà notifiche di chiamata multiple agli agenti, in particolare se alcuni agenti non rispondono alla chiamata iniziale presentata.
>
> Quando si usa il **routing basato sulla presenza**, a volte un agente riceve una chiamata dalla coda poco dopo la non disponibilità o un breve ritardo nella ricezione di una chiamata dalla coda dopo essere diventato disponibile.
>
> Gli agenti che usano il client Skype for Business non sono inclusi nell'elenco di routing delle chiamate quando è abilitato il routing basato sulla presenza. Se ci sono agenti che usano Skype for Business, non abilitare il routing delle chiamate basato sulla presenza.

### <a name="call-agents-can-opt-out-of-taking-calls"></a>Gli agenti di chiamata possono rifiutare esplicitamente di effettuare chiamate

È possibile specificare se gli agenti di chiamata possono o meno rifiutare esplicitamente di effettuare chiamate.

È consigliabile attivare **Gli agenti di chiamata possono rifiutare esplicitamente di effettuare chiamate**.

### <a name="agent-alert-time"></a>Ora avviso agente

**L'ora di avviso** dell'agente specifica per quanto tempo il telefono di un agente squillerà prima che la coda reindirizza la chiamata all'agente successivo.

> [!TIP]
> L'impostazione consigliata prevede l'impostazione di impostare **l'ora di avviso dell'agente** su un minimo di **20 secondi** .

Dopo aver selezionato le opzioni di routing delle chiamate dell'agente, seleziona il pulsante **Avanti** nella parte inferiore della pagina **Aggiungi una coda di chiamata** .

# <a name="step-5-call-overflow"></a>[Passaggio 5: Overflow chiamata](#tab/call-overflow)

## <a name="step-5-set-how-to-handle-call-overflow"></a>Passaggio 5: Impostare come gestire l'overflow delle chiamate

**Il numero massimo di chiamate in coda** specifica il numero massimo di chiamate che possono aspettare in coda in un determinato momento.

Il valore predefinito è 50, ma può essere compreso tra 0 e 200.

Quando viene raggiunto questo limite, la chiamata viene gestita come specificato dall'impostazione **Quando viene raggiunto il numero massimo di chiamate** .

È possibile scegliere di **disconnettere** la chiamata o **reindirizzarla** a una delle destinazioni di instradamento delle chiamate.

È ad esempio possibile che il chiamante lasci una segreteria telefonica per gli agenti in coda.

*Nuovo: i controlli per **ignorare** i messaggi di sistema della segreteria telefonica vengono ora esposti durante il routing alla segreteria telefonica condivisa, che si applica anche all'aggiunta di **messaggi di saluto** .*

Per i trasferimenti esterni, vedere [Prerequisiti](./plan-auto-attendant-call-queue.md#prerequisites) e [trasferimenti di numeri di telefono esterni - dettagli tecnici](create-a-phone-system-auto-attendant.md?tabs=additional-resources) per la formattazione dei numeri.

> [!NOTE]
> Se il numero massimo di chiamate è impostato su 0, il messaggio di saluto non verrà riprodotto.
> 
> La segreteria telefonica (personale) invierà chiamate all'utente e non direttamente alla segreteria telefonica come indicato. Questo argomento è in fase di analisi da parte del supporto tecnico.

Dopo aver selezionato le opzioni di gestione dell'overflow delle chiamate, seleziona il pulsante **Avanti** nella parte inferiore della pagina **Aggiungi una coda di chiamata** .

# <a name="step-6-call-timeout"></a>[Passaggio 6: Timeout chiamata](#tab/call-timeout)

## <a name="step-6-set-how-to-handle-call-timeouts"></a>Passaggio 6: Impostare come gestire i timeout delle chiamate

**Timeout chiamata: il tempo massimo di attesa** specifica il tempo massimo per cui una chiamata può rimanere in attesa in coda prima di essere reindirizzata o disconnessa.

È possibile specificare un valore compreso tra 0 secondi e 45 minuti.

È possibile scegliere di **disconnettere** la chiamata o **reindirizzarla** a una delle destinazioni di instradamento delle chiamate.

È ad esempio possibile che il chiamante lasci una segreteria telefonica per gli agenti in coda.

*Nuovo: i controlli per **ignorare** i messaggi di sistema della segreteria telefonica vengono ora esposti durante il routing alla segreteria telefonica condivisa, che si applica anche all'aggiunta di **messaggi di saluto** .*

Per i trasferimenti esterni, vedere [Prerequisiti](./plan-auto-attendant-call-queue.md#prerequisites) e [trasferimenti di numeri di telefono esterni - dettagli tecnici](create-a-phone-system-auto-attendant.md?tabs=additional-resources) per la formattazione dei numeri.

> [!NOTE]
> La segreteria telefonica (personale) invierà chiamate all'utente e non direttamente alla segreteria telefonica come indicato. Questo argomento è in fase di analisi da parte del supporto tecnico.

Dopo aver selezionato le opzioni di gestione dei timeout di chiamata, selezionare il pulsante **Invia** nella parte inferiore della pagina **Aggiungi una coda di chiamata** .

---

## <a name="resources-for-complex-scenarios"></a>Risorse per scenari complessi

### <a name="summary-of-recommended-call-queue-settings"></a>Riepilogo delle impostazioni consigliate per la coda di chiamata

Sono consigliate le impostazioni seguenti:

- **Modalità conferenza** su **Attivato**
- **Metodo di routing** a **Round robin** o **Long idle**
- **Routing basato sulla presenza** su **Attivato**
- **Tempo di avviso dell'agente:** almeno **20 secondi**

### <a name="call-queue-feature-compatibility"></a>Compatibilità delle funzionalità delle code di chiamata

|Funzionalità                          |Teams Desktop<sup>1</sup> |Teams Web | Teams Mobile<sup>2</sup> |Skype for Business |Telefoni IP | Code di chiamata standard |Code di chiamata basate sui canali | Commento |
|:--------------------------------|:------------------------:|:--------:|:--------------:|:---:|:--------:|:--------------------:|:------------------------:|:--------|
|**Metodi di routing dell'agente**        |                          |          |                |     |          |                      |                          |   |
|`Attendant Routing`              |S                         |S         |S               |S    |S         |S                     |S                         |*Predefinito*     |
|`Longest Idle`<sup>3</sup>       |S                         |S         |S               |N    |S         |S                     |S                         |*Consigliata* |
|`Round Robin`                    |S                         |S         |S               |S    |S         |S                     |S                         |*Consigliata* |
|`Serial`                         |S                         |S         |S               |S    |S         |Y<sup>4</sup>         |Y<sup>4</sup>             |   |
|**Opzioni routing agente**        |                          |          |                |     |          |                      |                          |   |
|`Presence Based Routing`<sup>3</sup>|S                      |S         |S               |N    |S         |S                     |S                         |*Predefinito* |
|`Agents can Opt-out`               |S                       |S         |S               |Y<sup>7</sup>|Y<sup>7</sup>|S          |S                         |*Predefinito*     |
|**Modalità di trasferimento**               |                          |          |                |     |          |                      |                          |   |
|`Conference Mode`<sup>5</sup>    |S                         |S         |S               |N    |Y<sup>6</sup>|S                  |S                         |*Predefinito* |
|`Transfer Mode`                  |S                         |S         |S               |S    |S         |S                     |S                         |   |
|**Chiamate collaborative**        |                          |          |                |     |          |                      |                          |   |
|`Channel Based Queues`             |S                       |N         |N               |N    |N         |n/d                   |Y<sup>8</sup>             |   |
|**ID chiamante dinamico**            |                          |          |                |     |          |                      |                          |   |
|`Standard call queue`            |S                         |S         |S               |N    |N         |S                     |n/d                       |   |
|`Channel based call queue`       |S                         |n/d       |n/d             |n/d  |n/d       |n/d                   |S                         |   |
|**Metodi di connettività PSTN**    |                          |          |                |     |          |                      |                          |Vedere la nota 9   |
|`Calling Plans`                  |S                         |S         |S               |S    |S         |S                     |S                         |   |
|`Direct Routing`                 |S                         |S         |S               |N    |S         |Y<sup>6</sup>         |S                         |   |
|`Operator Connect`               |S                         |S         |S               |     |S         |Y<sup>6</sup>         |S                         |   |
|**Varie**                |                          |          |                |     |          |                      |                          |   |
|`Call toast shows Resource Account Name` |S                 |N         |S               |S    |          |S                     |S                         |              |

#### <a name="notes"></a>Note

1. Client Windows di Microsoft Teams, client Mac di Microsoft Teams, Microsoft Teams sull'infrastruttura desktop virtualizzata.
2. App Microsoft Teams per iPhone, app Microsoft Teams per Android.
3. Se si seleziona Inattività più lunga per il metodo di routing dell'agente, verrà automaticamente abilitato Presence-Based Routing.
4. Non è possibile impostare l'ordine in cui verranno chiamati gli agenti.
5. La modalità conferenza non è supportata se le telefonate vengono instradate alla coda da un gateway di routing diretto abilitato per Location-Based Routing.
6. Telefono di Microsoft Teams Solo sistema.
7. Tramite la pagina portale delle impostazioni utente all'indirizzo [https://aka.ms/vmsettings](https://aka.ms/vmsettings).
- GCCH: [https://dialin.cpc.gov.teams.microsoft.us/usp](https://dialin.cpc.gov.teams.microsoft.us/usp).
- DOD: [https://dialin.cpc.dod.teams.microsoft.us/usp](https://dialin.cpc.dod.teams.microsoft.us/usp).
8. Sono supportati solo i canali pubblici.
9. Gli operatori automatici e le code di chiamata non possono trasferire le chiamate tra i metodi di connettività PSTN.

### <a name="supported-clients"></a>Client supportati

Per gli agenti di chiamata in una coda di chiamata sono supportati i client seguenti:

- Skype for Business client desktop 2016 (versioni a 32 bit e a 64 bit).
- Client desktop Lync 2013 (versioni a 32 bit e a 64 bit).
- Tutti i modelli di telefono IP supportati per Microsoft Teams. Vedere [Ottenere telefoni per Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).
- Mac Skype for Business Client (versione 16.8.196 e successive).
- Client Android Skype for Business (versione 6.16.0.9 e successive).
- iPhone Skype for Business Client (versione 6.16.0 e successive).
- iPad Skype for Business Client (versione 6.16.0 e successive).
- Client Windows di Microsoft Teams (versioni a 32 bit e a 64 bit).
- Client Mac di Microsoft Teams.
- Microsoft Teams su [Virtualized Desktop Infrastructure](teams-for-vdi.md) (Windows Virtual Desktop, Citrix e VMware).
- App Microsoft Teams per iPhone.
- App Microsoft Teams per Android.

> [!NOTE]
> Le code di chiamata assegnate a un numero di routing diretto non supportano Skype for Business client, client Lync o telefoni IP Skype for Business come agenti. Il client Teams è supportato solo con una [modalità di coesistenza di Solo Teams](setting-your-coexistence-and-upgrade-settings.md).

### <a name="call-queue-diagnostic-tool"></a>Strumento di diagnostica coda di chiamata

Se sei un amministratore, puoi usare il seguente strumento di diagnostica per verificare che una coda di chiamata sia in grado di ricevere chiamate:

1. Selezionare **Esegui test** di seguito, che popola la diagnostica nel interfaccia di amministrazione di Microsoft 365.

   > [!div class="nextstepaction"]
   > [Esecuzione dei test: coda di chiamata di Teams](https://aka.ms/TeamsCallQueueDiag)

2. Nel riquadro Di diagnostica Esegui immettere l'account della risorsa nel campo **Nome utente o Email** e quindi selezionare **Esegui test**.

3. I test restituiscono i passaggi successivi migliori per risolvere eventuali configurazioni di tenant, criteri e account delle risorse per verificare che la coda di chiamata sia in grado di ricevere chiamate.

### <a name="related-articles"></a>Articoli correlati

[Ecco cosa ottieni con Telefono di Microsoft Teams System](here-s-what-you-get-with-phone-system.md)

[Ottenere numeri telefonici di servizio](getting-service-phone-numbers.md).

[Disponibilità di Audioconferenza e Piani per chiamate per Paese e area geografica](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
