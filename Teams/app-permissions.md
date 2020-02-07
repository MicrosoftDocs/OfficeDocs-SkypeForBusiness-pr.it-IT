---
title: Autorizzazioni e considerazioni sulle app di Microsoft Teams
author: rmw2890
ms.author: rowille
manager: serdars
ms.date: 06/27/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-voice
- M365-collaboration
search.appverid: MET150
ms.reviewer: rowille
description: Informazioni sulle app per i dati e le autorizzazioni richieste dall'organizzazione.
f1.keywords:
- NOCSH
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5d7548d4d162310bc239c752e2bce38e725008f9
ms.sourcegitcommit: 8e2fa7b744d0a174b699ae7298d4688b971eeff3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/07/2020
ms.locfileid: "41845227"
---
# <a name="microsoft-teams-apps-permissions-and-considerations"></a>Autorizzazioni e considerazioni sulle app di Microsoft Teams

Le app di Microsoft teams sono un modo per aggregare una o più funzionalità in un _pacchetto dell'app_ che può essere installato, aggiornato e disinstallato. Le funzionalità includono:

- Bot
- Estensioni della messaggistica
- Schede
- Connettori

Le app vengono consentite dagli utenti e gestite da una prospettiva politica. Tuttavia, per la maggior parte, le autorizzazioni e il profilo di rischio di un'app sono definiti dalle autorizzazioni e dai profili di rischio delle funzionalità contenute nell'app. Questo articolo si basa quindi sulle autorizzazioni e sulle considerazioni a livello di funzionalità.

Le autorizzazioni elencate di seguito in lettere maiuscole, ad esempio RECEIVE_MESSAGE e REPLYTO_MESSAGE, non vengono visualizzate in un punto qualsiasi della [documentazione dello sviluppatore di Microsoft teams](https://aka.ms/teamsdevdocs) o delle [autorizzazioni per Microsoft Graph](https://developer.microsoft.com/graph/docs/concepts/permissions_reference). Sono semplicemente una scorciatoia descrittiva ai fini di questo articolo.


|    |     |
|-----------|------------|
| ![Icona che descrive un punto decisionale](media/audio_conferencing_image7.png) <br/>Punto decisionale|<ul><li>Usare le tabelle seguenti come guida per individuare le autorizzazioni richieste dalle app che si stanno esaminando.</li></ul> |
| ![Icona che descrive il passaggio successivo](media/audio_conferencing_image9.png)<br/>Passaggio successivo|<ul><li>Eseguire ricerche nell'app o nel servizio stesso per decidere se si vuole consentire l'accesso all'interno dell'organizzazione. Ad esempio, i bot inviano e ricevono messaggi dagli utenti e, ad eccezione dei bot line-of-business aziendali, sono situati al di fuori del limite di conformità. Di conseguenza, qualsiasi app che includa un bot richiede le autorizzazioni e ha il profilo di rischio, come minimo. </li></ul>|

## <a name="global-app-permissions-and-considerations"></a>Autorizzazioni e considerazioni sulle app globali

### <a name="required-permissions"></a>Autorizzazioni necessarie

Nessuno

### <a name="optional-permissions"></a>Autorizzazioni facoltative

Nessuno

### <a name="considerations"></a>Considerazioni

Un'app deve rivelare i dati che usa e i dati usati per i collegamenti alle condizioni d'uso e ai criteri di privacy.</td>

## <a name="bots-and-messaging-extensions"></a>Bot e estensioni di messaggistica

### <a name="required-permissions"></a>Autorizzazioni necessarie

- RECEIVE_MESSAGE, REPLYTO_MESSAGE. Il bot può ricevere messaggi dagli utenti e rispondere. <sup>1</sup>

- POST_MESSAGE_USER. Dopo che un utente ha inviato un messaggio a un bot, il bot può inviare i messaggi diretti dell'utente (detti anche *messaggi proattivi* in qualsiasi momento.

- GET_CHANNEL_LIST. I bot aggiunti ai team possono ottenere un elenco di nomi e ID dei canali in un team.

### <a name="optional-permissions"></a>Autorizzazioni facoltative

- Identità. Quando viene usato in un canale, i bot dell'app possono accedere alle informazioni di base sulle identità dei membri del team (nome, cognome, nome dell'entità utente [UPN], indirizzo di posta elettronica); Quando viene usata in una chat personale o di gruppo, il bot può accedere alle stesse informazioni per gli utenti.

- POST_MESSAGE_TEAM. Consente ai bot di un'app di inviare messaggi diretti (proattivi) a qualsiasi membro del team in qualsiasi momento, anche se l'utente non ha mai parlato con il bot prima.

- Le autorizzazioni seguenti non sono esplicite, ma sono implicite in RECEIVE_MESSAGE e REPLYTO_MESSAGE e gli ambiti in cui possono essere usati i bot, dichiarati nel manifesto:
 
    - RECEIVE_MESSAGE_PERSONAL REPLYTO_MESSAGE_PERSONAL
    - RECEIVE_MESSAGE_GROUPCHAT REPLYTO_MESSAGE_GROUPCHAT
    - RECEIVE_MESSAGE_TEAM REPLYTO_MESSAGE_TEAM

- SEND_FILES, RECEIVE_FILES. <sup>2</sup> controlla se un bot può inviare e ricevere file in chat personali (non ancora supportati per la chat di gruppo o i canali).

### <a name="considerations"></a>Considerazioni

- I bot hanno accesso solo ai team a cui sono stati aggiunti o agli utenti che li hanno installati.

- I bot ricevono solo i messaggi in cui sono menzionati esplicitamente dagli utenti. Questi dati lasciano la rete aziendale.

- I bot possono solo rispondere alle conversazioni in cui sono menzionati.

- Dopo che un utente ha conversato con un bot, se il bot archivia l'ID dell'utente, può inviare messaggi diretti dall'utente in qualsiasi momento.

- È teoricamente possibile che i messaggi di bot contengano collegamenti a siti di phishing o malware, ma i bot possono essere bloccati dall'utente, dall'amministratore del tenant o globalmente da Microsoft.

- Un bot può recuperare (e potrebbe archiviare) informazioni di identità molto basilari per i membri del team a cui è stata aggiunta l'app o per singoli utenti in chat personali o di gruppo. Per ottenere altre informazioni su questi utenti, il bot deve richiedere l'accesso a Azure Active Directory (Azure AD)

- I bot possono recuperare (e potrebbero archiviare) l'elenco dei canali in un team; questi dati lasciano la rete aziendale.

- Quando un file viene inviato a un bot, il file esce dalla rete aziendale. L'invio e la ricezione di file richiede l'approvazione dell'utente per ogni file. 

- Per impostazione predefinita, i bot non hanno la possibilità di agire per conto dell'utente, ma i bot possono chiedere agli utenti di effettuare l'accesso; non appena l'utente accede, il bot avrà un token di accesso con cui può eseguire altre operazioni. Esattamente ciò che questi elementi aggiuntivi dipendono dal bot e dalla posizione in cui l'utente accede: un bot è un'app Azure AD registrata https://apps.dev.microsoft.com/ e può avere un proprio set di autorizzazioni.

- I bot vengono informati ogni volta che gli utenti vengono aggiunti o eliminati da un team.

- I bot non vedono gli indirizzi IP degli utenti o altre informazioni sul referrer. Tutte le informazioni provengono da Microsoft. (C'è un'eccezione: se un bot implementa la propria esperienza di accesso, l'interfaccia utente di accesso vedrà gli indirizzi IP degli utenti e le informazioni sul referrer).

- Le estensioni della messaggistica, invece, vedono gli indirizzi IP degli utenti e le informazioni sul referrer.

- Le linee guida per le app (e il processo di revisione di AppSource) richiedono discrezionalità nella pubblicazione di messaggi di chat personali agli utenti (tramite l'autorizzazione POST_MESSAGE_TEAM) per scopi validi. In caso di abuso, gli utenti possono bloccare il bot, gli amministratori del tenant possono bloccare l'app e Microsoft può bloccare i bot centralmente, se necessario.

<sup>1</sup> alcuni bot inviano solo messaggi (POST_MESSAGE_USER). Si chiamano bot "solo notifica", ma il termine non fa riferimento a ciò che un bot è autorizzato o non può fare, ma significa che il bot non vuole esporre un'esperienza di conversazione. Teams USA questo campo per disabilitare la funzionalità nell'interfaccia utente che verrebbe normalmente abilitata; il bot non è limitato in ciò che è consentito eseguire rispetto ai bot che espongono un'esperienza di conversazione.

<sup>2</sup> regolato dalla proprietà booleana supportsFiles sull'oggetto bot nel file manifest. JSON per l'app.

> [!NOTE]
> Se un bot ha un proprio accesso, la prima volta che l'utente accede a un'esperienza di consenso diversa è la seconda:
>
>Attualmente, le autorizzazioni di Azure AD associate a qualsiasi funzionalità all'interno di un'app Teams (bot, TAB, Connector o Messaging Extension) sono completamente separate dalle autorizzazioni per i team elencate qui.

## <a name="tabs"></a>Schede

Una scheda è un sito Web che si trova all'interno di teams.

### <a name="required-permissions"></a>Autorizzazioni necessarie

SEND_AND_RECEIVE_WEB_DATA

### <a name="optional-permissions"></a>Autorizzazioni facoltative

Nessuno (attualmente)

### <a name="considerations"></a>Considerazioni

- Il profilo di rischio per una tabulazione è quasi identico a quello stesso sito Web in uso in una scheda del browser. 

- Una scheda ottiene anche il contesto in cui è in corso, incluso il nome di accesso e l'UPN dell'utente corrente, l'ID oggetto di Azure AD per l'utente corrente, l'ID del gruppo Office 365 in cui risiede (se si tratta di un team), l'ID tenant e le impostazioni locali correnti dell'utente. Tuttavia, per eseguire il mapping di questi ID alle informazioni di un utente, la scheda dovrebbe rendere l'accesso dell'utente ad Azure AD.

## <a name="connectors"></a>Connettori

Un connettore invia i messaggi a un canale quando si verificano gli eventi in un sistema esterno.

### <a name="required-permissions"></a>Autorizzazioni necessarie

POST_MESSAGE_CHANNEL

### <a name="optional-permissions"></a>Autorizzazioni facoltative

REPLYTO_CONNECTOR_MESSAGE. Alcuni connettori supportano i messaggi di azione, che consentono agli utenti di inserire risposte mirate al messaggio del connettore, ad esempio aggiungendo una risposta a un problema di GitHub o aggiungendo una data a una scheda Trello.

### <a name="considerations"></a>Considerazioni

- Il sistema che invia messaggi di connettore non conosce chi sta inviando o chi riceve i messaggi: non vengono divulgate informazioni sul destinatario. (Microsoft è il destinatario effettivo, non il tenant; Microsoft esegue il post effettivo sul canale.

- Nessun dato esce dalla rete aziendale quando i messaggi del connettore vengono inseriti in un canale.

- I connettori che supportano i messaggi actionable (REPLYTO_CONNECTOR_MESSAGE autorizzazione) non vedono inoltre l'indirizzo IP e le informazioni sul referrer; Queste informazioni vengono inviate a Microsoft e quindi instradate agli endpoint HTTP precedentemente registrati con Microsoft nel portale dei connettori.

- Ogni volta che un connettore è configurato per un canale, viene creato un URL univoco per l'istanza del connettore. Se l'istanza del connettore viene eliminata, l'URL non può più essere usato.

- I messaggi del connettore non possono contenere file allegati.

- L'URL dell'istanza del connettore deve essere considerato segreto/riservato: chiunque disponga di tale URL può inserire un post, ad esempio un indirizzo di posta elettronica. C'è quindi qualche rischio di spam o collegamenti a siti di phishing o malware. Se ciò dovesse accadere, i proprietari del team possono eliminare l'istanza del connettore.

- Se il servizio che invia i messaggi del connettore dovesse essere compromesso e iniziare a inviare collegamenti di posta indesiderata/phishing/malware, un amministratore del tenant può impedire la creazione di nuove istanze di connettori e Microsoft può bloccarle centralmente.

> [!NOTE]
> Attualmente non è possibile sapere quali connettori supportano i messaggi di azione (REPLYTO_CONNECTOR_MESSAGE autorizzazione).

## <a name="outgoing-webhooks"></a>Webhook in uscita

I *webhook in uscita* vengono creati al volo dai proprietari o dai membri del team. Non sono funzionalità delle app Teams; Queste informazioni sono incluse per la completezza.

### <a name="required-permissions"></a>Autorizzazioni necessarie

RECEIVE_MESSAGE, REPLYTO_MESSAGE. Può ricevere messaggi dagli utenti e rispondere.

### <a name="optional-permissions"></a>Autorizzazioni facoltative

Nessuno

### <a name="considerations"></a>Considerazioni

- I webhook in uscita sono simili ai bot, ma hanno meno privilegi. Devono essere esplicitamente menzionati, proprio come i bot.

- Quando viene registrato un webhook in uscita, viene generato un segreto, che consente al webhook in uscita di verificare che il mittente sia Microsoft teams in contrapposizione a un utente malintenzionato. Questo segreto deve rimanere segreto; chiunque abbia accesso può rappresentare Microsoft teams. Se il segreto è compromesso, il webhook in uscita può essere eliminato e ricreato e verrà generato un nuovo segreto.

- Anche se è possibile creare un webhook in uscita che non convalidi il segreto, è consigliabile sconsigliarlo.

- Oltre a ricevere e rispondere ai messaggi, i webhook in uscita non possono fare molto: non possono inviare messaggi in modo proattivo, non possono inviare o ricevere file, ma non possono fare altro che i bot possano fare tranne che per ricevere e rispondere ai messaggi.
