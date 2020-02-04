---
title: "Lync Server 2013: Eseguire la migrazione degli utenti nell'archivio contatti unificato"
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
ms.openlocfilehash: 5a57ea93af90176009fff43ed4dcca9f1880a658
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41766047"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-users-to-unified-contact-store-in-lync-server-2013"></a>Eseguire la migrazione degli utenti nell'archivio contatti unificato in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-15_

I contatti di un utente vengono automaticamente migrati nel server di Exchange 2013 quando l'utente:

  - È stato assegnato un criterio servizi utente con UcsAllowed impostato su true.

  - È stato effettuato il provisioning con una cassetta postale di Exchange 2013 e ha eseguito l'accesso alla cassetta postale almeno una volta.

  - Accede utilizzando un client RTF di Lync 2013.

Se l'utente esegue l'accesso con un client Lync 2010 o versioni precedenti oppure se l'utente non è connesso a un server di Exchange 2013, il criterio servizi utente viene ignorato e i contatti dell'utente restano in Lync Server.

Puoi determinare se i contatti di un utente sono stati migrati usando uno dei metodi seguenti:

  - Selezionare la chiave del registro di sistema seguente nel computer client:
    
    HKEY\_software\_\\dell'\\utente corrente\\Microsoft\\Office\\15,0\\\<UCS SIP\>\\dell'URL di Lync
    
    Se i contatti dell'utente sono archiviati in Exchange 2013, questa chiave contiene un valore di InUCSMode con il valore 2165.

  - Eseguire il cmdlet **Test-CsUnifiedContactStore** . Nella riga di comando di Lync Server Management Shell digitare:
    
        Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
    
    Se **Test-CsUnifiedContactStore** ha esito positivo, i contatti dell'utente sono stati migrati in archivio contatti unificato.

</div>

<span> </span>

</div>

</div>

</div>

