---
title: Aggiungere associazioni di Front End Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndAssociationsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 95620425-defd-47fd-a5c0-e4a283d812a5
description: 'È ora possibile abilitare il supporto di funzionalità specifiche che richiedono la distribuzione di altri server associando ruoli del server al pool Front End. È inoltre possibile associare ruoli del server con il pool Front End in un secondo momento. I ruoli del server che possono essere associati a un pool Front End includono quanto segue:'
ms.openlocfilehash: df7183915316f4b3b7c198c5fce735fa6969e6057b7a0ef95a7ce12b74eb5b8e
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54345753"
---
# <a name="add-front-end-associations"></a>Aggiungere associazioni di Front End Server

È ora possibile abilitare il supporto di funzionalità specifiche che richiedono la distribuzione di altri server associando ruoli del server al pool Front End. È inoltre possibile associare ruoli del server con il pool Front End in un secondo momento. I ruoli del server che possono essere associati a un pool Front End includono quanto segue:

- A/V Edge Server. Per informazioni dettagliate sull'implementazione di un A/V Edge Server, vedere [Planning for Conferencing](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-conferencing) nella documentazione relativa alla pianificazione.

> [!IMPORTANT]
> Se si abilita ora il supporto per una di queste funzionalità, la progettazione della topologia pubblicata includerà i componenti server necessari per implementare ogni funzionalità selezionata. Per pubblicare una topologia senza che vengano generati errori, è necessario che i computer fisici siano aggiunti al dominio. Ad esempio, se si abilita ora il supporto per l'archiviazione, è necessario distribuire un server di archiviazione e configurare le opzioni di archiviazione appropriate prima di avviare l'archiviazione delle comunicazioni per l'organizzazione.