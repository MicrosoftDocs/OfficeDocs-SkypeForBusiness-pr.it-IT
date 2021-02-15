---
title: Preparare un singolo server Standard Edition (Invoke)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployAIOInvoke
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5da0aa73-8bf8-41f3-81e7-94f955cda541
description: Nella pagina Esecuzione comandi in esecuzione è possibile visualizzare nel riquadro attività le attività relative all'installazione di SQL Server Express e alla configurazione dell'archivio di gestione centrale. Per impostazione predefinita, viene creata un'istanza SQL Server database basato su server denominato RTC. Vengono inoltre create regole del firewall per consentire l'accesso in entrata e in uscita, in modo che i server e i client possano comunicare con il database e l'istanza. Al termine dell'attività, è possibile selezionare il file di registro nell'elenco a discesa. Tale file è denominato Avvio automatico computer locale. Dopo avere selezionato il file di registro, fare clic su Visualizza registro. Esaminare gli eventuali errori e avvisi presenti nel file. Quando si è pronti per continuare, fare clic su Fine. È ora consigliabile definire la topologia con Generatore di topologie se non è già stata eseguita.
ms.openlocfilehash: adf980ec2576eb4e23983fcd99befb1fc6bfb6ee
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49829746"
---
# <a name="prepare-single-standard-edition-server-invoke"></a>Preparare un singolo server Standard Edition (Invoke)
 
Nella pagina **Esecuzione comandi** in esecuzione è possibile visualizzare nel riquadro attività le attività relative all'installazione di SQL Server Express e alla configurazione dell'archivio di gestione centrale. Per impostazione predefinita, viene creata un'istanza SQL Server database basato su server denominato RTC. Vengono inoltre create regole del firewall per consentire l'accesso in entrata e in uscita, in modo che i server e i client possano comunicare con il database e l'istanza. Al termine dell'attività, è possibile selezionare il file di registro nell'elenco a discesa. Tale file è denominato **Avvio automatico computer locale**. Dopo avere selezionato il file di registro, fare clic su **Visualizza registro**. Esaminare gli eventuali errori e avvisi presenti nel file. Quando si è pronti per continuare, fare clic su **Fine**. È ora consigliabile definire la topologia con Generatore di topologie se non è già stata eseguita.
  
> [!IMPORTANT]
> Il completamento dell'installazione SQL Server Express può richiedere del tempo. Durante l'installazione non sono visibili indicatori di stato sullo schermo o nel riquadro attività. Per monitorare l'installazione, è consigliabile utilizzare Gestione attività di Windows e cercare i processi MSIExec e i file di installazione per SQL Server. In questo modo è possibile visualizzare lo stato dell'installazione e assicurarsi che proceda correttamente. A seconda dei fattori che esono dall'ambito di questo argomento della Guida, il completamento dell'installazione dell'istanza SQL Server può richiedere fino a 15 minuti o più. 
  

