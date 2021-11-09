---
title: Gestione del ripristino di emergenza, della disponibilità elevata e del servizio di backup
ms.reviewer: ''
author: HowlinWolf-92
ms.author: v-mahoffman
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Informazioni sulle procedure per le operazioni di ripristino di emergenza e sulla manutenzione del servizio di backup, che sincronizza i dati in pool Front End abbinati.
ms.openlocfilehash: 6d3eb3356c48a99974390f43bc0114d7d6507353
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60849939"
---
# <a name="managing-skype-for-business-server-disaster-recovery-high-availability-and-backup-service"></a>Gestione Skype for Business Server ripristino di emergenza, disponibilità elevata e servizio di backup

In questa sezione sono contenute le procedure per le operazioni di ripristino di emergenza, nonché per la manutenzione del servizio di backup, che sincronizza i dati in pool Front End abbinati.

Le procedure di ripristino di emergenza, sia di failover che di failback, sono manuali. In caso di emergenza, è necessario che l'amministratore richiami manualmente le procedure di failover. La stessa procedura si applica al failback dopo che il pool è stato ripristinato.

Le procedure di ripristino di emergenza descritte in questa sezione presuppongono quanto segue:

  - Si dispone di una distribuzione con pool Front End abbinati, che si trovano in siti diversi, come descritto in [Plan for high availability and disaster recovery.](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) Il servizio di backup è stato eseguito nei pool abbinati per mantenerli sincronizzati.

  - Se l'archivio di gestione centrale è ospitato in uno dei due pool, viene installato ed eseguito in entrambi i pool associati, con uno di questi pool che ospita il master attivo e l'altro pool che ospita lo standby.

> [!IMPORTANT]
> Nelle procedure seguenti il parametro *PoolFQDN* si riferisce al nome di dominio completo (FQDN) del pool interessato dall'emergenza, non al pool da cui gli utenti interessati dal problema vengono reindirizzati. Per lo stesso gruppo di utenti interessati dal problema, si riferisce allo stesso pool nei cmdlet di failover e failback (il pool che ospitava gli utenti prima del failover).<BR><br>Si supponga ad esempio un caso in cui per tutti gli utenti ospitati in un pool P1 sia stato eseguito il failover nel pool di backup, P2. Se l'amministratore desidera spostare tutti gli utenti serviti da P2 in modo che siano serviti da P1, è necessario che esegua le procedure seguenti: 
> <OL>
> <LI>
> <P>Eseguire il failback di tutti gli utenti originariamente ospitati in P1 da P2 a P1 utilizzando il cmdlet di failback. In tal caso, *PoolFQDN* è il nome di dominio completo (FQDN) di P1.</P>
> <LI>
> <P>Eseguire il failover di tutti gli utenti originariamente ospitati in P2 a P1 utilizzando il cmdlet di failover. In tal caso, PoolFQDN è il nome di dominio completo (FQDN) di P2.</P>
> <LI>
> <P>Se successivamente l'amministratore desidera eseguire il failback degli utenti P2 a P2, PoolFQDN è il nome di dominio completo (FQDN) di P2.</P></LI></OL><br>Per preservare l'integrità del pool, è necessario eseguire la procedura 1 prima della procedura 2. Se si esegue la procedura 2 prima della procedura 1, il cmdlet della procedura 2 avrà esito negativo.


## <a name="see-also"></a>Vedere anche

[Pianificare la disponibilità elevata e il ripristino di emergenza](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) 
  
