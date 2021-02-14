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
description: Pubblicare la topologia configurata utilizzando Generatore di topologie. Viene richiesto di selezionare da un elenco il Front End Server o il pool Front End che assumerà il ruolo di detenere l'archivio di gestione centrale. Questo ruolo può essere assegnato a un solo Front End Server o pool Front End alla volta.
ms.openlocfilehash: d4af4756dc42c54790ee1120b418eb5e6a349387
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822186"
---
# <a name="publish-topology-select-cms-page"></a>Pubblicare topologia, pagina Seleziona l'archivio di gestione centrale
 
Pubblicare la topologia configurata utilizzando Generatore di topologie. Viene richiesto di selezionare da un elenco il Front End Server o il pool Front End che assumerà il ruolo di detenere l'archivio di gestione centrale. Questo ruolo può essere assegnato a un solo Front End Server o pool Front End alla volta. 
  
### <a name="about-the-central-management-server"></a>Informazioni sul server di gestione centrale
Il server di gestione centrale è un singolo sistema di replica master/multiple, in cui la copia di lettura/scrittura del database è contenuta nel Front End Server contenente il server di gestione centrale. Ogni computer della topologia, incluso il Front End Server contenente il server di gestione centrale, dispone di una copia di sola lettura dei dati dell'archivio di gestione centrale nel database di SQL Server (denominato RTCLOCAL per impostazione predefinita) installato nel computer durante l'installazione e la distribuzione. Il database locale riceve gli aggiornamenti delle repliche tramite l'agente Replicator di Lync Server eseguito come servizio in tutti i computer. Il nome del database effettivo nel server di gestione centrale e nella replica locale è XDS, costituito da file xds.mdf e xds.ldf. Al percorso del database master viene fatto riferimento da un punto di controllo del servizio (SCP) in Servizi di dominio Active Directory. Tutti gli strumenti che utilizzano il server di gestione centrale per gestire e configurare Lync Server utilizzano SCP per individuare l'archivio di gestione centrale.
  
## <a name="see-also"></a>Vedere anche

[Move-CsManagementServer](https://docs.microsoft.com/powershell/module/skype/move-csmanagementserver?view=skype-ps)
