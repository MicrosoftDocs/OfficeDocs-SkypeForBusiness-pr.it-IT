---
title: Microsoft Teams e considerazioni sulle app
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
description: L'amministratore può scoprire quali dati e autorizzazioni Microsoft Teams app richiedono all'organizzazione.
f1.keywords:
- NOCSH
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ae050080814afe12ce2ba791c6b68058d5e4bc58
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120858"
---
# <a name="microsoft-teams-apps-permissions-and-considerations"></a>Microsoft Teams e considerazioni sulle app

Microsoft Teams sono un modo per aggregare una o più funzionalità in un pacchetto di _app_ che può essere installato, aggiornato e disinstallato. Le funzionalità includono:

- Bot
- Estensioni di messaggistica
- Schede
- Connettori

Le app sono autorizzate dagli utenti e gestite dall'IT dal punto di vista dei criteri. Tuttavia, per la maggior parte, le autorizzazioni e il profilo di rischio di un'app sono definiti dalle autorizzazioni e dai profili di rischio delle funzionalità contenute nell'app. Di conseguenza, questo articolo si concentra sulle autorizzazioni e sulle considerazioni a livello di funzionalità.

Le autorizzazioni elencate di seguito in lettere maiuscole, ad esempio RECEIVE_MESSAGE e REPLYTO_MESSAGE, non vengono visualizzate nella documentazione per sviluppatori di [Microsoft Teams](/microsoftteams/platform/overview) o nelle autorizzazioni per [Microsoft Graph](/graph/permissions-reference). Si tratta semplicemente di una abbreviazione descrittiva ai fini di questo articolo.


| Titolo   | Descrizione    |
|-----------|------------|
| ![Icona che descrive un punto decisionale](media/audio_conferencing_image7.png) <br/>Punto di decisione|<ul><li>Usare le tabelle seguenti come guida per comprendere le autorizzazioni richieste dall'app che si sta esaminando.</li></ul> |
| ![Icona che descrive il passaggio successivo](media/audio_conferencing_image9.png)<br/>Passaggio successivo|<ul><li>Eseguire ricerche nell'app o nel servizio stesso per decidere se consentire l'accesso all'app o al servizio stesso all'interno dell'organizzazione. Ad esempio, i bot inviano e ricevono messaggi dagli utenti e, ad eccezione dei bot personalizzati aziendali, si trovano all'esterno del limite di conformità. Pertanto, qualsiasi app che include un bot richiede queste autorizzazioni e ha almeno quel profilo di rischio. </li></ul>|

Vedere anche [Richiedere autorizzazioni per i dispositivi per la Microsoft Teams scheda .](/microsoftteams/platform/concepts/device-capabilities/native-device-permissions)

## <a name="global-app-permissions-and-considerations"></a>Considerazioni e autorizzazioni per le app globali

### <a name="required-permissions"></a>Autorizzazioni obbligatorie

Nessuno

### <a name="optional-permissions"></a>Autorizzazioni facoltative

Nessuno

### <a name="considerations"></a>Considerazioni

- Un'app deve divulgare i dati usati e i relativi collegamenti alle condizioni d'uso e all'informativa sulla privacy.

- [Il consenso specifico delle](resource-specific-consent.md) risorse fornisce un set di autorizzazioni che le app possono richiedere, che vengono visualizzate nella schermata di installazione dell'app. Per altre informazioni sulle autorizzazioni di consenso specifiche delle risorse, vedere informazioni di [Graph sulle autorizzazioni.](/graph/permissions-reference#teams-resource-specific-consent-permissions)

- Le app potrebbero anche avere bisogno di autorizzazioni diverse da quelle specifiche per le risorse. Dopo l'installazione di un'app, l'app può richiedere Graph autorizzazioni tramite una richiesta di consenso. Per altre informazioni, vedere Informazioni sulle esperienze [di consenso delle applicazioni di Azure AD.](/azure/active-directory/develop/application-consent-experience) È possibile configurare le autorizzazioni API e il consenso nel portale di Azure. Per altre informazioni, vedere Azure Active Directory [framework di consenso.](/azure/active-directory/develop/consent-framework)

## <a name="bots-and-messaging-extensions"></a>Bot ed estensioni di messaggistica

### <a name="required-permissions"></a>Autorizzazioni obbligatorie

- RECEIVE_MESSAGE, REPLYTO_MESSAGE. Il bot può ricevere messaggi dagli utenti e rispondere. <sup>1</sup>

- POST_MESSAGE_USER. Dopo che un utente ha inviato un messaggio a un bot, il bot può inviare messaggi diretti all'utente , detti anche *messaggi proattivi* in qualsiasi momento.

- GET_CHANNEL_LIST. I bot aggiunti ai team possono ottenere un elenco di nomi e ID dei canali in un team.

### <a name="optional-permissions"></a>Autorizzazioni facoltative

- IDENTITY. Quando viene usato in un canale, i bot dell'app possono accedere alle informazioni di identità di base dei membri del team (nome, cognome, nome dell'entità utente [UPN], indirizzo di posta elettronica); quando viene usato in una chat personale o di gruppo, il bot può accedere alle stesse informazioni per tali utenti.

- POST_MESSAGE_TEAM. Consente ai bot di un'app di inviare messaggi diretti (proattivi) a qualsiasi membro del team in qualsiasi momento, anche se l'utente non ha mai parlato con il bot prima.

- Le autorizzazioni seguenti non sono esplicite, ma sono implicite da RECEIVE_MESSAGE e REPLYTO_MESSAGE e dagli ambiti in cui è possibile usare i bot, dichiarati nel manifesto:
 
    - RECEIVE_MESSAGE_PERSONAL, REPLYTO_MESSAGE_PERSONAL
    - RECEIVE_MESSAGE_GROUPCHAT, REPLYTO_MESSAGE_GROUPCHAT
    - RECEIVE_MESSAGE_TEAM, REPLYTO_MESSAGE_TEAM

- SEND_FILES, RECEIVE_FILES. <sup>2</sup> Controlla se un bot può inviare e ricevere file nella chat personale (non ancora supportata per la chat di gruppo o i canali).

### <a name="considerations"></a>Considerazioni

- I bot hanno accesso solo ai team a cui sono stati aggiunti o agli utenti che li hanno installati.

- I bot ricevono solo messaggi in cui vengono menzionati esplicitamente dagli utenti. Questi dati lasciano la rete aziendale.

- I bot possono rispondere solo alle conversazioni in cui sono menzionati.

- Dopo che un utente ha conversato con un bot, se il bot archivia l'ID dell'utente, può inviare messaggi diretti all'utente in qualsiasi momento.

- È in teoria possibile che i messaggi bot contengano collegamenti a siti di phishing o malware, ma i bot possono essere bloccati dall'utente, dall'amministratore del tenant o globalmente da Microsoft.

- Un bot può recuperare (e archiviare) informazioni di identità molto di base per i membri del team a cui è stata aggiunta l'app o per i singoli utenti nelle chat personali o di gruppo. Per ottenere altre informazioni su questi utenti, il bot deve richiedere l'accesso a Azure Active Directory (Azure AD).

- I bot possono recuperare (e archiviare) l'elenco dei canali in un team; questi dati lasciano la rete aziendale.

- Quando un file viene inviato a un bot, il file lascia la rete aziendale. L'invio e la ricezione di file richiede l'approvazione dell'utente per ogni file. 

- Per impostazione predefinita, i bot non hanno la possibilità di agire per conto dell'utente, ma i bot possono chiedere agli utenti di accedere. Non appena l'utente accede, il bot avrà un token di accesso con cui può eseguire altre operazioni. Esattamente quali sono questi elementi aggiuntivi dipendono dal bot e dalla posizione in cui l'utente accede: un bot è un'app Azure AD registrata in e può avere un https://apps.dev.microsoft.com/ proprio set di autorizzazioni.

- I bot vengono informati ogni volta che gli utenti vengono aggiunti o eliminati da un team.

- I bot non vedono gli indirizzi IP degli utenti o altre informazioni di riferimento. Tutte le informazioni provengono da Microsoft. Esiste un'eccezione: se un bot implementa la propria esperienza di accesso, l'interfaccia utente di accesso visualizza gli indirizzi IP degli utenti e le informazioni sul referrer.

- Le estensioni di messaggistica, invece, visualizzano gli indirizzi IP degli utenti e le informazioni sul referrer.

- Le linee guida per le app (e il processo di revisione di AppSource) richiedono la discrezione di pubblicare messaggi di chat personali agli utenti (tramite l'autorizzazione POST_MESSAGE_TEAM) per scopi validi. In caso di abuso, gli utenti possono bloccare il bot, gli amministratori del tenant possono bloccare l'app e Microsoft può bloccare i bot centralmente, se necessario.

<sup>1</sup> Alcuni bot inviano solo messaggi (POST_MESSAGE_USER). Si chiamano bot "solo notifiche", ma il termine non fa riferimento a ciò che un bot è consentito o non può eseguire, significa che il bot non vuole esporre un'esperienza di conversazione. Teams usa questo campo per disabilitare la funzionalità nell'interfaccia utente che normalmente verrebbe abilitata; il bot non è limitato alle attività consentite rispetto ai bot che espongono un'esperienza di conversazione.

<sup>2</sup> Regolato dalla proprietà booleana supportsFiles sull'oggetto bot nell'manifest.jsfile per l'app.

> [!NOTE]
> Se un bot ha un proprio accesso, la prima volta che l'utente effettua l'accesso esiste un'esperienza di consenso diversa.
>
>Attualmente, le autorizzazioni di Azure AD associate a qualsiasi funzionalità all'interno di un'app Teams (bot, scheda, connettore o estensione di messaggistica) sono completamente separate dalle autorizzazioni Teams di messaggistica qui elencate.

## <a name="tabs"></a>Schede

Una scheda è un sito Web in esecuzione all'interno Teams.

### <a name="required-permissions"></a>Autorizzazioni obbligatorie

SEND_AND_RECEIVE_WEB_DATA

### <a name="optional-permissions"></a>Autorizzazioni facoltative

Nessuno (attualmente)

### <a name="considerations"></a>Considerazioni

- Il profilo di rischio per una scheda è quasi identico allo stesso sito Web in esecuzione in una scheda del browser. 

- Una scheda ottiene anche il contesto in cui è in esecuzione, inclusi il nome di accesso e l'UPN dell'utente corrente, l'ID oggetto di Azure AD per l'utente corrente, l'ID del gruppo Microsoft 365 in cui si trova (se si tratta di un team), l'ID tenant e le impostazioni locali correnti dell'utente. Tuttavia, per mappare questi ID alle informazioni di un utente, la scheda deve rendere l'utente connesso ad Azure AD.

## <a name="connectors"></a>Connettori

Un connettore invia messaggi a un canale quando si verificano eventi in un sistema esterno.

### <a name="required-permissions"></a>Autorizzazioni obbligatorie

POST_MESSAGE_CHANNEL

### <a name="optional-permissions"></a>Autorizzazioni facoltative

REPLYTO_CONNECTOR_MESSAGE. Alcuni connettori supportano messaggi utilizzabili, che consentono agli utenti di pubblicare risposte mirate al messaggio del connettore, ad esempio aggiungendo una risposta a un problema di GitHub o aggiungendo una data a una scheda Trello.

### <a name="considerations"></a>Considerazioni

- Il sistema che pubblica i messaggi del connettore non sa chi pubblica o chi riceve i messaggi: nessuna informazione sul destinatario viene divulgata. Microsoft è il destinatario effettivo, non il tenant. Microsoft esegue il post effettivo nel canale.

- Nessun dato lascia la rete aziendale quando i messaggi del connettore vengono pubblicati in un canale.

- Anche i connettori che supportano i messaggi REPLYTO_CONNECTOR_MESSAGE non visualizzano le informazioni sull'indirizzo IP e sul referrer. queste informazioni vengono inviate a Microsoft e quindi indirizzate agli endpoint HTTP precedentemente registrati con Microsoft nel portale connettori.

- Ogni volta che un connettore viene configurato per un canale, viene creato un URL univoco per l'istanza del connettore. Se l'istanza del connettore viene eliminata, l'URL non può più essere usato.

- I messaggi del connettore non possono contenere file allegati.

- L'URL dell'istanza del connettore deve essere considerato segreto/riservato: chiunque abbia tale URL può pubblicarlo, ad esempio un indirizzo di posta elettronica. Di conseguenza, esiste un rischio di posta indesiderata o collegamenti a siti di phishing o malware. In questo caso, i proprietari del team possono eliminare l'istanza del connettore.

- Se il servizio che invia i messaggi del connettore viene compromesso e inizia a inviare collegamenti di posta indesiderata/phishing/malware, un amministratore del tenant può impedire la creazione di nuove istanze del connettore e Microsoft può bloccarle centralmente.

> [!NOTE]
> Al momento non è possibile sapere quali connettori supportano i messaggi REPLYTO_CONNECTOR_MESSAGE messaggi.

## <a name="outgoing-webhooks"></a>Webhook in uscita

*I webhook in uscita* vengono creati al volo dai proprietari del team o dai membri del team. Non sono funzionalità delle Teams app. queste informazioni sono incluse per completezza.

### <a name="required-permissions"></a>Autorizzazioni obbligatorie

RECEIVE_MESSAGE, REPLYTO_MESSAGE. Può ricevere messaggi dagli utenti e rispondere.

### <a name="optional-permissions"></a>Autorizzazioni facoltative

Nessuno

### <a name="considerations"></a>Considerazioni

- I webhook in uscita sono simili ai bot, ma hanno meno privilegi. Devono essere menzionati esplicitamente, proprio come i bot.

- Quando viene registrato un webhook in uscita, viene generato un segreto, che consente al webhook in uscita di verificare che il mittente sia Microsoft Teams invece di un utente malintenzionato. Questo segreto deve rimanere segreto; chiunque abbia accesso ad esso può impersonare Microsoft Teams. Se il segreto viene compromesso, il webhook in uscita può essere eliminato e ri-creato e verrà generato un nuovo segreto.

- Anche se è possibile creare un webhook in uscita che non convalida il segreto, è consigliabile non farlo.

- Oltre a ricevere e rispondere ai messaggi, i webhook in uscita non possono fare molto: non possono inviare messaggi in modo proattivo, non possono inviare o ricevere file, non possono fare altro che ricevere e rispondere ai messaggi.