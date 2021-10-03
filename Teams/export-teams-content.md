---
title: Esportare contenuto con le API di Microsoft Teams di esportazione
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: reference
audience: admin
ms.service: msteams
ms.reviewer: vikramju
description: In questo articolo imparerai a esportare Teams contenuto usando le API di Microsoft Teams esporta.
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 84f53b5c75c9e99e3a3bfc2877c096b32fe3b9c0
ms.sourcegitcommit: 26ce61afcb743c8b9e06b4fa048ad93ab70c31c5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/02/2021
ms.locfileid: "60082866"
---
# <a name="export-content-with-the-microsoft-teams-export-apis"></a>Esportare contenuto con le API di Microsoft Teams di esportazione

Teams Le API di esportazione consentono di esportare 1:1, chat di gruppo, chat di riunione e messaggi di canale da Microsoft Teams. Se l'organizzazione deve esportare Microsoft Teams messaggi, è possibile estrarli usando le API di Teams esporta. *Messaggio chat* rappresenta un singolo messaggio di chat all'interno di [un canale o](/graph/api/resources/channel?view=graph-rest-beta) di una [chat.](/graph/api/resources/chat?view=graph-rest-beta) Il messaggio di chat può essere un messaggio di chat radice o parte di un thread di risposta definito dalla proprietà **replyToId** nel messaggio di chat.

Ecco alcuni esempi su come usare queste API di esportazione:

- **Esempio 1:** se è stato abilitato il Microsoft Teams nell'organizzazione e si vogliono esportare tutti i messaggi Microsoft Teams a livello di programmazione passando l'intervallo di date per un determinato utente o team.
- **Esempio 2:** se si vuole esportare a livello di programmazione tutti i messaggi degli utenti o del team ogni giorno fornendo un intervallo di date. Le API di esportazione possono recuperare tutti i messaggi creati o aggiornati durante l'intervallo di date specificato.

## <a name="what-is-supported-by-the-teams-export-apis"></a>Cosa è supportato dalle API di Teams di esportazione?

- Esportazione in blocco di un messaggio di **Teams:** le API di esportazione di Teams supportano fino a 200 RPS per app per tenant e 600 RPS per un'applicazione, con questi limiti dovrebbe essere possibile esportare in blocco i messaggi Teams.
- **Contesto applicazione:** per chiamare Microsoft Graph, l'app deve acquisire un token di accesso dal Microsoft Identity Platform. Il token di accesso contiene informazioni sull'app e sulle autorizzazioni di cui dispone per le risorse e le API disponibili tramite Microsoft Graph. Per ottenere un token di accesso, l'app deve essere registrata con il Microsoft Identity Platform ed essere autorizzata da un utente o da un amministratore per l'accesso alle risorse di Microsoft Graph necessarie.

    Se si ha già familiarità con l'integrazione di un'app con [](/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps) il Microsoft Identity Platform per ottenere i token, vedere la sezione Passaggi successivi per informazioni ed esempi specifici di Microsoft Graph.
- **Ambiente ibrido:** Le API di esportazione supportano i messaggi inviati da utenti di cui è stato eseguito il provisioning nell'ambiente ibrido (Exchange e Teams). Tutti i messaggi inviati da utenti configurati per l'ambiente ibrido saranno accessibili tramite le API di esportazione.
- **Messaggi eliminati dall'utente:** È possibile accedere ai messaggi eliminati dagli utenti dal client Teams tramite le API di esportazione fino a 21 giorni dal momento dell'eliminazione.
- **Allegati del messaggio:** Le API di esportazione includono i collegamenti agli allegati inviati come parte dei messaggi. Usando le API di esportazione è possibile recuperare i file allegati nei messaggi.
- **Proprietà messaggio chat:** Fare riferimento all'elenco completo delle proprietà supportate Teams api di esportazione [qui](/graph/api/resources/chatmessage?view=graph-rest-beta#properties).

>[!NOTE]
>Le API di esportazione non supportano *le reazioni.*

## <a name="how-to-access-teams-export-apis"></a>Come accedere alle API di Teams di esportazione

- **L'esempio 1** è una semplice query per recuperare tutti i messaggi di un utente o di un team senza filtri:

    ```HTTP
    GET https://graph.microsoft.com/v1.0/users/{id}/chats/getAllMessages
    ```
     ```HTTP
    GET https://graph.microsoft.com/v1.0/teams/{id}/channels/getAllMessages
    ```

- **L'esempio 2** è una query di esempio per recuperare tutti i messaggi di un utente o di un team specificando i filtri data e ora e i primi 50 messaggi:

    ```HTTP
    GET https://graph.microsoft.com/v1.0/users/{id}/chats/getAllMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```
    ```HTTP
    GET https://graph.microsoft.com/v1.0/teams/{id}/channels/getAllMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```
>[!NOTE]
>L'API restituisce la risposta con il collegamento alla pagina successiva in caso di più risultati. Per ottenere il set di risultati successivo, è sufficiente chiamare GET sull'URL da @odata.nextlink. Se @odata.nextlink non è presente o Null, vengono recuperati tutti i messaggi.

## <a name="prerequisites-to-access-teams-export-apis"></a>Prerequisiti per l'accesso Teams API di esportazione 

- Microsoft Teams Le API in Microsoft Graph che accedono ai dati riservati sono considerate API protette. Le API di esportazione richiedono la convalida aggiuntiva, oltre alle autorizzazioni e al consenso, prima di poterle usare. Per richiedere l'accesso a queste API protette, compilare il [modulo di richiesta.](https://aka.ms/teamsgraph/requestaccess)
- Le autorizzazioni per le applicazioni vengono usate dalle app eseguite senza che sia presente un utente connesso. le autorizzazioni dell'applicazione possono essere concesse solo da un amministratore. Sono necessarie le autorizzazioni seguenti:

    - *Chat.Read.All*: consente l'accesso a tutti i messaggi 1:1, chat di gruppo e chat della riunione 
    - *ChannelMessage.Read.All*: consente l'accesso a tutti i messaggi del canale  
    - *User.Read.All*: consente l'accesso all'elenco di utenti per un tenant

## <a name="license-requirements-for-teams-export-apis"></a>Requisiti di licenza per Teams api di esportazione

L'API di esportazione supporta gli scenari di sicurezza e conformità (S+C) e gli scenari di utilizzo generale tramite un parametro di query del modello. Gli scenari S+C (modello A) includono capacità di seed e richiedono un abbonamento E5 e scenari di utilizzo generale (modello B) sono disponibili per tutte le sottoscrizioni ed è solo a consumo. Per altre informazioni sulle spese di capacità e consumo di seeded, vedere Requisiti di licenza e pagamento per [le API Graph Teams Microsoft](/graph/teams-licenses).

### <a name="scmodel-a-scenarios"></a>Scenari S+C/Model A

Limitato alle applicazioni che eseguono funzioni di sicurezza e/o conformità, gli utenti devono avere licenze E5 specifiche per usare questa funzionalità e ricevere capacità di seed. La capacità con seed è per utente e viene calcolata al mese e viene aggregata a livello di tenant. Per un utilizzo che non supera la capacità di seed, i proprietari delle app vengono fatturati per il consumo di API. Il modello A può accedere solo ai messaggi provenienti da utenti a cui è assegnata una licenza E5.

### <a name="general-usagemodel-b-scenarios"></a>Utilizzo generale/Scenari di modello B

Disponibile per tutti gli scenari non correlati a S+C, non sono disponibili requisiti di licenza o capacità di seed. Quando i contatori dei consumi diventano disponibili, ai proprietari delle app verrà addebitato l'addebito per tutte le chiamate API mensili. 

### <a name="evaluation-mode-default"></a>Modalità di valutazione (impostazione predefinita)

Nessuna dichiarazione di modello consente l'accesso alle API con utilizzo limitato per ogni richiesta di applicazione a scopo di valutazione. 

## <a name="json-representation"></a>Rappresentazione JSON

L'esempio seguente è una rappresentazione JSON della risorsa:

Spazio dei nomi: microsoft.graph

```JSON
{
"id": "string (identifier)",
"replyToId": "string (identifier)",
"from": {"@odata.type": "microsoft.graph.identitySet"},
"etag": "string",
"messageType": "string",
"createdDateTime": "string (timestamp)",
"lastModifiedDateTime": "string (timestamp)",
"deletedDateTime": "string (timestamp)",
"subject": "string",
"from": {
                "application": null,
                "device": null,
                "conversation": null,
                "user": {

                    "id": \[{"@odata.type": "microsoft.graph.user"}\],
                    "displayName": "User Name",

                    "userIdentityType": "aadUser"                }
            },
"body": {"@odata.type": "microsoft.graph.itemBody"},
"summary": "string",

"chatId": \[{"@odata.type": "microsoft.graph.chat"}\]

"attachments": \[{"@odata.type": "microsoft.graph.chatMessageAttachment"}\],
"mentions": \[{"@odata.type": "microsoft.graph.chatMessageMention"}\],
"importance": "string",
"locale": "string",
}
```

>[!NOTE]
>Per altre informazioni sulla risorsa chatMessage, vedere l'articolo sul tipo [di risorsa chatMessage.](/graph/api/resources/chatmessage)