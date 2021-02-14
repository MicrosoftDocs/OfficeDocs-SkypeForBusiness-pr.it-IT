---
title: Aspetto della riga condivisa in Microsoft Teams
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
- ms.teamsadmincenter.users.voice.calldelegation.tooltip
- seo-marvel-apr2020
description: Informazioni su come inviare agli utenti un messaggio di posta elettronica con le informazioni sui servizi di audioconferenza in Microsoft Teams.
ms.openlocfilehash: 7750f85e959f332832c24b60b4efafd784218f61
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583835"
---
# <a name="shared-line-appearance-in-microsoft-teams"></a>Aspetto della riga condivisa in Microsoft Teams

L'aspetto delle righe condivise fa parte della caratteristica di delega che consente a un utente di scegliere un delegato per rispondere o gestire le chiamate per conto dell'utente. Questa caratteristica è utile se un utente ha un assistente amministrativo che gestisce regolarmente le chiamate dell'utente. Nel contesto dell'aspetto delle linee condivise, un responsabile è una persona che autorizza un delegato a effettuare o ricevere chiamate per proprio conto e un delegato può effettuare e ricevere chiamate per conto di un altro utente.

> [!IMPORTANT]
> Questa funzione è disponibile solo in modalità di distribuzione di Teams. Per maggiori dettagli sulle modalità di distribuzione di Teams, consulta Informazioni sulla coesistenza e [l'interoperabilità](teams-and-skypeforbusiness-coexistence-and-interoperability.md) di Microsoft Teams e Skype for Business

## <a name="license-required"></a>Licenza richiesta

Un utente deve disporre di Sistema telefonico con connettività PSTN (licenza del Piano per chiamate o Routing diretto OnlineVoiceRoutingPolicy) come delegato o impostazione della delega e consentire ad altri utenti di effettuare o ricevere chiamate per proprio conto.

Sia i responsabili che i delegati devono disporre di Sistema telefonico con connettività PSTN (licenza per il Piano per chiamate o Routing diretto OnlineVoiceRoutingPolicy). L'esperienza linea condivisa fa parte della delega ed è inclusa nel Sistema telefonico. Per ulteriori dettagli sul modello di licenza, vedere la descrizione [del servizio Microsoft Teams.](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)

## <a name="configuring-delegation-and-shared-line-appearance"></a>Configurazione della delega e dell'aspetto delle righe condivise

La delega e l'aspetto delle righe condivise sono caratteristiche a livello di utente: non sono disponibili impostazioni di amministrazione da configurare. Per informazioni su come usare la funzionalità, vedere [Condividere una linea telefonica con un delegato](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)

Per il funzionamento di questa funzionalità, l'amministratore del tenant può abilitare la delega tramite l'impostazione **AllowDelegation di TeamsCallingPolicy** o tramite il portale di amministrazione di Teams. 

L'amministratore del tenant può anche configurare le relazioni di delega per un utente nell'interfaccia di amministrazione di Teams. Inoltre, l'utente finale può anche configurare le relazioni di delega direttamente in Teams. L'amministratore del tenant o l'utente non può bloccare la configurazione tra loro, ma l'interfaccia di amministrazione di Teams e il client Teams devono mostrare questa relazione in modo accurato in entrambe le posizioni. 

> [!IMPORTANT]
> Quando l'amministratore del tenant disattiva la delega per un utente (dopo che è stato attivato), deve anche eliminare le relazioni di delega per quell'utente nell'interfaccia di amministrazione di Teams per evitare un instradamento delle chiamate non corretto.

## <a name="shared-line-appearance-feature-availability"></a>Disponibilità delle caratteristiche per l'aspetto delle righe condivise

L'aspetto delle righe condivise è attualmente supportato dalle app e dai dispositivi seguenti.

| Funzionalità | Teams Desktop | Teams Mac App | Teams Web App (Edge) |App Teams per dispositivi mobili iOS/Android | Telefono IP Teams |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|
| Configurare la delega | Sì | Sì | Sì | No | Sì |
| Ricevere chiamate per conto di un altro | Sì | Sì | Sì | Sì | Sì |
| Chiamare un numero di telefono per conto di un altro utente | Sì | Sì | Sì | Sì | Sì |
| Chiamare un utente di Teams per conto di un altro | Sì | Sì | Sì | Sì | Sì |
| Visualizzare la visualizzazione amministratore delle righe condivise | Sì | Sì | Sì | No | No |
| Visualizzare la visualizzazione amministratore delle attività di chiamata del responsabile | Sì | Sì | Sì | No | No |
| Visualizzare la visualizzazione Responsabile dei delegati | Sì | Sì | Sì | No | No |
| L'amministratore o il responsabile può tenere premuto o riprendere | Sì | Sì | Sì | No | No |

## <a name="limitations"></a>Limitazioni

I responsabili possono aggiungere fino a 25 delegati e i delegati possono avere fino a 25 responsabili. Non sono presenti limiti al numero di relazioni di delega che è possibile creare in un tenant. 
 
Se il delegante e il delegato non si trova nella stessa posizione geografica, è il provider PSTN a consentire la visualizzazione dell'ID chiamante da una località geografica diversa per una chiamata delegata (per conto di). 
 
## <a name="more-information"></a>Altre informazioni

[Condividere una linea telefonica con un delegato](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)
