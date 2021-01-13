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
description: È possibile pubblicare la topologia configurata utilizzando Generatore di topologie. Viene chiesto di selezionare da un elenco il front end server o il pool Front End assumerà il ruolo di Holding The Central Management store. Solo un front end server o un pool Front end può contenere questo ruolo in un determinato momento.
ms.openlocfilehash: d4af4756dc42c54790ee1120b418eb5e6a349387
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822186"
---
# <a name="publish-topology-select-cms-page"></a>Pubblicare topologia, pagina Seleziona l'archivio di gestione centrale
 
È possibile pubblicare la topologia configurata utilizzando Generatore di topologie. Viene chiesto di selezionare da un elenco il front end server o il pool Front End assumerà il ruolo di Holding The Central Management store. Solo un front end server o un pool Front end può contenere questo ruolo in un determinato momento. 
  
### <a name="about-the-central-management-server"></a>Informazioni sul server di gestione centrale
Il server di gestione centrale è un singolo sistema di replica master/multiple, in cui la copia di lettura/scrittura del database è conservata dal front end server che contiene il server di gestione centrale. Ogni computer della topologia, incluso il front end server che contiene il server di gestione centrale, dispone di una copia di sola lettura dei dati dell'archivio di gestione centrale nel database di SQL Server, denominata RTCLOCAL per impostazione predefinita, installata nel computer durante l'installazione e la distribuzione. Il database locale riceve gli aggiornamenti delle repliche tramite l'agente Replicator di replica di Lync Server eseguito come servizio in tutti i computer. Il nome del database effettivo sul server di gestione centrale e la replica locale è XDS, costituito dai file XDS. mdf e XDS. ldf. Il percorso del database master è fatto riferimento da un punto di controllo del servizio (SCP) in servizi di dominio Active Directory. Tutti gli strumenti che utilizzano il server di gestione centrale per la gestione e la configurazione di Lync Server utilizzano l'SCP per individuare l'archivio di gestione centrale.
  
## <a name="see-also"></a>Vedere anche

[Move-CsManagementServer](https://docs.microsoft.com/powershell/module/skype/move-csmanagementserver?view=skype-ps)
