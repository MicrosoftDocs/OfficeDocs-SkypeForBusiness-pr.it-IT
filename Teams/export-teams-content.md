---
title: Esportare contenuto con le API di esportazione di Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: reference
audience: admin
ms.service: msteams
ms.reviewer: vikramju
description: In questo articolo vengono illustrate le informazioni su come esportare il contenuto dei team tramite le API di esportazione di Microsoft teams.
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
ms.openlocfilehash: f4ea2d747d40c221d9e99b51fc7b15da8e2cdd12
ms.sourcegitcommit: 04eba352d9e203aa9cd1282c4f4c7158a0469678
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2021
ms.locfileid: "49944601"
---
# <a name="export-content-with-the-microsoft-teams-export-apis"></a>Esportare contenuto con le API di esportazione di Microsoft Teams

Le API di esportazione dei team consentono di esportare 1:1, chat di gruppo e messaggi di canale da Microsoft teams. Se l'organizzazione deve esportare i messaggi di Microsoft teams, è possibile estrarli usando le API di esportazione di teams. *Messaggio di chat* rappresenta un singolo messaggio di chat all'interno di un [canale](https://docs.microsoft.com/graph/api/resources/channel?view=graph-rest-beta) o una [chat](https://docs.microsoft.com/graph/api/resources/chat?view=graph-rest-beta). Il messaggio di chat può essere un messaggio di chat radice o parte di un thread di risposta definito dalla proprietà **replyToId** nel messaggio di chat.

Ecco alcuni esempi su come usare queste API di esportazione:

- **Esempio 1**: se sono stati abilitati Microsoft teams nell'organizzazione e si vogliono esportare tutti i messaggi di Microsoft teams fino a una data a livello di codice, passando l'intervallo di date per un utente o un team specifico.
- **Esempio 2**: se si vuole esportare a livello di codice tutti i messaggi dell'utente o del team ogni giorno fornendo un intervallo di date. Le API di esportazione possono recuperare tutti i messaggi creati o aggiornati durante l'intervallo di date specifico.

## <a name="what-is-supported-by-the-teams-export-apis"></a>Cosa è supportato dalle API di esportazione dei team?

- **Esportazione in blocco del messaggio teams:** Le API di esportazione dei team supportano fino a 200 RPS per app per tenant e 600 RPS per un'applicazione, con questi limiti dovresti essere in grado di esportare in blocco i messaggi di teams.
- **Contesto applicazione**: per chiamare Microsoft Graph, la tua app deve acquisire un token di accesso dalla piattaforma Microsoft Identity. Il token di accesso contiene informazioni sulla tua app e sulle autorizzazioni per le risorse e le API disponibili tramite Microsoft Graph. Per ottenere un token di accesso, la tua app deve essere registrata con la piattaforma di identità Microsoft ed essere autorizzata da un utente o da un amministratore per accedere alle risorse di Microsoft Graph necessarie.

    Se si ha già familiarità con l'integrazione di un'app con la piattaforma Microsoft Identity per ottenere i token, vedere la sezione [passaggi successivi](https://docs.microsoft.com/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps) per informazioni ed esempi specifici di Microsoft Graph.
- **Ambiente ibrido:** Le API di esportazione supportano i messaggi inviati dagli utenti che hanno eseguito il provisioning in ambiente ibrido (Exchange locale e teams). Tutti i messaggi inviati dagli utenti configurati per l'ambiente ibrido saranno accessibili con le API di esportazione.
- **Messaggi eliminati dall'utente:** I messaggi eliminati dall'utente da teams client possono essere raggiunti usando le API di esportazione fino a 30 giorni dopo l'eliminazione.
- **Allegati ai messaggi:** Le API di esportazione includono i collegamenti agli allegati inviati come parte dei messaggi. Uso delle API di esportazione è possibile recuperare i file allegati nei messaggi.
- **Proprietà del messaggio di chat:** Fare riferimento all'elenco completo delle proprietà supportate da teams Export [Apis.](https://docs.microsoft.com/graph/api/resources/chatmessage?view=graph-rest-beta#properties)

## <a name="how-to-access-teams-export-apis"></a>Come accedere alle API di esportazione di Teams

- L' **esempio 1** è una semplice query per recuperare tutti i messaggi di un utente o di un team senza filtri:

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/allMessages
    ```
     ```HTTP
    GET https://graph.microsoft.com/beta/teams/{id}/channels/allMessages
    ```

- L' **esempio 2** è una query di esempio che consente di recuperare tutti i messaggi di un utente o di un team specificando i filtri di data e ora principali 50:

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/allMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```
```HTTP
    GET https://graph.microsoft.com/beta/teams/{id}/channels/allMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```
>[!NOTE]
>The API returns response with next page link in case of multiple results. For getting next set of results, simply call GET on the url from @odata.nextlink. If @odata.nextlink is not present or null then all messages are retrieved.

## Prerequisites to access Teams Export APIs 

- Teams Export APIs are currently in preview. It will only be available to users and tenants that have the [required licenses](https://aka.ms/teams-changenotification-licenses) for APIs. In the future, Microsoft may require you or your customers to pay additional fees based on the amount of data accessed through the API.
- Microsoft Teams APIs in Microsoft Graph that access sensitive data are considered protected APIs. Export APIs require that you have additional validation, beyond permissions and consent, before you can use them. To request access to these protected APIs, complete the [request form](https://aka.ms/teamsgraph/requestaccess).
- Application permissions are used by apps that run without a signed-in user present; application permissions can only be consented by an administrator. The following permissions are needed:

    - *Chat.Read.All*: enables access to all 1:1 and Group chat messages 
    - *User.Read.All*: enables access to the list of users for a tenant 

## JSON representation

The following example is a JSON representation of the resource:

Namespace: microsoft.graph

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
                    "id": "string (identifier)",
                    "displayName": "string",
                    "userIdentityType": "aadUser"                }
            },
"body": {"@odata.type": "microsoft.graph.itemBody"},
"summary": "string",
"chatId": "string (identifier)"
"attachments": \[{"@odata.type": "microsoft.graph.chatMessageAttachment"}\],
"mentions": \[{"@odata.type": "microsoft.graph.chatMessageMention"}\],
"importance": "string",
"locale": "string",
}
```

>[!NOTE]
>Per altre informazioni sulla risorsa chatMessage, Vedi l'articolo relativo al [tipo di risorsa chatMessage](https://docs.microsoft.com/graph/api/resources/chatmessage) .
