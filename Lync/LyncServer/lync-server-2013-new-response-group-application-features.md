---
title: "Lync Server 2013: nuove funzionalità dell'applicazione Response Group"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New Response Group application features
ms:assetid: 569544b4-fa97-429b-97e6-568afab6c19b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398373(v=OCS.15)
ms:contentKeyID: 48184196
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f4ae3ad427164d8a948130e69fd54d1e6f8c37b9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536853"
---
# <a name="new-response-group-application-features-in-lync-server-2013"></a>Nuove funzionalità dell'applicazione Response Group in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-29_

Con l'applicazione Response Group, è possibile instradare e accodare le chiamate in arrivo per persone designate a svolgere compiti particolari come il servizio clienti, l'helpdesk interno o il supporto telefonico generico per un reparto.

Le seguenti funzionalità dell'applicazione Response Group sono nuove in Lync Server 2013:

  - **Ruolo Responsabile**
    
    Lync Server 2013 introduce un nuovo ruolo di Manager di Response Group. Sono disponibili due ruoli di gestione per i Response Group: il responsabile del gruppo di risposta e l'amministratore di Response Group. Mentre gli amministratori di Response Group possono ancora configurare qualsiasi elemento per qualsiasi Response Group, i manager possono configurare solo determinati elementi, solo per i gruppi di risposta di cui sono proprietari.
    
    Questo miglioramento del modello di amministrazione va a vantaggio della scalabilità dei Response Group, soprattutto negli scenari di distribuzioni di grandi dimensioni.

  - **Disponibilità elevata**
    
    Il supporto per la disponibilità elevata per l'applicazione Response Group, sotto forma di mirroring di SQL Server, è abilitato nell'ambito della configurazione complessiva e della distribuzione della disponibilità elevata per Lync Server 2013. Se la configurazione prevede la disponibilità elevata e si perde la connettività al server back-end primario, il funzionamento di Response Group non ne risente, grazie all'intervento del server back-end mirror.
    
    Il supporto per il mirroring di SQL Server per l'applicazione Response Group non può essere abilitato o configurato singolarmente all'esterno della configurazione complessiva di Lync Server 2013 a disponibilità elevata.

  - **Ripristino d'emergenza**
    
    Il supporto per il ripristino di emergenza per l'applicazione Response Group è abilitato nell'ambito della configurazione e della distribuzione dei pool Front End abbinati, che fanno parte della configurazione complessiva del ripristino di emergenza di Lync Server 2013. Inoltre, i cmdlet di importazione ed esportazione di Response Group supportano il processo di failover al pool di backup e il processo di failback al pool primario o a un nuovo pool. Se si verifica un'interruzione del pool primario, per i Response Group è possibile eseguire il failover al pool di backup e quindi, al termine dell'interruzione, il failback al pool primario o a un nuovo pool.

<div id="sectionSection0" class="section">

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Pianificazione dei Response Group in Lync Server 2013](lync-server-2013-planning-for-response-groups.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

