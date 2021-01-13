---
title: Pianificare la disponibilità elevata e il ripristino di emergenza per il server Chat persistente in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 5/17/2016
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d9aa622a-95a3-4d8e-8d49-cbfe183f25bf
description: 'Riepilogo: leggere questo argomento per informazioni su come pianificare la disponibilità elevata e il ripristino di emergenza per il server Chat persistente in Skype for Business Server 2015.'
ms.openlocfilehash: d29271b314981f3de0eb7bd0b963637c554fb26f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832356"
---
# <a name="plan-for-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Pianificare la disponibilità elevata e il ripristino di emergenza per il server Chat persistente in Skype for Business Server 2015
 
**Riepilogo:** Leggere questo argomento per informazioni su come pianificare la disponibilità elevata e il ripristino di emergenza per il server Chat persistente in Skype for Business Server 2015.
  
La disponibilità elevata e il ripristino di emergenza per il server Chat persistente richiedono ulteriori risorse oltre a ciò che in genere è necessario per l'operazione completa. 
  
> [!NOTE]
> L'utilizzo di gruppi di disponibilità AlwaysOn SQL non è supportato con i database del server Chat persistente. 

> [!NOTE] 
> La chat persistente è disponibile in Skype for Business Server 2015 ma non è più supportata in Skype for Business Server 2019. La stessa funzionalità è disponibile in teams. Per ulteriori informazioni, vedere [Guida introduttiva all'aggiornamento di Microsoft teams](/microsoftteams/upgrade-start-here). Se è necessario utilizzare la chat persistente, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità ai team oppure continuare a utilizzare Skype for Business Server 2015. 
  
## <a name="resource-requirements"></a>Requisiti in termini di risorse

Prima di configurare il server Chat persistente per la disponibilità elevata e il ripristino di emergenza, verificare di disporre delle risorse aggiuntive seguenti. 
  
- Un'istanza di database dedicata che si trova nello stesso data center fisico in cui si trova l'Home Front-end del servizio server Chat persistente. Questo database fungerà da mirror di SQL Server per il database di Persistent Chat principale. Facoltativamente, designare un ulteriore server SQL per fungere da controllo del mirroring se si desidera un failover automatizzato per il database mirror.
    
- Un'istanza di database dedicata nell'altro data center fisico. Questo database fungerà da database secondario di log shipping di SQL Server per il database nel data center principale.
    
- Un'istanza di database dedicata che funge da mirror di SQL Server per il database secondario. Facoltativamente, è possibile designare un ulteriore SQL Server per il server come testimone del mirroring. Entrambi devono trovarsi nello stesso data center fisico del database secondario.
    
- Se è abilitata la conformità del server Chat persistente, sono necessarie altre tre istanze di database dedicate. La distribuzione è identica a quella descritta in precedenza per il database di chat persistente. Anche se è possibile che il database di conformità condivida la stessa istanza di SQL Server del database di chat persistente, sono consigliate le istanze autonome per la disponibilità elevata e il ripristino di emergenza.
    
- È necessario creare una condivisione file e designarla per i log delle transazioni di log shipping di SQL Server. Tutti i server SQL in entrambi i data center che eseguono i database di Persistent Chat devono avere accesso in lettura/scrittura alla condivisione di file. Tale condivisione non è definita come parte di un ruolo FileStore.
    
- Una condivisione file nel server di database secondario che funge da cartella di destinazione per i registri delle transazioni di SQL Server che vengono copiati dalla condivisione file del server primario.
    
## <a name="disaster-recovery-and-high-availability-solutions"></a>Soluzioni per il ripristino di emergenza e la disponibilità elevata

Skype for Business Server supporta più modalità di disponibilità elevata per i server back-end, incluso il mirroring del database. Per ulteriori informazioni, vedere [pianificare la disponibilità elevata e il ripristino di emergenza in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md). 
  
La soluzione di ripristino di emergenza per il server Chat persistente descritta in questo argomento si basa su un pool di server Persistent Chat esteso. Non è previsto alcun requisito per una VLAN (Virtual Local Area Network) estesa. Se si estende un pool di server Chat persistente, è possibile configurare un pool nella topologia logicamente, ma i server del pool vengono fisicamente posizionati in due diversi Data Center. È possibile configurare il mirroring di SQL Server per il database nello stesso modo e distribuire il database e il mirror nello stesso data center. È necessario configurare un database di backup nel data center secondario (con un mirror facoltativo per garantire una disponibilità elevata durante il ripristino di emergenza). Si tratta del database di backup utilizzato per il failover durante il ripristino di emergenza. 
  
Per informazioni dettagliate su come configurare la disponibilità elevata e il ripristino di emergenza per il server Chat persistente, vedere [configurare la disponibilità elevata e il ripristino di emergenza per il server Chat persistente in Skype for Business server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md). 
  
Nelle figure seguenti viene mostrato il modo in cui il pool di server Chat persistente può essere configurato in due topologie di pool estese diverse:
  
- Pool di server Persistent Chat esteso quando i data center sono georilevati con un'elevata larghezza di banda e una bassa latenza.
    
- Pool di server Persistent Chat esteso quando i data center sono georilevati con una bassa larghezza di banda e un'elevata latenza.
    
Nella figura 1 viene illustrata una topologia del pool di server Chat persistente estesa in cui i Data Center sono geolocalizzati con larghezza di banda elevata o bassa latenza. Si presuppone quanto segue per le topologie logiche e fisiche:
  
- La topologia logica è costituita dai seguenti elementi:
    
  - Un pool di chat persistente tra i siti 1 e 2 che contengono i server da 1 a 8.
    
  - Un pool di server front-end, un database di chat persistente, un database con mirroring e, facoltativamente, un database di controllo (non illustrato nel diagramma) che risiede fisicamente nel sito 1. 
    
  - Un secondo pool Front End Server e un database di backup che risiede fisicamente nel sito 2.
    
- La topologia fisica è costituita dai siti 1 e 2, come indicato di seguito:
    
  - Un pool di chat persistente, contenente i server da 1 a 4, due attivi, due inattivi nel sito 1.
    
  - Un pool di chat persistente, contenente i server da 5 a 8, due attivi, due inattivi nel sito 2.
    
  - Un pool di server front-end, un database di chat persistente, un database con mirroring e, facoltativamente, un database di controllo (non illustrato nel diagramma) nel sito 1.
    
  - Un pool Front End Server e un database di backup, ovvero la destinazione del log shipping SQL, nel sito 2.
    
**Pool di server Persistent Chat esteso quando i Data Center sono geolocalizzati con larghezza di banda elevata o bassa latenza**

![Pool esteso di chat persistente con larghezza di banda elevata o bassa latenza](../../media/55cf3d4b-5f51-4d2f-84ca-b4a13dc5eba3.png)
  
Nella figura 2 viene illustrata una topologia del pool di server Chat persistente estesa in cui i Data Center sono geolocalizzati con una bassa larghezza di banda e una latenza
  
- La topologia logica è costituita dai seguenti elementi:
    
  - Un pool di chat persistente tra i siti 1 e 2 che contengono i server da 1 a 8.
    
  - Un pool di server front-end, un database di chat persistente, un database con mirroring e, facoltativamente, un database di controllo (non illustrato nel diagramma) che risiede fisicamente nel sito 1. 
    
  - Un secondo pool Front End Server e un database di backup che risiede fisicamente nel sito 2.
    
- La topologia fisica è costituita dai siti 1 e 2, come indicato di seguito:
    
  - Un pool di chat persistente, contenente i server da 1 a 4, tutti attivi nel sito 1.
    
  - Un pool di chat persistente, contenente i server da 5 a 8, tutti inattivi, nel sito 2.
    
  - Un pool di server front-end, un database di chat persistente, un database con mirroring e, facoltativamente, un database di controllo (non illustrato nel diagramma) nel sito 1.
    
  - Un pool Front End Server e un database di backup, ovvero la destinazione del log shipping SQL, nel sito 2.
    
**Pool di server Persistent Chat esteso quando i Data Center sono geolocalizzati con larghezza di banda bassa/alta latenza**

![Pool di stretching chat persistente con larghezza di banda bassa/alta latenza](../../media/40cbd902-57b8-4d57-a61c-cde4e0bd47f0.png)
  

