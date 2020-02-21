---
title: 'Lync Server 2013: configurare il controllo di ammissione di chiamata'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure call admission control
ms:assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398870(v=OCS.15)
ms:contentKeyID: 48185464
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e318ac448aa046f001022d40bc5680fd62d37378
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205132"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-call-admission-control-in-lync-server-2013"></a>Configurare il controllo di ammissione di chiamata in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-21_

Il servizio Controllo di ammissione di chiamata è una soluzione che determina se è possibile stabilire una sessione in tempo reale in base alla larghezza di banda disponibile per evitare di fornire una qualità audio/video scadente per gli utenti su reti congestionate. Questo servizio controlla il traffico in tempo reale solo per audio e video e non ha effetto sul traffico di dati. Controllo di ammissione di chiamata può instradare la chiamata attraverso un percorso Internet qualora la larghezza di banda del percorso WAN predefinito non sia sufficiente. Per informazioni dettagliate, vedere [Planning for Call Admission Control in Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md) nella documentazione relativa alla pianificazione.

In questa sezione è contenuto un set di procedure di esempio che illustrano in che modo distribuire e gestire Controllo di ammissione di chiamata nella rete.

<div>


> [!IMPORTANT]  
> Prima di distribuire il servizio di controllo di ammissione di chiamata, è necessario raccogliere tutte le informazioni necessarie per la topologia di rete aziendale, come descritto nell' <A href="lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md">esempio: Gathering your requirements for Call Admission Control in Lync Server 2013</A> nella documentazione relativa alla pianificazione. Verificare inoltre che i componenti CAC siano stati installati e attivati, come descritto in <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">definire e configurare un pool Front end o un server Standard Edition in Lync server 2013</A> nella documentazione relativa alla distribuzione.



</div>

<div>


> [!NOTE]  
> Tutti gli esempi di distribuzione e gestione di CAC in questa sezione vengono eseguiti utilizzando Lync Server Management Shell. In alternativa, è possibile utilizzare anche la sezione <STRONG>configurazione di rete</STRONG> del pannello di controllo di Lync Server per gestire il servizio di gestione dei comandi.



</div>

<div>

## <a name="in-this-section"></a>Argomenti della sezione

  - [Configurare le aree di rete per il servizio di controllo di ammissione in Lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md)

  - [Creare profili di criteri di larghezza di banda in Lync Server 2013](lync-server-2013-create-bandwidth-policy-profiles.md)

  - [Configurazione dei siti di rete per il servizio di controllo di ammissione in Lync Server 2013](lync-server-2013-configure-network-sites-for-cac.md)

  - [Associare subnet a siti di rete per il servizio di controllo di ammissione in Lync Server 2013](lync-server-2013-associate-subnets-with-network-sites-for-cac.md)

  - [Creare collegamenti area di rete in Lync Server 2013](lync-server-2013-create-network-region-links.md)

  - [Creare route tra aree di rete in Lync Server 2013](lync-server-2013;-create-network-interregion-routes.md)

  - [Creare criteri intersito di rete in Lync Server 2013](lync-server-2013-create-network-intersite-policies.md)

  - [Abilitare il controllo di ammissione di chiamata in Lync Server 2013](lync-server-2013-enable-call-admission-control.md)

  - [Elenco di controllo per la distribuzione dei controlli di ammissione di chiamata per Lync Server 2013](lync-server-2013-call-admission-control-deployment-checklist.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

