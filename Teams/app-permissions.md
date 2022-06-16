---
title: Microsoft Teams le autorizzazioni e le considerazioni relative alle app
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.date: 06/27/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-voice
- M365-collaboration
search.appverid: MET150
ms.reviewer: rowille
description: Amministrazione possibile sapere quali dati e autorizzazioni Microsoft Teams app richiedono all'organizzazione.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a9ce3fccd8974bd7f8cba04d01bf16738772ea11
ms.sourcegitcommit: e38dc23e3968f55625e90c8883884045f80d22ee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2022
ms.locfileid: "66124181"
---
# <a name="microsoft-teams-apps-permissions-and-considerations"></a>Microsoft Teams le autorizzazioni e le considerazioni relative alle app

Microsoft Teams app sono un modo per aggregare una o più funzionalità in app che possono essere installate, aggiornate e disinstallate. Le funzionalità delle app includono:

* Bot
* Estensioni di messaggistica
* Schede
* Connettori

Gli amministratori gestiscono solo le app. Tuttavia, l'articolo è incentrato sulle autorizzazioni e considerazioni a livello di funzionalità, in quanto le funzionalità di un'app influiscono sulle autorizzazioni necessarie e sui profili di rischio dell'app. Per l'utilizzo, le app sono autorizzate dagli utenti e gestite da professionisti IT dal punto di vista dei criteri.

Le autorizzazioni elencate di seguito in lettere maiuscole, ad esempio `RECEIVE_MESSAGE` `REPLYTO_MESSAGE` , sono solo a scopo di illustrazione e spiegazione. Queste stringhe o autorizzazioni non vengono visualizzate nella [documentazione di Microsoft Teams sviluppatore](/microsoftteams/platform/overview) o nelle [autorizzazioni per Microsoft Graph](/graph/permissions-reference).

## <a name="global-app-permissions-and-considerations"></a>Considerazioni e autorizzazioni globali per le app

### <a name="required-permissions"></a>Autorizzazioni necessarie

Nessuno

### <a name="optional-permissions"></a>Autorizzazioni facoltative

Nessuno

### <a name="considerations"></a>Considerazioni

* Un'app deve divulgare quali dati utilizza e per cosa vengono utilizzati i dati nei propri collegamenti alle condizioni per l'utilizzo e all'informativa sulla privacy.

* [Il consenso specifico delle risorse](resource-specific-consent.md) fornisce un set di autorizzazioni che le app possono richiedere, che viene visualizzato nella schermata di installazione dell'app. Per altre informazioni sulle autorizzazioni di consenso specifiche per le risorse, vedere [Graph informazioni di riferimento sulle autorizzazioni](/graph/permissions-reference#teams-resource-specific-consent-permissions).

* Le app potrebbero anche richiedere autorizzazioni diverse da quelle specifiche per le risorse. Dopo l'installazione di un'app, l'app può richiedere Graph autorizzazioni tramite una richiesta di consenso. Per altre informazioni, vedere [Informazioni sulle esperienze di consenso dell'applicazione Azure AD](/azure/active-directory/develop/application-consent-experience). Puoi configurare le autorizzazioni e il consenso API nel portale di Azure. Per altre informazioni, vedi [Azure Active Directory framework di consenso](/azure/active-directory/develop/consent-framework).

## <a name="bots-and-messaging-extensions"></a>Bot ed estensioni di messaggistica

### <a name="required-permissions"></a>Autorizzazioni necessarie

* RECEIVE_MESSAGE, REPLYTO_MESSAGE: il bot può ricevere messaggi dagli utenti e rispondere. <sup>1</sup>

* POST_MESSAGE_USER: dopo che un utente ha inviato un messaggio a un bot, il bot può inviare all'utente messaggi diretti (detti anche *messaggi proattivi* in qualsiasi momento.

* GET_CHANNEL_LIST: I bot aggiunti ai team possono ottenere un elenco di nomi e ID dei canali di un team.

### <a name="optional-permissions"></a>Autorizzazioni facoltative

* IDENTITÀ: quando viene usata in un canale, i bot dell'app possono accedere alle informazioni di base sull'identità dei membri del team (nome, cognome, nome dell'entità utente [UPN], indirizzo di posta elettronica). Quando viene usato in una chat personale o di gruppo, il bot può accedere alle stesse informazioni per tali utenti.

* POST_MESSAGE_TEAM: consente ai bot di un'app di inviare messaggi diretti (proattivi) al membro del team in qualsiasi momento, anche se l'utente non ha mai interagito con il bot.

* Le seguenti autorizzazioni non sono esplicite, ma sono implicite da RECEIVE_MESSAGE e REPLYTO_MESSAGE e dagli ambiti in cui è possibile usare i bot, dichiarati nel manifesto:

  * RECEIVE_MESSAGE_PERSONAL, REPLYTO_MESSAGE_PERSONAL
  * RECEIVE_MESSAGE_GROUPCHAT REPLYTO_MESSAGE_GROUPCHAT
  * RECEIVE_MESSAGE_TEAM, REPLYTO_MESSAGE_TEAM

* Le seguenti autorizzazioni non sono esplicite, ma sono implicite da RECEIVE_MESSAGE e REPLYTO_MESSAGE e dagli ambiti in cui è possibile usare i bot, dichiarati nel manifesto:

  * RECEIVE_MESSAGE_PERSONAL, REPLYTO_MESSAGE_PERSONAL
  * RECEIVE_MESSAGE_GROUPCHAT REPLYTO_MESSAGE_GROUPCHAT
  * RECEIVE_MESSAGE_TEAM, REPLYTO_MESSAGE_TEAM

* SEND_FILES, RECEIVE_FILES:<sup>2</sup> Controlla se un bot può inviare e ricevere file nella chat personale (non ancora supportata per la chat di gruppo o i canali).

### <a name="considerations"></a>Considerazioni

* I bot hanno accesso solo ai team a cui sono stati aggiunti o agli utenti che li hanno installati.

* I bot ricevono solo i messaggi in cui vengono esplicitamente menzionati dagli utenti. Questi dati lasciano la rete aziendale.

* I bot possono rispondere solo alle conversazioni in cui vengono menzionati.

* Quando un utente comunica con un bot, se il bot archivia l'ID dell'utente, può inviare all'utente messaggi diretti in qualsiasi momento.

* Teoricamente è possibile che i messaggi bot contengano collegamenti a siti di phishing o malware. Tuttavia, i bot possono essere bloccati dall'utente, dall'amministratore del tenant o a livello globale da Microsoft. [I controlli di verifica e convalida](overview-of-app-validation.md) delle app assicurano che le app false non siano disponibili in Teams Store.

* Un bot può recuperare (e archiviare) le informazioni di identità di base per i membri del team a cui è stata aggiunta l'app o per singoli utenti in chat personali o di gruppo. Per ottenere altre informazioni su questi utenti, il bot deve richiedere loro di accedere a Azure Active Directory (Azure AD).

* I bot possono recuperare (e archiviare) l'elenco dei canali in un team; questi dati lasciano la rete aziendale.

* Per impostazione predefinita, i bot non hanno la possibilità di agire per conto dell'utente, ma i bot possono chiedere agli utenti di accedere. non appena l'utente accede, il bot avrà un token di accesso con cui può eseguire altre operazioni. Esattamente ciò che queste altre cose sono dipende dal bot e dove l'utente accede: un bot è un'app di Azure AD registrata in https://apps.dev.microsoft.com/ e può avere il proprio set di autorizzazioni.

* Quando un file viene inviato a un bot, il file lascia la rete aziendale. L'invio e la ricezione di file richiede l'approvazione dell'utente per ogni file.

* Per impostazione predefinita, i bot non hanno la possibilità di agire per conto dell'utente, ma i bot possono chiedere agli utenti di accedere. non appena l'utente accede, il bot avrà un token di accesso con cui può eseguire altre operazioni. Esattamente ciò che queste cose aggiuntive sono dipende dal bot e dove l'utente accede: un bot è un'app di Azure AD registrata al [portale di registrazione dell'applicazione](https://apps.dev.microsoft.com/?referrer=https:%2f%2fdocs.microsoft.com%2f#/appList) e può avere il proprio set di autorizzazioni.

* I bot vengono informati ogni volta che gli utenti vengono aggiunti o eliminati da un team.

* I bot non vedono gli indirizzi IP degli utenti o altre informazioni sui referrer. Tutte le informazioni provengono da Microsoft. Esiste un'eccezione: se un bot implementa la propria esperienza di accesso, l'interfaccia utente di accesso visualizzerà gli indirizzi IP degli utenti e le informazioni sui referrer.

* Le estensioni di messaggistica, invece, visualizzano gli indirizzi IP degli utenti e le informazioni sui referrer.

* Le linee guida per le app (e il processo di revisione di AppSource) richiedono discrezione nella pubblicazione di messaggi di chat personali agli utenti (tramite l'autorizzazione POST_MESSAGE_TEAM) per scopi validi. In caso di abuso, gli utenti possono bloccare il bot, gli amministratori del tenant possono bloccare l'app e Microsoft può bloccare i bot centralmente, se necessario.

<sup>1</sup> Alcuni bot inviano solo messaggi (POST_MESSAGE_USER). Si chiamano bot di sola notifica, ma il termine non fa riferimento a ciò che un bot è autorizzato o meno a fare, significa che il bot non vuole esporre un'esperienza conversazione. Teams usa questo campo per disabilitare nell'interfaccia utente funzionalità che normalmente sarebbero abilitate. Il bot non ha restrizioni sulle operazioni consentite rispetto ai bot che espongono un'esperienza conversazione.

<sup>2</sup> Disciplinata dalla proprietà booleana supportsFiles sull'oggetto bot nel `manifest.json` file per l'app.

> [!NOTE]
> Se un bot ha un proprio accesso, al primo accesso l'utente ha un'esperienza di consenso diversa.
>
>Attualmente, le autorizzazioni di Azure AD associate a una qualsiasi delle funzionalità all'interno di un'app di Teams (bot, scheda, connettore o estensione di messaggistica) sono completamente separate dalle autorizzazioni Teams elencate qui.

## <a name="tabs"></a>Schede

Una scheda è un sito Web che funziona all'interno di Teams.

### <a name="required-permissions"></a>Autorizzazioni necessarie

SEND_AND_RECEIVE_WEB_DATA

### <a name="optional-permissions"></a>Autorizzazioni facoltative

Nessuno (attualmente)

### <a name="considerations"></a>Considerazioni

* Il profilo di rischio per una scheda è quasi identico allo stesso sito Web in esecuzione in una scheda del browser.

* Una scheda ottiene anche il contesto in cui è in esecuzione, inclusi il nome di accesso e l'UPN dell'utente corrente, l'ID oggetto di Azure AD per l'utente corrente, l'ID del gruppo di Microsoft 365 in cui risiede (se si tratta di un team), l'ID tenant e le impostazioni locali correnti dell'utente. Tuttavia, per eseguire il mapping di questi ID alle informazioni di un utente, la scheda dovrà fare in modo che l'utente acceda ad Azure AD.

## <a name="connectors"></a>Connettori

Un connettore invia messaggi a un canale quando si verificano eventi in un sistema esterno.

### <a name="required-permissions"></a>Autorizzazioni necessarie

POST_MESSAGE_CHANNEL

### <a name="optional-permissions"></a>Autorizzazioni facoltative

REPLYTO_CONNECTOR_MESSAGE. Alcuni connettori supportano i messaggi su cui è possibile eseguire azioni, che consentono agli utenti di pubblicare risposte mirate al messaggio del connettore, ad esempio aggiungendo una risposta a un problema di GitHub o aggiungendo una data a una scheda Trello.

### <a name="considerations"></a>Considerazioni

* Il sistema che pubblica i messaggi dei connettori non sa a chi sta pubblicando o chi riceve i messaggi: nessuna informazione sul destinatario viene divulgata. (Microsoft è il destinatario effettivo, non il tenant; Microsoft pubblica il post effettivo sul canale).

* Nessun dato lascia la rete aziendale quando i messaggi dei connettori vengono pubblicati in un canale.

* Anche i connettori che supportano i messaggi su cui è possibile eseguire azioni (autorizzazione REPLYTO_CONNECTOR_MESSAGE) non vedono le informazioni sull'indirizzo IP e sul referrer. queste informazioni vengono inviate a Microsoft e quindi indirizzate agli endpoint HTTP precedentemente registrati con Microsoft nel portale Dei connettori.

* Ogni volta che un connettore viene configurato per un canale, viene creato un URL univoco per tale istanza del connettore. Se tale istanza del connettore viene eliminata, l'URL non può più essere usato.

* I messaggi dei connettori non possono contenere file allegati.

* L'URL dell'istanza del connettore deve essere considerato segreto/riservato: chiunque abbia quell'URL può pubblicarlo, ad esempio un indirizzo di posta elettronica. Di conseguenza, esiste un rischio di posta indesiderata o collegamenti a siti di phishing o malware. In questo caso, i proprietari del team possono eliminare l'istanza del connettore.

* Se il servizio che invia i messaggi dei connettori dovesse essere compromesso e iniziare a inviare collegamenti a posta indesiderata/phishing/malware, un amministratore del tenant può impedire la creazione di nuove istanze del connettore e Microsoft può bloccarle a livello centrale.

> [!NOTE]
> Attualmente non è possibile sapere quali connettori supportano i messaggi su cui è possibile eseguire azioni (REPLYTO_CONNECTOR_MESSAGE autorizzazione).

## <a name="outgoing-webhooks"></a>Webhook in uscita

_I webhook in uscita_ vengono creati dai proprietari o dai membri del team. Non sono funzionalità di Teams app. Queste informazioni sono incluse per la completezza.

### <a name="required-permissions"></a>Autorizzazioni necessarie

RECEIVE_MESSAGE, REPLYTO_MESSAGE. Può ricevere messaggi dagli utenti e rispondere.

### <a name="optional-permissions"></a>Autorizzazioni facoltative

Nessuno

### <a name="considerations"></a>Considerazioni

* I webhook in uscita sono simili ai bot, ma hanno meno privilegi. Devono essere esplicitamente menzionati, proprio come i bot.

* Quando viene registrato un webhook in uscita, viene generato un segreto che consente al webhook in uscita di verificare che il mittente sia Microsoft Teams rispetto a un utente malintenzionato. Questo segreto deve rimanere segreto; chiunque vi abbia accesso può rappresentare Microsoft Teams. Se il segreto viene compromesso, il webhook in uscita può essere eliminato e ricreato e verrà generato un nuovo segreto.

* Anche se è possibile creare un webhook in uscita che non convalidi il segreto, è consigliabile evitare di usarlo.

* Oltre a ricevere e rispondere ai messaggi, i webhook in uscita non possono fare molto: non possono inviare messaggi in modo proattivo, non possono inviare o ricevere file, non possono fare altro che ricevere e rispondere ai messaggi.
