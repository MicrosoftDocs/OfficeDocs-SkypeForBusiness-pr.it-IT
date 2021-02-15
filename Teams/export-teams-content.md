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
ms.openlocfilehash: 9c99bed1ef9a1862b469dd5214b8d829bde8479b
ms.sourcegitcommit: 15c45befbee35e69f9ec82493151cb82e61da4fb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2021
ms.locfileid: "50096929"
---
# <a name="export-content-with-the-microsoft-teams-export-apis"></a><span data-ttu-id="d6be1-103">Esportare contenuto con le API di esportazione di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d6be1-103">Export content with the Microsoft Teams Export APIs</span></span>

<span data-ttu-id="d6be1-104">Le API di esportazione di Teams consentono di esportare 1:1, chat di gruppo e messaggi del canale da Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d6be1-104">Teams Export APIs allow you to export 1:1, group chat, and channel messages from Microsoft Teams.</span></span> <span data-ttu-id="d6be1-105">Se l'organizzazione deve esportare i messaggi di Microsoft Teams, è possibile estrarli usando le API di esportazione di Teams.</span><span class="sxs-lookup"><span data-stu-id="d6be1-105">If your organization needs to export Microsoft Teams messages, you are able to extract them using Teams Export APIs.</span></span> <span data-ttu-id="d6be1-106">*Il messaggio di* chat rappresenta un singolo messaggio di chat all'interno [di un canale o](https://docs.microsoft.com/graph/api/resources/channel?view=graph-rest-beta) di una [chat.](https://docs.microsoft.com/graph/api/resources/chat?view=graph-rest-beta)</span><span class="sxs-lookup"><span data-stu-id="d6be1-106">*Chat Message* represents an individual chat message within a [channel](https://docs.microsoft.com/graph/api/resources/channel?view=graph-rest-beta) or [chat](https://docs.microsoft.com/graph/api/resources/chat?view=graph-rest-beta).</span></span> <span data-ttu-id="d6be1-107">Il messaggio di chat può essere un messaggio di chat radice o parte di un thread di risposta definito dalla proprietà **replyToId** nel messaggio di chat.</span><span class="sxs-lookup"><span data-stu-id="d6be1-107">The chat message can be a root chat message or part of a reply thread that is defined by the **replyToId** property in the chat message.</span></span>

<span data-ttu-id="d6be1-108">Ecco alcuni esempi su come usare queste API di esportazione:</span><span class="sxs-lookup"><span data-stu-id="d6be1-108">Here are some examples on how you can use these export APIs:</span></span>

- <span data-ttu-id="d6be1-109">**Esempio 1:** se Microsoft Teams è stato abilitato nell'organizzazione e si vogliono esportare tutti i messaggi di Microsoft Teams a livello di programmazione passando l'intervallo di date per un determinato utente o team.</span><span class="sxs-lookup"><span data-stu-id="d6be1-109">**Example 1**: If you have enabled Microsoft Teams in your organization and want to export all the Microsoft Teams messages to date programmatically by passing the date range for a given user or team.</span></span>
- <span data-ttu-id="d6be1-110">**Esempio 2:** se si vogliono esportare a livello di programmazione tutti i messaggi di utenti o del team quotidianamente, specificando un intervallo di date.</span><span class="sxs-lookup"><span data-stu-id="d6be1-110">**Example 2**: If you want to programmatically export all user or team messages daily by providing a date range.</span></span> <span data-ttu-id="d6be1-111">Le API di esportazione possono recuperare tutti i messaggi creati o aggiornati durante l'intervallo di date specificato.</span><span class="sxs-lookup"><span data-stu-id="d6be1-111">Export APIs can retrieve all the messages created or updated during the given date range.</span></span>

## <a name="what-is-supported-by-the-teams-export-apis"></a><span data-ttu-id="d6be1-112">Cosa è supportato dalle API di esportazione di Teams?</span><span class="sxs-lookup"><span data-stu-id="d6be1-112">What is supported by the Teams Export APIs?</span></span>

- <span data-ttu-id="d6be1-113">**Esportazione in blocco del messaggio di Teams:** Le API di esportazione di Teams supportano fino a 200 RPS per app Per tenant e 600 RPS per un'applicazione, con questi limiti dovrebbe essere possibile esportare in blocco i messaggi di Teams.</span><span class="sxs-lookup"><span data-stu-id="d6be1-113">**Bulk Export of Teams Message:** Teams Export APIs support up to 200 RPS Per App Per tenant and 600 RPS for an Application, with these limits you should be able to bulk export of Teams messages.</span></span>
- <span data-ttu-id="d6be1-114">**Contesto dell'applicazione:** per chiamare Microsoft Graph, l'app deve acquisire un token di accesso dalla piattaforma di identità Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d6be1-114">**Application Context**: To call Microsoft Graph, your app must acquire an access token from the Microsoft identity platform.</span></span> <span data-ttu-id="d6be1-115">Il token di accesso contiene informazioni sull'app e le autorizzazioni disponibili per le risorse e le API tramite Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="d6be1-115">The access token contains information about your app and the permissions it has for the resources and APIs available through Microsoft Graph.</span></span> <span data-ttu-id="d6be1-116">Per ottenere un token di accesso, l'app deve essere registrata con la piattaforma di identità Microsoft ed essere autorizzata da un utente o un amministratore per l'accesso alle risorse di Microsoft Graph necessarie.</span><span class="sxs-lookup"><span data-stu-id="d6be1-116">To get an access token, your app must be registered with the Microsoft identity platform and be authorized by either a user or an administrator for access to the Microsoft Graph resources it needs.</span></span>

    <span data-ttu-id="d6be1-117">Se si ha già familiarità con l'integrazione di un'app [](https://docs.microsoft.com/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps) con la piattaforma di identità Microsoft per ottenere token, vedere la sezione Passaggi successivi per informazioni ed esempi specifici per Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="d6be1-117">If you are already familiar with integrating an app with the Microsoft identity platform to get tokens, see the [Next Steps](https://docs.microsoft.com/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps) section for information and samples specific to Microsoft Graph.</span></span>
- <span data-ttu-id="d6be1-118">**Ambiente ibrido:** Esportare i messaggi di supporto delle API inviati da utenti con provisioning in ambiente ibrido (Exchange e Teams locale).</span><span class="sxs-lookup"><span data-stu-id="d6be1-118">**Hybrid Environment:** Export APIs support messages sent by users who are provisioned on Hybrid Environment (on-premises Exchange and Teams).</span></span> <span data-ttu-id="d6be1-119">Tutti i messaggi inviati dagli utenti configurati per l'ambiente ibrido saranno accessibili tramite le API di esportazione.</span><span class="sxs-lookup"><span data-stu-id="d6be1-119">Any messages that are sent by users who are configured for hybrid environment will be accessible using Export APIs.</span></span>
- <span data-ttu-id="d6be1-120">**Messaggi eliminati dall'utente:** I messaggi eliminati dall'utente dal client Teams sono accessibili tramite LE API di esportazione fino a 30 giorni dal momento dell'eliminazione.</span><span class="sxs-lookup"><span data-stu-id="d6be1-120">**User Deleted Messages:** Messages that are deleted by user from Teams client can be accessed using export APIs up to 30 days from the time of deletion.</span></span>
- <span data-ttu-id="d6be1-121">**Allegati del messaggio:** Le API di esportazione includono i collegamenti agli allegati inviati come parte dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="d6be1-121">**Message Attachments:** Export APIs include the links to the attachments that are sent as part of messages.</span></span> <span data-ttu-id="d6be1-122">Con le API di esportazione è possibile recuperare i file allegati nei messaggi.</span><span class="sxs-lookup"><span data-stu-id="d6be1-122">Using Export APIs you can retrieve the files attached in the messages.</span></span>
- <span data-ttu-id="d6be1-123">**Proprietà dei messaggi di chat:** Fare riferimento all'elenco completo delle proprietà supportate da queste API di Esportazione [di](https://docs.microsoft.com/graph/api/resources/chatmessage?view=graph-rest-beta#properties)Teams.</span><span class="sxs-lookup"><span data-stu-id="d6be1-123">**Chat Message Properties:** Refer to the complete list of properties that Teams Export APIs support [here](https://docs.microsoft.com/graph/api/resources/chatmessage?view=graph-rest-beta#properties).</span></span>

## <a name="how-to-access-teams-export-apis"></a><span data-ttu-id="d6be1-124">Come accedere alle API di esportazione di Teams</span><span class="sxs-lookup"><span data-stu-id="d6be1-124">How to access Teams Export APIs</span></span>

- <span data-ttu-id="d6be1-125">**L'esempio 1** è una query semplice per recuperare tutti i messaggi di un utente o un team senza filtri:</span><span class="sxs-lookup"><span data-stu-id="d6be1-125">**Example 1** is a simple query to retrieve all the messages of a user or team without any filters:</span></span>

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/getallMessages
    ```
     ```HTTP
    GET https://graph.microsoft.com/beta/teams/{id}/channels/getallMessages
    ```

- <span data-ttu-id="d6be1-126">**L'esempio 2** è una query di esempio per recuperare tutti i messaggi di un utente o di un team specificando filtri di data e ora e i primi 50 messaggi:</span><span class="sxs-lookup"><span data-stu-id="d6be1-126">**Example 2** is a sample query to retrieve all the messages of a user or team by specifying date time filters and top 50 messages:</span></span>

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/getallMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```
    ```HTTP
    GET https://graph.microsoft.com/beta/teams/{id}/channels/getallMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```
>[!NOTE]
><span data-ttu-id="d6be1-127">L'API restituisce la risposta con il collegamento alla pagina successiva in caso di più risultati.</span><span class="sxs-lookup"><span data-stu-id="d6be1-127">The API returns response with next page link in case of multiple results.</span></span> <span data-ttu-id="d6be1-128">Per ottenere il set di risultati successivo, basta chiamare GET sull'URL da @odata.nextlink.</span><span class="sxs-lookup"><span data-stu-id="d6be1-128">For getting next set of results, simply call GET on the url from @odata.nextlink.</span></span> <span data-ttu-id="d6be1-129">Se @odata.nextlink non è presente o Null, vengono recuperati tutti i messaggi.</span><span class="sxs-lookup"><span data-stu-id="d6be1-129">If @odata.nextlink is not present or null then all messages are retrieved.</span></span>

## <a name="prerequisites-to-access-teams-export-apis"></a><span data-ttu-id="d6be1-130">Prerequisiti per accedere alle API di esportazione di Teams</span><span class="sxs-lookup"><span data-stu-id="d6be1-130">Prerequisites to access Teams Export APIs</span></span> 

- <span data-ttu-id="d6be1-131">Le API di esportazione di Teams sono attualmente in anteprima.</span><span class="sxs-lookup"><span data-stu-id="d6be1-131">Teams Export APIs are currently in preview.</span></span> <span data-ttu-id="d6be1-132">Sarà disponibile solo per gli utenti e i tenant che hanno le [licenze necessarie](https://aka.ms/teams-changenotification-licenses) per le API.</span><span class="sxs-lookup"><span data-stu-id="d6be1-132">It will only be available to users and tenants that have the [required licenses](https://aka.ms/teams-changenotification-licenses) for APIs.</span></span> <span data-ttu-id="d6be1-133">In futuro, Microsoft potrebbe richiedere all'utente o ai clienti di pagare ulteriori costi in base all'importo dei dati a cui si accede tramite l'API.</span><span class="sxs-lookup"><span data-stu-id="d6be1-133">In the future, Microsoft may require you or your customers to pay additional fees based on the amount of data accessed through the API.</span></span>
- <span data-ttu-id="d6be1-134">Le API Microsoft Teams in Microsoft Graph che accedono ai dati sensibili sono considerate API protette.</span><span class="sxs-lookup"><span data-stu-id="d6be1-134">Microsoft Teams APIs in Microsoft Graph that access sensitive data are considered protected APIs.</span></span> <span data-ttu-id="d6be1-135">Per poter usare le API di esportazione è necessario disporre di una convalida aggiuntiva, oltre alle autorizzazioni e al consenso.</span><span class="sxs-lookup"><span data-stu-id="d6be1-135">Export APIs require that you have additional validation, beyond permissions and consent, before you can use them.</span></span> <span data-ttu-id="d6be1-136">Per richiedere l'accesso a queste API protette, completare il [modulo di richiesta.](https://aka.ms/teamsgraph/requestaccess)</span><span class="sxs-lookup"><span data-stu-id="d6be1-136">To request access to these protected APIs, complete the [request form](https://aka.ms/teamsgraph/requestaccess).</span></span>
- <span data-ttu-id="d6be1-137">Le autorizzazioni per le applicazioni vengono usate dalle app che vengono eseguite senza un utente connesso presente; le autorizzazioni dell'applicazione possono essere consentite solo da un amministratore.</span><span class="sxs-lookup"><span data-stu-id="d6be1-137">Application permissions are used by apps that run without a signed-in user present; application permissions can only be consented by an administrator.</span></span> <span data-ttu-id="d6be1-138">Sono necessarie le autorizzazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d6be1-138">The following permissions are needed:</span></span>

    - <span data-ttu-id="d6be1-139">*Chat.Read.All:* consente l'accesso a tutti i messaggi di chat 1:1 e di gruppo</span><span class="sxs-lookup"><span data-stu-id="d6be1-139">*Chat.Read.All*: enables access to all 1:1 and Group chat messages</span></span> 
    - <span data-ttu-id="d6be1-140">*User.Read.All:* abilita l'accesso all'elenco di utenti per un tenant</span><span class="sxs-lookup"><span data-stu-id="d6be1-140">*User.Read.All*: enables access to the list of users for a tenant</span></span> 

## <a name="json-representation"></a><span data-ttu-id="d6be1-141">Rappresentazione JSON</span><span class="sxs-lookup"><span data-stu-id="d6be1-141">JSON representation</span></span>

<span data-ttu-id="d6be1-142">L'esempio seguente è una rappresentazione JSON della risorsa:</span><span class="sxs-lookup"><span data-stu-id="d6be1-142">The following example is a JSON representation of the resource:</span></span>

<span data-ttu-id="d6be1-143">Spazio dei nomi: microsoft.graph</span><span class="sxs-lookup"><span data-stu-id="d6be1-143">Namespace: microsoft.graph</span></span>

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
><span data-ttu-id="d6be1-144">Per altre informazioni sulla risorsa ChatMessage, vedere l'articolo sul tipo [di risorsa chatMessage.](https://docs.microsoft.com/graph/api/resources/chatmessage)</span><span class="sxs-lookup"><span data-stu-id="d6be1-144">For more details on chatMessage resource, see the [chatMessage resource type](https://docs.microsoft.com/graph/api/resources/chatmessage) article.</span></span>
