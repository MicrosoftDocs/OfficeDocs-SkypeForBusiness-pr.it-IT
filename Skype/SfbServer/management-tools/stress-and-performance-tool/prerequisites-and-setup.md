---
title: Prerequisiti e configurazione per lo strumento di stress e prestazioni di Skype for busines
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Requisiti o prerequisiti per lo strumento di stress e prestazioni di Skype for Business Server 2015. Come installare o configurare lo strumento di stress e prestazioni.
ms.openlocfilehash: f52d92022e09314a8f9467cd939f67b2827cc153
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816175"
---
# <a name="prerequisites-and-setup-for-the-skype-for-busines-stress-and-performance-tool"></a>Prerequisiti e configurazione per lo strumento di stress e prestazioni di Skype for busines
 
Requisiti o prerequisiti per lo strumento di stress e prestazioni di Skype for Business Server 2015. Come installare o configurare lo strumento di stress e prestazioni.
  
Sono disponibili le sezioni seguenti di requisiti hardware, software e configurazione di sistema che è necessario tenere presenti prima di eseguire lo strumento di stress e prestazioni:
  
- [Requisiti hardware client](prerequisites-and-setup.md#ClientHardwareReqs)
    
- [Requisiti software client](prerequisites-and-setup.md#ClientSoftwareReqs)
    
- [Requisiti di configurazione](prerequisites-and-setup.md#ConfigReqs)
    
Inoltre, abbiamo una sezione di seguito per l' [installazione dello strumento di stress e prestazioni di Skype for Business Server 2015](prerequisites-and-setup.md#Installing)
  
## <a name="client-hardware-requirements"></a>Requisiti hardware client
<a name="ClientHardwareReqs"> </a>

Quando si utilizza lo strumento stress e prestazioni per la distribuzione di Skype for Business Server 2015, è necessario che questi requisiti hardware vengano soddisfatti per ogni utente di 4500 nel test:
  
- 1 scheda di rete Gigabit
    
- 8 GB DI RAM
    
- 2 CPU dual-core
    
## <a name="client-software-requirements"></a>Requisiti software client
<a name="ClientSoftwareReqs"> </a>

I sistemi operativi supportati per lo strumento stress e prestazioni sono i seguenti:
  
- Windows Server 2012
    
- Windows Server 2008 (64 bit)
    
Inoltre, i computer devono soddisfare i requisiti software seguenti:
  
- È necessario il Framework Microsoft .NET 4,5 installato. [Scaricare il Framework .NET 4,5 qui.](https://www.microsoft.com/en-us/download/details.aspx?id=30653)
    
- È necessaria la funzionalità esperienza desktop abilitata in Windows.
    
- È necessario installare Microsoft Visual C++ 2013 (x64). [Download di Visual C++ 2013 qui](https://www.microsoft.com/en-us/download/details.aspx?id=40784)
    
- Sarà necessario che Skype for Business Server 2015 sia stato distribuito correttamente.
    
## <a name="configuration-requirements"></a>Requisiti di configurazione
<a name="ConfigReqs"> </a>

Queste configurazioni aggiuntive saranno necessarie per eseguire correttamente lo strumento di stress e prestazioni:
  
- È necessario accedere al server come membro del gruppo Domain o Administrator locale.
    
- Non è possibile installare lo strumento di creazione degli utenti di Skype for Business Server 2015 (UserProvisioningTool. exe) in un server front-end o in un server Standard Edition in cui si trovano gli account utente.
    
- Quando lo strumento di creazione dell'utente viene eseguito più volte, ogni utente abilitato per le comunicazioni unificate Microsoft deve avere un numero di telefono univoco.
    
- Le dimensioni del file di pagina devono essere gestite da sistemi o in caso contrario deve essere almeno 1,5 volte la quantità di RAM nel sistema informatico.
    
## <a name="installing-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Installazione dello strumento di stress e prestazioni di Skype for Business Server 2015
<a name="Installing"> </a>

L'installazione non può essere più semplice. È necessario eseguire il file di Windows Installer, **CapacityPlanningTool. msi**, in ogni computer client che si vuole usare per simulare il traffico degli utenti e in un server front-end in ogni pool in cui verranno creati utenti e contatti.
  
Per scaricare il file con estensione msi, insieme agli script di esempio menzionati negli altri articoli, accedere al collegamento Download Center: [Skype for Business Server 2015, strumento di stress e prestazioni](https://www.microsoft.com/download/details.aspx?id=50367).
  

