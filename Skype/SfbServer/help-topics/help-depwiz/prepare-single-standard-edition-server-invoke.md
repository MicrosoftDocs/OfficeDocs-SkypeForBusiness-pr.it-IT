---
title: Preparare un singolo server Standard Edition (Invoke)
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployAIOInvoke
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 5da0aa73-8bf8-41f3-81e7-94f955cda541
description: Nella pagina Esecuzione comandi in esecuzione è possibile visualizzare nel riquadro attività le attività relative all'installazione del SQL Server Express e alla configurazione dell'archivio di gestione centrale. Per impostazione predefinita, viene creata un'istanza SQL Server database basato su server denominato RTC. Vengono inoltre create regole del firewall per consentire l'accesso in entrata e in uscita, in modo che i server e i client possano comunicare con il database e l'istanza. Al termine dell'attività, è possibile selezionare il file di registro nell'elenco a discesa. Tale file è denominato Avvio automatico computer locale. Dopo avere selezionato il file di registro, fare clic su Visualizza registro. Esaminare gli eventuali errori e avvisi presenti nel file. Quando si è pronti per continuare, fare clic su Fine. Se non si è già fatto, è consigliabile definire la topologia con Generatore di topologie.
ms.openlocfilehash: 8d72d69b8c5ea676bf1e944bda143ad8f56fea82
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60841588"
---
# <a name="prepare-single-standard-edition-server-invoke"></a>Preparare un singolo server Standard Edition (Invoke)
 
Nella pagina **Esecuzione comandi** in esecuzione è possibile visualizzare nel riquadro attività le attività relative all'installazione del SQL Server Express e alla configurazione dell'archivio di gestione centrale. Per impostazione predefinita, viene creata un'istanza SQL Server database basato su server denominato RTC. Vengono inoltre create regole del firewall per consentire l'accesso in entrata e in uscita, in modo che i server e i client possano comunicare con il database e l'istanza. Al termine dell'attività, è possibile selezionare il file di registro nell'elenco a discesa. Tale file è denominato **Avvio automatico computer locale**. Dopo avere selezionato il file di registro, fare clic su **Visualizza registro**. Esaminare gli eventuali errori e avvisi presenti nel file. Quando si è pronti per continuare, fare clic su **Fine**. Se non si è già fatto, è consigliabile definire la topologia con Generatore di topologie.
  
> [!IMPORTANT]
> Il completamento dell'SQL Server Express può richiedere del tempo. Durante l'installazione non sono visibili indicatori di stato sullo schermo o nel riquadro attività. Per monitorare l'installazione, è necessario Windows Task Manager e cercare i processi MSIExec e i file di installazione per SQL Server. In questo modo è possibile visualizzare lo stato dell'installazione e assicurarsi che proceda correttamente. A seconda dei fattori oltre l'ambito di questo argomento della Guida, il completamento dell'installazione dell'istanza SQL Server può richiedere fino a 15 minuti o più. 
  

