---
title: Gestire il ciclo di vita dei canali privati in Microsoft Teams
author: lanachin
ms.author: v-lanac
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
description: Informazioni su come gestire il ciclo di vita dei canali privati nell'organizzazione.
ms.openlocfilehash: dd4509e809348a21231a6aa136c6cb360a152472
ms.sourcegitcommit: 5fbb57c5f0692afcb8e65516c63b96814f51ca65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2020
ms.locfileid: "42417571"
---
# <a name="manage-the-life-cycle-of-private-channels-in-microsoft-teams"></a><span data-ttu-id="8d37b-103">Gestire il ciclo di vita dei canali privati in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8d37b-103">Manage the life cycle of private channels in Microsoft Teams</span></span>

<span data-ttu-id="8d37b-104">In questa sezione sono disponibili le indicazioni necessarie per gestire il ciclo di vita dei [canali privati](private-channels.md) nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8d37b-104">Here you'll find the guidance you need to manage the life cycle of [private channels](private-channels.md) in your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8d37b-105">Se si usano i passaggi di PowerShell in questo articolo per gestire i canali privati, è necessario installare e usare la versione più recente del modulo di PowerShell teams dalla raccolta di test di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8d37b-105">If you're using the PowerShell steps in this article to manage private channels, you must install and use the latest version of the Teams PowerShell module from the PowerShell Test Gallery.</span></span> <span data-ttu-id="8d37b-106">Per istruzioni su come eseguire questa operazione, vedere [installare il modulo di PowerShell più recente di teams dalla raccolta di test di PowerShell](#install-the-latest-teams-powershell-module-from-the-powershell-test-gallery).</span><span class="sxs-lookup"><span data-stu-id="8d37b-106">For steps on how to do this, see [Install the latest Teams PowerShell module from the PowerShell Test Gallery](#install-the-latest-teams-powershell-module-from-the-powershell-test-gallery).</span></span> <span data-ttu-id="8d37b-107">La versione più recente disponibile al pubblico del modulo di PowerShell Teams (attualmente [1.0.3](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.3)) non supporta la gestione dei canali privati.</span><span class="sxs-lookup"><span data-stu-id="8d37b-107">The latest publicly available version of the Teams PowerShell module (currently [1.0.3](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.3)) doesn't support managing private channels.</span></span>

## <a name="set-whether-team-members-can-create-private-channels"></a><span data-ttu-id="8d37b-108">Impostare se i membri del team possono creare canali privati</span><span class="sxs-lookup"><span data-stu-id="8d37b-108">Set whether team members can create private channels</span></span>

<span data-ttu-id="8d37b-109">I proprietari del team possono disattivare o attivare la possibilità per i membri di creare canali privati nelle impostazioni del team.</span><span class="sxs-lookup"><span data-stu-id="8d37b-109">Team owners can turn off or turn on the ability for members to create private channels in team settings.</span></span> <span data-ttu-id="8d37b-110">A questo scopo, nella scheda **Impostazioni** del team disattivare o attivare **Consenti ai membri di creare canali privati**.</span><span class="sxs-lookup"><span data-stu-id="8d37b-110">To do this, on the **Settings** tab for the team, turn off or turn on **Allow members to create private channels**.</span></span>

<span data-ttu-id="8d37b-111">Come amministratore, puoi usare l'API del grafico per controllare se i membri possono creare canali privati in team specifici.</span><span class="sxs-lookup"><span data-stu-id="8d37b-111">As an admin, you can use Graph API to control whether members can create private channels in specific teams.</span></span> <span data-ttu-id="8d37b-112">Ecco un esempio.</span><span class="sxs-lookup"><span data-stu-id="8d37b-112">Here's an example.</span></span>

```Graph API
PATCH /teams/<team_id>
{"memberSettings": 
  {
    "allowCreatePrivateChannels": false
  }
}
```

## <a name="set-whether-users-in-your-organization-can-create-private-channels"></a><span data-ttu-id="8d37b-113">Impostare se gli utenti dell'organizzazione possono creare canali privati</span><span class="sxs-lookup"><span data-stu-id="8d37b-113">Set whether users in your organization can create private channels</span></span>

<span data-ttu-id="8d37b-114">Come amministratore, puoi impostare i criteri usando l'interfaccia di amministrazione di Microsoft teams o PowerShell per controllare gli utenti autorizzati a creare canali privati nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8d37b-114">As an admin, you can set policies by using the Microsoft Teams admin center or PowerShell to control which users in your organization are allowed to create private channels.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="8d37b-115">Uso dell'interfaccia di amministrazione di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8d37b-115">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="8d37b-116">Usare i criteri team per impostare gli utenti autorizzati a creare canali privati nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8d37b-116">Use teams policies to set which users in your organization are allowed to create private channels.</span></span> <span data-ttu-id="8d37b-117">Per altre informazioni, vedere [gestire i criteri dei team in teams](teams-policies.md).</span><span class="sxs-lookup"><span data-stu-id="8d37b-117">To learn more, see [Manage teams policies in Teams](teams-policies.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="8d37b-118">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="8d37b-118">Using PowerShell</span></span>

<span data-ttu-id="8d37b-119">USA **CsTeamsChannelsPolicy** per impostare gli utenti dell'organizzazione che possono creare canali privati.</span><span class="sxs-lookup"><span data-stu-id="8d37b-119">Use **CsTeamsChannelsPolicy** to set which users in your organization are allowed to create private channels.</span></span> <span data-ttu-id="8d37b-120">Imposta il parametro **AllowPrivateChannelCreation** su **true** per consentire agli utenti a cui viene assegnato il criterio di creare canali privati.</span><span class="sxs-lookup"><span data-stu-id="8d37b-120">Set the **AllowPrivateChannelCreation** parameter to **true** to allow users who are assigned the policy to create private channels.</span></span> <span data-ttu-id="8d37b-121">Impostando il parametro su **false** si disattiva la possibilità di creare canali privati per gli utenti a cui è stato assegnato il criterio.</span><span class="sxs-lookup"><span data-stu-id="8d37b-121">Setting the parameter to **false** turns off the ability to create private channels for users who are assigned the policy.</span></span>

<span data-ttu-id="8d37b-122">Per altre informazioni, vedere [New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="8d37b-122">To learn more, see [New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps).</span></span>

## <a name="create-a-private-channel-on-behalf-of-a-team-owner"></a><span data-ttu-id="8d37b-123">Creare un canale privato per conto di un proprietario del team</span><span class="sxs-lookup"><span data-stu-id="8d37b-123">Create a private channel on behalf of a team owner</span></span>

<span data-ttu-id="8d37b-124">Come amministratore, puoi usare PowerShell o Graph API per creare un canale privato per conto di un proprietario del team.</span><span class="sxs-lookup"><span data-stu-id="8d37b-124">As an admin, you can use PowerShell or Graph API to create a private channel on behalf of a team owner.</span></span> <span data-ttu-id="8d37b-125">Ad esempio, potresti voler eseguire questa operazione se l'organizzazione vuole centralizzare la creazione di canali privati.</span><span class="sxs-lookup"><span data-stu-id="8d37b-125">For example, you may want to do this if your organization wants to centralize creation of private channels.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="8d37b-126">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="8d37b-126">Using PowerShell</span></span>

```PowerShell
New-TeamChannel –GroupId <Group_Id> –MembershipType Private –DisplayName “<Channel_Name>” –Owner <Owner_UPN>
```

### <a name="using-graph-api"></a><span data-ttu-id="8d37b-127">Uso dell'API del grafico</span><span class="sxs-lookup"><span data-stu-id="8d37b-127">Using Graph API</span></span>

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

## <a name="get-a-list-of-all-private-channel-messages"></a><span data-ttu-id="8d37b-128">Ottenere un elenco di tutti i messaggi di canale privato</span><span class="sxs-lookup"><span data-stu-id="8d37b-128">Get a list of all private channel messages</span></span>

<span data-ttu-id="8d37b-129">Potrebbe essere utile ottenere un elenco di tutti i messaggi e le risposte pubblicate in un canale privato per scopi di archiviazione e controllo.</span><span class="sxs-lookup"><span data-stu-id="8d37b-129">You may want to get a list of all messages and replies posted in a private channel for archiving and auditing purposes.</span></span>  <span data-ttu-id="8d37b-130">Ecco come usare l'API del grafico per eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="8d37b-130">Here's how to use Graph API to do this.</span></span>

```Graph API
GET /teams/{id}/channels/{id}/messages
GET /teams/{id}/channels/{id}/messages/{id}/replies/{id}
```

## <a name="find-sharepoint-urls-for-all-private-channels-in-a-team"></a><span data-ttu-id="8d37b-131">Trovare gli URL di SharePoint per tutti i canali privati in un team</span><span class="sxs-lookup"><span data-stu-id="8d37b-131">Find SharePoint URLs for all private channels in a team</span></span>

<span data-ttu-id="8d37b-132">Indipendentemente dal fatto che si voglia eseguire una eDiscovery o un blocco legale su file in un canale privato o che si cerchi di creare un'app line-of-business che inserisce i file in canali privati specifici, è possibile eseguire query sulle raccolte siti di SharePoint esclusive create per ogni canale privato.</span><span class="sxs-lookup"><span data-stu-id="8d37b-132">Whether you're looking to perform eDiscovery or legal hold on files in a private channel or looking to build a line-of-business app that places files in specific private channels, you'll want a way to query the unique SharePoint site collections that are created for each private channel.</span></span>

<span data-ttu-id="8d37b-133">Come amministratore, puoi usare i comandi delle API di PowerShell o Graph per eseguire query su questi URL.</span><span class="sxs-lookup"><span data-stu-id="8d37b-133">As an admin, you can use PowerShell or Graph APIs commands to query these URLs.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="8d37b-134">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="8d37b-134">Using PowerShell</span></span>

1. <span data-ttu-id="8d37b-135">Installare e connettersi a [SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) con l'account di amministratore.</span><span class="sxs-lookup"><span data-stu-id="8d37b-135">Install and connect to the [SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) with your admin account.</span></span>
2. <span data-ttu-id="8d37b-136">Eseguire le operazioni seguenti, &lt;dove&gt; group_id è l'ID del gruppo del team.</span><span class="sxs-lookup"><span data-stu-id="8d37b-136">Run the following, where &lt;group_id&gt; is the group ID of the team.</span></span> <span data-ttu-id="8d37b-137">È possibile trovare facilmente l'ID del gruppo nel collegamento al team.</span><span class="sxs-lookup"><span data-stu-id="8d37b-137">(You can easily find the group ID in the link to the team.)</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = “<group_id>"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity
    $site.url -Detail; if ($x.RelatedGroupId -eq $groupID)
    {$x.RelatedGroupId;$x.url}}
    ```

### <a name="using-graph-api"></a><span data-ttu-id="8d37b-138">Uso dell'API del grafico</span><span class="sxs-lookup"><span data-stu-id="8d37b-138">Using Graph API</span></span>

<span data-ttu-id="8d37b-139">Puoi provare questi comandi tramite [Esplora grafico](https://developer.microsoft.com/graph/graph-explorer).</span><span class="sxs-lookup"><span data-stu-id="8d37b-139">You can try these commands through [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

1. <span data-ttu-id="8d37b-140">Usa la seguente procedura per ottenere l'elenco di ID canale privati per un team specifico, dove <group_id> è l'ID del gruppo del team.</span><span class="sxs-lookup"><span data-stu-id="8d37b-140">Use the following to get the list of private channel IDs for a given team, where <group_id> is the group ID of the team.</span></span> <span data-ttu-id="8d37b-141">Sarà necessario nelle chiamate successive.</span><span class="sxs-lookup"><span data-stu-id="8d37b-141">You'll need this in subsequent calls.</span></span> <span data-ttu-id="8d37b-142">È possibile trovare facilmente l'ID del gruppo nel collegamento al team.</span><span class="sxs-lookup"><span data-stu-id="8d37b-142">(You can easily find the group ID in the link to the team).</span></span>

    <span data-ttu-id="8d37b-143">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="8d37b-143">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels?$filter=membershipType eq 'private'
    ```

    <span data-ttu-id="8d37b-144">**Risposta**</span><span class="sxs-lookup"><span data-stu-id="8d37b-144">**Response**</span></span>

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

2. <span data-ttu-id="8d37b-145">Per ogni canale privato per cui si vuole ottenere l'URL di SharePoint, eseguire la richiesta seguente, &lt;dove&gt; Channel_id è l'ID del canale.</span><span class="sxs-lookup"><span data-stu-id="8d37b-145">For each private channel which you want to get the SharePoint URL, make the following request, where &lt;channel_id&gt; is the channel ID.</span></span>

    <span data-ttu-id="8d37b-146">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="8d37b-146">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/filesFolder
    ```

    <span data-ttu-id="8d37b-147">**Risposta**</span><span class="sxs-lookup"><span data-stu-id="8d37b-147">**Response**</span></span>

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

## <a name="list-and-update-roles-of-owners-and-members-in-a-private-channel"></a><span data-ttu-id="8d37b-148">Elenco e aggiornamento dei ruoli di proprietari e membri in un canale privato</span><span class="sxs-lookup"><span data-stu-id="8d37b-148">List and update roles of owners and members in a private channel</span></span>

<span data-ttu-id="8d37b-149">È consigliabile elencare i proprietari e i membri di un canale privato per decidere se è necessario promuovere alcuni membri del canale privato con un proprietario.</span><span class="sxs-lookup"><span data-stu-id="8d37b-149">You may want to list out the owners and members of a private channel to decide whether you need to promote certain members of the private channel to an owner.</span></span> <span data-ttu-id="8d37b-150">Questo problema può verificarsi quando si hanno proprietari di canali privati che hanno lasciato l'organizzazione e il canale privato richiede all'amministratore la guida per rivendicare la proprietà del canale.</span><span class="sxs-lookup"><span data-stu-id="8d37b-150">This can happen when you have owners of private channels who have left the organization and the private channel requires admin help to claim ownership of the channel.</span></span>

<span data-ttu-id="8d37b-151">Come amministratore, puoi usare i comandi delle API di PowerShell o Graph per eseguire query su questi URL.</span><span class="sxs-lookup"><span data-stu-id="8d37b-151">As an admin, you can use PowerShell or Graph APIs commands to query these URLs.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="8d37b-152">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="8d37b-152">Using PowerShell</span></span>

1. <span data-ttu-id="8d37b-153">Eseguire le operazioni seguenti, &lt;dove&gt; group_id è l'ID del gruppo del team &lt;e&gt; channel_name è il nome del canale.</span><span class="sxs-lookup"><span data-stu-id="8d37b-153">Run the following, where &lt;group_id&gt; is the group ID of the team and &lt;channel_name&gt; is the channel name.</span></span>

    ```PowerShell
    Get-TeamChannelUser -GroupId <group_id> -DisplayName "<channel_name>" 
    ```

2. <span data-ttu-id="8d37b-154">Innalzare di livello un membro a un proprietario.</span><span class="sxs-lookup"><span data-stu-id="8d37b-154">Promote a member to an owner.</span></span>

    ```PowerShell
    Add-TeamChannelUser -GroupId <group_id> -DisplayName "<channel_name>" -User <UPN> -Role Owner
    ```

### <a name="using-graph-api"></a><span data-ttu-id="8d37b-155">Uso dell'API del grafico</span><span class="sxs-lookup"><span data-stu-id="8d37b-155">Using Graph API</span></span>

<span data-ttu-id="8d37b-156">Puoi provare questi comandi tramite [Esplora grafico](https://developer.microsoft.com/graph/graph-explorer).</span><span class="sxs-lookup"><span data-stu-id="8d37b-156">You can try these commands through [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

1. <span data-ttu-id="8d37b-157">Usare le opzioni seguenti, &lt;dove&gt; group_id è l'ID del gruppo del team &lt;e&gt; Channel_id è l'ID del canale.</span><span class="sxs-lookup"><span data-stu-id="8d37b-157">Use the following, where &lt;group_id&gt; is the group ID of the team and &lt;channel_id&gt; is the channel ID.</span></span>

    <span data-ttu-id="8d37b-158">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="8d37b-158">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members
    ```
    
    <span data-ttu-id="8d37b-159">**Risposta**</span><span class="sxs-lookup"><span data-stu-id="8d37b-159">**Response**</span></span>

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
2.  <span data-ttu-id="8d37b-160">Usa la seguente procedura per innalzare di livello il membro a &lt;un&gt;proprietario &lt;,&gt;dove group_id &lt;,&gt; channel_id e ID vengono restituiti dalla chiamata precedente.</span><span class="sxs-lookup"><span data-stu-id="8d37b-160">Use the following to promote the member to an owner, where &lt;group_id&gt;, &lt;channel_id&gt;, and &lt;id&gt; are returned from the previous call.</span></span> <span data-ttu-id="8d37b-161">Tieni presente &lt;che&gt; ID &lt;e&gt; UserID restituiti dalla chiamata precedente non sono uguali e non sono intercambiabili.</span><span class="sxs-lookup"><span data-stu-id="8d37b-161">Note that &lt;id&gt; and &lt;userId&gt; returned from the previous call aren't the same and aren't interchangeable.</span></span> <span data-ttu-id="8d37b-162">Assicurarsi di usare &lt;ID&gt;.</span><span class="sxs-lookup"><span data-stu-id="8d37b-162">Make sure you use &lt;id&gt;.</span></span>

    <span data-ttu-id="8d37b-163">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="8d37b-163">**Request**</span></span>

    ```Graph API
    PATCH 
    https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members/<id>
      
    {
    "@odata.type": "#microsoft.graph.aadUserConversationMember",
    "roles": ["owner"]
    }
    ```

    <span data-ttu-id="8d37b-164">**Risposta**</span><span class="sxs-lookup"><span data-stu-id="8d37b-164">**Response**</span></span>

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

## <a name="teams-powershell-module"></a><span data-ttu-id="8d37b-165">Modulo di PowerShell Teams</span><span class="sxs-lookup"><span data-stu-id="8d37b-165">Teams Powershell module</span></span>

### <a name="install-the-latest-teams-powershell-module-from-the-powershell-test-gallery"></a><span data-ttu-id="8d37b-166">Installare il modulo di PowerShell più recente della raccolta di test di PowerShell</span><span class="sxs-lookup"><span data-stu-id="8d37b-166">Install the latest Teams PowerShell module from the PowerShell Test Gallery</span></span>

<span data-ttu-id="8d37b-167">La versione più recente disponibile al pubblico del modulo di PowerShell Teams (attualmente [1.0.3](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.3)) non supporta la gestione dei canali privati.</span><span class="sxs-lookup"><span data-stu-id="8d37b-167">The latest publicly available version of the Teams PowerShell module (currently [1.0.3](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.3)) doesn't support managing private channels.</span></span> <span data-ttu-id="8d37b-168">Seguire questa procedura per installare la versione più recente del modulo di PowerShell teams con il supporto per i canali privati (attualmente 1.0.18) dalla raccolta di test di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8d37b-168">Use these steps to install the latest version of the Teams PowerShell module with private channel support (currently 1.0.18) from the PowerShell Test Gallery.</span></span>

> [!NOTE]
> <span data-ttu-id="8d37b-169">Non installare il modulo teams PowerShell dalla raccolta di test di PowerShell affiancata con una versione del modulo dalla raccolta di PowerShell pubblica.</span><span class="sxs-lookup"><span data-stu-id="8d37b-169">Don't install the Teams PowerShell module from the PowerShell Test Gallery side-by-side with a version of the module from the public PowerShell Gallery.</span></span> <span data-ttu-id="8d37b-170">Seguire questa procedura per disinstallare prima il modulo di PowerShell teams dalla raccolta di PowerShell pubblica e quindi installare la versione più recente del modulo dalla raccolta di test di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8d37b-170">Follow these steps to first uninstall the Teams PowerShell module from the public PowerShell Gallery, and then install the latest version of the module from the PowerShell Test Gallery.</span></span>

1. <span data-ttu-id="8d37b-171">Chiudere tutte le sessioni di PowerShell esistenti.</span><span class="sxs-lookup"><span data-stu-id="8d37b-171">Close all existing PowerShell sessions.</span></span>
2. <span data-ttu-id="8d37b-172">Avviare una nuova istanza del modulo di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8d37b-172">Start a new instance of the Windows PowerShell module.</span></span>
3. <span data-ttu-id="8d37b-173">Eseguire la procedura seguente per disinstallare il modulo di PowerShell teams dalla raccolta di PowerShell pubblica:</span><span class="sxs-lookup"><span data-stu-id="8d37b-173">Run the following to uninstall the Teams PowerShell module from the public PowerShell Gallery:</span></span>

    ```PowerShell
    Uninstall-Module -Name MicrosoftTeams
    ```

4. <span data-ttu-id="8d37b-174">Chiudere tutte le sessioni di PowerShell esistenti.</span><span class="sxs-lookup"><span data-stu-id="8d37b-174">Close all existing PowerShell sessions.</span></span>
5. <span data-ttu-id="8d37b-175">Avviare di nuovo il modulo di Windows PowerShell e quindi eseguire la procedura seguente per registrare la raccolta di test di PowerShell come origine attendibile:</span><span class="sxs-lookup"><span data-stu-id="8d37b-175">Start the Windows PowerShell module again, and then run the following to register the PowerShell Test Gallery as a trusted source:</span></span>

    ```PowerShell
    Register-PSRepository -Name PSGalleryInt -SourceLocation https://www.poshtestgallery.com/ -InstallationPolicy Trusted
    ```

6. <span data-ttu-id="8d37b-176">Eseguire la procedura seguente per installare il modulo di PowerShell più recente di teams dalla raccolta di test di PowerShell:</span><span class="sxs-lookup"><span data-stu-id="8d37b-176">Run the following to install the latest Teams PowerShell module from the PowerShell Test Gallery:</span></span>

    ```PowerShell
    Install-Module -Name MicrosoftTeams -Repository PSGalleryInt -Force
    ```

7. <span data-ttu-id="8d37b-177">Eseguire le operazioni seguenti per verificare che la versione più recente del modulo di PowerShell teams della raccolta di test di PowerShell sia installata correttamente:</span><span class="sxs-lookup"><span data-stu-id="8d37b-177">Run the following to verify that the latest version of the Teams PowerShell module from the PowerShell Test Gallery is successfully installed:</span></span>

    ```PowerShell
    Get-Module -Name MicrosoftTeams
    ```

#### <a name="update-to-the-latest-version-of-the-teams-powershell-module-from-the-powershell-test-gallery"></a><span data-ttu-id="8d37b-178">Aggiornamento alla versione più recente del modulo di PowerShell teams dalla raccolta di test di PowerShell</span><span class="sxs-lookup"><span data-stu-id="8d37b-178">Update to the latest version of the Teams PowerShell module from the PowerShell Test Gallery</span></span>

<span data-ttu-id="8d37b-179">Se il modulo teams PowerShell è già stato installato dalla raccolta test di PowerShell, eseguire la procedura seguente per aggiornare la versione più recente.</span><span class="sxs-lookup"><span data-stu-id="8d37b-179">If you already installed the Teams PowerShell module from the PowerShell Test Gallery, use the following steps to update to the latest version.</span></span>

1. <span data-ttu-id="8d37b-180">Chiudere tutte le sessioni di PowerShell esistenti.</span><span class="sxs-lookup"><span data-stu-id="8d37b-180">Close all existing PowerShell sessions.</span></span>
2. <span data-ttu-id="8d37b-181">Avviare una nuova istanza del modulo di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8d37b-181">Start a new instance of the Windows PowerShell module.</span></span>
3. <span data-ttu-id="8d37b-182">Eseguire la procedura seguente per aggiornare la versione attualmente installata del modulo di PowerShell teams dalla raccolta di test di PowerShell:</span><span class="sxs-lookup"><span data-stu-id="8d37b-182">Run the following to update the currently installed version of the Teams PowerShell module from the PowerShell Test Gallery:</span></span>

    ```PowerShell
    Update-Module -Name MicrosoftTeams -Force
    ```

4. <span data-ttu-id="8d37b-183">Eseguire le operazioni seguenti per verificare che la versione più recente del modulo di PowerShell teams della raccolta di test di PowerShell sia installata correttamente:</span><span class="sxs-lookup"><span data-stu-id="8d37b-183">Run the following to verify that the latest version of the Teams PowerShell module from the PowerShell Test Gallery is successfully installed:</span></span>

    ```PowerShell
    Get-Module -Name MicrosoftTeams
    ```

## <a name="related-topics"></a><span data-ttu-id="8d37b-184">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="8d37b-184">Related topics</span></span>

- [<span data-ttu-id="8d37b-185">Panoramica di PowerShell Teams</span><span class="sxs-lookup"><span data-stu-id="8d37b-185">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="8d37b-186">Usare l'API Microsoft Graph per lavorare con i team</span><span class="sxs-lookup"><span data-stu-id="8d37b-186">Use the Microsoft Graph API to work with Teams</span></span>](https://docs.microsoft.com/graph/api/resources/teams-api-overview?view=graph-rest-1.0)
    - [<span data-ttu-id="8d37b-187">Canali elenco</span><span class="sxs-lookup"><span data-stu-id="8d37b-187">List channels</span></span>](https://docs.microsoft.com/graph/api/channel-list)
    - [<span data-ttu-id="8d37b-188">Creare un canale</span><span class="sxs-lookup"><span data-stu-id="8d37b-188">Create channel</span></span>](https://docs.microsoft.com/graph/api/channel-post)
    - [<span data-ttu-id="8d37b-189">Aggiungere un membro al canale</span><span class="sxs-lookup"><span data-stu-id="8d37b-189">Add member to channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-add)
    - [<span data-ttu-id="8d37b-190">Aggiornare il membro nel canale</span><span class="sxs-lookup"><span data-stu-id="8d37b-190">Update member in channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-update)
    - [<span data-ttu-id="8d37b-191">Rimuovi membro dal canale</span><span class="sxs-lookup"><span data-stu-id="8d37b-191">Remove member from channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-delete)
