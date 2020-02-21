---
title: Requisiti hardware e software per il server Chat persistente in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: 39204b675feff78fef56ee02e1c7e381eb36f65f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213232"
---
# <a name="hardware-and-software-requirements-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Requisiti hardware e software per il server Chat persistente in Skype for Business Server 2015
 
**Riepilogo:** Leggere questo argomento per informazioni sui requisiti hardware e software per il server Chat persistente in Skype for Business Server 2015.
  
Il server Chat persistente può essere installato con Skype for Business Server 2015 Enterprise Edition o Standard Edition. I requisiti dipendono dall'edizione di Skype for Business Server 2015 installata e dai requisiti prestazionali dell'azienda. Enterprise Edition è in grado di supportare fino a 80.000 utenti simultanei; Standard Edition è in grado di supportare fino a 20.000 utenti simultanei. Persistent Chat è costituito da un componente front-end e da un componente di database SQL back-end.
  
Prima di distribuire il server Chat persistente, è necessario verificare che vengano soddisfatti i requisiti hardware e software seguenti:
  
- Hardware che soddisfi i requisiti minimi per il supporto di Skype for Business Server 2015, del server Chat persistente, dei server di database e dei file server. Per ulteriori informazioni, vedere [requisiti del server per Skype for Business server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).
    
- Sistema operativo supportato e software di database.
    
    Per informazioni dettagliate sui sistemi operativi e il software di database supportati e sui requisiti di Windows Update, vedere [requisiti del server per Skype for Business server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).
    
- Skype for Business Server 2015 front end server. Il front end server è la base per il routing SIP (Session Initiation Protocol), che rende possibile la comunicazione tra i computer che eseguono il server Chat persistente e la funzionalità Persistent Chat. 
    
- Software di Accodamento messaggi. Utilizzato dal server Chat persistente e dal servizio di conformità di Persistent Chat, se distribuito.
    
Nelle sezioni seguenti vengono descritti i requisiti specifici per il server Chat persistente e il database in cui sono archiviati i dati della chat persistente.

> [!NOTE] 
> La chat persistente è disponibile in Skype for Business Server 2015 ma non è più supportata in Skype for Business Server 2019. La stessa funzionalità è disponibile in teams. Per ulteriori informazioni, vedere [Guida introduttiva all'aggiornamento di Microsoft teams](/microsoftteams/upgrade-start-here). Se è necessario utilizzare la chat persistente, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità ai team oppure continuare a utilizzare Skype for Business Server 2015. 
  
## <a name="front-end-server-requirements"></a>Requisiti del server front end

I requisiti dei Front End Server dipendono dal fatto che si stia distribuendo il server Chat persistente con Skype for Business Server 2015 Enterprise Edition o Standard Edition.
  
- Se si sta distribuendo il server Chat persistente con Skype for Business Server 2015 Enterprise Edition, è possibile distribuire il server front-end di Persistent Chat Server in uno o più computer autonomi nel pool Enterprise Edition. Non è possibile collocare i front end server di chat persistente sul server front end di Skype for Business Server 2015. 
    
    Un singolo server front end del server di chat persistente può supportare 20.000 utenti attivi. È possibile disporre di un pool di server Chat persistente con un massimo di 4 front-end attivi in grado di supportare complessivamente 80.000 utenti simultanei. 
    
- Se si sta distribuendo il server Chat persistente con Skype for Business Server 2015 Standard Edition, è possibile collocare la chat persistente con il front end server. Questa distribuzione a server singolo può supportare fino a 20.000 utenti. 
    
## <a name="persistent-chat-server-database-requirements"></a>Requisiti del database del server Chat persistente

Il server Chat persistente richiede il software di database di SQL Server per archiviare la cronologia e il contenuto delle chat room, i dati di configurazione, i dati di provisioning degli utenti e altri metadati rilevanti. Facoltativamente, utilizza il database di conformità di Persistent Chat per archiviare i dati di conformità. I database di chat persistente possono essere collocati nello stesso server SQL o persino nella stessa istanza di SQL, come i database back-end. 
  
- Se si sta installando il server Chat persistente con Skype for Business Server 2015 Enterprise Edition, per garantire prestazioni ottimali, è consigliabile installare l'archivio file di Persistent Chat.
    
- Se si sta installando il server Chat persistente con Skype for Business Server 2015 Standard Edition, è possibile distribuire il server back-end di archiviazione di chat persistente nell'istanza locale di SQL Server Express.
    
- Il database di Persistent Chat (MGC) e il database di conformità (mgccomp) possono trovarsi nella stessa istanza di SQL Server o in SQL Server diversi.
    
Per preparare una piattaforma del server di database, accertarsi che ogni computer soddisfi i requisiti hardware e quindi installare il software prerequisito. La piattaforma server per i server di database di chat persistente richiede lo stesso hardware del server database back-end di Skype for Business Server 2015. Per ulteriori informazioni, vedere [requisiti del server per Skype for Business server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).
  
Nel server di database, assicurarsi che sia installata una delle applicazioni software seguenti:

- Microsoft SQL Server 2017 con il Service Pack più recente.

- Microsoft SQL Server 2016 con Service Pack 1 ed è necessario eseguire con l'aggiornamento cumulativo 7 o versioni successive di Skype for Business Server. È consigliabile eseguire SQL Server 2016 con il Service Pack più recente. Per informazioni dettagliate sull'installazione di Microsoft SQL Server 2016, vedere [Install SQL server 2016](https://docs.microsoft.com/sql/database-engine/install-windows/install-sql-server?view=sql-server-2016).

- Microsoft SQL Server 2014 ed è necessario eseguire con l'aggiornamento cumulativo 6 o versioni successive di Skype for Business Server. È consigliabile eseguire SQL Server 2014 con il Service Pack più recente. Per informazioni dettagliate sull'installazione di Microsoft SQL Server 2014, vedere [Install SQL server 2014](https://docs.microsoft.com/sql/database-engine/install-windows/install-sql-server?view=sql-server-2014).

- Microsoft SQL Server 2012 (versione 64 bit) e si consiglia di eseguire il Service Pack più recente. Per informazioni dettagliate sull'installazione di Microsoft SQL Server 2012, vedere [Install SQL server 2012](https://go.microsoft.com/fwlink/p/?LinkID=248559).

## <a name="persistent-chat-server-certificate-requirements"></a>Requisiti dei certificati del server Chat persistente

Per informazioni dettagliate sull'acquisizione dei certificati, la creazione del database di SQL Server e la creazione di archivi di file, vedere [deploy Skype for Business Server 2015](../../deploy/deploy.md). 
  
## <a name="for-more-information"></a>Ulteriori informazioni

Per ulteriori informazioni sui requisiti hardware e software, vedere i seguenti argomenti:
  
- [Requisiti del server per Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
    
- [Requisiti ambientali per Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)
    

