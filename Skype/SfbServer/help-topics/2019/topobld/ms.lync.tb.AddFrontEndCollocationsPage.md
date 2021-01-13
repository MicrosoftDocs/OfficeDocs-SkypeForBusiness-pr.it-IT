---
title: Aggiungere collocazioni di server Front End Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndCollocationsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 23e3bda7-a8bf-4da4-88e5-098ae2aa268f
ROBOTS: NOINDEX, NOFOLLOW
description: Per una distribuzione di Server Enterprise, il servizio A/V Conferencing viene collocato nel pool Front End. È anche possibile collocare Mediation Server sul pool Front End oppure distribuirlo come server autonomo. Se il servizio di conferenza è abilitato, il servizio A/V Conferencing sarà sempre collocato.
ms.openlocfilehash: 8dd984f52740d38689ec123cc51e5cdb2901f440
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49811726"
---
# <a name="add-front-end-server-collocations"></a>Aggiungere collocazioni di Front End Server

Per una distribuzione di Server Enterprise, il servizio A/V Conferencing viene collocato nel pool Front End. È anche possibile collocare Mediation Server sul pool Front End oppure distribuirlo come server autonomo. Se il servizio di conferenza è abilitato, il servizio A/V Conferencing sarà sempre collocato.

> [!NOTE]
> È necessario un servizio A/V Conferencing se nella pagina **Selezionare funzionalità** è stato selezionato **Servizio di conferenza**. Un pool Front End di Server Enterprise utilizza un servizio A/V Conferencing collocato. Se non è stato selezionato Servizio di conferenza, Colloca servizio A/V Conferencing non sarà disponibile.

È possibile collocare il ruolo Mediation Server in un server Standard Edition Front End Server o in un pool Enterprise Edition Front End. Se si distribuiscono connessioni SIP dirette a un gateway PSTN (Public Switched Telephone Network) qualificato in grado di supportare il bypass multimediale (Media Bypass) e il bilanciamento del carico DNS (Domain Name System), non è necessario un pool Mediation Server autonomo. Ciò è dovuto al fatto che i gateway qualificati possono effettuare il bilanciamento del carico DNS in un pool di Mediation Server e ricevere traffico da qualsiasi Mediation Server di un pool. È inoltre consigliabile collocare il Mediation Server in un pool Front end quando è stata distribuita IP-PBXs o connettersi a un SBC (Session Border Controller) di un provider di telefonia Internet, purché siano soddisfatte le condizioni seguenti:

- Il sistema IP-PBX o SBC è configurato per la ricezione di traffico da qualsiasi server Mediation Server nel pool e può eseguire il routing del traffico in modo uniforme a tutti i server Mediation Server nel pool.

- Il sistema IP-PBX o SBC è configurato per la ricezione di traffico da qualsiasi server Mediation Server nel pool e può eseguire il routing del traffico in modo uniforme a tutti i server Mediation Server nel pool.

È possibile utilizzare lo strumento di pianificazione per valutare se il pool Front end in cui si desidera collocare il Mediation Server è in grado di gestire il carico. Se l'ambiente non soddisfa questi requisiti, è necessario distribuire un pool di Mediation Server autonomo.

In generale, la collocazione di Mediation Server non è consigliabile se l'organizzazione ha disponibilità elevata e prevede requisiti di scalabilità. Per informazioni dettagliate sulla collocazione di questi ruoli server in un pool Front End in una distribuzione di Server Enterprise, vedere [Define and Configure a Front End Pool](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) nella documentazione relativa alla distribuzione. Per informazioni dettagliate sulla caratteristica e sui componenti di A/V Conferencing, vedere [Planning for Conferencing](https://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx) nella documentazione relativa alla pianificazione. Per informazioni dettagliate sulle caratteristiche e i componenti di VoIP aziendale, tra cui Mediation Server, vedere [Plan for Enterprise Voice in Skype for Business Server](../../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) nella documentazione relativa alla pianificazione.


