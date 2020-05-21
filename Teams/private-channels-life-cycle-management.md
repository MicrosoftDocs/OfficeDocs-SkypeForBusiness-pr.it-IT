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
ms.openlocfilehash: 45d9591eed2bd3a880d3ca3e2ceb2252bf6f8898
ms.sourcegitcommit: b381d8f0b9fc45133d52175fa85901b66e744abd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "44326693"
---
# <a name="manage-the-life-cycle-of-private-channels-in-microsoft-teams"></a><span data-ttu-id="b71b5-103">Gestire il ciclo di vita dei canali privati in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b71b5-103">Manage the life cycle of private channels in Microsoft Teams</span></span>

<span data-ttu-id="b71b5-104">In questa sezione sono disponibili le indicazioni necessarie per gestire il ciclo di vita dei [canali privati](private-channels.md) nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b71b5-104">Here you'll find the guidance you need to manage the life cycle of [private channels](private-channels.md) in your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b71b5-105">Se si usano i passaggi di PowerShell in questo articolo per gestire i canali privati, è necessario installare e usare la versione più recente del modulo di PowerShell per i team nella [raccolta di test di PowerShell](https://www.poshtestgallery.com/packages/MicrosoftTeams/).</span><span class="sxs-lookup"><span data-stu-id="b71b5-105">If you're using the PowerShell steps in this article to manage private channels, you must install and use the latest pre-release version of the Teams PowerShell module from the [PowerShell Test Gallery](https://www.poshtestgallery.com/packages/MicrosoftTeams/).</span></span> <span data-ttu-id="b71b5-106">Per istruzioni su come installare il modulo, vedere [installare la versione preliminare del modulo di PowerShell teams](install-prerelease-teams-powershell-module.md).</span><span class="sxs-lookup"><span data-stu-id="b71b5-106">For steps on how to install the module, see [Install the pre-release version of the Teams PowerShell module](install-prerelease-teams-powershell-module.md).</span></span> <span data-ttu-id="b71b5-107">La versione più recente disponibile al pubblico del modulo di PowerShell teams non supporta la gestione dei canali privati.</span><span class="sxs-lookup"><span data-stu-id="b71b5-107">The latest publicly available version of the Teams PowerShell module doesn't support managing private channels.</span></span>

## <a name="set-whether-team-members-can-create-private-channels"></a><span data-ttu-id="b71b5-108">Impostare se i membri del team possono creare canali privati</span><span class="sxs-lookup"><span data-stu-id="b71b5-108">Set whether team members can create private channels</span></span>

<span data-ttu-id="b71b5-109">I proprietari del team possono disattivare o attivare la possibilità per i membri di creare canali privati nelle impostazioni del team.</span><span class="sxs-lookup"><span data-stu-id="b71b5-109">Team owners can turn off or turn on the ability for members to create private channels in team settings.</span></span> <span data-ttu-id="b71b5-110">A questo scopo, nella scheda **Impostazioni** del team disattivare o attivare **Consenti ai membri di creare canali privati**.</span><span class="sxs-lookup"><span data-stu-id="b71b5-110">To do this, on the **Settings** tab for the team, turn off or turn on **Allow members to create private channels**.</span></span>

<span data-ttu-id="b71b5-111">Come amministratore, puoi usare l'API del grafico per controllare se i membri possono creare canali privati in team specifici.</span><span class="sxs-lookup"><span data-stu-id="b71b5-111">As an admin, you can use Graph API to control whether members can create private channels in specific teams.</span></span> <span data-ttu-id="b71b5-112">Ecco un esempio.</span><span class="sxs-lookup"><span data-stu-id="b71b5-112">Here's an example.</span></span>

```Graph API
PATCH /teams/<team_id>
{"memberSettings": 
  {
    "allowCreatePrivateChannels": false
  }
}
```

## <a name="set-whether-users-in-your-organization-can-create-private-channels"></a><span data-ttu-id="b71b5-113">Impostare se gli utenti dell'organizzazione possono creare canali privati</span><span class="sxs-lookup"><span data-stu-id="b71b5-113">Set whether users in your organization can create private channels</span></span>

<span data-ttu-id="b71b5-114">Come amministratore, puoi impostare i criteri usando l'interfaccia di amministrazione di Microsoft teams o PowerShell per controllare gli utenti autorizzati a creare canali privati nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b71b5-114">As an admin, you can set policies by using the Microsoft Teams admin center or PowerShell to control which users in your organization are allowed to create private channels.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="b71b5-115">Usando l'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b71b5-115">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="b71b5-116">Usare i criteri team per impostare gli utenti autorizzati a creare canali privati nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b71b5-116">Use teams policies to set which users in your organization are allowed to create private channels.</span></span> <span data-ttu-id="b71b5-117">Per altre informazioni, vedere [gestire i criteri dei team in teams](teams-policies.md).</span><span class="sxs-lookup"><span data-stu-id="b71b5-117">To learn more, see [Manage teams policies in Teams](teams-policies.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="b71b5-118">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="b71b5-118">Using PowerShell</span></span>

<span data-ttu-id="b71b5-119">USA **CsTeamsChannelsPolicy** per impostare gli utenti dell'organizzazione che possono creare canali privati.</span><span class="sxs-lookup"><span data-stu-id="b71b5-119">Use **CsTeamsChannelsPolicy** to set which users in your organization are allowed to create private channels.</span></span> <span data-ttu-id="b71b5-120">Imposta il parametro **AllowPrivateChannelCreation** su **true** per consentire agli utenti a cui viene assegnato il criterio di creare canali privati.</span><span class="sxs-lookup"><span data-stu-id="b71b5-120">Set the **AllowPrivateChannelCreation** parameter to **true** to allow users who are assigned the policy to create private channels.</span></span> <span data-ttu-id="b71b5-121">Impostando il parametro su **false** si disattiva la possibilità di creare canali privati per gli utenti a cui è stato assegnato il criterio.</span><span class="sxs-lookup"><span data-stu-id="b71b5-121">Setting the parameter to **false** turns off the ability to create private channels for users who are assigned the policy.</span></span>

<span data-ttu-id="b71b5-122">Per altre informazioni, vedere [New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="b71b5-122">To learn more, see [New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps).</span></span>

## <a name="create-a-private-channel-on-behalf-of-a-team-owner"></a><span data-ttu-id="b71b5-123">Creare un canale privato per conto di un proprietario del team</span><span class="sxs-lookup"><span data-stu-id="b71b5-123">Create a private channel on behalf of a team owner</span></span>

<span data-ttu-id="b71b5-124">Come amministratore, puoi usare PowerShell o Graph API per creare un canale privato per conto di un proprietario del team.</span><span class="sxs-lookup"><span data-stu-id="b71b5-124">As an admin, you can use PowerShell or Graph API to create a private channel on behalf of a team owner.</span></span> <span data-ttu-id="b71b5-125">Ad esempio, potresti voler eseguire questa operazione se l'organizzazione vuole centralizzare la creazione di canali privati.</span><span class="sxs-lookup"><span data-stu-id="b71b5-125">For example, you may want to do this if your organization wants to centralize creation of private channels.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="b71b5-126">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="b71b5-126">Using PowerShell</span></span>

```PowerShell
New-TeamChannel –GroupId <Group_Id> –MembershipType Private –DisplayName "<Channel_Name>" –Owner <Owner_UPN>
```

### <a name="using-graph-api"></a><span data-ttu-id="b71b5-127">Uso dell'API del grafico</span><span class="sxs-lookup"><span data-stu-id="b71b5-127">Using Graph API</span></span>

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

## <a name="get-a-list-of-all-private-channel-messages"></a><span data-ttu-id="b71b5-128">Ottenere un elenco di tutti i messaggi di canale privato</span><span class="sxs-lookup"><span data-stu-id="b71b5-128">Get a list of all private channel messages</span></span>

<span data-ttu-id="b71b5-129">Potrebbe essere utile ottenere un elenco di tutti i messaggi e le risposte pubblicate in un canale privato per scopi di archiviazione e controllo.</span><span class="sxs-lookup"><span data-stu-id="b71b5-129">You may want to get a list of all messages and replies posted in a private channel for archiving and auditing purposes.</span></span>  <span data-ttu-id="b71b5-130">Ecco come usare l'API del grafico per eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="b71b5-130">Here's how to use Graph API to do this.</span></span>

```Graph API
GET /teams/{id}/channels/{id}/messages
GET /teams/{id}/channels/{id}/messages/{id}/replies/{id}
```

## <a name="find-sharepoint-urls-for-all-private-channels-in-a-team"></a><span data-ttu-id="b71b5-131">Trovare gli URL di SharePoint per tutti i canali privati in un team</span><span class="sxs-lookup"><span data-stu-id="b71b5-131">Find SharePoint URLs for all private channels in a team</span></span>

<span data-ttu-id="b71b5-132">Indipendentemente dal fatto che si voglia eseguire una eDiscovery o un blocco legale su file in un canale privato o che si cerchi di creare un'app personalizzata che inserisce i file in canali privati specifici, è possibile eseguire query sulle raccolte siti di SharePoint create per ogni canale privato.</span><span class="sxs-lookup"><span data-stu-id="b71b5-132">Whether you're looking to perform eDiscovery or legal hold on files in a private channel or looking to build a custom app that places files in specific private channels, you'll want a way to query the unique SharePoint site collections that are created for each private channel.</span></span>

<span data-ttu-id="b71b5-133">Come amministratore, puoi usare i comandi delle API di PowerShell o Graph per eseguire query su questi URL.</span><span class="sxs-lookup"><span data-stu-id="b71b5-133">As an admin, you can use PowerShell or Graph APIs commands to query these URLs.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="b71b5-134">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="b71b5-134">Using PowerShell</span></span>

1. <span data-ttu-id="b71b5-135">Installare e connettersi a [SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) con l'account di amministratore.</span><span class="sxs-lookup"><span data-stu-id="b71b5-135">Install and connect to the [SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) with your admin account.</span></span>
2. <span data-ttu-id="b71b5-136">Eseguire le operazioni seguenti, dove &lt; group_id &gt; è l'ID del gruppo del team.</span><span class="sxs-lookup"><span data-stu-id="b71b5-136">Run the following, where &lt;group_id&gt; is the Group ID of the team.</span></span> <span data-ttu-id="b71b5-137">È possibile trovare facilmente l'ID del gruppo nel collegamento al team.</span><span class="sxs-lookup"><span data-stu-id="b71b5-137">(You can easily find the Group ID in the link to the team.)</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "<group_id>"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity
    $site.url -Detail; if ($x.RelatedGroupId -eq $groupID)
    {$x.RelatedGroupId;$x.url}}
    ```

### <a name="using-graph-api"></a><span data-ttu-id="b71b5-138">Uso dell'API del grafico</span><span class="sxs-lookup"><span data-stu-id="b71b5-138">Using Graph API</span></span>

<span data-ttu-id="b71b5-139">Puoi provare questi comandi tramite [Esplora grafico](https://developer.microsoft.com/graph/graph-explorer).</span><span class="sxs-lookup"><span data-stu-id="b71b5-139">You can try these commands through [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

1. <span data-ttu-id="b71b5-140">Usa la seguente procedura per ottenere l'elenco di ID canale privati per un team specifico, dove <group_id> è l'ID del gruppo del team.</span><span class="sxs-lookup"><span data-stu-id="b71b5-140">Use the following to get the list of private channel IDs for a given team, where <group_id> is the group ID of the team.</span></span> <span data-ttu-id="b71b5-141">Sarà necessario nelle chiamate successive.</span><span class="sxs-lookup"><span data-stu-id="b71b5-141">You'll need this in subsequent calls.</span></span> <span data-ttu-id="b71b5-142">È possibile trovare facilmente l'ID del gruppo nel collegamento al team.</span><span class="sxs-lookup"><span data-stu-id="b71b5-142">(You can easily find the group ID in the link to the team).</span></span>

    <span data-ttu-id="b71b5-143">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="b71b5-143">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels?$filter=membershipType eq 'private'
    ```

    <span data-ttu-id="b71b5-144">**Risposta**</span><span class="sxs-lookup"><span data-stu-id="b71b5-144">**Response**</span></span>

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

2. <span data-ttu-id="b71b5-145">Per ogni canale privato per cui si vuole ottenere l'URL di SharePoint, eseguire la richiesta seguente, dove &lt; channel_id &gt; è l'ID del canale.</span><span class="sxs-lookup"><span data-stu-id="b71b5-145">For each private channel which you want to get the SharePoint URL, make the following request, where &lt;channel_id&gt; is the channel ID.</span></span>

    <span data-ttu-id="b71b5-146">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="b71b5-146">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/filesFolder
    ```

    <span data-ttu-id="b71b5-147">**Risposta**</span><span class="sxs-lookup"><span data-stu-id="b71b5-147">**Response**</span></span>

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

## <a name="list-and-update-roles-of-owners-and-members-in-a-private-channel"></a><span data-ttu-id="b71b5-148">Elenco e aggiornamento dei ruoli di proprietari e membri in un canale privato</span><span class="sxs-lookup"><span data-stu-id="b71b5-148">List and update roles of owners and members in a private channel</span></span>

<span data-ttu-id="b71b5-149">È consigliabile elencare i proprietari e i membri di un canale privato per decidere se è necessario promuovere alcuni membri del canale privato con un proprietario.</span><span class="sxs-lookup"><span data-stu-id="b71b5-149">You may want to list out the owners and members of a private channel to decide whether you need to promote certain members of the private channel to an owner.</span></span> <span data-ttu-id="b71b5-150">Questo problema può verificarsi quando si hanno proprietari di canali privati che hanno lasciato l'organizzazione e il canale privato richiede all'amministratore la guida per rivendicare la proprietà del canale.</span><span class="sxs-lookup"><span data-stu-id="b71b5-150">This can happen when you have owners of private channels who have left the organization and the private channel requires admin help to claim ownership of the channel.</span></span>

<span data-ttu-id="b71b5-151">Gli amministratori possono usare l'API di Microsoft teams Center, PowerShell o Graph per eseguire queste azioni.</span><span class="sxs-lookup"><span data-stu-id="b71b5-151">As an admin, you can use the Microsoft Teams admin center, PowerShell, or Graph API to perform these actions.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="b71b5-152">Usando l'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b71b5-152">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="b71b5-153">Per informazioni su come gestire i membri del team con l'interfaccia di amministrazione di Microsoft teams, vedere [gestire team nell'interfaccia di amministrazione di Microsoft teams](manage-teams-in-modern-portal.md).</span><span class="sxs-lookup"><span data-stu-id="b71b5-153">To learn how to manage team members using the Microsoft Teams admin center, see [Manage teams in the Microsoft Teams admin center](manage-teams-in-modern-portal.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="b71b5-154">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="b71b5-154">Using PowerShell</span></span>

1. <span data-ttu-id="b71b5-155">Eseguire le operazioni seguenti, dove &lt; group_id &gt; è l'ID del gruppo del team e &lt; channel_name &gt; è il nome del canale.</span><span class="sxs-lookup"><span data-stu-id="b71b5-155">Run the following, where &lt;group_id&gt; is the group ID of the team and &lt;channel_name&gt; is the channel name.</span></span>

    ```PowerShell
    Get-TeamChannelUser -GroupId <group_id> -DisplayName "<channel_name>" 
    ```

2. <span data-ttu-id="b71b5-156">Innalzare di livello un membro a un proprietario.</span><span class="sxs-lookup"><span data-stu-id="b71b5-156">Promote a member to an owner.</span></span>

    ```PowerShell
    Add-TeamChannelUser -GroupId <group_id> -DisplayName "<channel_name>" -User <UPN> -Role Owner
    ```

### <a name="using-graph-api"></a><span data-ttu-id="b71b5-157">Uso dell'API del grafico</span><span class="sxs-lookup"><span data-stu-id="b71b5-157">Using Graph API</span></span>

<span data-ttu-id="b71b5-158">Puoi provare questi comandi tramite [Esplora grafico](https://developer.microsoft.com/graph/graph-explorer).</span><span class="sxs-lookup"><span data-stu-id="b71b5-158">You can try these commands through [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

1. <span data-ttu-id="b71b5-159">Usare le opzioni seguenti, dove &lt; group_id &gt; è l'ID del gruppo del team e &lt; CHANNEL_ID &gt; è l'ID del canale.</span><span class="sxs-lookup"><span data-stu-id="b71b5-159">Use the following, where &lt;group_id&gt; is the group ID of the team and &lt;channel_id&gt; is the channel ID.</span></span>

    <span data-ttu-id="b71b5-160">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="b71b5-160">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members
    ```
    
    <span data-ttu-id="b71b5-161">**Risposta**</span><span class="sxs-lookup"><span data-stu-id="b71b5-161">**Response**</span></span>

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
2. <span data-ttu-id="b71b5-162">Usa la seguente procedura per innalzare di livello il membro a un proprietario, dove &lt; group_id &gt; , &lt; channel_id &gt; e &lt; ID &gt; vengono restituiti dalla chiamata precedente.</span><span class="sxs-lookup"><span data-stu-id="b71b5-162">Use the following to promote the member to an owner, where &lt;group_id&gt;, &lt;channel_id&gt;, and &lt;id&gt; are returned from the previous call.</span></span> <span data-ttu-id="b71b5-163">Tieni presente che &lt; ID &gt; e &lt; userid &gt; restituiti dalla chiamata precedente non sono uguali e non sono intercambiabili.</span><span class="sxs-lookup"><span data-stu-id="b71b5-163">Note that &lt;id&gt; and &lt;userId&gt; returned from the previous call aren't the same and aren't interchangeable.</span></span> <span data-ttu-id="b71b5-164">Assicurarsi di usare &lt; ID &gt; .</span><span class="sxs-lookup"><span data-stu-id="b71b5-164">Make sure you use &lt;id&gt;.</span></span>

    <span data-ttu-id="b71b5-165">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="b71b5-165">**Request**</span></span>

    ```Graph API
    PATCH 
    https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members/<id>
      
    {
    "@odata.type": "#microsoft.graph.aadUserConversationMember",
    "roles": ["owner"]
    }
    ```

    <span data-ttu-id="b71b5-166">**Risposta**</span><span class="sxs-lookup"><span data-stu-id="b71b5-166">**Response**</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="b71b5-167">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="b71b5-167">Related topics</span></span>

- [<span data-ttu-id="b71b5-168">Panoramica di PowerShell per Teams</span><span class="sxs-lookup"><span data-stu-id="b71b5-168">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="b71b5-169">Usare l'API Microsoft Graph per lavorare con Teams</span><span class="sxs-lookup"><span data-stu-id="b71b5-169">Use the Microsoft Graph API to work with Teams</span></span>](https://docs.microsoft.com/graph/api/resources/teams-api-overview?view=graph-rest-1.0)
    - [<span data-ttu-id="b71b5-170">Canali elenco</span><span class="sxs-lookup"><span data-stu-id="b71b5-170">List channels</span></span>](https://docs.microsoft.com/graph/api/channel-list)
    - [<span data-ttu-id="b71b5-171">Creare un canale</span><span class="sxs-lookup"><span data-stu-id="b71b5-171">Create channel</span></span>](https://docs.microsoft.com/graph/api/channel-post)
    - [<span data-ttu-id="b71b5-172">Aggiungere un membro al canale</span><span class="sxs-lookup"><span data-stu-id="b71b5-172">Add member to channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-add)
    - [<span data-ttu-id="b71b5-173">Aggiornare il membro nel canale</span><span class="sxs-lookup"><span data-stu-id="b71b5-173">Update member in channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-update)
    - [<span data-ttu-id="b71b5-174">Rimuovi membro dal canale</span><span class="sxs-lookup"><span data-stu-id="b71b5-174">Remove member from channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-delete)
