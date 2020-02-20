---
title: 'Lync Server 2013: requisiti per la pubblicazione di una topologia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Requirements to publish a topology
ms:assetid: 841cdf5d-d884-414d-ab50-3bb681b622ed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195733(v=OCS.15)
ms:contentKeyID: 48184688
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5dac78de6d6cf0f86f0411b8085e6f8172b0f2f9
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144873"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="requirements-to-publish-a-topology-in-lync-server-2013"></a>Requisiti per la pubblicazione di una topologia in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-21_

In questo argomento vengono descritti i requisiti dell'infrastruttura e del software specifici per la pubblicazione di una topologia, se si utilizza il generatore di topologie o l'interfaccia della riga di comando di Lync Server 2013 Management Shell. Questi requisiti si aggiungono ai requisiti del sistema operativo, del software e delle autorizzazioni generali applicabili a tutti gli strumenti di amministrazione di Lync Server 2013. Assicurarsi di soddisfare tutti i requisiti degli strumenti di amministrazione prima di pubblicare una topologia.

  - È necessario eseguire Generatore di topologie in un computer aggiunto allo stesso dominio o foresta della distribuzione di Lync Server 2013 che si sta creando, in modo che i passaggi di preparazione di servizi di dominio Active Directory siano già stati completati, consentendo di utilizzare gli strumenti di amministrazione in tale computer per pubblicare correttamente la topologia.

  - I computer definiti nella topologia devono appartenere al dominio, ad eccezione dei server perimetrali, nonché essere in Servizi di dominio Active Directory. Non è tuttavia necessario che i computer siano online quando si pubblica la topologia.

  - La condivisione file per il pool deve essere creata ed essere disponibile per gli utenti remoti.

  - Per pubblicare un pool Enterprise Edition front end, il server back-end basato su SQL Server deve essere aggiunto al dominio in cui si distribuiscono i server, online e configurati con le regole del firewall appropriate per renderlo disponibile per gli utenti remoti. Per informazioni dettagliate su come specificare le eccezioni del firewall, vedere [Understanding firewall requirements for SQL Server with Lync server 2013](lync-server-2013-understanding-firewall-requirements-for-sql-server.md). Per ulteriori informazioni sulla configurazione di SQL Server, vedere [Configure SQL Server for Lync server 2013](lync-server-2013-configure-sql-server-for-lync-server.md).
    
    <div>
    

    > [!NOTE]  
    > Il server Standard Edition dispone di un database collocato che accetterà la configurazione pubblicata. È innanzitutto necessario eseguire l'attività <STRONG>preparazione del primo server Standard Edition</STRONG> nella distribuzione guidata di Lync Server.

    
    </div>

<div>

## <a name="see-also"></a>Vedere anche


[Pubblicare la topologia in Lync Server 2013](lync-server-2013-publish-the-topology.md)  
[Delegare le autorizzazioni di installazione in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md)  


[Requisiti software per gli strumenti di amministrazione in Lync Server 2013](lync-server-2013-administrative-tools-software-requirements.md)  
[Supporto del sistema operativo per server e strumenti in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md)  


[Autorizzazioni e diritti di amministratore necessari per l'installazione e l'amministrazione di Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

