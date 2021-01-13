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
ms.openlocfilehash: 95d0db07d118090d0af9d75676ff61fecb45a0a2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824176"
---
# <a name="add-front-end-associations"></a>Aggiungere associazioni di Front End Server

È ora possibile abilitare il supporto di funzionalità specifiche che richiedono la distribuzione di altri server associando ruoli del server al pool Front End. È inoltre possibile associare ruoli del server con il pool Front End in un secondo momento. I ruoli del server che possono essere associati a un pool Front End includono quanto segue:

- A/V Edge Server. Per informazioni dettagliate sull'implementazione di un server A/V Edge, vedere [Planning for Conferencing](https://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx) nella documentazione relativa alla pianificazione.

> [!IMPORTANT]
> Se si Abilita il supporto per una qualsiasi di queste funzionalità, la progettazione della topologia che verrà pubblicata includerà i componenti server necessari per implementare ogni caratteristica selezionata. Per pubblicare una topologia senza che vengano generati errori, è necessario che i computer fisici siano aggiunti al dominio. Ad esempio, se si Abilita il supporto per l'archiviazione adesso, è necessario distribuire un server di archiviazione e configurare le opzioni di archiviazione appropriate prima di avviare l'archiviazione delle comunicazioni per l'organizzazione.


