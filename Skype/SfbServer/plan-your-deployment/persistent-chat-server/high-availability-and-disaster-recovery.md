---
title: Pianificare l'elevata disponibilità e il ripristino di emergenza per il server di chat persistente in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 5/17/2016
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d9aa622a-95a3-4d8e-8d49-cbfe183f25bf
description: "Riepilogo: leggere questo argomento per informazioni su come pianificare l'elevata disponibilità e il ripristino di emergenza per il server di chat persistente in Skype for Business Server 2015."
ms.openlocfilehash: 0cdd1d17680f0546a0081bb769e2c6f45a370d0c
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2019
ms.locfileid: "36195965"
---
# <a name="plan-for-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Pianificare l'elevata disponibilità e il ripristino di emergenza per il server di chat persistente in Skype for Business Server 2015
 
**Riepilogo:** Leggere questo argomento per informazioni su come pianificare l'elevata disponibilità e il ripristino di emergenza per il server di chat persistente in Skype for Business Server 2015.
  
La disponibilità elevata e il ripristino di emergenza per il server di chat persistente richiedono risorse aggiuntive oltre a quelle in genere necessarie per l'operazione completa. 
  
> [!NOTE]
> L'uso di gruppi di disponibilità di SQL AlwaysOn non è supportato con i database del server di chat permanenti. 

> [!NOTE] 
> La chat persistente è disponibile in Skype for Business Server 2015 ma non è più supportata in Skype for Business Server 2019. La stessa funzionalità è disponibile in teams. Per altre informazioni, vedere [Introduzione all'aggiornamento di Microsoft teams](/microsoftteams/upgrade-start-here). Se è necessario usare la chat persistente, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità ai team o continuare a usare Skype for Business Server 2015. 
  
## <a name="resource-requirements"></a>Requisiti per le risorse

Prima di configurare il server di chat persistente per l'elevata disponibilità e il ripristino di emergenza, verificare di avere le risorse aggiuntive seguenti. 
  
- Un'istanza di database dedicata situata nello stesso centro dati fisico in cui si trova la parte anteriore iniziale del servizio server di chat persistente. Questo database fungerà da mirror di SQL Server per il database principale della chat persistente. Facoltativamente, è possibile designare un altro server SQL per fungere da Witness per il mirroring se si vuole un failover automatizzato nel database mirror.
    
- Un'istanza di database dedicata situata nell'altro centro dati fisico. Questo database fungerà da database secondario di SQL Server log shipping per il database nel centro dati principale.
    
- Un'istanza del database dedicata che funge da mirror di SQL Server per il database secondario. Facoltativamente, è possibile designare un altro server SQL in server come witness di mirroring. Entrambi devono essere situati nello stesso centro dati fisico del database secondario.
    
- Se è abilitata la conformità del server di chat persistente, sono necessarie altre tre istanze di database dedicate. La distribuzione è uguale a quelle descritte in precedenza per il database della chat persistente. Anche se è possibile che il database di conformità condivida la stessa istanza di SQL Server del database di chat persistente, sono consigliate istanze autonome per l'elevata disponibilità e il ripristino di emergenza.
    
- Una condivisione file deve essere creata e designata per i registri delle transazioni di log di SQL Server. Tutti i server SQL in entrambi i centri dati che eseguono database di chat permanenti devono avere accesso in lettura/scrittura alla condivisione file. Questa condivisione non è definita come parte di un ruolo di filestore.
    
- Una condivisione file nel server di database secondario per fungere da cartella di destinazione per i registri delle transazioni di SQL Server copiati dalla condivisione file del server principale.
    
## <a name="disaster-recovery-and-high-availability-solutions"></a>Soluzioni per il ripristino di emergenza e la disponibilità elevata

Skype for Business Server supporta più modalità di elevata disponibilità per i server back-end, incluso il mirroring del database. Per altre informazioni, vedere [pianificare l'elevata disponibilità e il ripristino di emergenza in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md). 
  
La soluzione di ripristino di emergenza per il server di chat persistente descritta in questo argomento è basata su un pool di server di chat persistente allungato. Non sono previsti requisiti per una rete locale virtuale allungata (VLAN). Se si estende un pool di server di chat persistente, si configura un pool nella topologia in modo logico, ma si posiziona fisicamente i server nel pool in due centri dati diversi. È possibile configurare il mirroring di SQL Server per il database nello stesso modo e distribuire il database e lo specchio nello stesso centro dati. È necessario configurare un database di backup nel centro dati secondario (con uno specchio facoltativo per ottenere una disponibilità elevata durante il ripristino di emergenza). Questo è il database di backup usato per il failover durante il ripristino di emergenza. 
  
Per informazioni dettagliate su come configurare la disponibilità elevata e il ripristino di emergenza per il server di chat persistente, vedere [configurare la disponibilità elevata e il ripristino di emergenza per il server di chat persistente in Skype for Business server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md). 
  
Le figure seguenti mostrano il modo in cui il pool di server di chat persistente può essere configurato in due topologie di pool estese diverse:
  
- Pool di server di chat persistente allungato quando i Data Center sono ubicati geograficamente con larghezza di banda elevata/bassa latenza.
    
- Pool di server di chat persistente allungato quando i Data Center sono ubicati geograficamente con larghezza di banda ridotta/alta latenza.
    
La figura 1 Mostra una topologia di pool di server di chat persistente allungata in cui i centri dati sono ubicati geograficamente con larghezza di banda elevata/bassa Si presuppone quanto segue per le topologie logiche e fisiche:
  
- La topologia logica è costituita dagli elementi seguenti:
    
  - Un pool di chat persistente tra i siti 1 e 2 che contengono i server da 1 a 8.
    
  - Un pool di server front-end, un database di chat persistente, un database con mirroring e, facoltativamente, un database di Witness (non illustrato nel diagramma) che risiede fisicamente nel sito 1. 
    
  - Un secondo pool di server front-end e un database di backup che risiede fisicamente nel sito 2.
    
- La topologia fisica è costituita dai siti 1 e 2 come indicato di seguito:
    
  - Un pool di chat persistente, contenente i server da 1 a 4, due attivi, due inattivi nel sito 1.
    
  - Un pool di chat persistente, contenente i server da 5 a 8, due attivi, due inattivi nel sito 2.
    
  - Un pool di server front-end, un database di chat persistente, un database con mirroring e, facoltativamente, un database di Witness (non illustrato nel diagramma) nel sito 1.
    
  - Un pool di server front-end e un database di backup, ovvero la destinazione di distribuzione del log SQL, nel sito 2.
    
**Pool di server di chat persistente allungato quando i Data Center si trovano in posizione geo con larghezza di banda elevata/bassa latenza**

![Chat persistente allungato il pool con larghezza di banda elevata/bassa latenza](../../media/55cf3d4b-5f51-4d2f-84ca-b4a13dc5eba3.png)
  
La figura 2 Mostra una topologia di pool di server di chat persistente allungata in cui i centri dati sono ubicati geograficamente con larghezza di banda ridotta o elevata
  
- La topologia logica è costituita dagli elementi seguenti:
    
  - Un pool di chat persistente tra i siti 1 e 2 che contengono i server da 1 a 8.
    
  - Un pool di server front-end, un database di chat persistente, un database con mirroring e, facoltativamente, un database di Witness (non illustrato nel diagramma) che risiede fisicamente nel sito 1. 
    
  - Un secondo pool di server front-end e un database di backup che risiede fisicamente nel sito 2.
    
- La topologia fisica è costituita dai siti 1 e 2 come indicato di seguito:
    
  - Un pool di chat persistente, contenente i server da 1 a 4, tutti attivi nel sito 1.
    
  - Un pool di chat persistente, contenente i server da 5 a 8, tutti inattivi, nel sito 2.
    
  - Un pool di server front-end, un database di chat persistente, un database con mirroring e, facoltativamente, un database di Witness (non illustrato nel diagramma) nel sito 1.
    
  - Un pool di server front-end e un database di backup, ovvero la destinazione di distribuzione del log SQL, nel sito 2.
    
**Pool di server di chat persistente allungato quando i Data Center sono ubicati in posizione geografica con larghezza di banda ridotta o elevata**

![Chat persistente allungato il pool con larghezza di banda bassa/alta latenza](../../media/40cbd902-57b8-4d57-a61c-cde4e0bd47f0.png)
  

