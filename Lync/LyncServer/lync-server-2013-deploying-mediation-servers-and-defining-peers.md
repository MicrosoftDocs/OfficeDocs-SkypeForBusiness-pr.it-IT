---
title: 'Lync Server 2013: distribuzione di Mediation Server e definizione di peer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Mediation Servers and defining peers
ms:assetid: a684f1da-6671-4011-adf6-2db49e2528e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412780(v=OCS.15)
ms:contentKeyID: 48185077
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16a5611e8137aba2f465c6488201ba1b2936dd76
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154038"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-mediation-servers-and-defining-peers-in-lync-server-2013"></a>Distribuzione di Mediation Server e definizione di peer in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-21_

Il carico di lavoro VoIP aziendale, le conferenze telefoniche con accesso esterno e le applicazioni vocali avanzate (applicazione Response Group, applicazione Parcheggio di chiamata, controllo di ammissione di chiamata e così via) sono disponibili nei pool Front end. Con Lync Server 2013, la funzionalità del Mediation Server è incorporata nel front end server. Non è più necessario un Mediation Server autonomo distinto. I pool Front end possono comunicare direttamente con i gateway supportati (un gateway PSTN (Public Switched Telephone Network) o un IP-PBX), eliminando la necessità che un Mediation Server funga da intermediario.

L'unica eccezione è rappresentata dalla configurazione di un trunk SIP per la connessione a un Session Border Controller per un provider di servizi di telefonia Internet (ITSP). Per connettere l'infrastruttura VoIP aziendale al provider trunk SIP, è necessario distribuire un Mediation Server separato.

La connessione tra Lync Server (il componente Mediation Server in un pool Front end o Mediation Server autonomo) e un gateway è definito come un'associazione logica denominata *trunk*. Negli argomenti di questa sezione viene illustrato come definire un trunk e come distribuire un Mediation Server autonomo se si effettua la connessione a un trunk SIP.

<div>

## <a name="in-this-section"></a>Argomenti della sezione

  - [Definire un Mediation Server in Generatore di topologie in Lync Server 2013](lync-server-2013-define-a-mediation-server-in-topology-builder.md)

  - [Definire un gateway in Generatore di topologie in Lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md)

  - [Installare i file per Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md)

  - [Definire ulteriori trunk in Generatore di topologie in Lync Server 2013](lync-server-2013-define-additional-trunks-in-topology-builder.md)

</div>

<div>

## <a name="related-sections"></a>Sezioni correlate

[Configurazione delle conferenze telefoniche con accesso esterno in Lync Server 2013](lync-server-2013-configuring-dial-in-conferencing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

