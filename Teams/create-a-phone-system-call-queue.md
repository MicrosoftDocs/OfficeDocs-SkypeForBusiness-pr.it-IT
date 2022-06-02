---
title: Creare una coda di chiamata in Microsoft Teams
author: CarolynRowe
ms.author: crowe
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
description: Informazioni su come configurare code di chiamata per le organizzazioni di grandi dimensioni in Microsoft Teams, che fornisce un messaggio di saluto, tenere musica, reindirizzamento chiamate e altre funzionalità.
ms.openlocfilehash: 7678d132b8711ea828bf643201df5501323ab77e
ms.sourcegitcommit: 18a26d07a335184dbcda71908452e82a6ddc3158
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2022
ms.locfileid: "65840988"
---
# <a name="create-a-call-queue"></a>Creare una coda di chiamata

Le code di chiamata forniscono un metodo per instradare i chiamanti a persone dell'organizzazione che possono aiutare con un particolare problema o domanda. Le chiamate vengono distribuite una alla volta alle persone in coda (note come *agenti*). 

> [!TIP]
> Questo articolo è rivolto alle organizzazioni di grandi dimensioni. Se l'organizzazione è una piccola azienda, vedere [Creare una coda di chiamata - esercitazione per le piccole imprese](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb) .

Le code di chiamata forniscono:

- Messaggio di saluto.

- Musica mentre le persone sono in attesa in attesa in coda.

- Instradamento chiamate - nell'ordine *First In, First Out* (FIFO) - agli agenti.

- Gestione delle opzioni per overflow e timeout della coda.

Assicurati di aver letto [Piano per Teams operatori automatici e code di chiamata](plan-auto-attendant-call-queue.md) e segui i [passaggi iniziali](plan-auto-attendant-call-queue.md#getting-started) prima di seguire le procedure descritte in questo articolo.

**Per altre informazioni, vedere la matrice di [compatibilità delle funzionalità della coda](#call-queue-feature-compatibility) di chiamata riportata di seguito.**

## <a name="video-demonstration"></a>Dimostrazione video

Questo video mostra un esempio di base su come creare una coda di chiamata in Teams.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWCF23?autoplay=false]

## <a name="create-the-call-queue"></a>Creare la coda di chiamata

Per impostare una coda di chiamata, nell'interfaccia di amministrazione di Teams espandere **Voce**, fare clic su **Code** di chiamata e quindi su **Aggiungi**.

Digitare un nome per la coda di chiamata.

## <a name="resource-accounts"></a>Account delle risorse

![Screenshot delle impostazioni dell'account delle risorse.](media/call-queue-name-language.png)

Fare clic su **Aggiungi account**, cercare l'account della risorsa da usare con questa coda di chiamata, fare clic su **Aggiungi** e quindi su **Aggiungi**. Gli agenti vedranno il nome dell'account della risorsa quando ricevono una chiamata in arrivo.

Per altre informazioni, vedere [Gestire Teams account delle risorse](manage-resource-accounts.md).

## <a name="dynamic-caller-id"></a>ID chiamante dinamico

![Screenshot delle impostazioni dell'ID chiamata.](media/call-queue-assign-calling-id.png)

**Disponibile per Teams utenti desktop per chiamate di canale/collaborative e Teams utenti client mobili con code di chiamata standard**

È possibile assegnare numeri di ID chiamante in uscita agli agenti specificando uno o più account delle risorse con un numero di telefono. Gli agenti possono selezionare il numero ID chiamante in uscita da usare con ogni chiamata in uscita effettuata.

Fare clic su **Aggiungi**, cercare gli account delle risorse che si desidera consentire agli agenti di usare ai fini dell'ID chiamante durante le chiamate in uscita, fare clic su **Aggiungi** e quindi su **Aggiungi**.

**Code di chiamata standard**

Per Teams utenti desktop e code di chiamata standard valutare l'impostazione diretta dell'ID chiamante per i membri della coda di chiamata sul numero di servizio della coda di chiamata o dell'operatore automatico appropriato. Per altre informazioni, vedere [Gestire i criteri ID chiamante in Microsoft Teams](caller-id-policies.md).

> [!NOTE]
> L'account della risorsa usato per gli scopi dell'ID chiamante deve avere una licenza utente virtuale di sistema Telefono di Microsoft Teams e una delle seguenti assegnazioni:
>
> - Una licenza per un Piano per chiamate e un numero di telefono assegnato
> - Un numero di telefono Connessione con operatore assegnato
> - Un criterio di routing vocale online (l'assegnazione del numero di telefono è facoltativa quando si usa l'instradamento diretto)


## <a name="language"></a>Lingua

![Screenshot delle impostazioni della lingua.](media/call-queue-language.png)

Scegliere una [lingua supportata](create-a-phone-system-call-queue-languages.md). Questa lingua verrà utilizzata per i comandi vocali generati dal sistema e per la trascrizione della segreteria telefonica (se abilitata).

## <a name="greetings-and-music-on-hold-in-queue"></a>Saluti e musica in attesa in coda

![Screenshot di saluto e musica in attesa nelle impostazioni della coda.](media/call-queue-greetings-music.png)

Specificare se si vuole riprodurre un messaggio di saluto ai chiamanti quando arrivano in coda. È necessario caricare un file MP3, WAV o WMA contenente il messaggio di saluto da riprodurre. La registrazione caricata non può avere dimensioni superiori a 5 MB.

Teams fornisce musica predefinita ai chiamanti mentre sono in attesa in coda. La musica predefinita fornita nelle code di chiamata Teams è priva di royalty e a pagamento da parte dell'organizzazione. Se si vuole riprodurre un file audio specifico, scegliere **Riproduci file audio** e caricare un file MP3, WAV o WMA.

> [!NOTE]
> L'utente è responsabile in modo indipendente della cancellazione e della protezione di tutti i diritti e le autorizzazioni necessari per l'uso di musica o file audio con il servizio Microsoft Teams dell'utente, che può includere la proprietà intellettuale e altri diritti in qualsiasi musica, effetti audio, audio, marchi, nomi e altri contenuti nel file audio da tutti i titolari dei diritti pertinenti, che possono includere artisti, attori,  artisti, musicisti, cantautori, compositori, etichette discografica, editori musicali, sindacati, corporazioni, società per i diritti, organizzazioni di gestione collettiva e qualsiasi altra parte che possiede, controlla o concede in licenza i diritti di copyright musicali, effetti sonori, audio e altri diritti di proprietà intellettuale.

## <a name="call-agents"></a>Agenti di chiamata

Esaminare i [prerequisiti per l'aggiunta di agenti a una coda di chiamata](plan-auto-attendant-call-queue.md#prerequisites).

![Screenshot delle impostazioni di utenti e gruppi per le code di chiamata.](media/call-queue-users-groups.png)

##### <a name="teams-channel"></a>canale Teams

È possibile aggiungere fino a 200 agenti tramite un canale di Teams. Devi essere un membro del team o il creatore o un proprietario del canale per aggiungere un canale alla coda.

Se si vuole [usare un canale Teams per gestire la coda](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e), selezionare l'opzione **Scegli un team** e fare clic su **Aggiungi canale**. Cercare il team che si vuole usare, selezionarlo e fare clic su **Aggiungi**. Selezionare il canale da usare (sono supportati solo i canali standard) e fare clic su **Applica**. 

Quando si utilizza un canale di Teams per le code di chiamata, sono supportati i client seguenti: 

  - client Microsoft Teams Windows
  - Client Microsoft Teams Mac

> [!NOTE]
> Se si usa questa opzione, possono essere richieste fino a 24 ore prima che la coda di chiamata sia pienamente operativa.

##### <a name="users-and-groups"></a>Utenti e gruppi

È possibile aggiungere fino a 20 agenti singolarmente e fino a 200 agenti tramite gruppi.

Per aggiungere singoli utenti o gruppi alla coda, selezionare l'opzione **Scegli utenti e gruppi** . 

Per aggiungere un utente alla coda, fare clic su **Aggiungi utenti**, cercare l'utente, fare clic su **Aggiungi** e quindi su **Aggiungi**.

Per aggiungere un gruppo alla coda, fare clic su **Aggiungi gruppi**, cercare il gruppo, fare clic su **Aggiungi** e quindi su **Aggiungi**. È possibile usare liste di distribuzione, gruppi di sicurezza e gruppi di Microsoft 365 o Microsoft Teams team.

> [!NOTE]
> I nuovi utenti aggiunti a un gruppo possono richiedere fino a otto ore per l'arrivo della prima chiamata.

## <a name="call-routing"></a>Routing delle chiamate

![Screenshot delle impostazioni relative alla modalità conferenza e al metodo di routing.](media/call-queue-conference-mode-routing-method.png)

**La modalità conferenza** riduce significativamente la quantità di tempo necessaria per la connessione di un chiamante a un agente, dopo che l'agente accetta la chiamata. Per il funzionamento della modalità conferenza, gli agenti nella coda di chiamata devono utilizzare uno dei client seguenti:

  - L'ultima versione del client desktop Microsoft Teams, dell'app Android o dell'app iOS
  - Telefono di Microsoft Teams versione 1449/1.0.94.2020051601 o successiva
  
Gli account Teams agenti devono essere impostati sulla modalità di sola Teams. Gli agenti che non soddisfano i requisiti non sono inclusi nell'elenco di routing delle chiamate. È consigliabile abilitare la modalità conferenza per le code di chiamata se gli agenti usano tutti client compatibili.

> [!NOTE]
> La modalità conferenza non è supportata se le telefonate vengono instradate alla coda da un gateway di routing diretto abilitato per il routing basato sulla posizione.
>
> La modalità conferenza è necessaria se Teams utenti devono consultare/trasferire chiamate con code di chiamata.

> [!TIP]
> L'impostazione consigliata è impostare la **modalità conferenza** su **Attivato** .

**Il metodo di routing** determina l'ordine in cui gli agenti ricevono chiamate dalla coda. Scegliere una delle opzioni seguenti:

- **L'instradamento dell'operatore** squilla tutti gli agenti in coda contemporaneamente. Il primo agente di chiamata che risponde alla chiamata riceve la chiamata.

- **Il routing seriale** squilla tutti gli agenti di chiamata uno alla uno nell'ordine specificato nell'elenco **Agenti di chiamata** . Se un agente chiude o non risponde a una chiamata, la chiamata squillerà all'agente successivo. Questa operazione si ripeterà fino al momento in cui la chiamata non viene ripresa o eseguita in timeout.

- **Round robin** bilancia il routing delle chiamate in arrivo in modo che ogni agente di chiamata riceva lo stesso numero di chiamate dalla coda. Questo metodo di routing può essere auspicabile in un ambiente di vendita in ingresso per assicurare pari opportunità tra tutti gli agenti di chiamata.

- **L'inattività più lunga** indirizza ogni chiamata all'agente che è rimasto inattivo più a lungo. Un agente viene considerato inattivo se lo stato presenza è Disponibile. Gli agenti il cui stato presenza non è Disponibile non saranno idonei a ricevere chiamate fino a quando non cambieranno la presenza su Disponibile. 

> [!TIP]
> L'impostazione consigliata è Impostare **Metodo routing** su **Round robin** o **Long idle** .

> [!NOTE]
> Se la [registrazione di conformità](teams-recording-policy.md) è abilitata per gli agenti, la combinazione di **modalità conferenza** e **instradamento dell'operatore** non è supportata. Se devi usare la **modalità Conferenza**, seleziona **Routing seriale**, **Round robin** o **Long idle** come **metodo routing**. Se devi usare **il routing Attendant**, imposta **La modalità conferenza su** **Disattivato**.
> 
> Quando si utilizza **Long idle** e quando ci sono meno chiamate in coda rispetto agli agenti disponibili, solo i primi due agenti inattivi più lunghi verranno presentati con chiamate dalla coda.
> 
> Quando si utilizza **l'inattività Più lunga** , a volte un agente riceve una chiamata dalla coda poco dopo essere diventato non disponibile o un breve ritardo nella ricezione di una chiamata dalla coda dopo essere diventato disponibile.
> 
> La presentazione delle chiamate in coda di chiamata agli agenti potrebbe essere in conflitto con le restrizioni di routing basato sulla posizione. In questo caso, l'agente riceverà un avviso popup di chiamata, ma non sarà in grado di rispondere alla chiamata. Questa condizione continuerà fino a quando un altro agente non sarà disponibile a rispondere alla chiamata, il chiamante si disconnette o si verifica la condizione di timeout della coda di chiamata.  


![Screenshot delle impostazioni di routing, rifiuto esplicito e orario di avviso.](media/call-queue-presence-agents-time.png)

**Il routing basato sulla presenza** usa lo stato di disponibilità degli agenti di chiamata per determinare se un agente deve essere incluso nell'elenco di routing delle chiamate per il metodo di routing selezionato. Gli agenti di chiamata il cui stato di disponibilità è impostato su **Disponibile** sono inclusi nell'elenco di instradamento chiamate e possono ricevere chiamate. Gli agenti il cui stato di disponibilità è impostato su qualsiasi altro stato vengono esclusi dall'elenco di routing delle chiamate e non riceveranno chiamate finché lo stato di disponibilità non torna a **Disponibile**. 

È possibile abilitare il routing delle chiamate basato sulla presenza con uno qualsiasi dei metodi di routing.

Se un agente rifiuta esplicitamente di ricevere chiamate, non verrà incluso nell'elenco di routing delle chiamate, indipendentemente dallo stato di disponibilità impostato. 

> [!NOTE]
> Quando l'opzione **Inattività più lunga** è selezionata come metodo di routing, il routing basato sulla presenza è obbligatorio e abilitato automaticamente anche se l'interruttore routing basato sulla presenza sarà **disattivato** e disattivato.
>
> Se il routing basato sulla presenza non è abilitato e ci sono più chiamate in coda, il sistema presenterà contemporaneamente queste chiamate agli agenti indipendentemente dal loro stato presenza. Ciò comporta più notifiche di chiamata agli agenti, in particolare se alcuni agenti non rispondono alla chiamata iniziale presentata loro.
>
> Quando si usa il **routing basato sulla presenza** , a volte un agente riceve una chiamata dalla coda poco dopo la non disponibilità o un breve ritardo nella ricezione di una chiamata dalla coda dopo essere diventato disponibile.
> 
> Gli agenti che usano il client Skype for Business non sono inclusi nell'elenco di routing delle chiamate quando è abilitato il routing basato sulla presenza. Se ci sono agenti che usano Skype for Business, non abilitare il routing delle chiamate basato sulla presenza.

> [!TIP]
> L'impostazione consigliata è impostare **il routing basato sulla presenza su** **Attivato** .

**L'ora di avviso** dell'agente specifica per quanto tempo il telefono di un agente squillerà prima che la coda reindirizza la chiamata all'agente successivo.

> [!TIP]
> L'impostazione consigliata è impostare **l'ora di avviso dell'agente** su **20 secondi** .

> [!NOTE]
> L'impostazione [gestione timeout di chiamata](#call-timeout-handling) ha la priorità rispetto al tempo di avviso dell'agente. Se è stato raggiunto il tempo massimo in coda configurato per la gestione del timeout di chiamata, la chiamata verrà recuperata dagli agenti anche se non è stato raggiunto il limite di tempo di avviso dell'agente.

## <a name="call-overflow-handling"></a>Gestione dell'overflow delle chiamate

![Screenshot delle impostazioni di overflow delle chiamate.](media/call-queue-overflow-handling.png)

**Il numero massimo di chiamate in coda** specifica il numero massimo di chiamate che possono aspettare in coda in un determinato momento. Il valore predefinito è 50, ma può essere compreso tra 0 e 200. Quando viene raggiunto questo limite, la chiamata viene gestita come specificato dall'impostazione **Quando viene raggiunto il numero massimo di chiamate** .

È possibile scegliere di disconnettere la chiamata o reindirizzarla a una delle destinazioni di instradamento delle chiamate. È ad esempio possibile che il chiamante lasci una segreteria telefonica per gli agenti in coda. Per i trasferimenti esterni, vedere [Prerequisiti](plan-auto-attendant-call-queue.md#prerequisites) e [trasferimenti di numeri di telefono esterni - dettagli tecnici](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) per la formattazione dei numeri.

> [!NOTE]
> Se il numero massimo di chiamate è impostato su 0, il messaggio di saluto non verrà riprodotto.
>
> Quando si reindirizza alla segreteria telefonica condivisa, assicurarsi che **l'opzione Consenti alle persone esterne all'organizzazione di inviare posta elettronica a questo team** sia abilitata per il team o il gruppo nel Centro Amministrazione Microsoft 365.


## <a name="call-timeout-handling"></a>Gestione del timeout di chiamata

![Screenshot delle impostazioni di timeout delle chiamate.](media/call-queue-timeout-handling.png)

**Timeout chiamata: il tempo massimo di attesa** specifica il tempo massimo per cui una chiamata può rimanere in attesa in coda prima di essere reindirizzata o disconnessa. È possibile specificare un valore compreso tra 0 secondi e 45 minuti.

È possibile scegliere di disconnettere la chiamata o reindirizzarla a una delle destinazioni di instradamento delle chiamate. È ad esempio possibile che il chiamante lasci una segreteria telefonica per gli agenti in coda. Per i trasferimenti esterni, fare riferimento a [Prerequisiti](plan-auto-attendant-call-queue.md#prerequisites) e [trasferimenti di numeri di telefono esterni - dettagli tecnici](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) per la formattazione dei numeri.

> [!NOTE]
> Quando si reindirizza alla segreteria telefonica condivisa, assicurarsi che **l'opzione Consenti alle persone esterne all'organizzazione di inviare posta elettronica a questo team** sia abilitata per il team o il gruppo nel Centro Amministrazione Microsoft 365.

Dopo aver selezionato le opzioni di timeout delle chiamate, fare clic su **Salva**.

## <a name="summary-of-recommended-call-queue-settings"></a>Riepilogo delle impostazioni consigliate per la coda di chiamata

Sono consigliate le impostazioni seguenti:

- **Modalità conferenza** su **Attivato**
- **Metodo di routing** a **Round robin** o **Long idle**
- **Routing basato sulla presenza** su **Attivato**
- **Tempo di avviso agente:** a **20 secondi**


## <a name="call-queue-feature-compatibility"></a>Compatibilità delle funzionalità delle code di chiamata

|Funzionalità                          |Teams Desktop<sup>1</sup> |Teams Mobile<sup>2</sup> |Lync |Telefoni IP | Code di chiamata standard |Code di chiamata basate sui canali | Commento |
|:--------------------------------|:------------------------:|:-----------------------:|:---:|:--------:|:--------------------:|:------------------------:|:-------------|
|**Metodi di routing dell'agente**        |                          |                         |     |          |                      |                          |              |
|`Attendant Routing`              |S                         |S                        |S    |S         |S                     |S                         |*Predefinito*     |
|`Longest Idle`<sup>3</sup>       |S                         |S                        |N    |S         |S                     |S                         |*Consigliata* |
|`Round Robin`                    |S                         |S                        |S    |S         |S                     |S                         |*Consigliata* |
|`Serial`                         |S                         |S                        |S    |S         |Y<sup>4</sup>         |Y<sup>4</sup>             |              |
|**Opzioni routing agente**        |                          |                         |     |          |                      |                          |              |
|`Presence Based Routing`<sup>3</sup>|S                        |S                        |N    |S         |S                     |S                         |*Consigliata* |
|`Agents can Opt-out`               |S                         |S                        |Y<sup>7</sup>|Y<sup>7</sup>|S          |S                         |*Predefinito*     |
|**Modalità di trasferimento**               |                          |                         |     |          |                      |                          |              |
|`Conference Mode`<sup>5</sup>    |S                         |S                        |N    |Y<sup>6</sup>|S                  |S                         |*Consigliata* |
|`Transfer Mode`                  |S                         |S                        |S    |S         |S                     |S                         |*Predefinito*              |
|**Chiamate collaborative**        |                          |                         |     |          |                      |                          |              |
|`Channel Based Queues`             |S                         |N                        |N    |N         |n/d                   |Y<sup>8</sup>             |              |
|**ID chiamante dinamico**            |                          |                         |     |          |                      |                          |              |
|`Standard call queue`            |N                         |S                        |N    |N         |S                     |n/d                       |              |
|`Channel based call queue`       |S                         |n/d                      |n/d  |n/d       |n/d                   |S                         |              |
|**Metodi di connettività PSTN**    |                          |                         |     |          |                      |                          |Vedi Nota 10   |
|`Calling Plans`                  |S                         |S                        |S    |S         |S                     |S                         |              |
|`Direct Routing`                 |S                         |S                        |N    |N         |S                     |S                         |              |
|`Operator Connect`               |S                         |S                        |     |          |S                     |S                         |              |
|**Varie**    |                          |                         |     |          |                      |                          |Vedi Nota 10   |
|`Call toast shows Resource Account Name` |Y<sup>9</sup>       |S                        |S    |          |S                     |S                         |              |

Note:
1. client Microsoft Teams Windows, client Microsoft Teams Mac Microsoft Teams su Virtualized Desktop Infrastructure Microsoft Teams client Web.
2. Microsoft Teams iPhone'app Microsoft Teams Android.
3. Se si seleziona Inattività più lunga per il metodo di routing dell'agente, verrà automaticamente abilitato il routing basato sulla presenza.
4. Può impostare l'ordine solo quando si aggiungono singoli utenti come parte di code di chiamata standard. Quando si usa una lista di distribuzione o Teams Channel, l'ordine sarà alfabetico.
5. La modalità conferenza non è supportata se le telefonate vengono instradate alla coda da un gateway di routing diretto abilitato per il routing basato sulla posizione.
6. Microsoft Teams solo telefono.
7. Tramite la pagina portale Impostazioni utenti all'indirizzohttps://aka.ms/vmsettings
8. Sono supportati solo i canali pubblici.
9. Esclusione di Teams client Web.
10. Gli operatori automatici e le code di chiamata non possono trasferire le chiamate tra i metodi di connettività PSTN.


## <a name="supported-clients"></a>Client supportati

Per gli agenti di chiamata in una coda di chiamata sono supportati i client seguenti:

  - Skype for Business client desktop 2016 (versioni a 32 bit e a 64 bit)
  - Client desktop Lync 2013 (versioni a 32 bit e a 64 bit)
  - Tutti i modelli di telefono IP supportati per Microsoft Teams. Vedere [Ottenere telefoni per Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).
  - Client Mac Skype for Business (versione 16.8.196 e versioni successive)
  - Client Android Skype for Business (versione 6.16.0.9 e versioni successive)
  - Client iPhone Skype for Business (versione 6.16.0 e versioni successive)
  - Client Mac Skype for Business (versione 6.16.0 e versioni successive)
  - client Microsoft Teams Windows (versioni a 32 bit e a 64 bit)
  - Client Microsoft Teams Mac
  - Microsoft Teams su [Virtualized Desktop Infrastructure](/microsoftteams/teams-for-vdi) (Windows Virtual Desktop, Citrix e VMware)
  - app Microsoft Teams iPhone
  - app Microsoft Teams Android

    > [!NOTE]
    > Le code di chiamata assegnate a un numero di routing diretto non supportano Skype for Business client, client Lync o telefoni IP Skype for Business come agenti. Il client Teams è supportato solo con una [modalità di coesistenza di solo Teams](/microsoftteams/setting-your-coexistence-and-upgrade-settings).

## <a name="call-queue-cmdlets"></a>Cmdlet della coda di chiamata

Windows PowerShell consente di creare e gestire code di chiamata tramite la riga di comando in modo batch o programmatico.

I cmdlet seguenti consentono di gestire una coda di chiamata:

- [New-CsCallQueue](/powershell/module/skype/New-CsCallQueue)
- [Get-CsCallQueue](/powershell/module/skype/Get-CsCallQueue)
- [Set-CsCallQueue](/powershell/module/skype/Set-CsCallQueue)
- [Remove-CsCallQueue](/powershell/module/skype/Remove-CsCallQueue)

Per gestire gli utenti, gli account delle risorse, le licenze di Telefono di Microsoft Teams, i numeri di telefono, i file audio e la lingua supportata, sono necessari anche i seguenti cmdlet aggiuntivi, che verranno utilizzati con le code di chiamata:

Utenti/Teams

- Utenti
- - [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser)

- Teams: 
- - [Get-Team](/powershell/module/teams/Get-Team)
- - [Get-TeamChannel](/powershell/module/teams/Get-TeamChannel)

Account delle risorse:

- [New-CsOnlineApplicationInstance](/powershell/module/skype/New-CsOnlineApplicationInstance)
- [Find-CsOnlineApplicationInstance](/powershell/module/skype/Find-CsOnlineApplicationInstance)
- [Get-CsOnlineApplicationInstance](/powershell/module/skype/Get-CsOnlineApplicationInstance)
- [Set-CsOnlineApplicationInstance](/powershell/module/skype/Set-CsOnlineApplicationInstance)
- [New-CsOnlineApplicationInstanceAssociation](/powershell/module/skype/New-CsOnlineApplicationInstanceAssociation)
- [Get-CsOnlineApplicationInstanceAssociation](/powershell/module/skype/Get-CsOnlineApplicationInstanceAssociation)
- [Remove-CsOnlineApplicationInstanceAssociation](/powershell/module/skype/Remove-CsOnlineApplicationInstanceAssociation)
- [Get-CsOnlineApplicationInstanceAssociationStatus](/powershell/module/skype/Get-CsOnlineApplicationInstanceAssociationStatus)

Licenze Teams Telefono virtuali:

- [Get-MsolAccountSku](/powershell/module/msonline/get-msolaccountsku)
- [Set-MsolUserLicense](/powershell/module/msonline/set-msoluserlicense)

Telefono assegnazione di numeri:

- [Get-CsOnlineTelephoneNumber](/powershell/module/skype/Get-CsOnlineTelephoneNumber)
- [Set-CsPhoneNumberAssignment](/powershell/module/teams/Set-csphonenumberassignment)

File audio

- [Get-CsOnlineAudioFile](/powershell/module/skype/Get-CsOnlineAudioFile)
- [Import-CsOnlineAudioFile](/powershell/module/skype/Import-CsOnlineAudioFile)
- [Export-CsOnlineAudioFile](/powershell/module/skype/Export-CsOnlineAudioFile)
- [Remove-CsOnlineAudioFile](/powershell/module/skype/Remove-CsOnlineAudioFile)

Elenchi delle lingue di supporto

- [Get-CsAutoAttendantSupportedLanguage](/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage)

Per una guida dettagliata alla creazione di code di chiamata con PowerShell, vedere [Creazione di code di chiamata con i cmdlet di PowerShell](create-a-phone-system-call-queue-via-cmdlets.md)

## <a name="call-queue-diagnostic-tool"></a>Strumento di diagnostica coda di chiamata

Se sei un amministratore, puoi usare il seguente strumento di diagnostica per verificare che una coda di chiamata sia in grado di ricevere chiamate:

1. Selezionare **Esegui test** di seguito, per popolare la diagnostica nell’interfaccia Amministrazione Microsoft 365. 

   > [!div class="nextstepaction"]
   > [Esegui test: coda di chiamata Teams](https://aka.ms/TeamsCallQueueDiag)

2. Nel riquadro Esegui diagnostica immettere l'account di risorsa nel campo **Nome utente o Posta elettronica** e quindi selezionare **Esegui test**.

3. I test restituiscono i passaggi successivi migliori per risolvere eventuali configurazioni di tenant, criteri e account delle risorse per verificare che la coda di chiamata sia in grado di ricevere chiamate.

## <a name="related-topics"></a>Argomenti correlati

[Ecco cosa ottieni con Telefono di Microsoft Teams](here-s-what-you-get-with-phone-system.md)

[Ottenere numeri telefonici di servizio](getting-service-phone-numbers.md).

[Disponibilità di Audioconferenza e Piani per chiamate per Paese e area geografica](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
