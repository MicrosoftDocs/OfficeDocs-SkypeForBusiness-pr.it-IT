---
title: Preparare un singolo server Standard Edition (Invoke)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployAIOInvoke
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 5da0aa73-8bf8-41f3-81e7-94f955cda541
ROBOTS: NOINDEX, NOFOLLOW
description: Nella pagina esecuzione comandi in corso, le attività di installazione di SQL Server Express e di configurazione per agire come archivio di gestione centrale possono essere visualizzate nel riquadro attività. Per impostazione predefinita, viene creata un'istanza di un database basato su SQL Server denominato RTC. Vengono inoltre create regole del firewall per consentire l'accesso in entrata e in uscita, in modo che i server e i client possano comunicare con il database e l'istanza. Al termine dell'attività, è possibile selezionare il file di registro nell'elenco a discesa. Tale file è denominato Avvio automatico computer locale. Dopo avere selezionato il file di registro, fare clic su Visualizza registro. Esaminare gli eventuali errori e avvisi presenti nel file. Quando si è pronti per continuare, fare clic su Fine. Se non è stato ancora fatto, è necessario definire la topologia con il generatore di topologie.
ms.openlocfilehash: c3e6e01f7aed0471d8f1eed0ad79f8ef6320f86a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820616"
---
# <a name="prepare-single-standard-edition-server-invoke"></a>Preparare un singolo server Standard Edition (Invoke)
 
Nella pagina **esecuzione comandi** in corso, le attività di installazione di SQL Server Express e di configurazione per agire come archivio di gestione centrale possono essere visualizzate nel riquadro attività. Per impostazione predefinita, viene creata un'istanza di un database basato su SQL Server denominato RTC. Vengono inoltre create regole del firewall per consentire l'accesso in entrata e in uscita, in modo che i server e i client possano comunicare con il database e l'istanza. Al termine dell'attività, è possibile selezionare il file di registro nell'elenco a discesa. Tale file è denominato **Avvio automatico computer locale**. Dopo avere selezionato il file di registro, fare clic su **Visualizza registro**. Esaminare gli eventuali errori e avvisi presenti nel file. Quando si è pronti per continuare, fare clic su **Fine**. Se non è stato ancora fatto, è necessario definire la topologia con il generatore di topologie.
  
> [!IMPORTANT]
> L'installazione di SQL Server Express può richiedere del tempo per il completamento. Durante l'installazione non sono visibili indicatori di stato sullo schermo o nel riquadro attività. Per monitorare l'installazione, è consigliabile utilizzare Windows Task Manager e cercare i processi MSIExec e i file di installazione di SQL Server. In questo modo è possibile visualizzare lo stato dell'installazione e assicurarsi che proceda correttamente. A seconda dei fattori che esulano dall'ambito di questo argomento della guida, è possibile richiedere fino a 15 minuti o più per l'installazione dell'istanza di SQL Server da completare. 
  

