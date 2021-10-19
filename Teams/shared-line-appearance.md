---
title: Aspetto della linea condivisa in Microsoft Teams
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 02/19/2019
ms.reviewer: srividhc
ms.topic: conceptual
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
- ms.teamsadmincenter.users.voice.calldelegation.tooltip
- seo-marvel-apr2020
description: Informazioni su come inviare agli utenti un messaggio di posta elettronica con le informazioni relative ai servizi di audioconferenza in Microsoft Teams.
ms.openlocfilehash: 057c9a91e1eab20ab7f9ece6c427b6c39ef762b9
ms.sourcegitcommit: 279ab5236431961c5181e2c01a69e5aa4290d381
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2021
ms.locfileid: "60462380"
---
# <a name="shared-line-appearance-in-microsoft-teams"></a>Aspetto della linea condivisa in Microsoft Teams

L'aspetto della linea condivisa fa parte della funzionalità di delega che consente a un utente di scegliere un delegato per rispondere o gestire le chiamate per loro conto. Questa funzionalità è utile se un utente ha un assistente amministrativo che gestisce regolarmente le chiamate dell'utente. Nel contesto dell'aspetto condiviso delle righe, un responsabile è una persona che autorizza un delegato a effettuare o ricevere chiamate per suo conto e un delegato può effettuare e ricevere chiamate per conto di un altro utente.

> [!IMPORTANT]
> Questa caratteristica è disponibile solo in modalità Teams solo distribuzione. Per altre informazioni sulle modalità Teams distribuzione, vedere Informazioni sulla Microsoft Teams e [Skype for Business e sull'interoperabilità](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

## <a name="license-required"></a>Licenza richiesta

Un utente deve avere un Sistema telefonico con connettività PSTN (una licenza piano per chiamate o Direct Routing OnlineVoiceRoutingPolicy) per essere un delegato o configurare la delega e consentire ad altri utenti di effettuare o ricevere chiamate per loro conto.

Sia i responsabili che i delegati devono avere a Sistema telefonico connettività PSTN (una licenza per il piano di chiamata o una Direct Routing OnlineVoiceRoutingPolicy). L'esperienza di linea condivisa fa parte della delega ed è inclusa in Sistema telefonico. Per altri dettagli sul modello di licenza, vedere la [descrizione Microsoft Teams servizio.](/office365/servicedescriptions/teams-service-description)

## <a name="configuring-delegation-and-shared-line-appearance"></a>Configurazione della delega e dell'aspetto della linea condivisa

La delega e l'aspetto della linea condivisa sono caratteristiche guidate dall'utente: non sono disponibili impostazioni di amministratore da configurare. Per informazioni su come usare la funzionalità, vedere [Condividere una linea telefonica con un delegato](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)

L'amministratore tenant può abilitare la delega tramite l'impostazione **TeamsCallingPolicy AllowDelegation** o tramite il portale di amministrazione di Teams per il funzionamento di questa funzionalità. 

L'amministratore tenant può anche configurare le relazioni di delega per un utente nell'Teams di amministrazione. Inoltre, l'utente finale può anche configurare le relazioni di delega direttamente Teams. L'amministratore tenant o l'utente non può bloccare la configurazione tra loro, ma l'interfaccia di amministrazione di Teams e il client Teams devono mostrare questa relazione in modo accurato in entrambe le posizioni. 

> [!IMPORTANT]
> Quando l'amministratore tenant disattiva la delega per un utente (dopo che è stato attivato), deve anche pulire le relazioni di delega per quell'utente nell'interfaccia di amministrazione di Teams per evitare un instradamento non corretto delle chiamate.

## <a name="shared-line-appearance-feature-availability"></a>Disponibilità della caratteristica Aspetto linea condivisa

L'aspetto della linea condivisa è attualmente supportato dalle app e dai dispositivi seguenti.

| Funzionalità | Teams Desktop | Teams Mac App | Teams Web App (Edge) |Teams app per dispositivi mobili iOS/Android | Teams Telefono IP |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|
| Configurare la delega | Sì | Sì | Sì | No | Sì |
| Ricevere chiamate per conto di un altro | Sì | Sì | Sì | Sì | Sì |
| Chiamare un numero di telefono per conto di un altro | Sì | Sì | Sì | Sì | Sì |
| Chiamare un Teams utente per conto di un altro utente | Sì | Sì | Sì | Sì | Sì |
| Visualizzare la visualizzazione delegata delle righe condivise | Sì | Sì | Sì | No | No |
| Visualizzare la visualizzazione delegata delle attività di chiamata del manager | Sì | Sì | Sì | No | No |
| Visualizzare la visualizzazione responsabile dei delegati | Sì | Sì | Sì | No | No |
| Il delegato o il responsabile può tenere o riprendere | Sì | Sì | Sì | No | No |

## <a name="limitations"></a>Limitazioni

I responsabili possono aggiungere fino a 25 delegati e i delegati possono avere fino a 25 responsabili. Non esiste alcun limite al numero di relazioni di delega che è possibile creare in un tenant. 
 
Se il delegato e il delegato non si trova nella stessa posizione geografica, è il provider PSTN a consentire la visualizzazione dell'ID chiamante da una posizione geografica diversa per una chiamata delegata (per conto di). 
 
## <a name="more-information"></a>Altre informazioni

[Condividere una linea telefonica con un delegato](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)
