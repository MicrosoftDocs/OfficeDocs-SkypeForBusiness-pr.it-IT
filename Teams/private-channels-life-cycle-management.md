---
title: Gestire il ciclo di vita dei canali privati in Microsoft Teams
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
description: Informazioni su come gestire il ciclo di vita dei canali privati nell'organizzazione.
ms.openlocfilehash: 336d97071c30bca145d26f4c853d5bb30265721f
ms.sourcegitcommit: 68dffc3aca46992448bc2be0689bfd352e016316
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/08/2020
ms.locfileid: "49601661"
---
# <a name="manage-the-life-cycle-of-private-channels-in-microsoft-teams"></a><span data-ttu-id="89098-103">Gestire il ciclo di vita dei canali privati in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="89098-103">Manage the life cycle of private channels in Microsoft Teams</span></span>

<span data-ttu-id="89098-104">In quest’articolo sarà possibile trovare informazioni su come gestire il ciclo di vita dei [canali privati](private-channels.md) nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="89098-104">Here you'll find the guidance you need to manage the life cycle of [private channels](private-channels.md) in your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="89098-105">Se si stanno seguendo i passaggi di PowerShell qui descritti, per gestire i canali privati, è necessario installare e usare il modulo di anteprima pubblica di PowerShell per Teams dalla [Raccolta PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/).</span><span class="sxs-lookup"><span data-stu-id="89098-105">If you're using the PowerShell steps in this article to manage private channels, you must install and use the Teams PowerShell public preview module from the [PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams/).</span></span> <span data-ttu-id="89098-106">Per la procedura su come installare il modulo, vedere [Installare PowerShell per Microsoft Teams](teams-powershell-install.md).</span><span class="sxs-lookup"><span data-stu-id="89098-106">For steps on how to install the module, see [Install Microsoft Teams PowerShell](teams-powershell-install.md).</span></span> <span data-ttu-id="89098-107">L'ultimo modulo di disponibilità generale di PowerShell per Teams non supporta la gestione dei canali privati.</span><span class="sxs-lookup"><span data-stu-id="89098-107">The latest General Availability Teams PowerShell module doesn't support managing private channels.</span></span>

## <a name="set-whether-team-members-can-create-private-channels"></a><span data-ttu-id="89098-108">Specificare se i membri del team possono creare canali privati</span><span class="sxs-lookup"><span data-stu-id="89098-108">Set whether team members can create private channels</span></span>

<span data-ttu-id="89098-109">I proprietari del team possono disattivare o attivare la possibilità per i membri di creare canali privati nelle impostazioni del team.</span><span class="sxs-lookup"><span data-stu-id="89098-109">Team owners can turn off or turn on the ability for members to create private channels in team settings.</span></span> <span data-ttu-id="89098-110">Per fare ciò, dalla scheda **Impostazioni** per il team, abilitare o disabilitare l’opzione **Consenti ai membri di creare canali privati**.</span><span class="sxs-lookup"><span data-stu-id="89098-110">To do this, on the **Settings** tab for the team, turn off or turn on **Allow members to create private channels**.</span></span>

<span data-ttu-id="89098-111">Gli amministratori possono usare l’API Graph per controllare se i membri possono creare canali privati in specifici team.</span><span class="sxs-lookup"><span data-stu-id="89098-111">As an admin, you can use Graph API to control whether members can create private channels in specific teams.</span></span> <span data-ttu-id="89098-112">Di seguito viene riportato un esempio.</span><span class="sxs-lookup"><span data-stu-id="89098-112">Here's an example.</span></span>

```Graph API
PATCH /teams/<team_id>
{"memberSettings": 
  {
    "allowCreatePrivateChannels": false
  }
}
```

## <a name="set-whether-users-in-your-organization-can-create-private-channels"></a><span data-ttu-id="89098-113">Specificare se gli utenti dell'organizzazione possono creare canali privati</span><span class="sxs-lookup"><span data-stu-id="89098-113">Set whether users in your organization can create private channels</span></span>

<span data-ttu-id="89098-114">L’amministratore può impostare i criteri usando l'interfaccia di amministrazione di Microsoft Teams o PowerShell per controllare quali utenti dell'organizzazione possono creare canali privati.</span><span class="sxs-lookup"><span data-stu-id="89098-114">As an admin, you can set policies by using the Microsoft Teams admin center or PowerShell to control which users in your organization are allowed to create private channels.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="89098-115">Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="89098-115">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="89098-116">È possibile usare i criteri dei team per impostare quali utenti dell'organizzazione possono creare canali privati.</span><span class="sxs-lookup"><span data-stu-id="89098-116">Use teams policies to set which users in your organization are allowed to create private channels.</span></span> <span data-ttu-id="89098-117">Per altre informazioni, vedere [Gestire i criteri di riunione in Teams](teams-policies.md).</span><span class="sxs-lookup"><span data-stu-id="89098-117">To learn more, see [Manage teams policies in Teams](teams-policies.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="89098-118">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="89098-118">Using PowerShell</span></span>

<span data-ttu-id="89098-119">È possibile usare **CsTeamsChannelsPolicy** per impostare quali utenti dell'organizzazione possono creare canali privati.</span><span class="sxs-lookup"><span data-stu-id="89098-119">Use **CsTeamsChannelsPolicy** to set which users in your organization are allowed to create private channels.</span></span> <span data-ttu-id="89098-120">Impostare il parametro **AllowPrivateChannelCreation** su **true** per consentire agli utenti a cui sono assegnati i criteri di creare canali privati.</span><span class="sxs-lookup"><span data-stu-id="89098-120">Set the **AllowPrivateChannelCreation** parameter to **true** to allow users who are assigned the policy to create private channels.</span></span> <span data-ttu-id="89098-121">L'impostazione del parametro su **false** disabilita la possibilità di creare canali privati da parte degli utenti a cui è assegnato il criterio.</span><span class="sxs-lookup"><span data-stu-id="89098-121">Setting the parameter to **false** turns off the ability to create private channels for users who are assigned the policy.</span></span>

<span data-ttu-id="89098-122">Per altre informazioni, vedere [New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="89098-122">To learn more, see [New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps).</span></span>

## <a name="create-a-private-channel-on-behalf-of-a-team-owner"></a><span data-ttu-id="89098-123">Creare un canale privato per conto del proprietario del team</span><span class="sxs-lookup"><span data-stu-id="89098-123">Create a private channel on behalf of a team owner</span></span>

<span data-ttu-id="89098-124">Gli amministratori possono usare PowerShell o l’API Graph per creare un canale privato per conto del proprietario del team.</span><span class="sxs-lookup"><span data-stu-id="89098-124">As an admin, you can use PowerShell or Graph API to create a private channel on behalf of a team owner.</span></span> <span data-ttu-id="89098-125">Ad esempio, questa operazione potrebbe essere effettuata se l'organizzazione vuole centralizzare la creazione di canali privati.</span><span class="sxs-lookup"><span data-stu-id="89098-125">For example, you may want to do this if your organization wants to centralize creation of private channels.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="89098-126">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="89098-126">Using PowerShell</span></span>

```PowerShell
New-TeamChannel –GroupId <Group_Id> –MembershipType Private –DisplayName "<Channel_Name>" –Owner <Owner_UPN>
```

### <a name="using-graph-api"></a><span data-ttu-id="89098-127">Utilizzo dell’API Graph</span><span class="sxs-lookup"><span data-stu-id="89098-127">Using Graph API</span></span>

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

## <a name="get-a-list-of-all-private-channel-messages"></a><span data-ttu-id="89098-128">Ottenere un elenco di tutti i messaggi del canale privato</span><span class="sxs-lookup"><span data-stu-id="89098-128">Get a list of all private channel messages</span></span>

<span data-ttu-id="89098-129">Potrebbe essere necessario ottenere un elenco di tutti i messaggi e le risposte pubblicate in un canale privato a scopo di archiviazione e controllo.</span><span class="sxs-lookup"><span data-stu-id="89098-129">You may want to get a list of all messages and replies posted in a private channel for archiving and auditing purposes.</span></span>  <span data-ttu-id="89098-130">Di seguito viene illustrato come usare l'API di Graph per eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="89098-130">Here's how to use Graph API to do this.</span></span>

```Graph API
GET /teams/{id}/channels/{id}/messages
GET /teams/{id}/channels/{id}/messages/{id}/replies/{id}
```

## <a name="find-sharepoint-urls-for-all-private-channels-in-a-team"></a><span data-ttu-id="89098-131">Trovare gli URL di SharePoint per tutti i canali privati di un team</span><span class="sxs-lookup"><span data-stu-id="89098-131">Find SharePoint URLs for all private channels in a team</span></span>

<span data-ttu-id="89098-132">Sia che si stia cercando di eseguire l'eDiscovery o la conservazione legale su file in un canale privato, oppure si stia cercando di creare un'app personalizzata che metta i file in canali privati specifici, è necessario un modo per effettuare una query delle raccolte siti univoci di SharePoint create per ciascuno canale privato.</span><span class="sxs-lookup"><span data-stu-id="89098-132">Whether you're looking to perform eDiscovery or legal hold on files in a private channel or looking to build a custom app that places files in specific private channels, you'll want a way to query the unique SharePoint site collections that are created for each private channel.</span></span>

<span data-ttu-id="89098-133">Gli amministratori possono usare i comandi di PowerShell o dell’API Graph per eseguire una query su questi URL.</span><span class="sxs-lookup"><span data-stu-id="89098-133">As an admin, you can use PowerShell or Graph APIs commands to query these URLs.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="89098-134">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="89098-134">Using PowerShell</span></span>

1. <span data-ttu-id="89098-135">Installare e connettersi al [Management Shell di SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) con l'account amministratore.</span><span class="sxs-lookup"><span data-stu-id="89098-135">Install and connect to the [SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) with your admin account.</span></span>
2. <span data-ttu-id="89098-136">Eseguire le operazioni seguenti, in cui&lt;group_id&gt; è l'ID del gruppo del team.</span><span class="sxs-lookup"><span data-stu-id="89098-136">Run the following, where &lt;group_id&gt; is the Group ID of the team.</span></span> <span data-ttu-id="89098-137">È possibile trovare facilmente l'ID del gruppo nel collegamento al team.</span><span class="sxs-lookup"><span data-stu-id="89098-137">(You can easily find the Group ID in the link to the team.)</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "<group_id>"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity
    $site.url -Detail; if ($x.RelatedGroupId -eq $groupID)
    {$x.RelatedGroupId;$x.url}}
    ```

### <a name="using-graph-api"></a><span data-ttu-id="89098-138">Utilizzo dell’API Graph</span><span class="sxs-lookup"><span data-stu-id="89098-138">Using Graph API</span></span>

<span data-ttu-id="89098-139">È possibile provare questi comandi con [Graph explorer](https://developer.microsoft.com/graph/graph-explorer).</span><span class="sxs-lookup"><span data-stu-id="89098-139">You can try these commands through [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

1. <span data-ttu-id="89098-140">Usare la procedura seguente per ottenere l'elenco di ID del canale privato per un determinato team, in cui <group_id> è l'ID del gruppo del team.</span><span class="sxs-lookup"><span data-stu-id="89098-140">Use the following to get the list of private channel IDs for a given team, where <group_id> is the group ID of the team.</span></span> <span data-ttu-id="89098-141">Questo sarà necessario nelle chiamate successive.</span><span class="sxs-lookup"><span data-stu-id="89098-141">You'll need this in subsequent calls.</span></span> <span data-ttu-id="89098-142">È possibile trovare facilmente l'ID del gruppo nel collegamento al team.</span><span class="sxs-lookup"><span data-stu-id="89098-142">(You can easily find the group ID in the link to the team).</span></span>

    <span data-ttu-id="89098-143">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="89098-143">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels?$filter=membershipType eq 'private'
    ```

    <span data-ttu-id="89098-144">**Risposta**</span><span class="sxs-lookup"><span data-stu-id="89098-144">**Response**</span></span>

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

2. <span data-ttu-id="89098-145">Per ogni canale privato per il quale si vuole ottenere l'URL di SharePoint, eseguire la richiesta seguente, in cui &lt;channel_id&gt; è l'ID del canale.</span><span class="sxs-lookup"><span data-stu-id="89098-145">For each private channel which you want to get the SharePoint URL, make the following request, where &lt;channel_id&gt; is the channel ID.</span></span>

    <span data-ttu-id="89098-146">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="89098-146">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/filesFolder
    ```

    <span data-ttu-id="89098-147">**Risposta**</span><span class="sxs-lookup"><span data-stu-id="89098-147">**Response**</span></span>

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

## <a name="list-and-update-roles-of-owners-and-members-in-a-private-channel"></a><span data-ttu-id="89098-148">Elencare e aggiornare i ruoli di proprietari e membri in un canale privato</span><span class="sxs-lookup"><span data-stu-id="89098-148">List and update roles of owners and members in a private channel</span></span>

<span data-ttu-id="89098-149">È possibile elencare i proprietari e i membri di un canale privato per decidere se sia necessario alzare di livello determinati membri del canale privato e impostarli come proprietari.</span><span class="sxs-lookup"><span data-stu-id="89098-149">You may want to list out the owners and members of a private channel to decide whether you need to promote certain members of the private channel to an owner.</span></span> <span data-ttu-id="89098-150">Questo può verificarsi se sono presenti proprietari di canali privati che hanno lasciato l'organizzazione e il canale privato richiede l'assistenza da parte dell'amministratore per rivendicarne la proprietà.</span><span class="sxs-lookup"><span data-stu-id="89098-150">This can happen when you have owners of private channels who have left the organization and the private channel requires admin help to claim ownership of the channel.</span></span>

<span data-ttu-id="89098-151">L'amministratore può usare l'interfaccia di amministrazione di Microsoft Teams, PowerShell o l’API Graph per eseguire queste azioni.</span><span class="sxs-lookup"><span data-stu-id="89098-151">As an admin, you can use the Microsoft Teams admin center, PowerShell, or Graph API to perform these actions.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="89098-152">Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="89098-152">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="89098-153">Per informazioni su come gestire i membri del team attraverso l'interfaccia di amministrazione di Microsoft Teams, vedere [Gestire i team nell'interfaccia di amministrazione di Microsoft Teams](manage-teams-in-modern-portal.md).</span><span class="sxs-lookup"><span data-stu-id="89098-153">To learn how to manage team members using the Microsoft Teams admin center, see [Manage teams in the Microsoft Teams admin center](manage-teams-in-modern-portal.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="89098-154">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="89098-154">Using PowerShell</span></span>

1. <span data-ttu-id="89098-155">Eseguire le operazioni seguenti, in cui&lt;group_id&gt; è l'ID del gruppo del team e &lt;channel_name&gt; è il nome del canale.</span><span class="sxs-lookup"><span data-stu-id="89098-155">Run the following, where &lt;group_id&gt; is the group ID of the team and &lt;channel_name&gt; is the channel name.</span></span>

    ```PowerShell
    Get-TeamChannelUser -GroupId <group_id> -DisplayName "<channel_name>" 
    ```

2. <span data-ttu-id="89098-156">Alzare di livello un membro per impostarlo come proprietario.</span><span class="sxs-lookup"><span data-stu-id="89098-156">Promote a member to an owner.</span></span>

    ```PowerShell
    Add-TeamChannelUser -GroupId <group_id> -DisplayName "<channel_name>" -User <UPN> -Role Owner
    ```

### <a name="using-graph-api"></a><span data-ttu-id="89098-157">Utilizzo dell’API Graph</span><span class="sxs-lookup"><span data-stu-id="89098-157">Using Graph API</span></span>

<span data-ttu-id="89098-158">È possibile provare questi comandi con [Graph explorer](https://developer.microsoft.com/graph/graph-explorer).</span><span class="sxs-lookup"><span data-stu-id="89098-158">You can try these commands through [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

1. <span data-ttu-id="89098-159">Usare quanto segue, in cui&lt;group_id&gt; è l'ID del gruppo del team e &lt;channel_id&gt; è l’ID del canale.</span><span class="sxs-lookup"><span data-stu-id="89098-159">Use the following, where &lt;group_id&gt; is the group ID of the team and &lt;channel_id&gt; is the channel ID.</span></span>

    <span data-ttu-id="89098-160">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="89098-160">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members
    ```
    
    <span data-ttu-id="89098-161">**Risposta**</span><span class="sxs-lookup"><span data-stu-id="89098-161">**Response**</span></span>

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
2. <span data-ttu-id="89098-162">Usare quanto segue per alzare di livello un membro a proprietario, in cui &lt;group_id&gt;, &lt;channel_id&gt;, e &lt;id&gt; vengono restituiti dalla chiamata precedente.</span><span class="sxs-lookup"><span data-stu-id="89098-162">Use the following to promote the member to an owner, where &lt;group_id&gt;, &lt;channel_id&gt;, and &lt;id&gt; are returned from the previous call.</span></span> <span data-ttu-id="89098-163">Si noti che &lt;id&gt; e &lt;userId&gt; restituiti dalla chiamata precedente non sono uguali e non sono intercambiabili.</span><span class="sxs-lookup"><span data-stu-id="89098-163">Note that &lt;id&gt; and &lt;userId&gt; returned from the previous call aren't the same and aren't interchangeable.</span></span> <span data-ttu-id="89098-164">Assicurarsi di usare &lt;id&gt;.</span><span class="sxs-lookup"><span data-stu-id="89098-164">Make sure you use &lt;id&gt;.</span></span>

    <span data-ttu-id="89098-165">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="89098-165">**Request**</span></span>

    ```Graph API
    PATCH 
    https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members/<id>
      
    {
    "@odata.type": "#microsoft.graph.aadUserConversationMember",
    "roles": ["owner"]
    }
    ```

    <span data-ttu-id="89098-166">**Risposta**</span><span class="sxs-lookup"><span data-stu-id="89098-166">**Response**</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="89098-167">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="89098-167">Related topics</span></span>

- [<span data-ttu-id="89098-168">Panoramica di PowerShell per Teams</span><span class="sxs-lookup"><span data-stu-id="89098-168">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="89098-169">Usare l'API Microsoft Graph per lavorare con Teams</span><span class="sxs-lookup"><span data-stu-id="89098-169">Use the Microsoft Graph API to work with Teams</span></span>](https://docs.microsoft.com/graph/api/resources/teams-api-overview?view=graph-rest-1.0)
    - [<span data-ttu-id="89098-170">Elencare canali</span><span class="sxs-lookup"><span data-stu-id="89098-170">List channels</span></span>](https://docs.microsoft.com/graph/api/channel-list)
    - [<span data-ttu-id="89098-171">Creare canali</span><span class="sxs-lookup"><span data-stu-id="89098-171">Create channel</span></span>](https://docs.microsoft.com/graph/api/channel-post)
    - [<span data-ttu-id="89098-172">Aggiungere membri al canale</span><span class="sxs-lookup"><span data-stu-id="89098-172">Add member to channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-add)
    - [<span data-ttu-id="89098-173">Aggiornare membri nel canale</span><span class="sxs-lookup"><span data-stu-id="89098-173">Update member in channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-update)
    - [<span data-ttu-id="89098-174">Rimuovere membri dal canale</span><span class="sxs-lookup"><span data-stu-id="89098-174">Remove member from channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-delete)
