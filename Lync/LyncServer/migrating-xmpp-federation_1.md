---
title: Migrazione della federazione di XMPP
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrating XMPP federation
ms:assetid: 7368ee8f-a201-4d3a-b4e8-68396b156d4d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688093(v=OCS.15)
ms:contentKeyID: 49733692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 953b422527e095a6fef1e34cbf8b8fde2d494f42
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731066"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-xmpp-federation"></a>Migrazione della federazione di XMPP

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-16_

Le versioni precedenti di Office Communications Server fornivano un gateway XMPP (Extensible Messaging and Presence Protocol) che potrebbe essere distribuito come ruolo server distinto per consentire la Federazione con le distribuzioni XMPP. In Lync Server 2013 la funzionalità XMPP può essere distribuita come caratteristica. La funzionalità XMPP viene installata in due parti: come proxy XMPP eseguito su Lync Server 2013 Edge Server e il gateway XMPP eseguito nel server front-end di Lync Server 2013.

Da una prospettiva di migrazione, un account utente di Office Communications Server 2007 R2 può essere spostato in un pool di Lync Server 2013 e continuare a usare il gateway XMPP di Office Communications Server 2007 R2. Questo è possibile solo quando il partner federato XMPP non è configurato in Lync Server 2013.

In sintesi, se Office Communications Server è stato distribuito con il gateway XMPP di Office Communications Server 2007 R2 e la Federazione XMPP è stata abilitata per gli utenti legacy di Office Communications Server 2007 R2, per eseguire la migrazione della Federazione XMPP a Lync Server 2013:

1.  Distribuire un pool di Lync Server 2013.

2.  Distribuire un server perimetrale di Lync Server 2013.

3.  Trasferire tutti gli utenti nel pool di Lync Server 2013.

4.  Creare criteri di accesso e certificati XMPP per il server perimetrale.

5.  Abilitare la Federazione XMPP in Lync Server 2013. 

6.  Aggiornare le voci DNS in punti al gateway XMPP di Lync Server 2013.

</div>

<span> </span>

</div>

</div>

</div>

