---
title: 'Lync Server 2013: Distribuzione di Survivable Branch Appliance o Survivable Branch Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying a Survivable Branch Appliance or Server
ms:assetid: cb780c14-dc5f-41ba-8092-f20ae905bd16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398849(v=OCS.15)
ms:contentKeyID: 48185643
ms.date: 12/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c7cf894fe6650ff3c06eaaa37f6ba05d70f50eeb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980016"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-a-survivable-branch-appliance-or-server-with-lync-server-2013"></a>Distribuzione di Survivable Branch Appliance o Survivable Branch Server con Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-12-10_

Resiliente Enterprise Voice si riferisce alla resilienza del sito di succursale, ovvero la possibilità di specificare un servizio VoIP aziendale continuo per la succursale degli utenti del sito nel caso in cui il collegamento al sito centrale diventi non disponibile.

Per i siti di piccole e medie dimensioni (siti di succursale con utenti da 25 a 1.000), è consigliabile distribuire un Survivable Branch Appliance, che terminerà le chiamate PSTN (Public Switched Telephone Network) tramite il gateway PSTN incorporato o un trunk SIP a un telefono provider di servizi. Un Survivable Branch Appliance è un dispositivo di terze parti che include un server blade che gestisce il sistema operativo Windows Server 2008 R2, il registrar di Lync Server 2013, il software Mediation Server e un gateway PSTN, tutto in uno chassis di un singolo dispositivo.

Per i siti di succursale con 1.000 per gli utenti di 5.000 e nessuna WAN resiliente, è consigliabile un server di succursale superstite connesso a un gateway PSTN o a un trunk SIP a un provider di servizi telefonici. Un Survivable Branch Server è un computer basato su Windows Server in cui è installato il software registrar e Mediation Server.

<div>


> [!NOTE]  
> Per i siti di succursale con più di 5.000 utenti e amministratori di Lync Server dedicati, è consigliabile una distribuzione completa di Lync Server 2013, separata da quella del sito centrale.<BR>Per informazioni dettagliate sulla scelta della soluzione di resilienza ottimale per i siti delle succursali dell'organizzazione, inclusi prerequisiti e considerazioni sulla pianificazione, vedere requisiti di resilienza dei siti secondari <A href="lync-server-2013-branch-site-resiliency-requirements.md">per Lync Server 2013</A> nella documentazione relativa alla pianificazione.



</div>

<div>


> [!NOTE]  
> Gli utenti ospitati in un dispositivo Survivable Branch di Lync Server non riescono a creare nuove chat room o a visualizzare la scheda della sala per le camere esistenti.



</div>

<div>

## <a name="in-this-section"></a>Contenuto della sezione

  - [Distribuzione di Survivable Branch Appliance o Survivable Branch Server con Lync Server 2013 - Attività presso il sito centrale](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md)

  - [Distribuire un Survivable Branch Appliance o un Survivable Branch Server con Lync Server 2013 - Attività presso il sito di succursale](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)

  - [Configurazione degli utenti per la resilienza dei siti di succursale in Lync Server 2013](lync-server-2013-configuring-users-for-branch-site-resiliency.md)

  - [Ospitare utenti in Survivable Branch Appliance o Survivable Branch Server in Lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md)

  - [Appendici: Survivable Branch Appliance e Survivable Branch Server in Lync Server 2013](lync-server-2013-appendices-survivable-branch-appliances-and-servers.md)

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

