---
title: Eseguire la migrazione di Mediation Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate Mediation Server
ms:assetid: b0b77121-2c8f-413e-b276-dbf1038361d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205173(v=OCS.15)
ms:contentKeyID: 48185117
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e1a4caf5585758a22848ad644f83965a979de78
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190169"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-mediation-server"></a>Eseguire la migrazione di Mediation Server

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-28_

Il Mediation Server viene unito alla topologia pilota di Lync Server 2013 quando si esegue la procedura guidata di Unione. È tuttavia possibile configurare Lync Server 2013 Mediation Server, dopo la migrazione di tutti gli utenti, perché un pool di Office Communications Server 2007 R2 non è in grado di comunicare con un server di mediazione Lync Server 2013. Durante la migrazione affiancata, il pool di Lync Server 2013 comunica con il Mediation Server di Office Communications Server 2007 R2.

Quando si configura Lync Server 2013 Mediation Server, è inoltre necessario aggiornare o sostituire i gateway di Office Communications Server 2007 R2. I gateway di Office Communications Server 2007 R2 non supportano Lync Server 2013 Mediation Server. È necessario distribuire i gateway certificati per Lync Server 2013 e associarli a Lync Server 2013 Mediation Server. Questo passaggio è necessario prima di poter rimuovere completamente la distribuzione di Office Communications Server 2007 R2.

Negli argomenti di questa sezione vengono descritte le attività di configurazione che è necessario eseguire dopo aver completato la migrazione di Lync Server 2013 Mediation Server. L'esecuzione della transizione dal Mediation Server collocato a un Mediation Server autonomo è un'attività facoltativa.

  - [Configurare Mediation Server](configure-mediation-server.md)

  - [Modificare le route vocali per l'utilizzo del nuovo Lync Server 2013 Mediation Server](change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md)

  - [Eseguire la transizione di un Mediation Server collocato a un Mediation Server autonomo (facoltativo)](transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server-optional.md)

</div>

<span> </span>

</div>

</div>

</div>

