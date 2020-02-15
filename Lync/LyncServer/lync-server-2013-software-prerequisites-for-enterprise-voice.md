---
title: 'Lync Server 2013: prerequisiti software per VoIP aziendale'
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
ms.openlocfilehash: dc6c5e5f3f9fc92f56ee1f044419f67f5ded32ce
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "41987021"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="software-prerequisites-for-enterprise-voice-in-lync-server-2013"></a>Prerequisiti software per VoIP aziendale in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-03_

Verificare che l'infrastruttura in cui si intende distribuire VoIP aziendale soddisfi i prerequisiti software seguenti:

  - Lync Server 2013 Standard Edition o Enterprise Edition è installato e funzionante nella rete.

  - Tutti i server perimetrali sono distribuiti e operativi nella rete perimetrale, inclusi i server perimetrali che eseguono il servizio Access Edge, il servizio A/V Edge, il servizio Web Conferencing Edge e un proxy inverso.

  - Microsoft Exchange Server 2007 Service Pack 3 (SP3), Microsoft Exchange Server 2010 o Microsoft Exchange Server 2013 è necessario per l'integrazione della messaggistica unificata di Exchange con Lync Server e per fornire notifiche ricche e informazioni sui registri di chiamata al Endpoint di Lync.

  - Uno o più utenti sono stati creati e abilitati per Lync Server.

  - I client e i dispositivi Lync sono stati distribuiti correttamente.

  - Generatore di topologie è installato in un server della rete.

<div>

## <a name="next-steps-verify-security-and-configuration-prerequisites"></a>Passaggi successivi: verificare i prerequisiti della sicurezza e della configurazione

Dopo aver verificato i prerequisiti software per VoIP aziendale, è possibile utilizzare la documentazione per continuare la preparazione per la distribuzione di VoIP aziendale:

1.  Verificare la sicurezza, la configurazione utente e i componenti hardware di prerequisiti, come descritto in [prerequisiti di configurazione e sicurezza per VoIP aziendale in Lync Server 2013](lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md).

2.  Installare il Mediation Server, come descritto in [Install the files for Mediation Server in Lync server 2013](lync-server-2013-install-the-files-for-mediation-server.md), ma *solo* se si desidera distribuire un Mediation Server autonomo o un pool perché i Mediation Server vengono installati come parte del pool Front end o del processo di distribuzione del server Standard Edition durante la collocazione.

3.  Configurare le connessioni trunk per garantire la connettività PSTN per gli utenti, come descritto in [Configuring Trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

