---
title: 'Lync Server 2013: distribuzione di un Survivable Branch Appliance o server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying a Survivable Branch Appliance or Server
ms:assetid: cb780c14-dc5f-41ba-8092-f20ae905bd16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398849(v=OCS.15)
ms:contentKeyID: 48185643
ms.date: 12/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 835a12cb49c8474389b8ae3cc26773fcea2e4157
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140139"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-a-survivable-branch-appliance-or-server-with-lync-server-2013"></a>Distribuzione di un Survivable Branch Appliance o server con Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-12-10_

Resiliente Enterprise Voice si riferisce alla resilienza dei siti di succursale, ovvero la possibilità di fornire un servizio di VoIP aziendale continuo per la succursale degli utenti del sito nel caso in cui il collegamento al sito centrale non diventi disponibile.

Per i siti di succursale di piccole e medie dimensioni (siti di succursale con utenti da 25 a 1.000), è consigliabile distribuire un Survivable Branch Appliance, che consente di terminare le chiamate PSTN (Public Switched Telephone Network) tramite il gateway PSTN incorporato o un trunk SIP a un telefono provider di servizi. Un Survivable Branch Appliance è un dispositivo di terze parti che include un server blade che esegue il sistema operativo Windows Server 2008 R2, il servizio di registrazione di Lync Server 2013, il software Mediation Server e un gateway PSTN, tutto in un singolo chassis di appliance.

Per i siti di succursale con 1.000 a 5.000 utenti e nessuna WAN resiliente, è consigliabile un Survivable Branch Server connesso a un gateway PSTN o a un trunk SIP a un provider di servizi di telefonia. Survivable Branch Server è un computer basato su Windows Server in cui è installato il software di registrazione e Mediation Server.

<div>


> [!NOTE]  
> Per i siti di succursale con più di 5.000 utenti e amministratori dedicati di Lync Server, è consigliabile disporre di una distribuzione completa di Lync Server 2013, separata da quella del sito centrale.<BR>Per informazioni dettagliate sulla scelta della soluzione di resilienza ottimale per i siti di succursale nell'organizzazione, inclusi i prerequisiti e le considerazioni relative alla pianificazione, vedere <A href="lync-server-2013-branch-site-resiliency-requirements.md">requisiti di resilienza dei siti di succursale per Lync Server 2013</A> nella documentazione relativa alla pianificazione.



</div>

<div>


> [!NOTE]  
> Gli utenti ospitati in un Survivable Branch Appliance di Lync Server non sono in grado di creare nuove chat room o di visualizzare la scheda sala per le sale esistenti.



</div>

<div>

## <a name="in-this-section"></a>Argomenti della sezione

  - [Distribuzione di un Survivable Branch Appliance o server con Lync Server 2013-attività del sito centrale](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md)

  - [Distribuire un Survivable Branch Appliance o server con Lync Server 2013-Branch site Task](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)

  - [Configurazione degli utenti per la resilienza dei siti di succursale in Lync Server 2013](lync-server-2013-configuring-users-for-branch-site-resiliency.md)

  - [Utenti domestici in un Survivable Branch Appliance o server in Lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md)

  - [Appendici: Survivable Branch Appliance e server in Lync Server 2013](lync-server-2013-appendices-survivable-branch-appliances-and-servers.md)

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Distribuzione di Lync Server 2013](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

