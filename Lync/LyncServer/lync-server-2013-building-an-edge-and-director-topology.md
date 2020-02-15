---
title: 'Lync Server 2013: creazione di una topologia Edge e Director'
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
ms.openlocfilehash: f5948793090c84a0f28094e4f6ed4e1b425d21fd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044758"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="building-an-edge-and-director-topology-in-lync-server-2013"></a>Creazione di una topologia Edge e Director in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-08_

La creazione della topologia prevede l'esecuzione delle attività di pianificazione e distribuzione seguenti:

  - **Pianificazione**   è necessario definire una topologia appropriata per l'organizzazione e identificare i componenti necessari per la distribuzione. Questi sono passaggi standard del processo di pianificazione. Microsoft Lync Server 2013, strumento di pianificazione fornito con Lync Server 2013, semplifica l'avvio del processo di pianificazione, nonché la possibilità di apportare facilmente modifiche man mano che i piani e i requisiti vengono finalizzati.

  - **Distribuzione**   la topologia definita tramite Generatore di topologie è essenziale per la distribuzione di qualsiasi server Lync Server 2013. Se non si termina la definizione e la pubblicazione della topologia tramite Generatore di topologie nell'ambito delle attività di pianificazione, è necessario completarla e pubblicare la topologia prima di distribuire i server perimetrali.

Non è possibile distribuire i componenti del server perimetrale finché non è stato distribuito almeno un pool interno ed è necessario installare il generatore di topologie per distribuire un pool interno. Questa sezione non riguarda l'installazione di generatore di topologie perché fa parte del processo di installazione per il pool interno.

Per informazioni dettagliate su questi strumenti, vedere [elenco di controllo di distribuzione per l'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-deployment-checklist-for-external-user-access.md).

<div>


> [!NOTE]  
> Se in precedenza è stato utilizzato il generatore di topologie per definire una topologia completa, inclusa la topologia perimetrale, è possibile ignorare la topologia <A href="lync-server-2013-define-your-edge-topology.md">perimetrale define in Lync server 2013</A> e <A href="lync-server-2013-publish-your-topology.md">pubblicare la topologia nelle attività di Lync Server 2013</A> in questa sezione, ma è necessario completare la <A href="lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md">topologia export your Lync Server 2013 e copiarla su supporto esterno per l'attività di installazione perimetrale</A> .



</div>

<div>

## <a name="in-this-section"></a>Argomenti della sezione

  - [Definire la topologia perimetrale in Lync Server 2013](lync-server-2013-define-your-edge-topology.md)

  - [Definire topologie Director opzionali nella topologia per Lync Server 2013](lync-server-2013-define-optional-director-topologies-in-your-topology.md)

  - [Pubblicare la topologia in Lync Server 2013](lync-server-2013-publish-your-topology.md)

  - [Esportare la topologia di Lync Server 2013 e copiarla su supporto esterno per l'installazione perimetrale](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

