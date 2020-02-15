---
title: 'Lync Server 2013: richiedere i certificati in anticipo (facoltativo)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Request certificates in advance (optional)
ms:assetid: 9d6d7de6-ff2a-46da-b1b7-a354c8e383e4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412733(v=OCS.15)
ms:contentKeyID: 48184915
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c2df4d328154133df91503877a22234e6a05aa3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046902"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="request-certificates-in-advance-optional-for-lync-server-2013"></a>Richiedere certificati in anticipo (facoltativo) per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-21_

I certificati sono necessari per tutti i server interni che eseguono Lync Server 2013, tra cui ogni server Enterprise Edition front-end, server Standard Edition, Director, server perimetrale e Mediation Server autonomo. Benché per i server interni sia consigliata un'autorità di certificazione (CA) globale (enterprise) interna, è inoltre possibile utilizzare una CA pubblica. Per informazioni dettagliate sui requisiti dei certificati e sull'utilizzo di una CA pubblica, vedere [Certificate Requirements for Internal Servers in Lync server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) nella documentazione relativa alla pianificazione.

Nel programma di installazione di Lync Server 2013 è inclusa la procedura guidata certificate, che facilita le attività relative alla richiesta, all'assegnazione e all'installazione dei certificati durante la distribuzione. Se si desidera richiedere certificati prima di installare i server (ad esempio, per risparmiare tempo durante la distribuzione effettiva dei server), è possibile farlo utilizzando un computer in cui sono installati gli strumenti di amministrazione di Lync Server 2013 o utilizzando una richiesta di certificato procedure definite nell'organizzazione, purché siano esportabili i certificati e che contengano tutti i nomi alternativi del soggetto richiesti. La richiesta di certificati in anticipo è facoltativa. Se non vengono richiesti in anticipo, è necessario richiederli come parte del programma di installazione di ogni server che richiede un certificato.

In questa documentazione relativa alla distribuzione vengono fornite le procedure per l'utilizzo della creazione guidata certificati per richiedere i certificati nell'ambito del processo di installazione, come descritto in [Configure Certificates for Servers in Lync server 2013](lync-server-2013-configure-certificates-for-servers.md), [Configure Certificates for the Director in Lync Server 2013](lync-server-2013-configure-certificates-for-the-director.md)e [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) sections of this Deployment documentation. Se si richiedono preventivamente i certificati, è necessario modificare le procedure di distribuzione dei certificati in queste sezioni, per importare e assegnare i certificati anziché richiederli al momento della distribuzione.

<div>


> [!NOTE]  
> Lync Server 2013 include il supporto per i certificati SHA-256 per le connessioni dai client che eseguono i sistemi&nbsp;operativi Windows Vista,&nbsp;Windows&nbsp;Server 2008, Windows Server 2008 R2 e Windows 7 e Lync Phone Edition. Per supportare l'accesso esterno mediante SHA-256, il certificato esterno viene rilasciato da una CA pubblica mediante SHA-256.



</div>

</div>

<span> </span>

</div>

</div>

</div>

