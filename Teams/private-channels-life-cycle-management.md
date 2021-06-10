---
title: Gestire i canali privati in Microsoft Teams con Graph API
author: MikePlumleyMSFT
ms.author: mikeplum
manager: serdars
ms.reviewer: suchakr, phlouie
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Informazioni su come gestire i canali privati nell'organizzazione usando Graph API.
ms.openlocfilehash: e97d808bd9f544ef611b0b5e4b0456d302b4013d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117744"
---
# <a name="manage-the-life-cycle-of-private-channels-in-microsoft-teams"></a><span data-ttu-id="64040-103">Gestire il ciclo di vita dei canali privati in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="64040-103">Manage the life cycle of private channels in Microsoft Teams</span></span>

<span data-ttu-id="64040-104">Ecco le indicazioni necessarie per gestire l'uso dell'API Graph per gestire Teams [canali privati](./private-channels.md) dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="64040-104">Here you'll find the guidance you need to manage use the Graph API to manage [Teams private channels](./private-channels.md) in your organization.</span></span>

## <a name="set-whether-team-members-can-create-private-channels"></a><span data-ttu-id="64040-105">Specificare se i membri del team possono creare canali privati</span><span class="sxs-lookup"><span data-stu-id="64040-105">Set whether team members can create private channels</span></span>

<span data-ttu-id="64040-106">Gli amministratori possono usare l’API Graph per controllare se i membri possono creare canali privati in specifici team.</span><span class="sxs-lookup"><span data-stu-id="64040-106">As an admin, you can use Graph API to control whether members can create private channels in specific teams.</span></span> <span data-ttu-id="64040-107">Di seguito viene riportato un esempio.</span><span class="sxs-lookup"><span data-stu-id="64040-107">Here's an example.</span></span>

```Graph API
PATCH /teams/<team_id>
{"memberSettings": 
  {
    "allowCreatePrivateChannels": false
  }
}
```

## <a name="create-a-private-channel-on-behalf-of-a-team-owner"></a><span data-ttu-id="64040-108">Creare un canale privato per conto del proprietario del team</span><span class="sxs-lookup"><span data-stu-id="64040-108">Create a private channel on behalf of a team owner</span></span>

<span data-ttu-id="64040-109">Gli amministratori possono usare l'API Graph per creare un canale privato per conto di un proprietario del team.</span><span class="sxs-lookup"><span data-stu-id="64040-109">As an admin, you can use the Graph API to create a private channel on behalf of a team owner.</span></span> <span data-ttu-id="64040-110">Ad esempio, questa operazione potrebbe essere effettuata se l'organizzazione vuole centralizzare la creazione di canali privati.</span><span class="sxs-lookup"><span data-stu-id="64040-110">For example, you may want to do this if your organization wants to centralize creation of private channels.</span></span>

```Graph API
POST /teams/{id}/channels
{ "membershipType": "Private",
  "displayName": "<Channel_Name>",
  "members":[{    
           "@odata.type":"#microsoft.graph.aadUserConversationMember",
           "user@odata.bind":"https://graph.microsoft.com/beta/users('<user_id>')",
           "roles":["owner"]
            }]
```

## <a name="get-a-list-of-all-private-channel-messages"></a><span data-ttu-id="64040-111">Ottenere un elenco di tutti i messaggi del canale privato</span><span class="sxs-lookup"><span data-stu-id="64040-111">Get a list of all private channel messages</span></span>

<span data-ttu-id="64040-112">Potrebbe essere necessario ottenere un elenco di tutti i messaggi e le risposte pubblicate in un canale privato a scopo di archiviazione e controllo.</span><span class="sxs-lookup"><span data-stu-id="64040-112">You may want to get a list of all messages and replies posted in a private channel for archiving and auditing purposes.</span></span>  <span data-ttu-id="64040-113">Di seguito viene illustrato come usare l'API di Graph per eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="64040-113">Here's how to use Graph API to do this.</span></span>

```Graph API
GET /teams/{id}/channels/{id}/messages
GET /teams/{id}/channels/{id}/messages/{id}/replies/{id}
```

## <a name="find-sharepoint-urls-for-all-private-channels-in-a-team"></a><span data-ttu-id="64040-114">Trovare gli URL di SharePoint per tutti i canali privati di un team</span><span class="sxs-lookup"><span data-stu-id="64040-114">Find SharePoint URLs for all private channels in a team</span></span>

<span data-ttu-id="64040-115">Sia che si stia cercando di eseguire l'eDiscovery o la conservazione legale su file in un canale privato, oppure si stia cercando di creare un'app personalizzata che metta i file in canali privati specifici, è necessario un modo per effettuare una query delle raccolte siti univoci di SharePoint create per ciascuno canale privato.</span><span class="sxs-lookup"><span data-stu-id="64040-115">Whether you're looking to perform eDiscovery or legal hold on files in a private channel or looking to build a custom app that places files in specific private channels, you'll want a way to query the unique SharePoint site collections that are created for each private channel.</span></span>

<span data-ttu-id="64040-116">Gli amministratori possono usare i comandi api Graph per eseguire query su questi URL.</span><span class="sxs-lookup"><span data-stu-id="64040-116">As an admin, you can use Graph APIs commands to query these URLs.</span></span>

<span data-ttu-id="64040-117">È possibile provare questi comandi con [Graph explorer](https://developer.microsoft.com/graph/graph-explorer).</span><span class="sxs-lookup"><span data-stu-id="64040-117">You can try these commands through [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

1. <span data-ttu-id="64040-118">Usare la procedura seguente per ottenere l'elenco di ID del canale privato per un determinato team, in cui <group_id> è l'ID del gruppo del team.</span><span class="sxs-lookup"><span data-stu-id="64040-118">Use the following to get the list of private channel IDs for a given team, where <group_id> is the group ID of the team.</span></span> <span data-ttu-id="64040-119">Questo sarà necessario nelle chiamate successive.</span><span class="sxs-lookup"><span data-stu-id="64040-119">You'll need this in subsequent calls.</span></span> <span data-ttu-id="64040-120">È possibile trovare facilmente l'ID del gruppo nel collegamento al team.</span><span class="sxs-lookup"><span data-stu-id="64040-120">(You can easily find the group ID in the link to the team).</span></span>

    <span data-ttu-id="64040-121">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="64040-121">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels?$filter=membershipType eq 'private'
    ```

    <span data-ttu-id="64040-122">**Risposta**</span><span class="sxs-lookup"><span data-stu-id="64040-122">**Response**</span></span>

    ```Graph API
    HTTP/1.1 200 OK
    Content-type: application/json
    Content-length:
    
    {
      "value": [
        {
          "description": "description-value",
          "displayName": "display-name-value",
          "id": "channel_id",
          "membershipType": "membership-type-value",
          "isFavoriteByDefault": false,
          "webUrl": "webUrl-value",
          "email": "email-value"
        }
      ]
    }
    ```

2. <span data-ttu-id="64040-123">Per ogni canale privato per il quale si vuole ottenere l'URL di SharePoint, eseguire la richiesta seguente, in cui &lt;channel_id&gt; è l'ID del canale.</span><span class="sxs-lookup"><span data-stu-id="64040-123">For each private channel which you want to get the SharePoint URL, make the following request, where &lt;channel_id&gt; is the channel ID.</span></span>

    <span data-ttu-id="64040-124">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="64040-124">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/filesFolder
    ```

    <span data-ttu-id="64040-125">**Risposta**</span><span class="sxs-lookup"><span data-stu-id="64040-125">**Response**</span></span>

    ```Graph API
    HTTP/1.1 200 OK
    Content-type: application/json
    Content-length:
      
    {
      "value": [
        {
          "description": "description-value",
          "displayName": "display-name-value",
          "id": "channel_id",
          "membershipType": "membership-type-value",
          "isFavoriteByDefault": false,
          "webUrl": "webUrl-value",
          "email": "email-value"
        }
      ]
    }
    ```

## <a name="list-and-update-roles-of-owners-and-members-in-a-private-channel"></a><span data-ttu-id="64040-126">Elencare e aggiornare i ruoli di proprietari e membri in un canale privato</span><span class="sxs-lookup"><span data-stu-id="64040-126">List and update roles of owners and members in a private channel</span></span>

<span data-ttu-id="64040-127">È possibile elencare i proprietari e i membri di un canale privato per decidere se sia necessario alzare di livello determinati membri del canale privato e impostarli come proprietari.</span><span class="sxs-lookup"><span data-stu-id="64040-127">You may want to list out the owners and members of a private channel to decide whether you need to promote certain members of the private channel to an owner.</span></span> <span data-ttu-id="64040-128">Questo può verificarsi se sono presenti proprietari di canali privati che hanno lasciato l'organizzazione e il canale privato richiede l'assistenza da parte dell'amministratore per rivendicarne la proprietà.</span><span class="sxs-lookup"><span data-stu-id="64040-128">This can happen when you have owners of private channels who have left the organization and the private channel requires admin help to claim ownership of the channel.</span></span>

<span data-ttu-id="64040-129">L'amministratore può usare l'API Graph per eseguire queste azioni.</span><span class="sxs-lookup"><span data-stu-id="64040-129">As an admin, you can use the Graph API to perform these actions.</span></span>

<span data-ttu-id="64040-130">È possibile provare questi comandi con [Graph explorer](https://developer.microsoft.com/graph/graph-explorer).</span><span class="sxs-lookup"><span data-stu-id="64040-130">You can try these commands through [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

1. <span data-ttu-id="64040-131">Usare quanto segue, in cui&lt;group_id&gt; è l'ID del gruppo del team e &lt;channel_id&gt; è l’ID del canale.</span><span class="sxs-lookup"><span data-stu-id="64040-131">Use the following, where &lt;group_id&gt; is the group ID of the team and &lt;channel_id&gt; is the channel ID.</span></span>

    <span data-ttu-id="64040-132">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="64040-132">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members
    ```
    
    <span data-ttu-id="64040-133">**Risposta**</span><span class="sxs-lookup"><span data-stu-id="64040-133">**Response**</span></span>

    ```Graph API
    HTTP/1.1 200 OK Content-type: application/json
    Content-length: 
    {
          "@odata.context": "https://graph.microsoft.com/beta/$metadata#teams({group_id}')/channels('{channel_id}')/members",
          "@odata.count": 2,
          "value": [
              {
                  "@odata.type": "#microsoft.graph.aadUserConversationMember",
                  "id": "id-value",
                  "roles": [],
                  "displayName": "display-name-value",
                  "userId": "userId-value",
                  "email": "email-value"
              },
              {
                  "@odata.type": "#microsoft.graph.aadUserConversationMember",
              "id": "id-value",
              "roles": ["owner"],
              "displayName": "display-name-value",
              "userId": "userId-value",
              "email": "email-value"
              }
          ]
    }
    ```    
2. <span data-ttu-id="64040-134">Usare quanto segue per alzare di livello un membro a proprietario, in cui &lt;group_id&gt;, &lt;channel_id&gt;, e &lt;id&gt; vengono restituiti dalla chiamata precedente.</span><span class="sxs-lookup"><span data-stu-id="64040-134">Use the following to promote the member to an owner, where &lt;group_id&gt;, &lt;channel_id&gt;, and &lt;id&gt; are returned from the previous call.</span></span> <span data-ttu-id="64040-135">Si noti che &lt;id&gt; e &lt;userId&gt; restituiti dalla chiamata precedente non sono uguali e non sono intercambiabili.</span><span class="sxs-lookup"><span data-stu-id="64040-135">Note that &lt;id&gt; and &lt;userId&gt; returned from the previous call aren't the same and aren't interchangeable.</span></span> <span data-ttu-id="64040-136">Assicurarsi di usare &lt;id&gt;.</span><span class="sxs-lookup"><span data-stu-id="64040-136">Make sure you use &lt;id&gt;.</span></span>

    <span data-ttu-id="64040-137">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="64040-137">**Request**</span></span>

    ```Graph API
    PATCH 
    https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members/<id>
      
    {
    "@odata.type": "#microsoft.graph.aadUserConversationMember",
    "roles": ["owner"]
    }
    ```

    <span data-ttu-id="64040-138">**Risposta**</span><span class="sxs-lookup"><span data-stu-id="64040-138">**Response**</span></span>

    ```Graph API
    HTTP/1.1 200 OK
    Content-type: application/json

    {
      "@odata.context": "https://graph.microsoft.com/beta/$metadata#teams('{group_id}')/channels('{channel_id}')/members/$entity",
      "@odata.type": "#microsoft.graph.aadUserConversationMember",
      "id": "id-value",
      "roles": ["owner"],
      "displayName": "display-name-value",
      "userId": "userId-value",
      "email": "email-value"
     }
    ```

## <a name="related-topics"></a><span data-ttu-id="64040-139">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="64040-139">Related topics</span></span>

[<span data-ttu-id="64040-140">Usare l'API Microsoft Graph per lavorare con Teams</span><span class="sxs-lookup"><span data-stu-id="64040-140">Use the Microsoft Graph API to work with Teams</span></span>](/graph/api/resources/teams-api-overview?view=graph-rest-1.0)

[<span data-ttu-id="64040-141">Elencare canali</span><span class="sxs-lookup"><span data-stu-id="64040-141">List channels</span></span>](/graph/api/channel-list)

[<span data-ttu-id="64040-142">Creare canali</span><span class="sxs-lookup"><span data-stu-id="64040-142">Create channel</span></span>](/graph/api/channel-post)

[<span data-ttu-id="64040-143">Aggiungere membri al canale</span><span class="sxs-lookup"><span data-stu-id="64040-143">Add member to channel</span></span>](/graph/api/conversationmember-add)

[<span data-ttu-id="64040-144">Aggiornare membri nel canale</span><span class="sxs-lookup"><span data-stu-id="64040-144">Update member in channel</span></span>](/graph/api/conversationmember-update)

[<span data-ttu-id="64040-145">Rimuovere membri dal canale</span><span class="sxs-lookup"><span data-stu-id="64040-145">Remove member from channel</span></span>](/graph/api/conversationmember-delete)