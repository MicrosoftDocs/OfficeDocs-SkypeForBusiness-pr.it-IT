---
title: Aggiungere collocazioni di server Front End Server (2010)
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
  - CSH
ms.custom:
  - ms.lync.tb.AddFrontEndCollocationsPage2010
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 4d328bf4-85bc-4870-8d6f-008c0e46520e
description: 'Per una distribuzione di Server Enterprise, è possibile collocare il servizio A/V Conferencing, il Mediation Server o entrambi nel pool Front End oppure è possibile distribuire ognuno come server autonomo. Per una distribuzione di server Standard Edition, il servizio A/V Conferencing viene sempre collocato se le conferenze sono abilitate.'
---

# <a name="add-front-end-server-collocations-2010"></a>Aggiungere collocazioni di Front End Server 2010

Per una distribuzione di Server Enterprise, è possibile collocare il servizio A/V Conferencing, il Mediation Server o entrambi nel pool Front End oppure è possibile distribuire ognuno come server autonomo. Per una distribuzione di server Standard Edition, il servizio A/V Conferencing viene sempre collocato se le conferenze sono abilitate.

> [!NOTE]
> È necessario un servizio A/V Conferencing se nella pagina **Selezionare funzionalità** è stato selezionato **Servizio di conferenza**. Un pool Enterprise Edition Front End può utilizzare un servizio A/V Conferencing collocato oppure un pool A/V Conferencing autonomo. Se non è stato selezionato Servizio di conferenza, Colloca servizio A/V Conferencing non sarà disponibile.

È possibile collocare il ruolo Mediation Server in un server Standard Edition Front End Server o in un pool Enterprise Edition Front End. Se si distribuiscono connessioni SIP dirette a un gateway PSTN (Public Switched Telephone Network) qualificato in grado di supportare il bypass multimediale (Media Bypass) e il bilanciamento del carico DNS (Domain Name System), non è necessario un pool Mediation Server autonomo. Ciò è dovuto al fatto che i gateway qualificati possono effettuare il bilanciamento del carico DNS in un pool di Mediation Server e ricevere traffico da qualsiasi Mediation Server di un pool. È inoltre consigliabile collocare il Mediation Server in un pool Front End dopo aver distribuito IP-PBXs o connettersi al Session Border Controller (SBC) di un provider di servizi di telefonia Internet, purché siano soddisfatte le condizioni seguenti:

- Il sistema IP-PBX o SBC è configurato per la ricezione di traffico da qualsiasi server Mediation Server nel pool e può eseguire il routing del traffico in modo uniforme a tutti i server Mediation Server nel pool.

- Il sistema IP-PBX o SBC è configurato per la ricezione di traffico da qualsiasi server Mediation Server nel pool e può eseguire il routing del traffico in modo uniforme a tutti i server Mediation Server nel pool.

È possibile utilizzare lo Strumento di pianificazione di Microsoft Lync Server 2013 per valutare se il pool Front End in cui si desidera collocare il Mediation Server può gestire il carico. Se l'ambiente non soddisfa questi requisiti, è necessario distribuire un pool di Mediation Server autonomo.

In generale, la collocazione di A/V Conferencing Server o Mediation Server non è consigliata se l'organizzazione dispone di requisiti di disponibilità elevata e scalabilitàPer informazioni dettagliate sulla collocazione di questi ruoli del server in un pool Front End in una distribuzione di edizione Enterprise, vedere [Define and Configure a Front End Pool](/previous-versions/office/lync-server-2013/lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server) nella documentazione relativa alla distribuzione. Per informazioni dettagliate sulla caratteristica e sui componenti di A/V Conferencing, vedere [Planning for Conferencing](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-conferencing) nella documentazione relativa alla pianificazione. Per informazioni dettagliate sulle VoIP aziendale e sui componenti, incluso Mediation Server, vedere [Plan for VoIP aziendale in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) nella documentazione relativa alla pianificazione.