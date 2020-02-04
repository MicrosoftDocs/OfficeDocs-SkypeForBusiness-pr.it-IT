---
title: 'Lync Server 2013: configurare il controllo di ammissione alle chiamate'
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
ms.openlocfilehash: 62f6858aa84309a268e8fc55af6cc0a63e6010a1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757790"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-call-admission-control-in-lync-server-2013"></a>Configurare il controllo di ammissione di chiamata in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-21_

Il controllo di ammissione di chiamata (CAC) è una soluzione che determina se una sessione in tempo reale può essere stabilita in base alla larghezza di banda disponibile per evitare una scarsa qualità audio/video per gli utenti nelle reti congestionate. CAC controlla il traffico in tempo reale solo per l'audio e il video e non influisce sul traffico dei dati. CAC può instradare la chiamata tramite un percorso Internet quando il percorso WAN predefinito non ha la larghezza di banda necessaria. Per informazioni dettagliate, vedere [pianificazione del controllo dell'ammissione alle chiamate in Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md) nella documentazione relativa alla pianificazione.

Questa sezione contiene un set di procedure di esempio che illustrano come distribuire e gestire CAC nella rete.

<div>


> [!IMPORTANT]  
> Prima di distribuire CAC, è necessario raccogliere tutte le informazioni necessarie per la topologia di rete aziendale, come descritto in <A href="lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md">esempio: raccogliere i requisiti per il controllo di ammissione di chiamata in Lync Server 2013</A> nella documentazione relativa alla pianificazione. Verificare inoltre che i componenti CAC siano stati installati e attivati, come descritto in <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">definire e configurare un pool Front end o un server Standard Edition in Lync server 2013</A> nella documentazione relativa alla distribuzione.



</div>

<div>


> [!NOTE]  
> Tutti gli esempi di distribuzione e gestione di CAC in questa sezione vengono eseguiti tramite Lync Server Management Shell. In alternativa, è possibile usare anche la sezione <STRONG>configurazione di rete</STRONG> del pannello di controllo di Lync Server per gestire CAC.



</div>

<div>

## <a name="in-this-section"></a>Contenuto della sezione

  - [Configurare le aree di rete per CAC in Lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md)

  - [Creare profili dei criteri di larghezza di banda in Lync Server 2013](lync-server-2013-create-bandwidth-policy-profiles.md)

  - [Configurare i siti di rete per CAC in Lync Server 2013](lync-server-2013-configure-network-sites-for-cac.md)

  - [Associare subnet a siti di rete per CAC in Lync Server 2013](lync-server-2013-associate-subnets-with-network-sites-for-cac.md)

  - [Creare collegamenti all'area di rete in Lync Server 2013](lync-server-2013-create-network-region-links.md)

  - [Creare route interregion di rete in Lync Server 2013](lync-server-2013;-create-network-interregion-routes.md)

  - [Creare criteri di intersito di rete in Lync Server 2013](lync-server-2013-create-network-intersite-policies.md)

  - [Abilitare il controllo di ammissione alle chiamate in Lync Server 2013](lync-server-2013-enable-call-admission-control.md)

  - [Elenco di controllo della distribuzione dei controlli di ammissione delle chiamate per Lync Server 2013](lync-server-2013-call-admission-control-deployment-checklist.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

