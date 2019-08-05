---
title: Gestire il ripristino di emergenza, la disponibilità elevata e il servizio di backup
ms.reviewer: ''
author: lanachin
ms.author: v-lanac
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Informazioni sulle procedure per le operazioni di ripristino di emergenza, nonché per la gestione del servizio di backup, che sincronizza i dati in pool Front-End associati.
ms.openlocfilehash: 9664a7d9d48ca084232e2a0473a15d29d970cea6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195532"
---
# <a name="managing-skype-for-business-server-disaster-recovery-high-availability-and-backup-service"></a>Gestire il ripristino di emergenza di Skype for Business Server, la disponibilità elevata e il servizio di backup

Questa sezione contiene le procedure per le operazioni di ripristino di emergenza, nonché per la gestione del servizio di backup, che sincronizza i dati in pool Front-End associati.

Le procedure di ripristino di emergenza, sia failover che failback, sono manuali. In caso di emergenza, l'amministratore deve richiamare manualmente le procedure di failover. Lo stesso vale per il failback dopo la riparazione del pool.

Le procedure di ripristino di emergenza in questa sezione presuppongono quanto segue:

  - Si dispone di una distribuzione con pool Front-End associati, che si trova in siti diversi, come descritto in [pianificare l'elevata disponibilità e il ripristino di emergenza](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md). Il servizio di backup è stato eseguito in questi pool associati per mantenerli sincronizzati.

  - Se l'archivio di gestione centrale è ospitato in un pool, viene installato ed eseguito in entrambi i pool associati, con uno di questi pool che ospitano l'Active master e l'altro pool che ospita la modalità standby.

> [!IMPORTANT]
> Nelle procedure seguenti il parametro *PoolFqdn* si riferisce al nome di dominio completo del pool interessato da Disaster, non al pool in cui vengono reindirizzati gli utenti interessati. Per lo stesso set di utenti interessati, si riferisce allo stesso pool sia in cmdlet di failover che di failback, ovvero il pool che ha prima ospitato gli utenti prima del failover.<BR><br>Ad esempio, supponiamo che un caso in cui tutti gli utenti ospitati in un pool P1 non siano stati rilevati nel pool di backup, P2. Se l'amministratore vuole trasferire tutti gli utenti attualmente serviti da P2 per essere serviti da P1, l'amministratore deve eseguire i passaggi seguenti: 
> <OL>
> <LI>
> <P>Non eseguire il backup di tutti gli utenti originariamente assegnati a P1 da P2 a P1 usando il cmdlet failback. In questo caso, *PoolFqdn* è il nome di dominio completo di P1.</P>
> <LI>
> <P>Non eseguire il failover di tutti gli utenti originariamente ospitati in P2 in P1 usando il cmdlet per l'uso del protocollo. In questo caso, PoolFQDN è il nome di dominio completo di P2's.</P>
> <LI>
> <P>Se l'amministratore vuole in seguito riuscire a restituire gli utenti P2 a P2, PoolFQDN è il nome di dominio completo di P2's.</P></LI></OL><br>Tieni presente che il passaggio 1 deve essere eseguito prima del passaggio 2 per mantenere l'integrità del pool. Se si prova il passaggio 2 prima del passaggio 1, il cmdlet Step 2 non riuscirà.


## <a name="see-also"></a>Vedere anche

[Pianificare l'elevata disponibilità e il ripristino di emergenza](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) 
  
