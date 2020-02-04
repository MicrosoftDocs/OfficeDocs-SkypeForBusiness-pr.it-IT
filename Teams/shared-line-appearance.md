---
title: Aspetto della linea condivisa in Microsoft Teams
ms.author: lolaj
author: LolaJacobsen
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
localization_priority: Normal
f1.keywords:
- ms.teamsadmincenter.users.voice.calldelegation.tooltip
ms.custom:
- Phone System
description: L'aspetto della linea condivisa consente a un utente di scegliere un delegato per rispondere o gestire le chiamate per proprio conto.
ms.openlocfilehash: 2d050d341d22d74f0d207873925126ad5f7fdc3b
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41694361"
---
# <a name="shared-line-appearance-in-microsoft-teams"></a>Aspetto della linea condivisa in Microsoft Teams

L'aspetto della linea condivisa fa parte della caratteristica di delega che consente a un utente di scegliere un delegato per rispondere o gestire le chiamate per proprio conto. Questa funzionalità è utile se un utente ha un assistente amministrativo che gestisce regolarmente le chiamate dell'utente. Nel contesto dell'aspetto della linea condivisa, un responsabile è un utente che autorizza un delegato a effettuare o ricevere chiamate per conto di un delegato e può effettuare e ricevere chiamate per conto di un altro utente.

> [!IMPORTANT]
> Questa caratteristica è disponibile solo in modalità di distribuzione solo teams. Per altre informazioni sulle modalità di distribuzione dei team, vedere [comprendere la coesistenza e l'interoperabilità di Microsoft teams e Skype for business](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

## <a name="license-required"></a>Licenza richiesta

Un utente deve avere un sistema telefonico con connettività PSTN (una licenza per un piano di chiamata o un routing diretto OnlineVoiceRoutingPolicy) per essere un delegato o configurare la delega e consentire ad altri di effettuare o ricevere chiamate per proprio conto.

Sia i responsabili che i delegati devono avere un sistema telefonico con connettività PSTN (una licenza per un piano di chiamata o un routing diretto OnlineVoiceRoutingPolicy). L'esperienza della linea condivisa fa parte della delega ed è inclusa nel sistema telefonico. Per altre informazioni sul modello di licenza, vedere [licenze di Office 365 per Microsoft teams](office-365-licensing.md).

## <a name="configuring-delegation-and-shared-line-appearance"></a>Configurazione della delega e dell'aspetto delle linee condivise

La delega e l'aspetto delle linee condivise sono caratteristiche guidate dall'utente: non ci sono impostazioni di amministratore da configurare. Per informazioni sull'uso della funzionalità, vedere [condividere una linea telefonica con un delegato](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)

L'amministratore del tenant può abilitare la delega tramite l'impostazione **TeamsCallingPolicy AllowDelegation** o tramite il portale di amministrazione di teams affinché questa funzionalità funzioni. 

L'amministratore del tenant può anche configurare le relazioni di delega per un utente nell'interfaccia di amministrazione di teams. Inoltre, l'utente finale può anche configurare le relazioni di delega direttamente in teams. L'amministratore del tenant o l'utente non può bloccare la configurazione tra loro, ma l'interfaccia di amministrazione di teams e il client teams devono mostrare questa relazione accuratamente in entrambe le posizioni. 

> [!IMPORTANT]
> Quando l'amministratore del tenant disattiva la delega per un utente (dopo che è stato attivato), deve anche pulire le relazioni di delega per l'utente nell'interfaccia di amministrazione di teams per evitare il routing delle chiamate non corretto.

## <a name="shared-line-appearance-feature-availability"></a>Disponibilità delle caratteristiche delle linee condivise

L'aspetto delle linee condivise è attualmente supportato dalle app e dai dispositivi seguenti.

| Capacità | Desktop Teams | App teams Mac | App Web Teams (Edge) |App teams per dispositivi mobili iOS/Android | Telefono IP Teams |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|
| Configurare la delega | Sì | Sì | Sì | No | No |
| Ricevere chiamate per conto di un altro utente | Sì | Sì | Sì | Sì | Sì |
| Chiamare un numero di telefono per conto di un altro utente | Sì | Sì | Sì | Sì | Sì |
| Chiamare un utente di teams per conto di un altro | Sì | Sì | Sì | Sì | Sì |
| Vedere la visualizzazione amministratore delle righe condivise | Sì | Sì | Sì | No | No |
| Vedere la visualizzazione amministratore delle attività di chiamata del responsabile | Sì | Sì | Sì | No | No |
| Vedere la visualizzazione Manager dei delegati | Sì | Sì | Sì | No | No |
| L'amministratore o il responsabile può tenere o riprendere | Sì | Sì | Sì | No | No |

## <a name="limitations"></a>Limitazioni

I responsabili possono aggiungere fino a 25 delegati e i delegati possono avere fino a 25 responsabili. Non esiste alcun limite al numero di relazioni di delega che possono essere create in un tenant. 
 
Se il delegante e il delegato non si trovano nella stessa posizione geografica, spetta al provider PSTN consentire all'ID chiamante di presentarsi da una posizione geografica diversa per una chiamata delegata (per conto di). 
 
## <a name="more-information"></a>Altre informazioni

[Condividere una linea telefonica con un delegato](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)
