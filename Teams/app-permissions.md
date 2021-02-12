---
title: Autorizzazioni e considerazioni sulle app Microsoft Teams
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
description: L'amministratore può conoscere i dati e le autorizzazioni che le app di Microsoft Teams richiedono all'organizzazione.
f1.keywords:
- NOCSH
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 295bee65120e3c349efe1aa5fbc1e7b42c8da87a
ms.sourcegitcommit: 1db39fde090809d9abc6d7346dda55814d88993a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/23/2020
ms.locfileid: "48739384"
---
# <a name="microsoft-teams-apps-permissions-and-considerations"></a>Autorizzazioni e considerazioni sulle app Microsoft Teams

Le app di Microsoft Teams consentono di aggregare una o più funzionalità in un pacchetto _dell'app_ che può essere installato, aggiornato e disinstallato. Le funzionalità includono:

- Bot
- Estensioni per la messaggistica
- Schede
- Connettori

Le app sono autorizzate dagli utenti e gestite dal personale IT dal punto di vista dei criteri. Nella maggior parte dei casi, tuttavia, le autorizzazioni e il profilo di rischio di un'app sono definiti dalle autorizzazioni e dai profili di rischio delle funzionalità contenute nell'app. Di conseguenza, questo articolo è in particolare sulle autorizzazioni e considerazioni a livello di funzionalità.

Le autorizzazioni elencate di seguito in maiuscolo, ad esempio RECEIVE_MESSAGE e REPLYTO_MESSAGE, non compaiono in nessuna parte della documentazione per sviluppatori di [Microsoft Teams](https://aka.ms/teamsdevdocs) o delle autorizzazioni per [Microsoft Graph.](https://developer.microsoft.com/graph/docs/concepts/permissions_reference) Si tratta semplicemente di un'abbreviazione descrittiva dello scopo di questo articolo.


| Titolo   | Descrizione    |
|-----------|------------|
| ![Icona che descrive un punto decisionale](media/audio_conferencing_image7.png) <br/>Punto di decisione|<ul><li>Usare le tabelle seguenti come guida per determinare quali autorizzazioni vengono richieste dall'app che si sta esaminando.</li></ul> |
| ![Icona che descrive il passaggio successivo](media/audio_conferencing_image9.png)<br/>Passaggio successivo|<ul><li>Eseguire una ricerca nell'app o nel servizio stesso per decidere se consentire l'accesso all'app o al servizio stesso all'interno dell'organizzazione. Ad esempio, i bot inviano e ricevono messaggi dagli utenti e, ad eccezione dei bot personalizzati aziendali, si trovano al di fuori del limite di conformità. Di conseguenza, qualsiasi app che include un bot richiede tali autorizzazioni e ha almeno quel profilo di rischio. </li></ul>|

## <a name="global-app-permissions-and-considerations"></a>Considerazioni e autorizzazioni per le app globali

### <a name="required-permissions"></a>Autorizzazioni necessarie

Nessuno

### <a name="optional-permissions"></a>Autorizzazioni facoltative

Nessuno

### <a name="considerations"></a>Considerazioni

- Un'app deve divulgare i dati usati e i relativi dati nelle relative condizioni d'uso e nei collegamenti all'informativa sulla privacy.

- [Il consenso specifico delle](resource-specific-consent.md) risorse fornisce un set di autorizzazioni che le app possono richiedere, che viene visualizzato nella schermata di installazione dell'app. Per altre informazioni sulle autorizzazioni specifiche della risorsa, vedere Informazioni di riferimento [sulle autorizzazioni di Graph.](https://docs.microsoft.com/graph/permissions-reference#teams-resource-specific-consent-permissions)

- Le app possono anche avere bisogno di autorizzazioni diverse da quelle specifiche per le risorse. Dopo l'installazione di un'app, l'app può richiedere le autorizzazioni di Graph tramite una richiesta di consenso. Per altre informazioni, vedere Informazioni sulle esperienze di [consenso dell'applicazione Azure AD.](https://docs.microsoft.com/azure/active-directory/develop/application-consent-experience) Puoi configurare le autorizzazioni API e il consenso nel portale di Azure. Per altre informazioni, vedere Il framework di consenso [di Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/develop/consent-framework)

## <a name="bots-and-messaging-extensions"></a>Bot ed estensioni di messaggistica

### <a name="required-permissions"></a>Autorizzazioni necessarie

- RECEIVE_MESSAGE, REPLYTO_MESSAGE. Il bot può ricevere messaggi dagli utenti e rispondere. <sup>1</sup>

- POST_MESSAGE_USER. Dopo che un utente ha inviato un messaggio a un bot, il bot può inviare all'utente messaggi diretti (detti anche messaggi *proattivi* in qualsiasi momento.

- GET_CHANNEL_LIST. I bot aggiunti ai team possono ottenere un elenco di nomi e ID dei canali di un team.

### <a name="optional-permissions"></a>Autorizzazioni facoltative

- IDENTITY. Quando viene usato in un canale, i bot dell'app possono accedere alle informazioni di identità di base dei membri del team (nome, cognome, nome dell'entità utente [UPN], indirizzo di posta elettronica); quando viene usato in una chat personale o di gruppo, il bot può accedere alle stesse informazioni per tali utenti.

- POST_MESSAGE_TEAM. Consente ai bot di un'app di inviare messaggi diretti (proattivi) a qualsiasi membro del team in qualsiasi momento, anche se l'utente non ha mai parlato con il bot prima d'ora.

- Le autorizzazioni seguenti non sono esplicite, ma sono implicite da RECEIVE_MESSAGE e REPLYTO_MESSAGE e dagli ambiti in cui i bot possono essere usati, dichiarati nel manifesto:
 
    - RECEIVE_MESSAGE_PERSONAL, REPLYTO_MESSAGE_PERSONAL
    - RECEIVE_MESSAGE_GROUPCHAT, REPLYTO_MESSAGE_GROUPCHAT
    - RECEIVE_MESSAGE_TEAM, REPLYTO_MESSAGE_TEAM

- SEND_FILES, RECEIVE_FILES. <sup>2</sup> Controlla se un bot può inviare e ricevere file in una chat personale (non ancora supportato per chat di gruppo o canali).

### <a name="considerations"></a>Considerazioni

- I bot hanno accesso solo ai team a cui sono stati aggiunti o agli utenti che li hanno installati.

- I bot ricevono solo i messaggi in cui sono esplicitamente menzionati dagli utenti. Questi dati lasciano la rete aziendale.

- I bot possono rispondere solo alle conversazioni in cui sono menzionati.

- Dopo che un utente ha inversato con un bot, se il bot archivia l'ID di quell'utente, può inviare all'utente messaggi diretti in qualsiasi momento.

- In teoria, i messaggi bot potrebbero contenere collegamenti a siti di phishing o malware, ma i bot possono essere bloccati dall'utente, dall'amministratore del tenant o globalmente da Microsoft.

- Un bot può recuperare (e potrebbe archiviare) informazioni di identità molto di base per i membri del team a cui è stata aggiunta l'app o per singoli utenti in chat personali o di gruppo. Per ottenere altre informazioni su questi utenti, il bot deve richiedere loro di accedere ad Azure Active Directory (Azure AD).

- I bot possono recuperare (e archiviare) l'elenco dei canali di un team; questi dati lasciano la rete aziendale.

- Quando un file viene inviato a un bot, lascia la rete aziendale. L'invio e la ricezione di file richiede l'approvazione dell'utente per ogni file. 

- Per impostazione predefinita, i bot non hanno la possibilità di agire per conto dell'utente, ma possono chiedere agli utenti di accedere; Non appena l'utente accede, il bot avrà un token di accesso con cui può eseguire altre operazioni. La descrizione esatta di questi elementi aggiuntivi dipende dal bot e da dove l'utente accede: un bot è un'app di Azure AD registrata e può avere un https://apps.dev.microsoft.com/ proprio set di autorizzazioni.

- I bot vengono informati ogni volta che gli utenti vengono aggiunti o eliminati da un team.

- I bot non vedono gli indirizzi IP degli utenti o altre informazioni referenziante. Tutte le informazioni provengono da Microsoft. Esiste un'eccezione: se un bot implementa la propria esperienza di accesso, l'interfaccia utente di accesso visualizza gli indirizzi IP degli utenti e le informazioni di riferimento.

- Le estensioni per la messaggistica, al contrario, visualizzano gli indirizzi IP degli utenti e le informazioni di riferimento.

- Le linee guida per le app (e il processo di revisione di AppSource) richiedono la pubblicazione di messaggi di chat personali agli utenti (tramite l'autorizzazione POST_MESSAGE_TEAM) per scopi validi. In caso di abuso, gli utenti possono bloccare il bot, gli amministratori del tenant possono bloccare l'app e Microsoft può bloccare i bot a livello centrale, se necessario.

<sup>1</sup> Alcuni bot inviano solo messaggi (POST_MESSAGE_USER). Si tratta di bot "solo notifiche", ma il termine non fa riferimento a ciò che un bot è autorizzato a fare, significa che il bot non vuole esporre un'esperienza di conversazione. Teams utilizza questo campo per disabilitare nell'interfaccia utente funzionalità che normalmente verrebbero abilitate; il bot non si limita a ciò che è consentito fare rispetto ai bot che espongono un'esperienza di conversazione.

<sup>2</sup> Disciplinato dalla proprietà booleana supportsFiles dell'oggetto bot nell'manifest.jsfile per l'app.

> [!NOTE]
> Se un bot ha un proprio accesso, c'è un secondo, diverso, esperienza del consenso la prima volta che l'utente accede.
>
>Attualmente, le autorizzazioni di Azure AD associate a qualsiasi funzionalità all'interno di un'app Teams (bot, scheda, connettore o estensione di messaggistica) sono completamente separate dalle autorizzazioni di Teams elencate qui.

## <a name="tabs"></a>Schede

Una scheda è un sito Web in esecuzione all'interno di Teams.

### <a name="required-permissions"></a>Autorizzazioni necessarie

SEND_AND_RECEIVE_WEB_DATA

### <a name="optional-permissions"></a>Autorizzazioni facoltative

Nessuno (attualmente)

### <a name="considerations"></a>Considerazioni

- Il profilo di rischio per una scheda è quasi identico allo stesso sito Web in esecuzione in una scheda del browser. 

- Una scheda ottiene anche il contesto in cui è in esecuzione, inclusi il nome di accesso e l'UPN dell'utente corrente, l'ID oggetto di Azure ACTIVE per l'utente corrente, l'ID del gruppo di Microsoft 365 in cui si trova (se si tratta di un team), l'ID tenant e le impostazioni locali correnti dell'utente. Tuttavia, per mappare questi ID alle informazioni di un utente, la scheda deve fare in modo che l'utente abbia accesso ad Azure AD.

## <a name="connectors"></a>Connettori

Un connettore pubblica messaggi in un canale quando si verificano eventi in un sistema esterno.

### <a name="required-permissions"></a>Autorizzazioni necessarie

POST_MESSAGE_CHANNEL

### <a name="optional-permissions"></a>Autorizzazioni facoltative

REPLYTO_CONNECTOR_MESSAGE. Alcuni connettori supportano messaggi su cui è possibile eseguire azioni, che consentono agli utenti di pubblicare risposte mirate al messaggio del connettore, ad esempio aggiungendo una risposta a un problema di GitHub o aggiungendo una data a una scheda di Trello.

### <a name="considerations"></a>Considerazioni

- Il sistema in cui vengono pubblicati i messaggi dei connettori non sa chi pubblica o chi riceve i messaggi: non vengono divulgate informazioni sul destinatario. (Microsoft è il destinatario effettivo, non il tenant; Microsoft pubblica effettivamente il post sul canale.

- Nessun dato lascia la rete aziendale quando i messaggi dei connettori vengono pubblicati su un canale.

- Anche i connettori che supportano messaggi che REPLYTO_CONNECTOR_MESSAGE autorizzazioni di riferimento non vedono l'indirizzo IP e le informazioni sul referenziante; queste informazioni vengono inviate a Microsoft e quindi indirizzate agli endpoint HTTP precedentemente registrati con Microsoft nel portale dei connettori.

- Ogni volta che si configura un connettore per un canale, viene creato un URL univoco per l'istanza del connettore. Se l'istanza del connettore viene eliminata, l'URL non può più essere usato.

- I messaggi del connettore non possono contenere file allegati.

- L'URL dell'istanza del connettore deve essere considerato segreto/riservato: chiunque abbia tale URL può inserire un post, ad esempio un indirizzo di posta elettronica. Di conseguenza, esiste un rischio di posta indesiderata o collegamenti a siti di phishing o malware. In questo caso, i proprietari del team possono eliminare l'istanza del connettore.

- Se il servizio che invia messaggi del connettore viene compromesso e inizia a inviare collegamenti a posta indesiderata/phishing/malware, un amministratore del tenant può impedire la creazione di nuove istanze del connettore e Microsoft può bloccarle centralmente.

> [!NOTE]
> Attualmente non è possibile sapere quali connettori supportano i messaggi su cui è possibile eseguire azioni (REPLYTO_CONNECTOR_MESSAGE autorizzazioni).

## <a name="outgoing-webhooks"></a>Webhook in uscita

*I webhook in uscita* vengono creati al volo dai proprietari del team o dai membri del team. Non sono funzionalità delle app di Teams; queste informazioni sono incluse per completare l'operazione.

### <a name="required-permissions"></a>Autorizzazioni necessarie

RECEIVE_MESSAGE, REPLYTO_MESSAGE. Può ricevere messaggi dagli utenti e rispondere.

### <a name="optional-permissions"></a>Autorizzazioni facoltative

Nessuno

### <a name="considerations"></a>Considerazioni

- I webhook in uscita sono simili ai bot, ma hanno un numero inferiore di privilegi. Devono essere menzionati esplicitamente, proprio come i bot.

- Quando viene registrato un webhook in uscita, viene generato un segreto, che consente al webhook in uscita di verificare che il mittente sia Microsoft Teams invece di un utente malintenzionato. Questo segreto deve rimanere un segreto; chiunque vi abbia accesso può impersonare Microsoft Teams. Se il segreto viene compromesso, il Webhook in uscita può essere eliminato e ri creato di nuovo e verrà generato un nuovo segreto.

- Anche se è possibile creare un webhook in uscita che non convalida il segreto, è consigliabile usare questo metodo.

- Oltre a ricevere e rispondere ai messaggi, gli webhook in uscita non possono fare molto: non possono inviare proattivamente messaggi, non possono inviare o ricevere file, non possono fare altro che ricevere e rispondere ai messaggi.
