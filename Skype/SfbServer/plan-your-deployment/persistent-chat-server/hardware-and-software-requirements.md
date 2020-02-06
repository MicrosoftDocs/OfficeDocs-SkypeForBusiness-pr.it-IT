---
title: Requisiti hardware e software per il server Chat persistente
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
description: 'Riepilogo: leggere questo argomento per informazioni sui requisiti hardware e software per il server di chat persistente in Skype for Business Server 2015.'
ms.openlocfilehash: cba3b340710e4c5ed041c085f39f1a4cc209a789
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815754"
---
# <a name="hardware-and-software-requirements-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Requisiti hardware e software per il server Chat persistente
 
**Riepilogo:** Leggere questo argomento per informazioni sui requisiti hardware e software per il server di chat persistente in Skype for Business Server 2015.
  
Il server di chat persistente può essere installato con Skype for Business Server 2015 Enterprise Edition o Standard Edition. I requisiti dipendono dall'edizione di Skype for Business Server 2015 installata e dai requisiti di prestazioni della tua azienda. Enterprise Edition può supportare fino a 80.000 utenti simultanei; Standard Edition può supportare fino a 20.000 utenti simultanei. La chat persistente è costituita da un componente front-end e da un componente di database SQL back-end.
  
Prima di distribuire il server di chat persistente, è necessario assicurarsi che siano soddisfatti i requisiti hardware e software seguenti:
  
- Hardware che soddisfa i requisiti minimi per supportare Skype for Business Server 2015, il server di chat persistente, i server di database e i file server. Per altre informazioni, vedere [requisiti del server per Skype for Business server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).
    
- Sistema operativo e software di database supportati.
    
    Per informazioni dettagliate sui sistemi operativi e il software di database supportati e sui requisiti di Windows Update, vedere [requisiti del server per Skype for Business server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).
    
- Server front-end di Skype for Business Server 2015. Il server front-end è la base per il routing SIP (Session Initiation Protocol), che rende possibile la comunicazione tra i computer che eseguono il server di chat persistente e la funzionalità di chat persistente. 
    
- Software di Accodamento messaggi. Usato dal server di chat persistente e dal servizio di conformità della chat persistente, se distribuito.
    
Nelle sezioni seguenti vengono descritti i requisiti specifici per il server di chat persistente e il database in cui sono archiviati i dati della chat persistente.

> [!NOTE] 
> La chat persistente è disponibile in Skype for Business Server 2015 ma non è più supportata in Skype for Business Server 2019. La stessa funzionalità è disponibile in teams. Per altre informazioni, vedere [Introduzione all'aggiornamento di Microsoft teams](/microsoftteams/upgrade-start-here). Se è necessario usare la chat persistente, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità ai team o continuare a usare Skype for Business Server 2015. 
  
## <a name="front-end-server-requirements"></a>Requisiti del server front-end

I requisiti del server front-end variano a seconda che si stia distribuendo il server di chat persistente con Skype for Business Server 2015 Enterprise Edition o Standard Edition.
  
- Se si sta distribuendo il server di chat persistente con Skype for Business Server 2015 Enterprise Edition, è possibile distribuire il server front end del server di chat persistente in uno o più computer autonomi nel pool di Enterprise Edition. Non è possibile collocare i server front-end della chat persistente nel server front-end di Skype for Business Server 2015. 
    
    Un singolo server front-end di server di chat persistente può supportare utenti attivi di 20.000. È possibile avere un pool di server di chat persistente con un massimo di 4 front-end attivi in modo da supportare un totale di 80.000 utenti simultanei. 
    
- Se si sta distribuendo il server di chat persistente con Skype for Business Server 2015 Standard Edition, è possibile collocare la chat persistente con il server front-end. Questa distribuzione a server singolo può supportare fino a 20.000 utenti. 
    
## <a name="persistent-chat-server-database-requirements"></a>Requisiti del database del server Chat persistente

Persistent Chat Server richiede il software di database di SQL Server per archiviare la cronologia delle chat room e il contenuto, i dati di configurazione, i dati di provisioning degli utenti e altri metadati rilevanti. Facoltativamente, usa il database di conformità della chat persistente per archiviare i dati di conformità. I database di chat permanenti possono essere collocati nello stesso SQL Server o anche nella stessa istanza SQL, come database back-end. 
  
- Se si sta installando il server di chat persistente con Skype for Business Server 2015 Enterprise Edition, per garantire prestazioni ottimali, è consigliabile installare l'archivio di file della chat persistente.
    
- Se si sta installando il server di chat persistente con Skype for Business Server 2015 Standard Edition, è possibile distribuire il server back-end della chat persistente nell'istanza di SQL Server Express locale.
    
- Il database di chat persistente (MGC) e il database di conformità (mgccomp) possono trovarsi nella stessa istanza di SQL Server o in server SQL diversi.
    
Per preparare una piattaforma del server di database, assicurarsi che ogni computer soddisfi i requisiti hardware e quindi installare il software prerequisito. La piattaforma server per i server di database della chat persistente richiede lo stesso hardware del server di database back-end di Skype for Business Server 2015. Per informazioni dettagliate, vedere [requisiti del server per Skype for Business server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).
  
Nel server database verificare che sia installata una delle applicazioni software seguenti:

- Microsoft SQL Server 2017 con il Service Pack più recente.

- Microsoft SQL Server 2016 con Service Pack 1 ed è necessario eseguire l'aggiornamento cumulativo 7 o versioni successive di Skype for Business Server. È consigliabile eseguire SQL Server 2016 con il Service Pack più recente. Per informazioni dettagliate su come installare Microsoft SQL Server 2016, vedere [installare SQL server 2016](https://docs.microsoft.com/pt-pt/sql/database-engine/install-windows/install-sql-server?view=sql-server-2016).

- Microsoft SQL Server 2014 ed è necessario eseguire l'aggiornamento cumulativo 6 o versioni successive di Skype for Business Server. È consigliabile eseguire SQL Server 2014 con il Service Pack più recente. Per informazioni dettagliate su come installare Microsoft SQL Server 2014, vedere [installare SQL server 2014](https://docs.microsoft.com/pt-pt/sql/database-engine/install-windows/install-sql-server?view=sql-server-2014).

- Microsoft SQL Server 2012 (64 bit Edition) e si consiglia di eseguire con il Service Pack più recente. Per informazioni dettagliate su come installare Microsoft SQL Server 2012, vedere [installare SQL server 2012](https://go.microsoft.com/fwlink/p/?LinkID=248559).

## <a name="persistent-chat-server-certificate-requirements"></a>Requisiti del certificato del server di chat persistente

Per informazioni dettagliate sull'acquisizione di certificati, sulla creazione del database di SQL Server e sulla creazione di archivi di file, vedere [distribuire Skype for Business Server 2015](../../deploy/deploy.md). 
  
## <a name="for-more-information"></a>Per altre informazioni

Per altre informazioni sui requisiti hardware e software, vedere gli argomenti seguenti:
  
- [Requisiti server di Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
    
- [Requisiti ambientali di Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)
    

