---
title: Aggiungere collocazioni di Front End Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.AddFrontEndCollocationsPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d328bf4-85bc-4870-8d6f-008c0e46520e
description: Per una distribuzione di Enterprise Edition, è possibile collocare il servizio di conferenza A/V, il Mediation Server o entrambi nel pool Front-end oppure è possibile distribuirli singolarmente come server autonomi. Per la distribuzione di un server Standard Edition, il servizio di conferenza A/V è sempre collocato se è abilitata la conferenza.
ms.openlocfilehash: 4a488aeca543d95042f9dfeec860934f472b94c3
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820838"
---
# <a name="add-front-end-server-collocations-2010"></a>Aggiungere collocazioni di Front End Server 2010

Per una distribuzione di Enterprise Edition, è possibile collocare il servizio di conferenza A/V, il Mediation Server o entrambi nel pool Front-end oppure è possibile distribuirli singolarmente come server autonomi. Per la distribuzione di un server Standard Edition, il servizio di conferenza A/V è sempre collocato se è abilitata la conferenza.

> [!NOTE]
> È necessario un servizio di conferenza A/V se è stato selezionato servizi di **conferenza** nella pagina **Seleziona funzionalità** . Un pool di front-end Enterprise Edition può usare un servizio di conferenza A/V collocato o un pool di servizi di conferenza a/V autonomo. Se non è stata selezionata l'opzione servizi di conferenza, il servizio A/V Conferencing collocato non sarà disponibile.

È possibile collocare il ruolo di Mediation Server in un server front-end Standard Edition o in un pool di front-end Enterprise Edition. Se si distribuiscono connessioni SIP dirette a un gateway PSTN (Public Switched Telephone Network) qualificato che supporta il bypass multimediale e il bilanciamento del carico DNS (Domain Name System), non è necessario un pool di Mediation Server autonomo. Un pool di Mediation Server autonomo non è necessario perché i gateway qualificati sono in grado di bilanciamento del carico DNS in un pool di server di mediazione e possono ricevere traffico da qualsiasi Mediation Server in un pool. È anche consigliabile collocare il Mediation Server in un pool Front-end quando si sono distribuiti IP-PBX o connettersi a un SBC (Session Border Controller) di un provider di telefonia Internet, purché siano soddisfatte le condizioni seguenti:

- IP-PBX o SBC è configurato per ricevere il traffico da qualsiasi Mediation Server nel pool e può instradare il traffico uniformemente a tutti i server di mediazione nel pool.

- IP-PBX o SBC è configurato per ricevere il traffico da qualsiasi Mediation Server nel pool e può instradare il traffico uniformemente a tutti i server di mediazione nel pool.

È possibile usare Microsoft Lync Server 2013, strumento di pianificazione per valutare se il pool di front end in cui si vuole collocare il Mediation Server può gestire il carico. Se l'ambiente non soddisfa questi requisiti, è necessario distribuire un pool di Mediation Server autonomo.

In generale, la collocazione di un/V Conferencing Server o Mediation Server non è consigliata se l'organizzazione ha una disponibilità elevata e la scalabilità requirementsFor dettagli sulla collocazione di questi ruoli del server in un pool di front end in una distribuzione di Enterprise Edition, vedere [definire e configurare un pool di front end](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) nella documentazione relativa alla distribuzione. Per informazioni dettagliate sulla funzionalità e i componenti di conferenza A/V, vedere [pianificazione per](https://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx) i servizi di conferenza nella documentazione relativa alla pianificazione. Per informazioni dettagliate sulle caratteristiche e i componenti di VoIP aziendale, incluso Mediation Server, vedere [pianificare l'organizzazione di VoIP aziendale in Skype for Business server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) nella documentazione relativa alla pianificazione.


