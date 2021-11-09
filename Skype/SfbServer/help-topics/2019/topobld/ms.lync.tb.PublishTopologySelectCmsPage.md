---
title: Pubblica topologia, pagina Seleziona l'archivio di gestione centrale
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.PublishTopologySelectCmsPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: df447066-2840-431b-bc4e-acf8aa692d71
ROBOTS: NOINDEX, NOFOLLOW
description: Pubblicare la topologia configurata utilizzando Generatore di topologie. Viene richiesto di selezionare da un elenco quale Front End Server o pool Front End assumerà il ruolo di conservare l'archivio di gestione centrale. Solo un Front End Server o un pool Front End può mantenere questo ruolo in un determinato momento.
ms.openlocfilehash: 4f4658b13a634d5f1d231d4e8fe7683b3fc38b8f
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60860563"
---
# <a name="publish-topology-select-cms-page"></a>Pubblicare topologia, pagina Seleziona l'archivio di gestione centrale
 
Pubblicare la topologia configurata utilizzando Generatore di topologie. Viene richiesto di selezionare da un elenco quale Front End Server o pool Front End assumerà il ruolo di conservare l'archivio di gestione centrale. Solo un Front End Server o un pool Front End può mantenere questo ruolo in un determinato momento. 
  
### <a name="about-the-central-management-server"></a>Informazioni sul server di gestione centrale
Il server di gestione centrale è un singolo sistema di replica master/a più repliche, in cui la copia di lettura/scrittura del database viene mantenuta dal Front End Server che contiene il server di gestione centrale. Ogni computer della topologia, incluso il Front End Server contenente il server di gestione centrale, dispone di una copia di sola lettura dei dati dell'archivio di gestione centrale nel database di SQL Server (denominato RTCLOCAL per impostazione predefinita) installato nel computer durante l'installazione e la distribuzione. Il database locale riceve gli aggiornamenti delle repliche tramite l'agente Replicator di Lync Server eseguito come servizio in tutti i computer. Il nome del database effettivo nel server di gestione centrale e della replica locale è XDS, costituito da file xds.mdf e xds.ldf. Al percorso del database master fa riferimento un punto di controllo del servizio (SCP) in Servizi di dominio Active Directory. Tutti gli strumenti che utilizzano il server di gestione centrale per gestire e configurare Lync Server utilizzano il pannello SCP per individuare l'archivio di gestione centrale.
  
## <a name="see-also"></a>Vedere anche

[Move-CsManagementServer](/powershell/module/skype/move-csmanagementserver?view=skype-ps)