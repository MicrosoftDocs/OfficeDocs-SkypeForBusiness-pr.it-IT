---
title: 'Lync Server 2013: Distribuzione di Mediation Server e definizione di peer'
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
ms.openlocfilehash: b20f5e733dddd34971ca3a5070e99364785e147a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757640"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-mediation-servers-and-defining-peers-in-lync-server-2013"></a>Distribuzione di Mediation Server e definizione di peer in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-21_

Il carico di lavoro VoIP aziendale, i servizi di conferenza telefonica con accesso esterno e le applicazioni vocali avanzate di Enterprise (Response Group Application, Call Park application, Call ammissioni Control (CAC) e così via) sono disponibili nei pool Front-end. Con Lync Server 2013, la funzionalità di Mediation Server è integrata nel server front-end. Un Mediation Server autonomo separato non è più necessario. I pool Front-end possono comunicare direttamente con i gateway supportati (un gateway PSTN (Public Switched Telephone Network) o un IP-PBX), eliminando la necessità di un Mediation Server di fungere da intermediario.

L'unica eccezione è la configurazione di un trunk SIP per la connessione a un controller di bordo della sessione per un provider di servizi di telefonia Internet. Per connettere l'infrastruttura VoIP aziendale al provider trunk SIP, è necessario distribuire un server di mediazione separato.

La connessione tra Lync Server (il componente Mediation Server in un pool Front-end o un Mediation Server autonomo) e un gateway viene definita come associazione logica denominata *trunk*. Gli argomenti di questa sezione descrivono come definire un trunk e come distribuire un Mediation Server autonomo, se ci si connette a un trunk SIP.

<div>

## <a name="in-this-section"></a>Contenuto della sezione

  - [Definire un Mediation Server in Generatore di topologia in Lync Server 2013](lync-server-2013-define-a-mediation-server-in-topology-builder.md)

  - [Definire un gateway in Generatore di topologia in Lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md)

  - [Installare i file per Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md)

  - [Definire trunk aggiuntivi in Generatore di topologia in Lync Server 2013](lync-server-2013-define-additional-trunks-in-topology-builder.md)

</div>

<div>

## <a name="related-sections"></a>Sezioni correlate

[Configurazione di conferenze telefoniche con accesso esterno in Lync Server 2013](lync-server-2013-configuring-dial-in-conferencing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

