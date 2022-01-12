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
ms.localizationpriority: medium
search.appverid: MET150
description: Informazioni su come gestire i canali privati nell'organizzazione usando Graph API.
ms.openlocfilehash: 25065401216a29e28e0d4aa3f1ad02d071215188
ms.sourcegitcommit: a969502c0a5237caf041d7726f4f1edefdd75b44
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2022
ms.locfileid: "61766379"
---
# <a name="manage-the-life-cycle-of-private-channels-in-microsoft-teams"></a>Gestire il ciclo di vita dei canali privati in Microsoft Teams

Ecco le indicazioni necessarie per usare l'API Graph per gestire Teams [canali privati](./private-channels.md) nell'organizzazione.

## <a name="set-whether-team-members-can-create-private-channels"></a>Specificare se i membri del team possono creare canali privati

Gli amministratori possono usare l’API Graph per controllare se i membri possono creare canali privati in specifici team. Di seguito viene riportato un esempio.

```Graph API
PATCH /teams/<team_id>
{"memberSettings": 
  {
    "allowCreatePrivateChannels": false
  }
}
```

## <a name="create-a-private-channel-on-behalf-of-a-team-owner"></a>Creare un canale privato per conto del proprietario del team

Gli amministratori possono usare l'API Graph per creare un canale privato per conto di un proprietario del team. Ad esempio, questa operazione potrebbe essere effettuata se l'organizzazione vuole centralizzare la creazione di canali privati.

```Graph API
POST /teams/{id}/channels
{ "membershipType": "Private",
  "displayName": "<Channel_Name>",
  "members":[{    
           "@odata.type":"#microsoft.graph.aadUserConversationMember",
           "user@odata.bind":"https://graph.microsoft.com/users('<user_id>')",
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

Gli amministratori possono usare i comandi api Graph per eseguire query su questi URL.

È possibile provare questi comandi con [Graph explorer](https://developer.microsoft.com/graph/graph-explorer).

1. Usare la procedura seguente per ottenere l'elenco di ID del canale privato per un determinato team, in cui <group_id> è l'ID del gruppo del team. Questo sarà necessario nelle chiamate successive. È possibile trovare facilmente l'ID del gruppo nel collegamento al team.

    **Richiesta**

    ```Graph API
    GET https://graph.microsoft.com/teams/<group_id>/channels?$filter=membershipType eq 'private'
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
    GET https://graph.microsoft.com/teams/<group_id>/channels/<channel_id>/filesFolder
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

L'amministratore può usare l'API Graph per eseguire queste azioni.

È possibile provare questi comandi con [Graph explorer](https://developer.microsoft.com/graph/graph-explorer).

1. Usare quanto segue, in cui&lt;group_id&gt; è l'ID del gruppo del team e &lt;channel_id&gt; è l’ID del canale.

    **Richiesta**

    ```Graph API
    GET https://graph.microsoft.com/teams/<group_id>/channels/<channel_id>/members
    ```

    **Risposta**

    ```Graph API
    HTTP/1.1 200 OK Content-type: application/json
    Content-length: 
    {
          "@odata.context": "https://graph.microsoft.com/$metadata#teams({group_id}')/channels('{channel_id}')/members",
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
    https://graph.microsoft.com/teams/<group_id>/channels/<channel_id>/members/<id>
      
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
      "@odata.context": "https://graph.microsoft.com/$metadata#teams('{group_id}')/channels('{channel_id}')/members/$entity",
      "@odata.type": "#microsoft.graph.aadUserConversationMember",
      "id": "id-value",
      "roles": ["owner"],
      "displayName": "display-name-value",
      "userId": "userId-value",
      "email": "email-value"
     }
    ```

## <a name="related-topics"></a>Argomenti correlati

[Usare l'API Microsoft Graph per lavorare con Teams](/graph/api/resources/teams-api-overview?view=graph-rest-1.0)

[Elencare canali](/graph/api/channel-list)

[Creare canali](/graph/api/channel-post)

[Aggiungere membri al canale](/graph/api/conversationmember-add)

[Aggiornare membri nel canale](/graph/api/conversationmember-update)

[Rimuovere membri dal canale](/graph/api/conversationmember-delete)
