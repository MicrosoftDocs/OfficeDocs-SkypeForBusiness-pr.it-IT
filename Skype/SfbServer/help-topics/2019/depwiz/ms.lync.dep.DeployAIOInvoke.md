---
title: Preparare un singolo server Standard Edition (Invoke)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeployAIOInvoke
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5da0aa73-8bf8-41f3-81e7-94f955cda541
ROBOTS: NOINDEX, NOFOLLOW
description: Nella pagina esecuzione dei comandi, le attività di installazione di SQL Server Express e configurazione per fungere da Central Management Store possono essere visualizzate nel riquadro attività. Per impostazione predefinita, viene creata un'istanza di un database basato su SQL Server denominato RTC. Vengono create anche regole firewall per consentire l'accesso in ingresso e in uscita per i server e i client per comunicare con il database e l'istanza. Dopo aver completato l'attività, è possibile selezionare il file di log nell'elenco a discesa. Il file di log è denominato computer locale di bootstrap. Dopo aver selezionato il file di log, fare clic su Visualizza log. Esaminare il file di log per eventuali errori e avvisi. Quando si è pronti a procedere, fare clic su fine. Ora devi definire la topologia con generatore di topologia se non l'hai già fatto.
ms.openlocfilehash: 900ef91184a13c67676cfd89a40694ce9fb6224a
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41705891"
---
# <a name="prepare-single-standard-edition-server-invoke"></a>Preparare un singolo server Standard Edition (Invoke)
 
Nella pagina **esecuzione dei comandi** , le attività di installazione di SQL Server Express e configurazione per fungere da Central Management Store possono essere visualizzate nel riquadro attività. Per impostazione predefinita, viene creata un'istanza di un database basato su SQL Server denominato RTC. Vengono create anche regole firewall per consentire l'accesso in ingresso e in uscita per i server e i client per comunicare con il database e l'istanza. Dopo aver completato l'attività, è possibile selezionare il file di log nell'elenco a discesa. Il file di log è denominato **computer locale di bootstrap**. Dopo aver selezionato il file di log, fare clic su **Visualizza log**. Esaminare il file di log per eventuali errori e avvisi. Quando si è pronti a procedere, fare clic su **fine.** Ora devi definire la topologia con generatore di topologia se non l'hai già fatto.
  
> [!IMPORTANT]
> L'installazione di SQL Server Express può richiedere del tempo per il completamento. Durante l'installazione non è visibile alcuno stato sullo schermo o nel riquadro attività. Per monitorare l'installazione, è consigliabile usare Gestione attività di Windows e cercare i processi MSIExec e i file di configurazione per SQL Server. In questo modo, puoi visualizzare lo stato dell'installazione e verificare che l'installazione proceda. A seconda dei fattori che esulano dall'ambito di questo argomento della guida, possono essere necessarie fino a 15 minuti o più per completare l'installazione dell'istanza di SQL Server. 
  

