---
title: 'Lync Server 2013: Requisiti per la pubblicazione di una topologia'
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
ms.openlocfilehash: 0f1422df35ebbe9f368dc8aa3d121caf740e7033
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723786"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="requirements-to-publish-a-topology-in-lync-server-2013"></a>Requisiti per la pubblicazione di una topologia Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-21_

Questo argomento descrive i requisiti di infrastruttura e software specifici per la pubblicazione di una topologia, sia tramite Generatore di topologia che con l'interfaccia della riga di comando di Lync Server 2013 Management Shell. Questi requisiti si aggiungono ai requisiti del sistema operativo, del software e delle autorizzazioni generali applicabili a tutti gli strumenti di amministrazione di Lync Server 2013. Verificare di soddisfare tutti i requisiti degli strumenti amministrativi prima di pubblicare una topologia.

  - È necessario eseguire Generatore di topologia in un computer associato allo stesso dominio o alla stessa foresta della distribuzione di Lync Server 2013 che si sta creando in modo che i passaggi di preparazione di Active Directory Domain Services siano già stati completati, consentendo di usare gli strumenti di amministrazione in tale computer per pubblicare correttamente la topologia.

  - I computer definiti nella topologia devono essere Uniti al dominio, ad eccezione di Edge Server e in Active Directory. Tuttavia, non è necessario che i computer siano online quando si pubblica la topologia.

  - La condivisione file per il pool deve essere creata e disponibile per gli utenti remoti.

  - Per pubblicare un pool Front-end Enterprise Edition, il server di back-end basato su SQL Server deve essere unito al dominio in cui si distribuiscono i server, online e configurati con le regole del firewall appropriate per renderlo disponibile per gli utenti remoti. Per informazioni dettagliate su come specificare le eccezioni del firewall, vedere [informazioni sui requisiti del firewall per SQL Server con Lync server 2013](lync-server-2013-understanding-firewall-requirements-for-sql-server.md). Per altri dettagli sulla configurazione di SQL Server, vedere [configurare SQL Server per Lync server 2013](lync-server-2013-configure-sql-server-for-lync-server.md).
    
    <div>
    

    > [!NOTE]  
    > Il server Standard Edition include un database collocato che accetterà la configurazione pubblicata. Prima di tutto, è necessario eseguire l'attività <STRONG>prepara prima configurazione server Standard Edition</STRONG> nella distribuzione guidata di Lync Server.

    
    </div>

<div>

## <a name="see-also"></a>Vedere anche


[Pubblicare la topologia in Lync Server 2013](lync-server-2013-publish-the-topology.md)  
[Delegare le autorizzazioni di installazione in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md)  


[Requisiti software degli strumenti di amministrazione in Lync Server 2013](lync-server-2013-administrative-tools-software-requirements.md)  
[Supporto del sistema operativo per server e strumenti in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md)  


[Autorizzazioni e diritti di amministratore necessari per l'installazione e l'amministrazione di Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

