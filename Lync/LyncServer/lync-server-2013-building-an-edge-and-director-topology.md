---
title: 'Lync Server 2013: Creazione di una topologia di server perimetrali e server Director'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Building an edge and Director topology
ms:assetid: 11e5759e-d69f-4c39-8994-f467c279c558
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398202(v=OCS.15)
ms:contentKeyID: 48183451
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9f8a86d4f80b7fb4fc9990911908ef0c8a317c98
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741786"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="building-an-edge-and-director-topology-in-lync-server-2013"></a>Creazione di una topologia di server perimetrali e server Director in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-08_

La compilazione della topologia prevede le attività di pianificazione e distribuzione seguenti:

  - **Pianificazione**   è necessario definire una topologia appropriata per l'organizzazione e identificare i componenti necessari per distribuirla. Questi sono i passaggi standard nel processo di pianificazione. Microsoft Lync Server 2013, strumento di pianificazione fornito con Lync Server 2013, semplifica l'avvio del processo di pianificazione, oltre a includere la possibilità di apportare facilmente modifiche in modo che i requisiti e i piani vengano finalizzati.

  - **Distribuzione**   la topologia definita tramite Generatore di topologia è essenziale per la distribuzione di qualsiasi server Lync Server 2013. Se non si termina la definizione e la pubblicazione della topologia con il generatore di topologie durante le attività di pianificazione, è necessario completarla e pubblicare la topologia prima di distribuire gli Edge Server.

Non è possibile distribuire componenti di Edge Server fino a quando non è stato distribuito almeno un pool interno ed è necessario installare Generatore di topologie per distribuire un pool interno. Questa sezione non include l'installazione di generatore di topologia perché fa parte del processo di installazione per il pool interno.

Per informazioni dettagliate su questi strumenti, vedere [elenco di controllo della distribuzione per l'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-deployment-checklist-for-external-user-access.md).

<div>


> [!NOTE]  
> Se in precedenza è stato usato generatore di topologie per definire una topologia completa, inclusa la topologia di Edge, è possibile ignorare la topologia <A href="lync-server-2013-define-your-edge-topology.md">Definisci il bordo in Lync server 2013</A> e <A href="lync-server-2013-publish-your-topology.md">pubblicare la topologia nelle attività di Lync Server 2013</A> in questa sezione, ma è necessario completare la <A href="lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md">topologia di Lync Server 2013 e copiarla in elementi multimediali esterni per l'</A> attività di installazione di Edge.



</div>

<div>

## <a name="in-this-section"></a>Contenuto della sezione

  - [Definire la topologia perimetrale in Lync Server 2013](lync-server-2013-define-your-edge-topology.md)

  - [Definire topologie con server Director facoltativi nella topologia per Lync Server 2013](lync-server-2013-define-optional-director-topologies-in-your-topology.md)

  - [Pubblicare la topologia in Lync Server 2013](lync-server-2013-publish-your-topology.md)

  - [Esportare la topologia di Lync Server 2013 e copiarla su supporto esterno per l'installazione perimetrale](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

