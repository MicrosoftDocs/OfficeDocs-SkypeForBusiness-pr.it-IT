---
title: Prerequisiti e configurazione per lo strumento di stress e prestazioni di Skype for busines
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 12/20/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 948c176c-75ce-418d-891a-a68427d61e40
description: Requisiti o prerequisiti per lo strumento di sollecito e prestazioni di Skype for Business Server 2015. Informazioni su come installare o configurare lo strumento di stress e prestazioni.
ms.openlocfilehash: a58eb5e291878bea74365cd1b9519983c7a77a84
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814956"
---
# <a name="prerequisites-and-setup-for-the-skype-for-busines-stress-and-performance-tool"></a>Prerequisiti e configurazione per lo strumento di stress e prestazioni di Skype for busines
 
Requisiti o prerequisiti per lo strumento di sollecito e prestazioni di Skype for Business Server 2015. Informazioni su come installare o configurare lo strumento di stress e prestazioni.
  
Sono disponibili le seguenti sezioni dei requisiti hardware, software e di configurazione del sistema di cui è necessario tenere conto prima di eseguire lo strumento stress and performance:
  
- [Requisiti hardware client](prerequisites-and-setup.md#ClientHardwareReqs)
    
- [Requisiti software client](prerequisites-and-setup.md#ClientSoftwareReqs)
    
- [Requisiti di configurazione](prerequisites-and-setup.md#ConfigReqs)
    
Inoltre, è presente una sezione per [l'installazione dello strumento di gestione dello stress e delle prestazioni di Skype for Business Server 2015](prerequisites-and-setup.md#Installing)
  
## <a name="client-hardware-requirements"></a>Requisiti hardware client
<a name="ClientHardwareReqs"> </a>

Quando si esegue lo strumento di stress e prestazioni per la distribuzione di Skype for Business Server 2015, è necessario soddisfare almeno i requisiti hardware per ogni 4500 utenti del test:
  
- 1 scheda di rete Gigabit
    
- 8 GB di RAM
    
- 2 CPU dual core
    
## <a name="client-software-requirements"></a>Requisiti software client
<a name="ClientSoftwareReqs"> </a>

I sistemi operativi supportati per lo strumento stress and performance sono i seguenti:
  
- Windows Server 2012
    
- Windows Server 2008 (64 bit)
    
Inoltre, i computer devono soddisfare i requisiti software seguenti:
  
- È necessario che sia installato Microsoft .NET 4,5 Framework. [Scaricare .NET 4,5 Framework qui.](https://www.microsoft.com/download/details.aspx?id=30653)
    
- È necessaria la funzionalità esperienza desktop abilitata in Windows.
    
- È necessario che Microsoft Visual C++ 2013 (x64) sia installato. [Scaricare Visual C++ 2013 qui](https://www.microsoft.com/download/details.aspx?id=40784)
    
- Sarà necessario che Skype for Business Server 2015 sia stato distribuito correttamente.
    
## <a name="configuration-requirements"></a>Requisiti di configurazione
<a name="ConfigReqs"> </a>

Per eseguire correttamente lo strumento stress and performance, sono necessarie ulteriori configurazioni:
  
- È necessario eseguire l'accesso al server come membro del gruppo del dominio o dell'amministratore locale.
    
- Non è possibile installare lo strumento di creazione degli utenti di Skype for Business Server 2015 (UserProvisioningTool.exe) su un server front end server o Standard Edition in cui si trovano gli account utente.
    
- Quando lo strumento per la creazione dell'utente viene eseguito più volte, ogni utente abilitato per le comunicazioni unificate di Microsoft deve disporre di un numero di telefono univoco.
    
- Le dimensioni del file di paging devono essere gestite da sistemi oppure devono essere almeno 1,5 volte la quantità di RAM nel computer.
    
## <a name="installing-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Installazione dello strumento di sollecito e prestazioni di Skype for Business Server 2015
<a name="Installing"> </a>

L'installazione non può essere più semplice. È necessario eseguire il file di Windows Installer, **CapacityPlanningTool.msi**, in ogni computer client che si intende utilizzare per simulare il traffico degli utenti e in un front end server in ogni pool in cui verranno creati utenti e contatti.
  
Per scaricare il. msi, insieme agli script di esempio menzionati negli altri articoli, passare al collegamento Centro download: [Skype for Business Server 2015, strumento di stress e prestazioni](https://www.microsoft.com/download/details.aspx?id=50367).
  

