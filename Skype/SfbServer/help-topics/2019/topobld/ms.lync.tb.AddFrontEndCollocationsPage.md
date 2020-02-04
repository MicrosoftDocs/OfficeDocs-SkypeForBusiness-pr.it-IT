---
title: Aggiungere collocazioni di Front End Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddFrontEndCollocationsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 23e3bda7-a8bf-4da4-88e5-098ae2aa268f
ROBOTS: NOINDEX, NOFOLLOW
description: Per una distribuzione di Enterprise Edition, il servizio di conferenza A/V è collocato nel pool Front-end. È anche possibile collocare il Mediation Server nel pool Front-end oppure distribuirlo come server autonomo. Il servizio di conferenza A/V è sempre collocato se è abilitata la conferenza.
ms.openlocfilehash: fe9eccaa7a59963b202009eba68aa0fdb9f1a15d
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41702921"
---
# <a name="add-front-end-server-collocations"></a>Aggiungere collocazioni di Front End Server

Per una distribuzione di Enterprise Edition, il servizio di conferenza A/V è collocato nel pool Front-end. È anche possibile collocare il Mediation Server nel pool Front-end oppure distribuirlo come server autonomo. Il servizio di conferenza A/V è sempre collocato se è abilitata la conferenza.

> [!NOTE]
> È necessario un servizio di conferenza A/V se è stato selezionato servizi di **conferenza** nella pagina **Seleziona funzionalità** . Un pool Front-end Enterprise Edition usa un servizio di conferenza A/V collocato. Se non è stata selezionata l'opzione servizi di conferenza, il servizio A/V Conferencing collocato non sarà disponibile.

È possibile collocare il ruolo di Mediation Server in un server front-end Standard Edition o in un pool di front-end Enterprise Edition. Se si distribuiscono connessioni SIP dirette a un gateway PSTN (Public Switched Telephone Network) qualificato che supporta il bypass multimediale e il bilanciamento del carico DNS (Domain Name System), non è necessario un pool di Mediation Server autonomo. Un pool di Mediation Server autonomo non è necessario perché i gateway qualificati sono in grado di bilanciamento del carico DNS in un pool di server di mediazione e possono ricevere traffico da qualsiasi Mediation Server in un pool. È anche consigliabile collocare il Mediation Server in un pool Front-end quando si sono distribuiti IP-PBX o connettersi a un SBC (Session Border Controller) di un provider di telefonia Internet, purché siano soddisfatte le condizioni seguenti:

- IP-PBX o SBC è configurato per ricevere il traffico da qualsiasi Mediation Server nel pool e può instradare il traffico uniformemente a tutti i server di mediazione nel pool.

- IP-PBX o SBC è configurato per ricevere il traffico da qualsiasi Mediation Server nel pool e può instradare il traffico uniformemente a tutti i server di mediazione nel pool.

È possibile usare lo strumento di pianificazione per valutare se il pool Front-end in cui si vuole collocare il Mediation Server può gestire il carico. Se l'ambiente non soddisfa questi requisiti, è necessario distribuire un pool di Mediation Server autonomo.

In generale, la collocazione di Mediation Server non è consigliata se l'organizzazione ha requisiti di elevata disponibilità e scalabilità. Per informazioni dettagliate sulla collocazione di questi ruoli del server in un pool Front-end in una distribuzione di Enterprise Edition, vedere [definire e configurare un pool Front End](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) nella documentazione relativa alla distribuzione. Per informazioni dettagliate sulla funzionalità e i componenti di conferenza A/V, vedere [pianificazione per](https://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx) i servizi di conferenza nella documentazione relativa alla pianificazione. Per informazioni dettagliate sulle caratteristiche e i componenti di VoIP aziendale, incluso Mediation Server, vedere [pianificare l'organizzazione di VoIP aziendale in Skype for Business Server](../../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) nella documentazione relativa alla pianificazione.


