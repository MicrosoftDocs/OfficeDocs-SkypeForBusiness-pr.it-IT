---
title: Pubblica topologia, pagina Seleziona l'archivio di gestione centrale
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.PublishTopologySelectCmsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df447066-2840-431b-bc4e-acf8aa692d71
ROBOTS: NOINDEX, NOFOLLOW
description: Pubblicare la topologia configurata utilizzando Generatore di topologie. Viene richiesto di selezionare da un elenco quale Front End Server o pool Front End assumerà il ruolo di conservare l'archivio di gestione centrale. Solo un Front End Server o un pool Front End può mantenere questo ruolo in un determinato momento.
ms.openlocfilehash: aba80733c215d9de1eab58be7054ad68519123a9f23f131f389b50754ac0dc73
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54307547"
---
# <a name="publish-topology-select-cms-page"></a>Pubblicare topologia, pagina Seleziona l'archivio di gestione centrale
 
Pubblicare la topologia configurata utilizzando Generatore di topologie. Viene richiesto di selezionare da un elenco quale Front End Server o pool Front End assumerà il ruolo di conservare l'archivio di gestione centrale. Solo un Front End Server o un pool Front End può mantenere questo ruolo in un determinato momento. 
  
### <a name="about-the-central-management-server"></a>Informazioni sul server di gestione centrale
Il server di gestione centrale è un singolo sistema di replica master/a più repliche, in cui la copia di lettura/scrittura del database viene mantenuta dal Front End Server che contiene il server di gestione centrale. Ogni computer della topologia, incluso il Front End Server contenente il server di gestione centrale, dispone di una copia di sola lettura dei dati dell'archivio di gestione centrale nel database di SQL Server (denominato RTCLOCAL per impostazione predefinita) installato nel computer durante l'installazione e la distribuzione. Il database locale riceve gli aggiornamenti delle repliche tramite l'agente Replicator di Lync Server eseguito come servizio in tutti i computer. Il nome del database effettivo nel server di gestione centrale e della replica locale è XDS, costituito da file xds.mdf e xds.ldf. Al percorso del database master fa riferimento un punto di controllo del servizio (SCP) in Servizi di dominio Active Directory. Tutti gli strumenti che utilizzano il server di gestione centrale per gestire e configurare Lync Server utilizzano il pannello SCP per individuare l'archivio di gestione centrale.
  
## <a name="see-also"></a>Vedere anche

[Move-CsManagementServer](/powershell/module/skype/move-csmanagementserver?view=skype-ps)