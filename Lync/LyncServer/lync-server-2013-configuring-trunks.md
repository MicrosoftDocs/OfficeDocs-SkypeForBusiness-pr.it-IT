---
title: 'Lync Server 2013: configurazione di trunk'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring trunks
ms:assetid: 0c339511-a185-484e-94f0-dbe918b7e48a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398170(v=OCS.15)
ms:contentKeyID: 48183389
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 123535ae3e14669e343c881869304e95ce666040
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "41996181"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-trunks-in-lync-server-2013"></a>Configurazione di trunk in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-11-01_

Nell'ambito della distribuzione di VoIP aziendale, è possibile configurare un trunk tra un Mediation Server e uno o più dei seguenti peer per fornire la connettività PSTN (Public Switched Telephone Network) per i client e i dispositivi Enterprise Voice nell'organizzazione:

  - Connessione con trunk SIP a un provider di servizi di telefonia Internet (ITSP)

  - Gateway PSTN

  - Centralino (PBX)

Per informazioni dettagliate, vedere [Planning for PSTN Connectivity in Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md) nella documentazione relativa alla pianificazione.

<div>


> [!IMPORTANT]  
> Prima di iniziare la configurazione del trunk, verificare che la topologia sia stata creata e che il Mediation Server e il relativo peer siano stati configurati e associati l'uno all'altro. Per informazioni dettagliate, vedere <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">define a gateway in Generatore di topologie in Lync Server 2013</A> nella documentazione relativa alla distribuzione.



</div>

<div>


> [!NOTE]  
> Come parte della configurazione trunk, è possibile abilitare la funzionalità di bypass multimediale di Lync Server 2013, che consente di bypassare il Mediation Server. I trunk possono essere configurati con o senza il bypass multimediale abilitato, ma è consigliabile abilitarlo. Per informazioni dettagliate, vedere <A href="lync-server-2013-planning-for-media-bypass.md">Planning for Media Bypass in Lync Server 2013</A> nella documentazione relativa alla pianificazione.



</div>

<div>

## <a name="in-this-section"></a>Argomenti della sezione

  - [Supporto per più trunk in Lync Server 2013](lync-server-2013-multiple-trunk-support.md)

  - [Routing tra trunk in Lync Server 2013](lync-server-2013-inter-trunk-routing.md)

  - [Visualizzare le informazioni di configurazione del trunk in Lync Server 2013](lync-server-2013-view-trunk-configuration-information.md)

  - [Configurare un trunk con bypass multimediale in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)

  - [Configurare un trunk senza bypass multimediale in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)

  - [Creare una nuova raccolta di impostazioni di configurazione trunk in Lync Server 2013](lync-server-2013-create-a-new-collection-of-trunk-configuration-settings.md)

  - [Eliminare una raccolta esistente di impostazioni di configurazione del trunk SIP in Lync Server 2013](lync-server-2013-delete-an-existing-collection-of-sip-trunk-configuration-settings.md)

  - [Modificare le impostazioni di configurazione del trunk SIP in Lync Server 2013](lync-server-2013-modify-sip-trunk-configuration-settings.md)

  - [Testare le impostazioni di configurazione del trunk SIP in Lync Server 2013](lync-server-2013-test-sip-trunk-configuration-settings.md)

  - [Visualizzare informazioni sui singoli trunk SIP in Lync Server 2013](lync-server-2013-view-information-about-individual-sip-trunks.md)

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Definire un gateway in Generatore di topologie in Lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md)  


[Pianificazione della connettività PSTN in Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md)  
[Pianificazione del bypass multimediale in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

