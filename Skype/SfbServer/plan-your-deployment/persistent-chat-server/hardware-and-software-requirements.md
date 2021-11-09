---
title: Requisiti hardware e software per il server Chat persistente in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 7/19/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 692b7d99-1bc9-4c99-a050-2bc2be8688b2
description: 'Riepilogo: leggere questo argomento per informazioni sui requisiti hardware e software per il server Chat persistente in Skype for Business Server 2015.'
ms.openlocfilehash: d911cdeb3aefddbf37d8857e86207fe84c4dce98
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60833290"
---
# <a name="hardware-and-software-requirements-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Requisiti hardware e software per il server Chat persistente in Skype for Business Server 2015
 
**Riepilogo:** Leggere questo argomento per informazioni sui requisiti hardware e software per il server Chat persistente in Skype for Business Server 2015.
  
Il server Chat persistente può essere installato con Skype for Business Server 2015 edizione Enterprise o edizione Standard. I requisiti dipendono dall'edizione Skype for Business Server 2015 installata e dai requisiti di prestazioni dell'azienda. edizione Enterprise può supportare fino a 80.000 utenti simultanei; edizione Standard può supportare fino a 20.000 utenti simultanei. Persistent Chat è costituito da un componente front-end e da un componente di database SQL back-end.
  
Prima di distribuire il server Chat persistente, è necessario verificare che siano soddisfatti i requisiti hardware e software seguenti:
  
- Hardware che soddisfa i requisiti minimi per supportare Skype for Business Server 2015, server Chat persistente, server di database e file server. Per ulteriori informazioni, vedere [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).
    
- Sistema operativo e software di database supportati.
    
    Per informazioni dettagliate sui sistemi operativi supportati e sul software di database e sui Windows di aggiornamento, vedere [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).
    
- Skype for Business Server 2015 Front End Server. Il Front End Server è la base per il routing SIP (Session Initiation Protocol), che rende possibile la comunicazione tra i computer che eseguono il server Chat persistente e la funzionalità Chat persistente. 
    
- Software di Accodamento messaggi. Utilizzato dal server Chat persistente e dal servizio Conformità chat persistente, se distribuito.
    
Nelle sezioni seguenti vengono descritti i requisiti specifici per il server Chat persistente e il database in cui sono archiviati i dati di Persistent Chat.

> [!NOTE] 
> La chat persistente è disponibile Skype for Business Server 2015, ma non è più supportata in Skype for Business Server 2019. La stessa funzionalità è disponibile in Teams. Per ulteriori informazioni, vedere [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here). Se è necessario utilizzare persistent chat, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità Teams o continuare a usare Skype for Business Server 2015. 
  
## <a name="front-end-server-requirements"></a>Requisiti del Front End Server

I requisiti del Front End Server dipendono dalla distribuzione del server Chat persistente con Skype for Business Server 2015 edizione Enterprise o edizione Standard.
  
- Se si distribuisce il server Chat persistente con Skype for Business Server 2015 edizione Enterprise, è possibile distribuire il Front End Server del server Chat persistente in uno o più computer autonomi nel pool di edizione Enterprise. Non è possibile collocare i Front End Server di Persistent Chat Skype for Business Server 2015 Front End Server. 
    
    Un singolo Front End Server del server Chat persistente può supportare 20.000 utenti attivi. È possibile disporre di un pool di server Chat persistente con un massimo di 4 front end attivi che supportano un totale di 80.000 utenti simultanei. 
    
- Se si distribuisce il server Chat persistente con Skype for Business Server 2015 edizione Standard, è possibile collocare Persistent Chat con il Front End Server. Questa distribuzione a server singolo può supportare fino a 20.000 utenti. 
    
## <a name="persistent-chat-server-database-requirements"></a>Requisiti del database del server Chat persistente

Il server Chat persistente richiede SQL Server software di database per archiviare la cronologia e il contenuto delle chat room, i dati di configurazione, i dati di provisioning degli utenti e altri metadati pertinenti. Facoltativamente, usa il database di conformità di Persistent Chat per archiviare i dati di conformità. I database di Persistent Chat possono essere collocati nello stesso SQL Server, o anche nella stessa istanza SQL, dei database back-end. 
  
- Se si installa il server Chat persistente con Skype for Business Server 2015 edizione Enterprise, per garantire prestazioni ottimali, è consigliabile installare l'archivio file di Persistent Chat.
    
- Se si installa il server Chat persistente con Skype for Business Server Edizione Standard 2015, è possibile distribuire il server back-end dell'archivio Chat persistente nell'istanza SQL Server Express locale.
    
- Il database di Persistent Chat (mgc) e il database di conformità (mgccomp) possono trovarsi nella stessa istanza di SQL Server o in server SQL diversi.
    
Per preparare una piattaforma server di database, assicurarsi che ogni computer soddisfi i requisiti hardware e quindi installare il software prerequisito. La piattaforma server per i server database di Persistent Chat richiede lo stesso hardware del server database back-end Skype for Business Server 2015. Per informazioni dettagliate, vedere [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).
  
Nel server di database verificare che sia installata una delle applicazioni software seguenti:

- Microsoft SQL Server 2017 con il Service Pack più recente.

- Microsoft SQL Server 2016 con Service Pack 1 ed è necessario eseguire con Skype for Business Server cumulativo 7 o versioni successive. È consigliabile eseguire SQL Server 2016 con il Service Pack più recente. Per informazioni dettagliate su come installare Microsoft SQL Server 2016, vedere [Install SQL Server 2016](/sql/database-engine/install-windows/install-sql-server?view=sql-server-2016).

- Microsoft SQL Server 2014 ed è necessario eseguire con Skype for Business Server cumulativo 6 o versioni successive. È consigliabile eseguire SQL Server 2014 con il Service Pack più recente. Per informazioni dettagliate su come installare Microsoft SQL Server 2014, vedere [Install SQL Server 2014](/sql/database-engine/install-windows/install-sql-server?view=sql-server-2014).

- Microsoft SQL Server 2012 (edizione a 64 bit) ed è consigliabile eseguire con il Service Pack più recente. Per informazioni dettagliate su come installare Microsoft SQL Server 2012, vedere [Install SQL Server 2012](/previous-versions/sql/sql-server-2012/bb500395(v=sql.110)).

## <a name="persistent-chat-server-certificate-requirements"></a>Requisiti dei certificati del server Chat persistente

Per informazioni dettagliate sull'acquisizione di certificati, sulla creazione del database SQL Server e sulla creazione di archivi file, vedere [Deploy Skype for Business Server 2015](../../deploy/deploy.md). 
  
## <a name="for-more-information"></a>Ulteriori informazioni

Per ulteriori informazioni sui requisiti hardware e software, vedere i seguenti argomenti:
  
- [Requisiti del server per Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
    
- [Requisiti ambientali per Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)
