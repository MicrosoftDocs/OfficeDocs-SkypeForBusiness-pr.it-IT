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
# <a name="export-content-with-the-microsoft-teams-export-apis"></a><span data-ttu-id="f3670-103">Esportare contenuto con le API di esportazione di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f3670-103">Export content with the Microsoft Teams Export APIs</span></span>

<span data-ttu-id="f3670-104">Le API di esportazione dei team consentono di esportare 1:1, chat di gruppo e messaggi di canale da Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="f3670-104">Teams Export APIs allow you to export 1:1, group chat, and channel messages from Microsoft Teams.</span></span> <span data-ttu-id="f3670-105">Se l'organizzazione deve esportare i messaggi di Microsoft teams, è possibile estrarli usando le API di esportazione di teams.</span><span class="sxs-lookup"><span data-stu-id="f3670-105">If your organization needs to export Microsoft Teams messages, you are able to extract them using Teams Export APIs.</span></span> <span data-ttu-id="f3670-106">*Messaggio di chat* rappresenta un singolo messaggio di chat all'interno di un [canale](https://docs.microsoft.com/graph/api/resources/channel?view=graph-rest-beta) o una [chat](https://docs.microsoft.com/graph/api/resources/chat?view=graph-rest-beta).</span><span class="sxs-lookup"><span data-stu-id="f3670-106">*Chat Message* represents an individual chat message within a [channel](https://docs.microsoft.com/graph/api/resources/channel?view=graph-rest-beta) or [chat](https://docs.microsoft.com/graph/api/resources/chat?view=graph-rest-beta).</span></span> <span data-ttu-id="f3670-107">Il messaggio di chat può essere un messaggio di chat radice o parte di un thread di risposta definito dalla proprietà **replyToId** nel messaggio di chat.</span><span class="sxs-lookup"><span data-stu-id="f3670-107">The chat message can be a root chat message or part of a reply thread that is defined by the **replyToId** property in the chat message.</span></span>

<span data-ttu-id="f3670-108">Ecco alcuni esempi su come usare queste API di esportazione:</span><span class="sxs-lookup"><span data-stu-id="f3670-108">Here are some examples on how you can use these export APIs:</span></span>

- <span data-ttu-id="f3670-109">**Esempio 1**: se sono stati abilitati Microsoft teams nell'organizzazione e si vogliono esportare tutti i messaggi di Microsoft teams fino a una data a livello di codice, passando l'intervallo di date per un utente o un team specifico.</span><span class="sxs-lookup"><span data-stu-id="f3670-109">**Example 1**: If you have enabled Microsoft Teams in your organization and want to export all the Microsoft Teams messages to date programmatically by passing the date range for a given user or team.</span></span>
- <span data-ttu-id="f3670-110">**Esempio 2**: se si vuole esportare a livello di codice tutti i messaggi dell'utente o del team ogni giorno fornendo un intervallo di date.</span><span class="sxs-lookup"><span data-stu-id="f3670-110">**Example 2**: If you want to programmatically export all user or team messages daily by providing a date range.</span></span> <span data-ttu-id="f3670-111">Le API di esportazione possono recuperare tutti i messaggi creati o aggiornati durante l'intervallo di date specifico.</span><span class="sxs-lookup"><span data-stu-id="f3670-111">Export APIs can retrieve all the messages created or updated during the given date range.</span></span>

## <a name="what-is-supported-by-the-teams-export-apis"></a><span data-ttu-id="f3670-112">Cosa è supportato dalle API di esportazione dei team?</span><span class="sxs-lookup"><span data-stu-id="f3670-112">What is supported by the Teams Export APIs?</span></span>

- <span data-ttu-id="f3670-113">**Esportazione in blocco del messaggio teams:** Le API di esportazione dei team supportano fino a 200 RPS per app per tenant e 600 RPS per un'applicazione, con questi limiti dovresti essere in grado di esportare in blocco i messaggi di teams.</span><span class="sxs-lookup"><span data-stu-id="f3670-113">**Bulk Export of Teams Message:** Teams Export APIs support up to 200 RPS Per App Per tenant and 600 RPS for an Application, with these limits you should be able to bulk export of Teams messages.</span></span>
- <span data-ttu-id="f3670-114">**Contesto applicazione**: per chiamare Microsoft Graph, la tua app deve acquisire un token di accesso dalla piattaforma Microsoft Identity.</span><span class="sxs-lookup"><span data-stu-id="f3670-114">**Application Context**: To call Microsoft Graph, your app must acquire an access token from the Microsoft identity platform.</span></span> <span data-ttu-id="f3670-115">Il token di accesso contiene informazioni sulla tua app e sulle autorizzazioni per le risorse e le API disponibili tramite Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="f3670-115">The access token contains information about your app and the permissions it has for the resources and APIs available through Microsoft Graph.</span></span> <span data-ttu-id="f3670-116">Per ottenere un token di accesso, la tua app deve essere registrata con la piattaforma di identità Microsoft ed essere autorizzata da un utente o da un amministratore per accedere alle risorse di Microsoft Graph necessarie.</span><span class="sxs-lookup"><span data-stu-id="f3670-116">To get an access token, your app must be registered with the Microsoft identity platform and be authorized by either a user or an administrator for access to the Microsoft Graph resources it needs.</span></span>

    <span data-ttu-id="f3670-117">Se si ha già familiarità con l'integrazione di un'app con la piattaforma Microsoft Identity per ottenere i token, vedere la sezione [passaggi successivi](https://docs.microsoft.com/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps) per informazioni ed esempi specifici di Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="f3670-117">If you are already familiar with integrating an app with the Microsoft identity platform to get tokens, see the [Next Steps](https://docs.microsoft.com/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps) section for information and samples specific to Microsoft Graph.</span></span>
- <span data-ttu-id="f3670-118">**Ambiente ibrido:** Le API di esportazione supportano i messaggi inviati dagli utenti che hanno eseguito il provisioning in ambiente ibrido (Exchange locale e teams).</span><span class="sxs-lookup"><span data-stu-id="f3670-118">**Hybrid Environment:** Export APIs support messages sent by users who are provisioned on Hybrid Environment (on-premises Exchange and Teams).</span></span> <span data-ttu-id="f3670-119">Tutti i messaggi inviati dagli utenti configurati per l'ambiente ibrido saranno accessibili con le API di esportazione.</span><span class="sxs-lookup"><span data-stu-id="f3670-119">Any messages that are sent by users who are configured for hybrid environment will be accessible using Export APIs.</span></span>
- <span data-ttu-id="f3670-120">**Messaggi eliminati dall'utente:** I messaggi eliminati dall'utente da teams client possono essere raggiunti usando le API di esportazione fino a 30 giorni dopo l'eliminazione.</span><span class="sxs-lookup"><span data-stu-id="f3670-120">**User Deleted Messages:** Messages that are deleted by user from Teams client can be accessed using export APIs up to 30 days from the time of deletion.</span></span>
- <span data-ttu-id="f3670-121">**Allegati ai messaggi:** Le API di esportazione includono i collegamenti agli allegati inviati come parte dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="f3670-121">**Message Attachments:** Export APIs include the links to the attachments that are sent as part of messages.</span></span> <span data-ttu-id="f3670-122">Uso delle API di esportazione è possibile recuperare i file allegati nei messaggi.</span><span class="sxs-lookup"><span data-stu-id="f3670-122">Using Export APIs you can retrieve the files attached in the messages.</span></span>
- <span data-ttu-id="f3670-123">**Proprietà del messaggio di chat:** Fare riferimento all'elenco completo delle proprietà supportate da teams Export [Apis.](https://docs.microsoft.com/graph/api/resources/chatmessage?view=graph-rest-beta#properties)</span><span class="sxs-lookup"><span data-stu-id="f3670-123">**Chat Message Properties:** Refer to the complete list of properties that Teams Export APIs support [here](https://docs.microsoft.com/graph/api/resources/chatmessage?view=graph-rest-beta#properties).</span></span>

## <a name="how-to-access-teams-export-apis"></a><span data-ttu-id="f3670-124">Come accedere alle API di esportazione di Teams</span><span class="sxs-lookup"><span data-stu-id="f3670-124">How to access Teams Export APIs</span></span>

- <span data-ttu-id="f3670-125">L' **esempio 1** è una semplice query per recuperare tutti i messaggi di un utente o di un team senza filtri:</span><span class="sxs-lookup"><span data-stu-id="f3670-125">**Example 1** is a simple query to retrieve all the messages of a user or team without any filters:</span></span>

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/allMessages
    ```
     ```HTTP
    GET https://graph.microsoft.com/beta/teams/{id}/channels/allMessages
    ```

- <span data-ttu-id="f3670-126">L' **esempio 2** è una query di esempio che consente di recuperare tutti i messaggi di un utente o di un team specificando i filtri di data e ora principali 50:</span><span class="sxs-lookup"><span data-stu-id="f3670-126">**Example 2** is a sample query to retrieve all the messages of a user or team by specifying date time filters and top 50 messages:</span></span>

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
><span data-ttu-id="f3670-127">Per altre informazioni sulla risorsa chatMessage, Vedi l'articolo relativo al [tipo di risorsa chatMessage](https://docs.microsoft.com/graph/api/resources/chatmessage) .</span><span class="sxs-lookup"><span data-stu-id="f3670-127">For more details on chatMessage resource, see the [chatMessage resource type](https://docs.microsoft.com/graph/api/resources/chatmessage) article.</span></span>
