---
title: Verificare la federazione e l'accesso remoto per gli utenti esterni
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Verify federation and remote access for external users
ms:assetid: a383fefb-c428-4462-93fd-15ba540fa867
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688163(v=OCS.15)
ms:contentKeyID: 49733768
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 33eb8fddaef96da047a6e87f1961b2fbea73c29d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975985"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-federation-and-remote-access-for-external-users"></a>Verificare la federazione e l'accesso remoto per gli utenti esterni

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-18_

Dopo aver eseguito la transizione della route federativa al server Edge di Lync Server 2013, è necessario eseguire alcuni test funzionali per verificare che la Federazione venga eseguita come previsto. I test per l'accesso degli utenti esterni devono includere ogni tipo di utente esterno supportato dall'organizzazione, inclusi uno o tutti gli elementi seguenti.

<div>

## <a name="test-connectivity-of-external-users-and-external-access"></a>Testare la connettività degli utenti esterni e dell'accesso esterno

  - Utenti di almeno un dominio federato, un utente interno in Lync Server 2013 e un utente in Lync Server 2010. Test di messaggistica istantanea (IM), presenza, audio/video (A/V) e condivisione desktop.

  - Utenti di ogni provider di servizi di messaggistica istantanea pubblico supportato dall'organizzazione (e per il quale è stato completato il provisioning) che comunica con un utente in Lync Server 2013 e un utente in Lync Server 2010.

  - Verificare che gli utenti anonimi siano in grado di partecipare a conferenze.

  - Un utente ospitato in Lync Server 2010 che usa l'accesso degli utenti remoti (accedendo a Lync Server 2010 dall'esterno della Intranet ma senza VPN) con un utente in Lync Server 2013 e un utente in Lync Server 2010. Test di messaggistica istantanea, presenza, A/V e condivisione desktop.

  - Un utente ospitato in Lync Server 2013 che usa l'accesso degli utenti remoti (accedendo a Lync Server 2013 dall'esterno della Intranet ma senza VPN) con un utente in Lync Server 2013 e un utente in Lync Server 2010. Test di messaggistica istantanea, presenza, A/V e condivisione desktop.

</div>

</div>

<span> </span>

</div>

</div>

</div>

