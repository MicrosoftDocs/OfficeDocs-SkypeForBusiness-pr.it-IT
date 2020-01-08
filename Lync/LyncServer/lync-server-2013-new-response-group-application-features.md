---
title: "Lync Server 2013: Nuove funzionalità dell'applicazione Response Group"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: New Response Group application features
ms:assetid: 569544b4-fa97-429b-97e6-568afab6c19b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398373(v=OCS.15)
ms:contentKeyID: 48184196
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 33dd01cf7516f950e58dbc90ee09b06901bccf74
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978553"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-response-group-application-features-in-lync-server-2013"></a>Nuove funzionalità dell'applicazione Response Group in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-29_

Con l'applicazione Response Group è possibile instradare e accodare le chiamate in arrivo a persone designate per scopi speciali, come il servizio clienti, un help desk interno o il supporto telefonico generale per un reparto.

Le caratteristiche dell'applicazione di Response Group seguenti sono nuove in Lync Server 2013:

  - **Ruolo di Manager**
    
    Lync Server 2013 introduce un nuovo ruolo di Response Group Manager. Ora ci sono due ruoli di gestione per i gruppi di risposta: Response Group Manager e Response Group Administrator. Mentre gli amministratori di Response Group possono ancora configurare qualsiasi elemento per qualsiasi gruppo di risposte, i responsabili possono configurare solo determinati elementi, solo per i gruppi di risposta di cui sono proprietari.
    
    Questo miglioramento del modello di amministrazione beneficia della scalabilità dei gruppi di risposta, in particolare per gli scenari di distribuzione di grandi dimensioni.

  - **Disponibilità elevata**
    
    Il supporto per la disponibilità elevata per l'applicazione Response Group, sotto forma di mirroring di SQL Server, è abilitato come parte della configurazione e della distribuzione generali della disponibilità elevata per Lync Server 2013. Se si configura per l'elevata disponibilità e si perde la connettività al server back-end principale, la funzionalità Response Group non viene modificata sfruttando il server back-end con mirroring.
    
    Il supporto per il mirroring di SQL Server per l'applicazione Response Group non può essere abilitato o configurato individualmente all'esterno della configurazione di disponibilità elevata di Lync Server 2013.

  - **Ripristino d'emergenza**
    
    Il supporto per il ripristino di emergenza per l'applicazione Response Group viene abilitato come parte della configurazione e della distribuzione dei pool di front end associati, che fanno parte della configurazione complessiva di Disaster Recovery di Lync Server 2013. Inoltre, i cmdlet di importazione ed esportazione di Response Group supportano il processo di failover per il pool di backup e il processo di failback nel pool principale o in un nuovo pool. Se si verifica un'interruzione nel pool principale, è possibile che i gruppi di risposta non vengano eseguiti nel pool di backup e quindi non vengano riportati nel pool principale o in un nuovo pool al termine dell'interruzione.

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

