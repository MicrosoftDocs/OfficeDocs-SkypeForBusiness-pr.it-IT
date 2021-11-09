---
title: Aggiungere associazioni di Front End Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndAssociationsPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 95620425-defd-47fd-a5c0-e4a283d812a5
ROBOTS: NOINDEX, NOFOLLOW
description: 'È ora possibile abilitare il supporto di funzionalità specifiche che richiedono la distribuzione di altri server associando ruoli del server al pool Front End. È inoltre possibile associare ruoli del server con il pool Front End in un secondo momento. I ruoli del server che possono essere associati a un pool Front End includono quanto segue:'
ms.openlocfilehash: a4a7806945a29b43a2acf9184c2a8f04e1af77eb
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60864123"
---
# <a name="add-front-end-associations"></a>Aggiungere associazioni di Front End Server

È ora possibile abilitare il supporto di funzionalità specifiche che richiedono la distribuzione di altri server associando ruoli del server al pool Front End. È inoltre possibile associare ruoli del server con il pool Front End in un secondo momento. I ruoli del server che possono essere associati a un pool Front End includono quanto segue:

- A/V Edge Server. Per informazioni dettagliate sull'implementazione di un A/V Edge Server, vedere [Planning for Conferencing](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-conferencing) nella documentazione relativa alla pianificazione.

> [!IMPORTANT]
> Se si abilita ora il supporto per una di queste funzionalità, la progettazione della topologia pubblicata includerà i componenti server necessari per implementare ogni funzionalità selezionata. Per pubblicare una topologia senza che vengano generati errori, è necessario che i computer fisici siano aggiunti al dominio. Ad esempio, se si abilita ora il supporto per l'archiviazione, è necessario distribuire un server di archiviazione e configurare le opzioni di archiviazione appropriate prima di avviare l'archiviazione delle comunicazioni per l'organizzazione.