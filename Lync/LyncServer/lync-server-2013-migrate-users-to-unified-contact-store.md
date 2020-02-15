---
title: "Lync Server 2013: eseguire la migrazione degli utenti nell'archivio contatti unificato"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migrate users to unified contact store
ms:assetid: 215a8ec1-d63e-4fdf-b73d-75aeb9dddb43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204737(v=OCS.15)
ms:contentKeyID: 48183600
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6d170fa183e045203398725a7b7ec4bdd4c38203
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42039323"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-users-to-unified-contact-store-in-lync-server-2013"></a>Eseguire la migrazione degli utenti nell'archivio contatti unificato in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-15_

I contatti di un utente vengono migrati automaticamente al server Exchange 2013 quando l'utente:

  - All'utente sono stati assegnati servizi utente per cui UcsAllowed è impostato su True.

  - È stato effettuato il provisioning con una cassetta postale di Exchange 2013 e ha eseguito l'accesso almeno una volta alla cassetta postale.

  - Esegue l'accesso utilizzando un rich client Lync 2013.

Se l'utente esegue l'accesso con un client Lync 2010 o versioni precedenti o se l'utente non è connesso a un server Exchange 2013, i criteri di servizi utente vengono ignorati e i contatti dell'utente restano in Lync Server.

È possibile stabilire se i contatti di un utente sono stati migrati usando uno dei metodi seguenti:

  - Verificare la chiave del Registro di sistema seguente nel computer client:
    
    HKEY\_software\_\\utente\\corrente Microsoft\\Office\\15,0\\Lync\\\<SIP URL\>\\UCS
    
    Se i contatti dell'utente sono archiviati in Exchange 2013, questa chiave contiene un valore di InUCSMode con un valore pari a 2165.

  - Eseguire il cmdlet **Test-CsUnifiedContactStore**. Nella riga di comando di Lync Server Management Shell digitare quanto segue:
    
        Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
    
    Se **Test-CsUnifiedContactStore** ha esito positivo, i contatti dell'utente sono stati migrati nell'archivio contatti unificato.

</div>

<span> </span>

</div>

</div>

</div>

