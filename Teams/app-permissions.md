---
title: Autorizzazioni e considerazioni per le app di Microsoft Teams
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.subservice: teams-apps
ms.collection:
- M365-voice
- M365-collaboration
search.appverid: MET150
ms.reviewer: rowille
description: L'amministratore può conoscere i dati e le autorizzazioni richiesti dalle app di Microsoft Teams all'organizzazione.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 42044bf8f74c99b27db724e87ee35e700491aa8e
ms.sourcegitcommit: ceba5fd8f098c8d0eafaffe5c5301c845a3ae7ab
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2022
ms.locfileid: "67837196"
---
# <a name="microsoft-teams-apps-permissions-and-considerations"></a>Autorizzazioni e considerazioni per le app di Microsoft Teams

Le app di Microsoft Teams consentono di aggregare una o più funzionalità in app che possono essere installate, aggiornate e disinstallate. Le funzionalità delle app includono:

* Bot
* Estensioni per la messaggistica
* Schede
* Connettori

Gli amministratori gestiscono solo le app. Tuttavia, l'articolo è incentrato sulle autorizzazioni e sulle considerazioni a livello di funzionalità, perché le funzionalità in un'app influiscono sulle autorizzazioni necessarie e sui profili di rischio dell'app. Per l'utilizzo, le app vengono concesse dagli utenti e gestite dai professionisti IT dal punto di vista dei criteri.

Le autorizzazioni elencate di seguito in lettere maiuscole, ad esempio `RECEIVE_MESSAGE` e `REPLYTO_MESSAGE` sono solo a scopo illustrativo e esplicativo. Queste stringhe o autorizzazioni non vengono visualizzate nella [documentazione per sviluppatori di Microsoft Teams](/microsoftteams/platform/overview) o nelle [autorizzazioni per Microsoft Graph](/graph/permissions-reference).

## <a name="global-app-permissions-and-considerations"></a>Considerazioni e autorizzazioni globali per le app

### <a name="required-permissions"></a>Autorizzazioni necessarie

Nessuno

### <a name="optional-permissions"></a>Autorizzazioni facoltative

Nessuno

### <a name="considerations"></a>Considerazioni

* Un'app deve divulgare i dati usati e i dati usati nei relativi collegamenti alle condizioni per l'utilizzo e all'informativa sulla privacy.

* [Il consenso specifico della risorsa](resource-specific-consent.md) fornisce un set di autorizzazioni che le app possono richiedere, che vengono visualizzate nella schermata di installazione dell'app. Per altre informazioni sulle autorizzazioni di consenso specifiche delle risorse, vedere le [informazioni di riferimento sulle autorizzazioni di Graph](/graph/permissions-reference#teams-resource-specific-consent-permissions).

* Le app possono anche avere bisogno di autorizzazioni diverse da quelle di consenso specifiche delle risorse. Dopo l'installazione di un'app, l'app può richiedere autorizzazioni Graph tramite una richiesta di consenso. Per altre informazioni, vedere [Informazioni Azure AD esperienze di consenso dell'applicazione](/azure/active-directory/develop/application-consent-experience). È possibile configurare le autorizzazioni e il consenso dell'API nel portale di Azure. Per altre informazioni, vedere [Azure Active Directory framework di consenso](/azure/active-directory/develop/consent-framework).

## <a name="bots-and-messaging-extensions"></a>Bot ed estensioni per la messaggistica

### <a name="required-permissions"></a>Autorizzazioni necessarie

* RECEIVE_MESSAGE, REPLYTO_MESSAGE: il bot può ricevere messaggi dagli utenti e rispondere.<sup>1</sup>

* POST_MESSAGE_USER: dopo che un utente ha inviato un messaggio a un bot, il bot può inviare i messaggi diretti dell'utente (detti anche *messaggi proattivi* in qualsiasi momento.

* GET_CHANNEL_LIST: i bot aggiunti ai team possono ottenere un elenco di nomi e ID dei canali in un team.

### <a name="optional-permissions"></a>Autorizzazioni facoltative

* IDENTITÀ: quando viene usata in un canale, i bot dell'app possono accedere alle informazioni di identità di base dei membri del team (nome, cognome, nome dell'entità utente [UPN], indirizzo di posta elettronica). Quando viene usato in una chat personale o di gruppo, il bot può accedere alle stesse informazioni per tali utenti.

* POST_MESSAGE_TEAM: consente ai bot di un'app di inviare messaggi diretti (proattivi) al membro del team in qualsiasi momento, anche se l'utente non ha mai interagito con il bot.

* Le autorizzazioni seguenti non sono esplicite, ma sono implicite in RECEIVE_MESSAGE e REPLYTO_MESSAGE e negli ambiti in cui è possibile usare i bot, dichiarati nel manifesto:

  * RECEIVE_MESSAGE_PERSONAL, REPLYTO_MESSAGE_PERSONAL
  * RECEIVE_MESSAGE_GROUPCHAT, REPLYTO_MESSAGE_GROUPCHAT
  * RECEIVE_MESSAGE_TEAM, REPLYTO_MESSAGE_TEAM

* Le autorizzazioni seguenti non sono esplicite, ma sono implicite in RECEIVE_MESSAGE e REPLYTO_MESSAGE e negli ambiti in cui è possibile usare i bot, dichiarati nel manifesto:

  * RECEIVE_MESSAGE_PERSONAL, REPLYTO_MESSAGE_PERSONAL
  * RECEIVE_MESSAGE_GROUPCHAT, REPLYTO_MESSAGE_GROUPCHAT
  * RECEIVE_MESSAGE_TEAM, REPLYTO_MESSAGE_TEAM

* SEND_FILES, RECEIVE_FILES:<sup>2</sup> Controlla se un bot può inviare e ricevere file nella chat personale (non ancora supportato per la chat di gruppo o i canali).

### <a name="considerations"></a>Considerazioni

* I bot hanno accesso solo ai team a cui sono stati aggiunti o agli utenti che li hanno installati.

* I bot ricevono solo i messaggi in cui vengono menzionati in modo esplicito dagli utenti. Questi dati lasciano la rete aziendale.

* I bot possono rispondere solo alle conversazioni in cui sono menzionati.

* Quando un utente dialoga con un bot, se il bot archivia l'ID dell'utente, può inviare messaggi diretti all'utente in qualsiasi momento.

* In teoria è possibile che i messaggi bot contengano collegamenti a siti di phishing o malware. Tuttavia, i bot possono essere bloccati dall'utente, dall'amministratore del tenant o a livello globale da Microsoft. [I controlli di verifica e convalida delle app](overview-of-app-validation.md) assicurano che le app false non siano disponibili in Teams Store.

* Un bot può recuperare (e archiviare) le informazioni di base sull'identità per i membri del team a cui è stata aggiunta l'app o per singoli utenti in chat personali o di gruppo. Per ottenere altre informazioni su questi utenti, il bot deve richiedere loro di accedere a Azure Active Directory (Azure AD).

* I bot possono recuperare (e archiviare) l'elenco dei canali in un team; questi dati lasciano la rete aziendale.

* Per impostazione predefinita, i bot non hanno la possibilità di agire per conto dell'utente, ma i bot possono chiedere agli utenti di accedere. non appena l'utente accede, il bot avrà un token di accesso con cui può eseguire operazioni aggiuntive. Esattamente quali sono gli altri elementi dipende dal bot e dal punto in cui l'utente accede: un bot è un'app Azure AD registrata in https://apps.dev.microsoft.com/ e può avere un proprio set di autorizzazioni.

* Quando un file viene inviato a un bot, il file lascia la rete aziendale. L'invio e la ricezione di file richiedono l'approvazione dell'utente per ogni file.

* I bot vengono informati ogni volta che gli utenti vengono aggiunti o eliminati da un team.

* I bot non visualizzano gli indirizzi IP degli utenti o altre informazioni di riferimento. Tutte le informazioni provengono da Microsoft. Esiste un'eccezione: se un bot implementa la propria esperienza di accesso, l'interfaccia utente di accesso visualizzerà gli indirizzi IP degli utenti e le informazioni del referrer.

* Le estensioni di messaggistica, d'altra parte, visualizzano gli indirizzi IP degli utenti e le informazioni sul referrer.

* Le linee guida per le app (e il processo di revisione di AppSource) richiedono la discrezione di pubblicare messaggi di chat personali agli utenti (tramite l'autorizzazione POST_MESSAGE_TEAM) per scopi validi. In caso di uso improprio, gli utenti possono bloccare il bot, gli amministratori tenant possono bloccare l'app e Microsoft può bloccare i bot centralmente, se necessario.

<sup>1</sup> Alcuni bot inviano solo messaggi (POST_MESSAGE_USER). Si chiamano bot "solo notifica", ma il termine non fa riferimento a ciò che un bot è consentito o non è autorizzato a fare, significa che il bot non vuole esporre un'esperienza di conversazione. Teams usa questo campo per disabilitare nell'interfaccia utente le funzionalità che normalmente verrebbero abilitate; il bot non è limitato alle operazioni consentite rispetto ai bot che espongono un'esperienza di conversazione.

<sup>2</sup> Regolato dalla proprietà booleana supportsFiles nell'oggetto bot nel file di `manifest.json` per l'app.

> [!NOTE]
> Se un bot ha un proprio accesso, la prima volta che l'utente esegue l'accesso è disponibile una seconda—esperienza di consenso diversa—.
>
>Attualmente, le autorizzazioni Azure AD associate a una qualsiasi delle funzionalità all'interno di un'app di Teams (bot, scheda, connettore o estensione di messaggistica) sono completamente separate dalle autorizzazioni di Teams elencate qui.

## <a name="tabs"></a>Schede

Una scheda è un sito Web in esecuzione all'interno di Teams.

### <a name="required-permissions"></a>Autorizzazioni necessarie

SEND_AND_RECEIVE_WEB_DATA

### <a name="optional-permissions"></a>Autorizzazioni facoltative

Nessuno (attualmente)

### <a name="considerations"></a>Considerazioni

* Il profilo di rischio per una scheda è quasi identico allo stesso sito Web in esecuzione in una scheda del browser.

* Una scheda ottiene anche il contesto in cui è in esecuzione, inclusi il nome di accesso e l'UPN dell'utente corrente, l'ID oggetto Azure AD per l'utente corrente, l'ID del gruppo di Microsoft 365 in cui risiede (se si tratta di un team), l'ID tenant e le impostazioni locali correnti dell'utente. Tuttavia, per eseguire il mapping di questi ID alle informazioni di un utente, la scheda dovrebbe fare in modo che l'utente accedi a Azure AD.

## <a name="connectors"></a>Connettori

Un connettore invia messaggi a un canale quando si verificano eventi in un sistema esterno.

### <a name="required-permissions"></a>Autorizzazioni necessarie

POST_MESSAGE_CHANNEL

### <a name="optional-permissions"></a>Autorizzazioni facoltative

REPLYTO_CONNECTOR_MESSAGE. Alcuni connettori supportano i messaggi interattivi, che consentono agli utenti di pubblicare risposte mirate al messaggio del connettore, ad esempio aggiungendo una risposta a un problema di GitHub o aggiungendo una data a una scheda Trello.

### <a name="considerations"></a>Considerazioni

* Il sistema che pubblica i messaggi del connettore non sa a chi sta pubblicando o a chi riceve i messaggi: non vengono divulgate informazioni sul destinatario. (Microsoft è il destinatario effettivo, non il tenant; Microsoft esegue il post effettivo nel canale.)

* Nessun dato lascia la rete aziendale quando i messaggi del connettore vengono inviati a un canale.

* Anche i connettori che supportano messaggi interattivi (autorizzazione REPLYTO_CONNECTOR_MESSAGE) non visualizzano l'indirizzo IP e le informazioni del referrer; queste informazioni vengono inviate a Microsoft e quindi indirizzate agli endpoint HTTP registrati in precedenza con Microsoft nel portale connettori.

* Ogni volta che un connettore viene configurato per un canale, viene creato un URL univoco per tale istanza del connettore. Se l'istanza del connettore viene eliminata, l'URL non può più essere usato.

* I messaggi del connettore non possono contenere file allegati.

* L'URL dell'istanza del connettore deve essere considerato segreto/riservato: chiunque disponga di tale URL può pubblicarlo, ad esempio un indirizzo di posta elettronica. Esiste quindi un rischio di posta indesiderata o collegamenti a siti di phishing o malware. In questo caso, i proprietari del team possono eliminare l'istanza del connettore.

* Se il servizio che invia i messaggi del connettore viene compromesso e inizia a inviare collegamenti di posta indesiderata/phishing/malware, un amministratore tenant può impedire la creazione di nuove istanze del connettore e Microsoft può bloccarle centralmente.

> [!NOTE]
> Attualmente non è possibile sapere quali connettori supportano i messaggi interattivi (autorizzazione REPLYTO_CONNECTOR_MESSAGE).

## <a name="outgoing-webhooks"></a>Webhook in uscita

_I webhook in uscita_ vengono creati dai proprietari del team o dai membri del team. Non sono funzionalità delle app di Teams; queste informazioni sono incluse per completezza.

### <a name="required-permissions"></a>Autorizzazioni necessarie

RECEIVE_MESSAGE, REPLYTO_MESSAGE. Può ricevere messaggi dagli utenti e rispondere a loro.

### <a name="optional-permissions"></a>Autorizzazioni facoltative

Nessuno

### <a name="considerations"></a>Considerazioni

* I webhook in uscita sono simili ai bot, ma hanno meno privilegi. Devono essere menzionati in modo esplicito, proprio come i bot.

* Quando viene registrato un webhook in uscita, viene generato un segreto che consente al webhook in uscita di verificare che il mittente sia Microsoft Teams anziché un utente malintenzionato. Questo segreto deve rimanere un segreto; chiunque abbia accesso può rappresentare Microsoft Teams. Se il segreto viene compromesso, eliminare e ricreare il webhook in uscita per generare un nuovo segreto.

* Anche se è possibile creare un webhook in uscita che non convalida il segreto, è consigliabile contro di esso.

* Oltre a ricevere e rispondere ai messaggi, i webhook in uscita non possono fare molto: non possono inviare messaggi in modo proattivo, non possono inviare o ricevere file, non possono fare altro che ricevere e rispondere ai messaggi.
