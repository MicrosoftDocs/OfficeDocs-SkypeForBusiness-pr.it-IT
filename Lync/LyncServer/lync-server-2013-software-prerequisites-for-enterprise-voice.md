---
title: 'Lync Server 2013: Prerequisiti software per VoIP aziendale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Software prerequisites for Enterprise Voice
ms:assetid: 41172119-9631-46c7-9d9f-386d951c650b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425916(v=OCS.15)
ms:contentKeyID: 48183960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cb85a8da9fe0d009f46ef23b919aeb9fd006fab4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731896"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="software-prerequisites-for-enterprise-voice-in-lync-server-2013"></a>Prerequisiti software per VoIP aziendale in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-03_

Verificare che l'infrastruttura in cui si intende distribuire Enterprise Voice soddisfi i prerequisiti software seguenti:

  - Lync Server 2013 Standard Edition o Enterprise Edition è installato e funzionante in rete.

  - Tutti i server perimetrali sono distribuiti e operativi nella rete perimetrale, inclusi i server perimetrali in cui è in corso Access Edge Services, A/V Edge service, Web Conferencing Edge Services e un proxy inverso.

  - Microsoft Exchange Server 2007 Service Pack 3 (SP3), Microsoft Exchange Server 2010 o Microsoft Exchange Server 2013 è necessario per l'integrazione della messaggistica unificata di Exchange con Lync Server e per l'inserimento di notifiche RTF e informazioni sul log delle chiamate Endpoint Lync.

  - Uno o più utenti sono stati creati e abilitati per Lync Server.

  - I client e i dispositivi Lync sono stati distribuiti correttamente.

  - Generatore di topologia è installato in un server della rete.

<div>

## <a name="next-steps-verify-security-and-configuration-prerequisites"></a>Passaggi successivi: verificare i prerequisiti per la sicurezza e la configurazione

Dopo aver verificato i prerequisiti software per VoIP aziendale, è possibile usare la documentazione per continuare la preparazione per la distribuzione di VoIP aziendale:

1.  Verificare sicurezza, configurazione utente e hardware prerequisiti, come descritto in [prerequisiti di sicurezza e configurazione per VoIP aziendale in Lync Server 2013](lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md).

2.  Installare il Mediation Server, come descritto in [installare i file per Mediation Server in Lync server 2013](lync-server-2013-install-the-files-for-mediation-server.md), ma *solo* se si vuole distribuire un server o un pool di mediazione autonomo perché i server di mediazione vengono installati come parte del pool di front-end o del processo di distribuzione del server standard in una posizione collocata.

3.  Configurare le connessioni trunk per consentire la connettività PSTN per gli utenti, come descritto in [configurazione di Trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

