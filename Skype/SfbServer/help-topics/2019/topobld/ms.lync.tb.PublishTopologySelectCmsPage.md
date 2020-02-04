---
title: Pagina Selezionare CMS per la pubblicazione della topologia
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.PublishTopologySelectCmsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df447066-2840-431b-bc4e-acf8aa692d71
ROBOTS: NOINDEX, NOFOLLOW
description: Viene pubblicata la topologia configurata con generatore di topologia. Viene richiesto di selezionare un elenco da un server front-end o da un pool Front-end che assumerà il ruolo di Holding The Central Management store. Solo un server front-end o un pool Front-end può contenere questo ruolo in un momento specifico.
ms.openlocfilehash: 9cecdc170934f7359597484e56299e2fe76499b9
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41701671"
---
# <a name="publish-topology-select-cms-page"></a>Pagina Selezionare CMS per la pubblicazione della topologia
 
Viene pubblicata la topologia configurata con generatore di topologia. Viene richiesto di selezionare un elenco da un server front-end o da un pool Front-end che assumerà il ruolo di Holding The Central Management store. Solo un server front-end o un pool Front-end può contenere questo ruolo in un momento specifico. 
  
### <a name="about-the-central-management-server"></a>Informazioni sul server di gestione centrale
Il server di gestione centrale è un singolo sistema master/replica multipla, in cui la copia di lettura/scrittura del database è tenuta dal server front-end che contiene il server di gestione centrale. Ogni computer della topologia, incluso il front end server che contiene il server di gestione centrale, ha una copia di sola lettura dei dati di Central Management store nel database di SQL Server (denominata RTCLOCAL per impostazione predefinita) installati nel computer durante l'installazione e distribuzione. Il database locale riceve gli aggiornamenti della replica tramite l'agente replicatore di Lync Server che viene eseguito come servizio in tutti i computer. Il nome del database effettivo nel server di gestione centrale e la replica locale è XDS, costituito dai file XDS. mdf e XDS. ldf. Il percorso del database master viene fatto riferimento da un punto di controllo del servizio (SCP) in servizi di dominio Active Directory. Tutti gli strumenti che usano il server di gestione centralizzato per gestire e configurare Lync Server usano l'SCP per individuare l'Central Management store.
  
## <a name="see-also"></a>Vedere anche

[Move-CsManagementServer](https://docs.microsoft.com/powershell/module/skype/move-csmanagementserver?view=skype-ps)
