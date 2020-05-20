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
ms.openlocfilehash: 154cde6ad8371b2d9f902bf3803f48e72ade0a77
ms.sourcegitcommit: 1a6b4efad1e6a958cdbaae4b0e2e231145c9658f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "44321701"
---
# <a name="manage-the-life-cycle-of-private-channels-in-microsoft-teams"></a>Gestire il ciclo di vita dei canali privati in Microsoft Teams

In questa sezione sono disponibili le indicazioni necessarie per gestire il ciclo di vita dei [canali privati](private-channels.md) nell'organizzazione.

> [!IMPORTANT]
> Se si usano i passaggi di PowerShell in questo articolo per gestire i canali privati, è necessario installare e usare la versione più recente del modulo di PowerShell per i team nella [raccolta di test di PowerShell](https://www.poshtestgallery.com/packages/MicrosoftTeams/). Per istruzioni su come installare il modulo, vedere [installare la versione preliminare del modulo di PowerShell teams](install-prerelease-teams-powershell-module.md). La versione più recente disponibile al pubblico del modulo di PowerShell teams non supporta la gestione dei canali privati.

## <a name="set-whether-team-members-can-create-private-channels"></a>Impostare se i membri del team possono creare canali privati

I proprietari del team possono disattivare o attivare la possibilità per i membri di creare canali privati nelle impostazioni del team. A questo scopo, nella scheda **Impostazioni** del team disattivare o attivare **Consenti ai membri di creare canali privati**.

Come amministratore, puoi usare l'API del grafico per controllare se i membri possono creare canali privati in team specifici. Ecco un esempio.

```Graph API
PATCH /teams/<team_id>
{"memberSettings": 
  {
    "allowCreatePrivateChannels": false
  }
}
```

## <a name="set-whether-users-in-your-organization-can-create-private-channels"></a>Impostare se gli utenti dell'organizzazione possono creare canali privati

Come amministratore, puoi impostare i criteri usando l'interfaccia di amministrazione di Microsoft teams o PowerShell per controllare gli utenti autorizzati a creare canali privati nell'organizzazione.

### <a name="using-the-microsoft-teams-admin-center"></a>Usando l'interfaccia di amministrazione di Microsoft Teams.

Usare i criteri team per impostare gli utenti autorizzati a creare canali privati nell'organizzazione. Per altre informazioni, vedere [gestire i criteri dei team in teams](teams-policies.md).

### <a name="using-powershell"></a>Utilizzo di PowerShell

USA **CsTeamsChannelsPolicy** per impostare gli utenti dell'organizzazione che possono creare canali privati. Imposta il parametro **AllowPrivateChannelCreation** su **true** per consentire agli utenti a cui viene assegnato il criterio di creare canali privati. Impostando il parametro su **false** si disattiva la possibilità di creare canali privati per gli utenti a cui è stato assegnato il criterio.

Per altre informazioni, vedere [New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps).

## <a name="create-a-private-channel-on-behalf-of-a-team-owner"></a>Creare un canale privato per conto di un proprietario del team

Come amministratore, puoi usare PowerShell o Graph API per creare un canale privato per conto di un proprietario del team. Ad esempio, potresti voler eseguire questa operazione se l'organizzazione vuole centralizzare la creazione di canali privati.

### <a name="using-powershell"></a>Utilizzo di PowerShell

```PowerShell
New-TeamChannel –GroupId <Group_Id> –MembershipType Private –DisplayName "<Channel_Name>" –Owner <Owner_UPN>
```

### <a name="using-graph-api"></a>Uso dell'API del grafico

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

## <a name="get-a-list-of-all-private-channel-messages"></a>Ottenere un elenco di tutti i messaggi di canale privato

Potrebbe essere utile ottenere un elenco di tutti i messaggi e le risposte pubblicate in un canale privato per scopi di archiviazione e controllo.  Ecco come usare l'API del grafico per eseguire questa operazione.

```Graph API
GET /teams/{id}/channels/{id}/messages
GET /teams/{id}/channels/{id}/messages/{id}/replies/{id}
```

## <a name="find-sharepoint-urls-for-all-private-channels-in-a-team"></a>Trovare gli URL di SharePoint per tutti i canali privati in un team

Indipendentemente dal fatto che si voglia eseguire una eDiscovery o un blocco legale su file in un canale privato o che si cerchi di creare un'app personalizzata che inserisce i file in canali privati specifici, è possibile eseguire query sulle raccolte siti di SharePoint create per ogni canale privato.

Come amministratore, puoi usare i comandi delle API di PowerShell o Graph per eseguire query su questi URL.

### <a name="using-powershell"></a>Utilizzo di PowerShell

1. Installare e connettersi a [SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) con l'account di amministratore.
2. Eseguire le operazioni seguenti, dove &lt; group_id &gt; è l'ID del gruppo del team. È possibile trovare facilmente l'ID del gruppo nel collegamento al team.

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "<group_id>"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity
    $site.url -Detail; if ($x.RelatedGroupId -eq $groupID)
    {$x.RelatedGroupId;$x.url}}
    ```

### <a name="using-graph-api"></a>Uso dell'API del grafico

Puoi provare questi comandi tramite [Esplora grafico](https://developer.microsoft.com/graph/graph-explorer).

1. Usa la seguente procedura per ottenere l'elenco di ID canale privati per un team specifico, dove <group_id> è l'ID del gruppo del team. Sarà necessario nelle chiamate successive. È possibile trovare facilmente l'ID del gruppo nel collegamento al team.

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

2. Per ogni canale privato per cui si vuole ottenere l'URL di SharePoint, eseguire la richiesta seguente, dove &lt; channel_id &gt; è l'ID del canale.

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

## <a name="list-and-update-roles-of-owners-and-members-in-a-private-channel"></a>Elenco e aggiornamento dei ruoli di proprietari e membri in un canale privato

È consigliabile elencare i proprietari e i membri di un canale privato per decidere se è necessario promuovere alcuni membri del canale privato con un proprietario. Questo problema può verificarsi quando si hanno proprietari di canali privati che hanno lasciato l'organizzazione e il canale privato richiede all'amministratore la guida per rivendicare la proprietà del canale.

Come amministratore, puoi usare i comandi delle API di PowerShell o Graph per eseguire query su questi URL.

### <a name="using-powershell"></a>Utilizzo di PowerShell

1. Eseguire le operazioni seguenti, dove &lt; group_id &gt; è l'ID del gruppo del team e &lt; channel_name &gt; è il nome del canale.

    ```PowerShell
    Get-TeamChannelUser -GroupId <group_id> -DisplayName "<channel_name>" 
    ```

2. Innalzare di livello un membro a un proprietario.

    ```PowerShell
    Add-TeamChannelUser -GroupId <group_id> -DisplayName "<channel_name>" -User <UPN> -Role Owner
    ```

### <a name="using-graph-api"></a>Uso dell'API del grafico

Puoi provare questi comandi tramite [Esplora grafico](https://developer.microsoft.com/graph/graph-explorer).

1. Usare le opzioni seguenti, dove &lt; group_id &gt; è l'ID del gruppo del team e &lt; CHANNEL_ID &gt; è l'ID del canale.

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
2. Usa la seguente procedura per innalzare di livello il membro a un proprietario, dove &lt; group_id &gt; , &lt; channel_id &gt; e &lt; ID &gt; vengono restituiti dalla chiamata precedente. Tieni presente che &lt; ID &gt; e &lt; userid &gt; restituiti dalla chiamata precedente non sono uguali e non sono intercambiabili. Assicurarsi di usare &lt; ID &gt; .

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
    - [Canali elenco](https://docs.microsoft.com/graph/api/channel-list)
    - [Creare un canale](https://docs.microsoft.com/graph/api/channel-post)
    - [Aggiungere un membro al canale](https://docs.microsoft.com/graph/api/conversationmember-add)
    - [Aggiornare il membro nel canale](https://docs.microsoft.com/graph/api/conversationmember-update)
    - [Rimuovi membro dal canale](https://docs.microsoft.com/graph/api/conversationmember-delete)
