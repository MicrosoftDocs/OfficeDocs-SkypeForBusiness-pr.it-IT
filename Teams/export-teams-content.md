---
title: Esportare contenuto con le API di esportazione di Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: reference
audience: admin
ms.service: msteams
ms.reviewer: vikramju
description: In questo articolo imparerai a esportare il contenuto di Teams usando le API di esportazione di Microsoft Teams.
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f1bca4eb70bff07e809630e1b997f377064b5e0e
ms.sourcegitcommit: b4b2c7e79679cce6cf5f863ddf708e50164f9a9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/17/2021
ms.locfileid: "50861410"
---
# <a name="export-content-with-the-microsoft-teams-export-apis"></a>Esportare contenuto con le API di esportazione di Microsoft Teams

Le API di esportazione di Teams consentono di esportare messaggi 1:1, chat di gruppo e canali da Microsoft Teams. Se l'organizzazione deve esportare i messaggi di Microsoft Teams, è possibile estrarli usando le API di esportazione di Teams. *Messaggio chat* rappresenta un singolo messaggio di chat all'interno di [un canale o](https://docs.microsoft.com/graph/api/resources/channel?view=graph-rest-beta) di una [chat.](https://docs.microsoft.com/graph/api/resources/chat?view=graph-rest-beta) Il messaggio di chat può essere un messaggio di chat radice o parte di un thread di risposta definito dalla proprietà **replyToId** nel messaggio di chat.

Ecco alcuni esempi su come usare queste API di esportazione:

- **Esempio 1:** se è stato abilitato Microsoft Teams nell'organizzazione e si vogliono esportare tutti i messaggi di Microsoft Teams a livello di programmazione passando l'intervallo di date per un determinato utente o team.
- **Esempio 2:** se si vuole esportare a livello di programmazione tutti i messaggi degli utenti o del team ogni giorno fornendo un intervallo di date. Le API di esportazione possono recuperare tutti i messaggi creati o aggiornati durante l'intervallo di date specificato.

## <a name="what-is-supported-by-the-teams-export-apis"></a>Cosa è supportato dalle API di esportazione di Teams?

- **Esportazione in blocco del messaggio di Teams:** Le API di esportazione di Teams supportano fino a 200 RPS per ogni app Per tenant e 600 RPS per un'applicazione, con questi limiti dovrebbe essere possibile esportare in blocco i messaggi di Teams.
- **Contesto applicazione:** per chiamare Microsoft Graph, l'app deve acquisire un token di accesso dalla piattaforma di identità Microsoft. Il token di accesso contiene informazioni sull'app e sulle autorizzazioni di cui dispone per le risorse e le API disponibili tramite Microsoft Graph. Per ottenere un token di accesso, l'app deve essere registrata con la piattaforma di identità Microsoft ed essere autorizzata da un utente o un amministratore per l'accesso alle risorse di Microsoft Graph necessarie.

    Se si ha già familiarità con l'integrazione di un'app con la piattaforma di identità Microsoft per ottenere token, vedere la [sezione Passaggi](https://docs.microsoft.com/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps) successivi per informazioni ed esempi specifici di Microsoft Graph.
- **Ambiente ibrido:** Le API di esportazione supportano i messaggi inviati da utenti di cui è stato eseguito il provisioning nell'ambiente ibrido (Exchange locale e Teams). Tutti i messaggi inviati da utenti configurati per l'ambiente ibrido saranno accessibili tramite le API di esportazione.
- **Messaggi eliminati dall'utente:** È possibile accedere ai messaggi eliminati dall'utente dal client Teams usando le API di esportazione fino a 30 giorni dal momento dell'eliminazione.
- **Allegati del messaggio:** Le API di esportazione includono i collegamenti agli allegati inviati come parte dei messaggi. Usando le API di esportazione è possibile recuperare i file allegati nei messaggi.
- **Proprietà messaggio chat:** Fare riferimento all'elenco completo delle proprietà supportate da Teams Export APIs [qui](https://docs.microsoft.com/graph/api/resources/chatmessage?view=graph-rest-beta#properties).

## <a name="how-to-access-teams-export-apis"></a>Come accedere alle API di esportazione di Teams

- **L'esempio 1** è una semplice query per recuperare tutti i messaggi di un utente o di un team senza filtri:

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/getallMessages
    ```
     ```HTTP
    GET https://graph.microsoft.com/beta/teams/{id}/channels/getallMessages
    ```

- **L'esempio 2** è una query di esempio per recuperare tutti i messaggi di un utente o di un team specificando i filtri data e ora e i primi 50 messaggi:

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/getallMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```
    ```HTTP
    GET https://graph.microsoft.com/beta/teams/{id}/channels/getallMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```
>[!NOTE]
>L'API restituisce la risposta con il collegamento alla pagina successiva in caso di più risultati. Per ottenere il set di risultati successivo, è sufficiente chiamare GET sull'URL da @odata.nextlink. Se @odata.nextlink non è presente o Null, vengono recuperati tutti i messaggi.

## <a name="prerequisites-to-access-teams-export-apis"></a>Prerequisiti per l'accesso alle API di esportazione di Teams 

- Le API di esportazione di Teams sono attualmente in anteprima. Sarà disponibile solo per gli utenti e i tenant che dispongono delle [licenze necessarie](https://aka.ms/teams-changenotification-licenses) per le API. In futuro, Microsoft potrebbe richiedere a te o ai tuoi clienti di pagare costi aggiuntivi in base alla quantità di dati a cui si accede tramite l'API.
- Le API di Microsoft Teams in Microsoft Graph che accedono ai dati riservati sono considerate API protette. Le API di esportazione richiedono la convalida aggiuntiva, oltre alle autorizzazioni e al consenso, prima di poterle usare. Per richiedere l'accesso a queste API protette, compilare il [modulo di richiesta.](https://aka.ms/teamsgraph/requestaccess)
- Le autorizzazioni per le applicazioni vengono usate dalle app eseguite senza che sia presente un utente connesso. le autorizzazioni dell'applicazione possono essere concesse solo da un amministratore. Sono necessarie le autorizzazioni seguenti:

    - *Chat.Read.All*: consente l'accesso a tutti i messaggi di chat 1:1 e di gruppo 
    - *User.Read.All*: consente l'accesso all'elenco di utenti per un tenant 

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
>Per altre informazioni sulla risorsa chatMessage, vedere l'articolo sul tipo [di risorsa chatMessage.](https://docs.microsoft.com/graph/api/resources/chatmessage)
