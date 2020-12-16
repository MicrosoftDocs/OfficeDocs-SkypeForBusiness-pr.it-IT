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
# <a name="manage-the-life-cycle-of-private-channels-in-microsoft-teams"></a>Gestire il ciclo di vita dei canali privati in Microsoft Teams

In quest’articolo sarà possibile trovare informazioni su come gestire il ciclo di vita dei [canali privati](private-channels.md) nell'organizzazione.

> [!IMPORTANT]
> Se si stanno seguendo i passaggi di PowerShell qui descritti, per gestire i canali privati, è necessario installare e usare il modulo di anteprima pubblica di PowerShell per Teams dalla [Raccolta PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/). Per la procedura su come installare il modulo, vedere [Installare PowerShell per Microsoft Teams](teams-powershell-install.md). L'ultimo modulo di disponibilità generale di PowerShell per Teams non supporta la gestione dei canali privati.

## <a name="set-whether-team-members-can-create-private-channels"></a>Specificare se i membri del team possono creare canali privati

I proprietari del team possono disattivare o attivare la possibilità per i membri di creare canali privati nelle impostazioni del team. Per fare ciò, dalla scheda **Impostazioni** per il team, abilitare o disabilitare l’opzione **Consenti ai membri di creare canali privati**.

Gli amministratori possono usare l’API Graph per controllare se i membri possono creare canali privati in specifici team. Di seguito viene riportato un esempio.

```Graph API
PATCH /teams/<team_id>
{"memberSettings": 
  {
    "allowCreatePrivateChannels": false
  }
}
```

## <a name="set-whether-users-in-your-organization-can-create-private-channels"></a>Specificare se gli utenti dell'organizzazione possono creare canali privati

L’amministratore può impostare i criteri usando l'interfaccia di amministrazione di Microsoft Teams o PowerShell per controllare quali utenti dell'organizzazione possono creare canali privati.

### <a name="using-the-microsoft-teams-admin-center"></a>Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.

È possibile usare i criteri dei team per impostare quali utenti dell'organizzazione possono creare canali privati. Per altre informazioni, vedere [Gestire i criteri di riunione in Teams](teams-policies.md).

### <a name="using-powershell"></a>Utilizzo di PowerShell

È possibile usare **CsTeamsChannelsPolicy** per impostare quali utenti dell'organizzazione possono creare canali privati. Impostare il parametro **AllowPrivateChannelCreation** su **true** per consentire agli utenti a cui sono assegnati i criteri di creare canali privati. L'impostazione del parametro su **false** disabilita la possibilità di creare canali privati da parte degli utenti a cui è assegnato il criterio.

Per altre informazioni, vedere [New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps).

## <a name="create-a-private-channel-on-behalf-of-a-team-owner"></a>Creare un canale privato per conto del proprietario del team

Gli amministratori possono usare PowerShell o l’API Graph per creare un canale privato per conto del proprietario del team. Ad esempio, questa operazione potrebbe essere effettuata se l'organizzazione vuole centralizzare la creazione di canali privati.

### <a name="using-powershell"></a>Utilizzo di PowerShell

```PowerShell
New-TeamChannel –GroupId <Group_Id> –MembershipType Private –DisplayName "<Channel_Name>" –Owner <Owner_UPN>
```

### <a name="using-graph-api"></a>Utilizzo dell’API Graph

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

## <a name="get-a-list-of-all-private-channel-messages"></a>Ottenere un elenco di tutti i messaggi del canale privato

Potrebbe essere necessario ottenere un elenco di tutti i messaggi e le risposte pubblicate in un canale privato a scopo di archiviazione e controllo.  Di seguito viene illustrato come usare l'API di Graph per eseguire questa operazione.

```Graph API
GET /teams/{id}/channels/{id}/messages
GET /teams/{id}/channels/{id}/messages/{id}/replies/{id}
```

## <a name="find-sharepoint-urls-for-all-private-channels-in-a-team"></a>Trovare gli URL di SharePoint per tutti i canali privati di un team

Sia che si stia cercando di eseguire l'eDiscovery o la conservazione legale su file in un canale privato, oppure si stia cercando di creare un'app personalizzata che metta i file in canali privati specifici, è necessario un modo per effettuare una query delle raccolte siti univoci di SharePoint create per ciascuno canale privato.

Gli amministratori possono usare i comandi di PowerShell o dell’API Graph per eseguire una query su questi URL.

### <a name="using-powershell"></a>Utilizzo di PowerShell

1. Installare e connettersi al [Management Shell di SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) con l'account amministratore.
2. Eseguire le operazioni seguenti, in cui&lt;group_id&gt; è l'ID del gruppo del team. È possibile trovare facilmente l'ID del gruppo nel collegamento al team.

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "<group_id>"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity
    $site.url -Detail; if ($x.RelatedGroupId -eq $groupID)
    {$x.RelatedGroupId;$x.url}}
    ```

### <a name="using-graph-api"></a>Utilizzo dell’API Graph

È possibile provare questi comandi con [Graph explorer](https://developer.microsoft.com/graph/graph-explorer).

1. Usare la procedura seguente per ottenere l'elenco di ID del canale privato per un determinato team, in cui <group_id> è l'ID del gruppo del team. Questo sarà necessario nelle chiamate successive. È possibile trovare facilmente l'ID del gruppo nel collegamento al team.

    **Richiesta**

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels?$filter=membershipType eq 'private'
    ```

    **Risposta**

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

2. Per ogni canale privato per il quale si vuole ottenere l'URL di SharePoint, eseguire la richiesta seguente, in cui &lt;channel_id&gt; è l'ID del canale.

    **Richiesta**

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/filesFolder
    ```

    **Risposta**

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

## <a name="list-and-update-roles-of-owners-and-members-in-a-private-channel"></a>Elencare e aggiornare i ruoli di proprietari e membri in un canale privato

È possibile elencare i proprietari e i membri di un canale privato per decidere se sia necessario alzare di livello determinati membri del canale privato e impostarli come proprietari. Questo può verificarsi se sono presenti proprietari di canali privati che hanno lasciato l'organizzazione e il canale privato richiede l'assistenza da parte dell'amministratore per rivendicarne la proprietà.

L'amministratore può usare l'interfaccia di amministrazione di Microsoft Teams, PowerShell o l’API Graph per eseguire queste azioni.

### <a name="using-the-microsoft-teams-admin-center"></a>Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.

Per informazioni su come gestire i membri del team attraverso l'interfaccia di amministrazione di Microsoft Teams, vedere [Gestire i team nell'interfaccia di amministrazione di Microsoft Teams](manage-teams-in-modern-portal.md).

### <a name="using-powershell"></a>Utilizzo di PowerShell

1. Eseguire le operazioni seguenti, in cui&lt;group_id&gt; è l'ID del gruppo del team e &lt;channel_name&gt; è il nome del canale.

    ```PowerShell
    Get-TeamChannelUser -GroupId <group_id> -DisplayName "<channel_name>" 
    ```

2. Alzare di livello un membro per impostarlo come proprietario.

    ```PowerShell
    Add-TeamChannelUser -GroupId <group_id> -DisplayName "<channel_name>" -User <UPN> -Role Owner
    ```

### <a name="using-graph-api"></a>Utilizzo dell’API Graph

È possibile provare questi comandi con [Graph explorer](https://developer.microsoft.com/graph/graph-explorer).

1. Usare quanto segue, in cui&lt;group_id&gt; è l'ID del gruppo del team e &lt;channel_id&gt; è l’ID del canale.

    **Richiesta**

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members
    ```
    
    **Risposta**

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
2. Usare quanto segue per alzare di livello un membro a proprietario, in cui &lt;group_id&gt;, &lt;channel_id&gt;, e &lt;id&gt; vengono restituiti dalla chiamata precedente. Si noti che &lt;id&gt; e &lt;userId&gt; restituiti dalla chiamata precedente non sono uguali e non sono intercambiabili. Assicurarsi di usare &lt;id&gt;.

    **Richiesta**

    ```Graph API
    PATCH 
    https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members/<id>
      
    {
    "@odata.type": "#microsoft.graph.aadUserConversationMember",
    "roles": ["owner"]
    }
    ```

    **Risposta**

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

## <a name="related-topics"></a>Argomenti correlati

- [Panoramica di PowerShell per Teams](teams-powershell-overview.md)
- [Usare l'API Microsoft Graph per lavorare con Teams](https://docs.microsoft.com/graph/api/resources/teams-api-overview?view=graph-rest-1.0)
    - [Elencare canali](https://docs.microsoft.com/graph/api/channel-list)
    - [Creare canali](https://docs.microsoft.com/graph/api/channel-post)
    - [Aggiungere membri al canale](https://docs.microsoft.com/graph/api/conversationmember-add)
    - [Aggiornare membri nel canale](https://docs.microsoft.com/graph/api/conversationmember-update)
    - [Rimuovere membri dal canale](https://docs.microsoft.com/graph/api/conversationmember-delete)
