---
title: Aspetto condiviso della linea in Microsoft Teams
author: CarolynRowe
ms.author: crowe
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
description: Informazioni su come inviare agli utenti un messaggio di posta elettronica con le informazioni sui servizi di audioconferenza in Microsoft Teams.
ms.openlocfilehash: 3646cf27e22f5224dc825c758f757cc04d5804fc
ms.sourcegitcommit: 4d88637f510a78d5709d1213c3e285d83a022014
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2022
ms.locfileid: "66794324"
---
# <a name="shared-line-appearance-in-microsoft-teams"></a>Aspetto condiviso della linea in Microsoft Teams

L'aspetto della riga condivisa fa parte della caratteristica di delega che consente a un utente di scegliere un delegato per rispondere o gestire le chiamate per suo conto. Questa funzionalità è utile se un utente ha un assistente amministrativo che gestisce regolarmente le chiamate dell'utente. Nel contesto dell'aspetto della riga condivisa, un responsabile è una persona che autorizza un delegato a effettuare o ricevere chiamate per suo conto e un delegato può effettuare e ricevere chiamate per conto di un altro utente.

> [!IMPORTANT]
> Questa funzionalità è disponibile solo in modalità di distribuzione di Teams. Per altri dettagli sulle modalità di distribuzione di Teams, vedere [Informazioni su Microsoft Teams e coesistenza e interoperabilità di Skype for Business](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

## <a name="license-required"></a>Licenza richiesta

Un utente deve avere un sistema telefonico con connettività PSTN (licenza Piano per chiamate o Direct Routing OnlineVoiceRoutingPolicy) per essere delegato o impostare la delega e consentire ad altri di effettuare o ricevere chiamate per proprio conto.

Sia i responsabili che i delegati devono avere un sistema telefonico con connettività PSTN (licenza Piano per chiamate o Direct Routing OnlineVoiceRoutingPolicy). L'esperienza di linea condivisa fa parte della delega ed è inclusa in Sistema telefonico. Per altri dettagli sul modello di licenza, vedere [Descrizione del servizio Microsoft Teams](/office365/servicedescriptions/teams-service-description).

## <a name="configuring-delegation-and-shared-line-appearance"></a>Configurazione dell'aspetto della delega e della riga condivisa

L'aspetto della delega e della linea condivisa sono caratteristiche basate sull'utente: non sono disponibili impostazioni di amministrazione da configurare. Per informazioni su come usare la funzionalità, vedere [Condividere una linea telefonica con un delegato](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)

Per il funzionamento di questa funzionalità, l'amministratore tenant può abilitare la delega tramite l'impostazione **TeamsCallingPolicy AllowDelegation** o tramite il portale di Teams Amministrazione. 

L'amministratore tenant può anche configurare le relazioni di delega per un utente nell'interfaccia di amministrazione di Teams. Inoltre, l'utente finale può anche configurare le relazioni di delega direttamente in Teams. L'amministratore tenant o l'utente non può bloccarsi reciprocamente la configurazione, ma l'interfaccia di amministrazione di Teams e il client Teams dovrebbero mostrare questa relazione in modo accurato in entrambe le posizioni. 

> [!IMPORTANT]
> Quando l'amministratore del tenant disattiva la delega per un utente (dopo che è stato attivato), deve anche pulire le relazioni di delega per l'utente nell'interfaccia di amministrazione di Teams per evitare un routing delle chiamate errato.

## <a name="shared-line-appearance-feature-availability"></a>Disponibilità della funzionalità Aspetto linea condivisa

L'aspetto della linea condivisa è attualmente supportato dalle app e dai dispositivi seguenti.

| Funzionalità | Teams Desktop | Teams Mac App | Teams Web App (Edge) |App Teams per dispositivi mobili iOS/Android | Telefono IP teams |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|
| Configurare la delega | Sì | Sì | Sì | No | Sì |
| Ricevere chiamate per conto di un altro | Sì | Sì | Sì | Sì | Sì |
| Chiamare un numero di telefono per conto di un altro | Sì | Sì | Sì | Sì | Sì |
| Chiamare un utente di Teams per conto di un altro | Sì | Sì | Sì | Sì | Sì |
| Visualizzare la visualizzazione delegato delle righe condivise | Sì | Sì | Sì | No | Sì |
| Visualizzare la visualizzazione delegato delle attività di chiamata del responsabile | Sì | Sì | Sì | No | Sì |
| Visualizzare la visualizzazione responsabile dei delegati | Sì | Sì | Sì | No | Sì |
| Il delegato o il responsabile può sospendere o riprendere la gestione | Sì | Sì | Sì | No | Sì |

## <a name="limitations"></a>Limitazioni

I responsabili possono aggiungere fino a 25 delegati e i delegati possono avere fino a 25 responsabili. Non esistono limiti al numero di relazioni di delega che è possibile creare in un tenant. 
 
Se il delegante e il delegato non si trovano nella stessa posizione geografica, spetta al provider PSTN consentire all'ID chiamante di essere visualizzato da una posizione geografica diversa per una chiamata delegata (per conto di). 

La configurazione della delega circolare non è consentita. Se anche gli utenti delegati dispongono di deleghe tra loro, potranno vedere solo la loro delega e non la delega iniziale.
 
## <a name="more-information"></a>Altre informazioni

[Condividere una linea telefonica con un delegato](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)
