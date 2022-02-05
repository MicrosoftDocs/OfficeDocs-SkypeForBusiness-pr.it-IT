---
title: Prerequisiti e configurazione per lo strumento Skype per Busines Stress and Performance Tool
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
ms.date: 12/20/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 948c176c-75ce-418d-891a-a68427d61e40
description: Requisiti o prerequisiti per lo strumento Skype for Business Server 2015 Stress and Performance Tool. Come installare o configurare lo strumento Stress and Performance.
---

# <a name="prerequisites-and-setup-for-the-skype-for-busines-stress-and-performance-tool"></a>Prerequisiti e configurazione per lo strumento Skype per Busines Stress and Performance Tool
 
Requisiti o prerequisiti per lo strumento Skype for Business Server 2015 Stress and Performance Tool. Come installare o configurare lo strumento Stress and Performance.
  
Sono disponibili le sezioni seguenti dei requisiti di configurazione hardware, software e di sistema di cui è necessario tenere conto prima di eseguire lo strumento Stress and Performance:
  
- [Requisiti hardware client](prerequisites-and-setup.md#ClientHardwareReqs)
    
- [Requisiti software client](prerequisites-and-setup.md#ClientSoftwareReqs)
    
- [Requisiti di configurazione](prerequisites-and-setup.md#ConfigReqs)
    
Inoltre, abbiamo anche una sezione di seguito per l'installazione dello strumento [Skype for Business Server 2015 Stress and Performance Tool](prerequisites-and-setup.md#Installing)
  
## <a name="client-hardware-requirements"></a>Requisiti hardware client
<a name="ClientHardwareReqs"> </a>

Quando si esegue lo Strumento stress e prestazioni nella distribuzione di Skype for Business Server 2015, è necessario soddisfare almeno questi requisiti hardware per ogni 4500 utenti nel test:
  
- Scheda di rete da 1 gigabit
    
- 8 GB di RAM
    
- 2 CPU dual-core
    
## <a name="client-software-requirements"></a>Requisiti software client
<a name="ClientSoftwareReqs"> </a>

I sistemi operativi supportati per lo strumento Stress and Performance Sono:
  
- Windows Server 2012
    
- Windows Server 2008 (64 bit)
    
Inoltre, i computer devono soddisfare i requisiti software seguenti:
  
- È necessario che sia installato Microsoft .NET 4.5 Framework. [Scarica .Net 4.5 Framework qui.](https://www.microsoft.com/download/details.aspx?id=30653)
    
- Sarà necessaria la funzionalità Esperienza desktop abilitata in Windows.
    
- È necessario installare Microsoft Visual C++ 2013 (x64). [Scaricare Visual C++ 2013 qui](https://www.microsoft.com/download/details.aspx?id=40784)
    
- You're going to need Skype for Business Server 2015 successfully deployed.
    
## <a name="configuration-requirements"></a>Requisiti di configurazione
<a name="ConfigReqs"> </a>

Per eseguire correttamente lo strumento Stress and Performance, sono necessarie queste configurazioni aggiuntive:
  
- È necessario accedere al server come membro del gruppo Domain o Local Administrator.You need to log into the server as a member of the Domain or Local Administrator's group.
    
- Non è possibile installare lo strumento Skype for Business Server 2015 User Creation (UserProvisioningTool.exe) in un Front End Server o in un server edizione Standard in cui risiederanno gli account utente.
    
- Quando lo strumento creazione utenti viene eseguito più volte, ogni utente abilitato per le comunicazioni unificate Microsoft deve disporre di un numero di telefono univoco.
    
- Le dimensioni del file di pagina devono essere gestite dal sistema o in caso contrario devono essere almeno 1,5 volte la quantità di RAM nel sistema computer.
    
## <a name="installing-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Installazione dello strumento Skype for Business Server 2015 Stress and Performance
<a name="Installing"> </a>

L'installazione non potrebbe essere più semplice. È necessario eseguire il file del programma di installazione **di Windows,CapacityPlanningTool.msi**, in ogni computer client che si utilizzerà per simulare il traffico degli utenti e in un Front End Server in ogni pool in cui verranno creati utenti e contatti.
  
Per scaricare il .msi, insieme agli script di esempio menzionati negli altri articoli, passare al collegamento Area download: [Skype for Business Server 2015, Strumento stress e prestazioni](https://www.microsoft.com/download/details.aspx?id=50367).
  

