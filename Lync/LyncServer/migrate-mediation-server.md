---
title: Eseguire la migrazione di Mediation Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrate Mediation Server
ms:assetid: b0b77121-2c8f-413e-b276-dbf1038361d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205173(v=OCS.15)
ms:contentKeyID: 48185117
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 79fc35a7641b4acb42578ec4e75375e171ae905e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982245"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-mediation-server"></a>Eseguire la migrazione di Mediation Server

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-28_

Il Mediation Server viene unito alla topologia pilota di Lync Server 2013 quando si esegue la creazione guidata unione. La configurazione di Lync Server 2013 Mediation Server viene tuttavia eseguita dopo la migrazione di tutti gli utenti perché un pool di Office Communications Server 2007 R2 non può comunicare con un server di mediazione di Lync Server 2013. Durante la migrazione affiancata, il pool di Lync Server 2013 comunica con Office Communications Server 2007 R2 Mediation Server.

Quando si configura Lync Server 2013 Mediation Server, è anche necessario aggiornare o sostituire i gateway di Office Communications Server 2007 R2. I gateway di Office Communications Server 2007 R2 non supportano Lync Server 2013 Mediation Server. È necessario distribuire gateway certificati per Lync Server 2013 e associarli a Lync Server 2013 Mediation Server. Questo passaggio è necessario prima di poter decommissionare completamente la distribuzione di Office Communications Server 2007 R2.

Gli argomenti di questa sezione descrivono le attività di configurazione che è necessario eseguire dopo aver completato la migrazione di Lync Server 2013 Mediation Server. La transizione del server di mediazione collocato a un Mediation Server autonomo è un'attività facoltativa.

  - [Configurare Mediation Server](configure-mediation-server.md)

  - [Modificare le route vocali per usare il nuovo server di mediazione Lync Server 2013](change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md)

  - [Transizione di un Mediation Server collocato a un Mediation Server autonomo (facoltativo)](transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server-optional.md)

</div>

<span> </span>

</div>

</div>

</div>

