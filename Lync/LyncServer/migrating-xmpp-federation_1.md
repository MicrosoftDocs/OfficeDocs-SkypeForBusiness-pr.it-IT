---
title: Migrazione della federazione di XMPP
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrating XMPP federation
ms:assetid: 7368ee8f-a201-4d3a-b4e8-68396b156d4d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688093(v=OCS.15)
ms:contentKeyID: 49733692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 716e3c5eebf365118e795d584f7c9e73f949cf9b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527323"
---
# <a name="migrating-xmpp-federation"></a>Migrazione della federazione di XMPP

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-16_

Le versioni precedenti di Office Communications Server fornivano un gateway XMPP (Extensible Messaging and Presence Protocol) che potrebbe essere distribuito come ruolo server separato per consentire la Federazione con le distribuzioni XMPP. In Lync Server 2013, la funzionalità XMPP può essere distribuita come caratteristica. La funzionalità XMPP è installata in due parti: come proxy XMPP eseguito sul server perimetrale di Lync Server 2013 e il gateway XMPP in esecuzione nel server front-end di Lync Server 2013.

Dal punto di vista della migrazione, un account utente di Office Communications Server 2007 R2 può essere spostato in un pool Lync Server 2013 e continuare a utilizzare il gateway XMPP di Office Communications Server 2007 R2. Ciò è possibile solo quando il partner federato XMPP non è configurato in Lync Server 2013.

In sintesi, se Office Communications Server è stato distribuito con il gateway XMPP di Office Communications Server 2007 R2 e la Federazione XMPP è stata abilitata per gli utenti di Office Communications Server 2007 R2 legacy, per eseguire la migrazione della Federazione XMPP a Lync Server 2013:

1.  Distribuire un pool di Lync Server 2013.

2.  Distribuire un server perimetrale di Lync Server 2013.

3.  Spostare tutti gli utenti nel pool di Lync Server 2013.

4.  Creare criteri di accesso XMPP e certificati per il server perimetrale.

5.  Abilitare la Federazione XMPP in Lync Server 2013. 

6.  Aggiornare le voci DNS in modo che puntino al gateway XMPP di Lync Server 2013.

</div>

<span> </span>

</div>

</div>

</div>

