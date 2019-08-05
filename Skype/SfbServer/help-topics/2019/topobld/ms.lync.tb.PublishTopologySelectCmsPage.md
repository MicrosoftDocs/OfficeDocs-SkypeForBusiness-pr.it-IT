---
title: Pagina di pubblicazione di selezione CMS per la topologia
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.PublishTopologySelectCmsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df447066-2840-431b-bc4e-acf8aa692d71
ROBOTS: NOINDEX, NOFOLLOW
description: Viene pubblicata la topologia configurata con generatore di topologia. Viene richiesto di selezionare un elenco da un server front-end o da un pool Front-end che assumerà il ruolo di Holding The Central Management store. Solo un server front-end o un pool Front-end può contenere questo ruolo in un momento specifico.
ms.openlocfilehash: e56597a1380f908c7abdb49b9b88edd7ad249870
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188039"
---
# <a name="publish-topology-select-cms-page"></a>Pagina di pubblicazione di selezione CMS per la topologia
 
Viene pubblicata la topologia configurata con generatore di topologia. Viene richiesto di selezionare un elenco da un server front-end o da un pool Front-end che assumerà il ruolo di Holding The Central Management store. Solo un server front-end o un pool Front-end può contenere questo ruolo in un momento specifico. 
  
### <a name="about-the-central-management-server"></a>Informazioni sul server di gestione centrale
Il server di gestione centrale è un singolo sistema master/replica multipla, in cui la copia di lettura/scrittura del database è tenuta dal server front-end che contiene il server di gestione centrale. Ogni computer della topologia, incluso il front end server che contiene il server di gestione centrale, ha una copia di sola lettura dei dati di Central Management store nel database di SQL Server (denominata RTCLOCAL per impostazione predefinita) installati nel computer durante l'installazione e distribuzione. Il database locale riceve gli aggiornamenti della replica tramite l'agente replicatore di Lync Server che viene eseguito come servizio in tutti i computer. Il nome del database effettivo nel server di gestione centrale e la replica locale è XDS, costituito dai file XDS. mdf e XDS. ldf. Il percorso del database master viene fatto riferimento da un punto di controllo del servizio (SCP) in servizi di dominio Active Directory. Tutti gli strumenti che usano il server di gestione centralizzato per gestire e configurare Lync Server usano l'SCP per individuare l'Central Management store.
  
## <a name="see-also"></a>Vedere anche

[Move-CsManagementServer](https://docs.microsoft.com/powershell/module/skype/move-csmanagementserver?view=skype-ps)
