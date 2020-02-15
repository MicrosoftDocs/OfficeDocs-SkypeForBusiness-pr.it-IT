---
title: Verificare la federazione e l'accesso remoto per gli utenti esterni
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify federation and remote access for external users
ms:assetid: a383fefb-c428-4462-93fd-15ba540fa867
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688163(v=OCS.15)
ms:contentKeyID: 49733768
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 382c3e892f7e4d46b5c584e7efc0c03cc89531ac
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "41983061"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-federation-and-remote-access-for-external-users"></a>Verificare la federazione e l'accesso remoto per gli utenti esterni

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-18_

Dopo la transizione della route di federazione al server perimetrale di Lync Server 2013, è necessario eseguire alcuni test funzionali per verificare che la Federazione venga eseguita come previsto. I test per l'accesso utente esterno devono includere ogni tipo di utente esterno supportato dall'organizzazione, inclusi alcuni o tutti quelli indicati di seguito.

<div>

## <a name="test-connectivity-of-external-users-and-external-access"></a>Testare la connettività degli utenti esterni e dell'accesso esterno

  - Utenti provenienti da almeno un dominio federato, un utente interno in Lync Server 2013 e un utente in Lync Server 2010. Testare la messaggistica istantanea, il traffico audio/video e la condivisione del desktop.

  - Utenti di ogni provider di servizi di messaggistica istantanea supportato dall'organizzazione (e per i quali è stato completato il provisioning) che comunicano con un utente in Lync Server 2013 e un utente in Lync Server 2010.

  - Verificare che gli utenti anonimi siano in grado di partecipare alle conferenze.

  - Un utente ospitato in Lync Server 2010 utilizzando l'accesso degli utenti remoti (accedendo a Lync Server 2010 dall'esterno della rete Intranet ma senza VPN) con un utente in Lync Server 2013 e un utente in Lync Server 2010. Testare la messaggistica istantanea, la presenza, il traffico audio/video e la condivisione del desktop.

  - Un utente ospitato in Lync Server 2013 utilizzando l'accesso degli utenti remoti (accedendo a Lync Server 2013 dall'esterno della rete Intranet ma senza VPN) con un utente in Lync Server 2013 e un utente in Lync Server 2010. Testare la messaggistica istantanea, la presenza, il traffico audio/video e la condivisione del desktop.

</div>

</div>

<span> </span>

</div>

</div>

</div>

