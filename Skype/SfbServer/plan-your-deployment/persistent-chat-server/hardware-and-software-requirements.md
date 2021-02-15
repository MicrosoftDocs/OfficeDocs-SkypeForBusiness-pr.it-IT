---
title: Requisiti hardware e software per il server Chat persistente in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/19/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 692b7d99-1bc9-4c99-a050-2bc2be8688b2
description: 'Riepilogo: leggere questo argomento per informazioni sui requisiti hardware e software per il server Chat persistente in Skype for Business Server 2015.'
ms.openlocfilehash: 32ba0d94679e6f326fa1821cbe3401d031854037
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834536"
---
# <a name="hardware-and-software-requirements-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Requisiti hardware e software per il server Chat persistente in Skype for Business Server 2015
 
**Riepilogo:** Leggere questo argomento per informazioni sui requisiti hardware e software per il server Chat persistente in Skype for Business Server 2015.
  
Il server Chat persistente può essere installato con Skype for Business Server 2015 Enterprise Edition o Standard Edition. I requisiti dipendono dall'edizione di Skype for Business Server 2015 installata e dai requisiti di prestazioni dell'azienda. Enterprise Edition può supportare fino a 80.000 utenti simultanei; Standard Edition può supportare fino a 20.000 utenti simultanei. Persistent Chat è costituito da un componente front-end e da un componente di database SQL back-end.
  
Prima di distribuire il server Chat persistente, è necessario verificare che siano soddisfatti i requisiti hardware e software seguenti:
  
- Hardware che soddisfa i requisiti minimi per supportare Skype for Business Server 2015, il server Chat persistente, i server di database e i file server. Per ulteriori informazioni, vedere [Requisiti server per Skype for Business Server 2015.](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
    
- Sistema operativo e software di database supportati.
    
    Per informazioni dettagliate sui sistemi operativi e sul software di database supportati e sui requisiti per gli aggiornamenti di Windows, vedere [Requisiti server per Skype for Business Server 2015.](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
    
- Skype for Business Server 2015 Front End Server. Il Front End Server è la base per il routing SIP (Session Initiation Protocol), che rende possibile la comunicazione tra i computer che eseguono il server Chat persistente e la funzionalità Chat persistente. 
    
- Software di Accodamento messaggi. Utilizzato dal server Chat persistente e dal servizio Conformità chat persistente, se distribuito.
    
Nelle sezioni seguenti vengono descritti i requisiti specifici per il server Chat persistente e il database in cui vengono archiviati i dati di Persistent Chat.

> [!NOTE] 
> La chat persistente è disponibile in Skype for Business Server 2015, ma non è più supportata in Skype for Business Server 2019. Le stesse funzionalità sono disponibili in Teams. Per altre informazioni, vedere [Introduzione all'aggiornamento di Microsoft Teams.](/microsoftteams/upgrade-start-here) Se è necessario usare Chat persistente, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità a Teams o continuare a usare Skype for Business Server 2015. 
  
## <a name="front-end-server-requirements"></a>Requisiti del Front End Server

I requisiti del Front End Server dipendono dalla distribuzione del server Chat persistente con Skype for Business Server 2015 Enterprise Edition o Standard Edition.
  
- Se si distribuisce il server Chat persistente con Skype for Business Server 2015 Enterprise Edition, è possibile distribuire il Front End Server del server Chat persistente in uno o più computer autonomi nel pool Enterprise Edition. Non è possibile collocare i Front End Server di Chat persistente nel Front End Server di Skype for Business Server 2015. 
    
    Un singolo Front End Server del server Chat persistente può supportare 20.000 utenti attivi. È possibile disporre di un pool di server Chat persistente con un massimo di 4 front-end attivi che supportano un totale di 80.000 utenti simultanei. 
    
- Se si distribuisce il server Chat persistente con Skype for Business Server 2015 Standard Edition, è possibile collocare Persistent Chat con il Front End Server. Questa distribuzione a server singolo può supportare fino a 20.000 utenti. 
    
## <a name="persistent-chat-server-database-requirements"></a>Requisiti del database del server Chat persistente

Il server Chat persistente richiede SQL Server software di database per archiviare la cronologia e il contenuto delle chat room, i dati di configurazione, i dati di provisioning degli utenti e altri metadati pertinenti. Facoltativamente, utilizza il database di conformità di Persistent Chat per archiviare i dati di conformità. I database di Persistent Chat possono essere collocati nello stesso SQL Server, o anche nella stessa istanza SQL, dei database back-end. 
  
- Se si installa il server Chat persistente con Skype for Business Server 2015 Enterprise Edition, per garantire prestazioni ottimali, è consigliabile installare l'archivio file di Persistent Chat.
    
- Se si installa il server Chat persistente con Skype for Business Server 2015 Standard Edition, è possibile distribuire il server back-end dell'archivio chat persistente nell'istanza locale di SQL Server Express.
    
- Il database di Persistent Chat (mgc) e il database di conformità (mgccomp) possono trovarsi nella stessa istanza di SQL Server o in server SQL diversi.
    
Per preparare una piattaforma server di database, assicurarsi che ogni computer soddisfi i requisiti hardware e quindi installare il software prerequisito. La piattaforma server per i server di database di Chat persistente richiede lo stesso hardware del server database back-end di Skype for Business Server 2015. Per informazioni dettagliate, [vedere Requisiti server per Skype for Business Server 2015.](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
Nel server di database verificare che sia installata una delle applicazioni software seguenti:

- Microsoft SQL Server 2017 con il Service Pack più recente.

- Microsoft SQL Server 2016 con Service Pack 1 ed è necessario eseguire l'aggiornamento cumulativo 7 o versioni successive di Skype for Business Server. È consigliabile eseguire SQL Server 2016 con il Service Pack più recente. Per informazioni dettagliate su come installare Microsoft SQL Server 2016, vedere [Install SQL Server 2016.](https://docs.microsoft.com/sql/database-engine/install-windows/install-sql-server?view=sql-server-2016)

- Microsoft SQL Server 2014 ed è necessario eseguire l'aggiornamento cumulativo 6 o versioni successive di Skype for Business Server. È consigliabile eseguire SQL Server 2014 con il Service Pack più recente. Per informazioni dettagliate su come installare Microsoft SQL Server 2014, vedere [Install SQL Server 2014](https://docs.microsoft.com/sql/database-engine/install-windows/install-sql-server?view=sql-server-2014).

- Microsoft SQL Server 2012 (edizione a 64 bit) ed è consigliabile eseguire il Service Pack più recente. Per informazioni dettagliate su come installare Microsoft SQL Server 2012, vedere [Install SQL Server 2012](https://go.microsoft.com/fwlink/p/?LinkID=248559).

## <a name="persistent-chat-server-certificate-requirements"></a>Requisiti dei certificati del server Chat persistente

Per informazioni dettagliate sull'acquisizione di certificati, la creazione del database SQL Server e la creazione di archivi file, vedere [Distribuire Skype for Business Server 2015.](../../deploy/deploy.md) 
  
## <a name="for-more-information"></a>Ulteriori informazioni

Per ulteriori informazioni sui requisiti hardware e software, vedere i seguenti argomenti:
  
- [Requisiti del server per Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
    
- [Requisiti ambientali per Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)
    

