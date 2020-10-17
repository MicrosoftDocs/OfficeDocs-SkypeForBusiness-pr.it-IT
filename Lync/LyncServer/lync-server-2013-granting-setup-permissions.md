---
title: 'Lync Server 2013: concessione di autorizzazioni di installazione'
description: 'Lync Server 2013: concessione di autorizzazioni di installazione.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Granting setup permissions
ms:assetid: 15982bfe-6844-44f6-815a-72dcaf0e4d21
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398225(v=OCS.15)
ms:contentKeyID: 48183491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5523494219d07907caeefc1bd139c41856effa54
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554482"
---
# <a name="granting-setup-permissions-in-lync-server-2013"></a>Concessione di autorizzazioni di installazione in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-08-27_

È possibile utilizzare il cmdlet **Grant-CsSetupPermission** per aggiungere autorizzazioni Read, Write, ReadSPN e WriteSPN al gruppo RTCUniversalServerAdmins per una determinata unità organizzativa (OU) di Active Directory. I membri del gruppo RTCUniversalServerAdmins nell'unità organizzativa possono quindi installare i server che eseguono Lync Server 2013 nel dominio specificato senza essere membri del gruppo Domain Admins.

Utilizzare il cmdlet **Test-CsSetupPermission** per verificare le autorizzazioni impostate mediante il cmdlet **Grant-CsSetupPermission**.

È possibile utilizzare il cmdlet **Revoke-CsSetupPermission** per rimuovere le autorizzazioni concesse mediante il cmdlet **Grant-CsSetupPermission**.

<div>

## <a name="to-grant-setup-permissions"></a>Per concedere autorizzazioni di installazione

1.  Accedere a un computer su cui è in esecuzione Lync Server 2013 nel dominio in cui si desidera concedere le autorizzazioni di installazione. Utilizzare un account membro del gruppo Domain Admins o del gruppo Enterprise Admins se l'unità organizzativa si trova in un altro dominio figlio.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

3.  Eseguire: 
    
        Grant-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    È possibile specificare il parametro ComputerOu in base al contesto dei nomi predefinito del dominio specificato, ad esempio CN=computer. In alternativa, è possibile specificare tale parametro come nome distinto (DN) completo dell'unità organizzativa (OU), ad esempio "CN=computer,DC=Contoso,DC=com". In quest'ultimo caso, è necessario specificare un nome distinto dell'unità organizzativa che sia coerente con il dominio specificato.
    
    Se non si specifica il parametro Domain, per impostazione predefinita verrà utilizzato il dominio locale.

</div>

<div>

## <a name="to-verify-setup-permissions"></a>Per verificare le autorizzazioni di installazione

1.  Accedere a un computer in cui è in esecuzione Lync Server 2013 nel dominio in cui si desidera verificare le autorizzazioni di installazione concesse utilizzando il cmdlet **Grant-CsSetupPermission** . Utilizzare un account membro del gruppo Domain Admins o del gruppo Enterprise Admins se l'unità organizzativa si trova in un altro dominio figlio.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

3.  Eseguire: 
    
        Test-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside> [-Domain <Domain FQDN>]
    
    È possibile specificare il parametro ComputerOu in base al contesto dei nomi predefinito del dominio specificato, ad esempio CN=computer. In alternativa, è possibile specificare tale parametro come nome distinto (DN) completo dell'unità organizzativa (OU), ad esempio "CN=computer,DC=Contoso,DC=com". In quest'ultimo caso, è necessario specificare un nome distinto dell'unità organizzativa che sia coerente con il dominio specificato.
    
    Se non si specifica il parametro Domain, per impostazione predefinita verrà utilizzato il dominio locale.

</div>

<div>

## <a name="to-revoke-setup-permissions"></a>Per revocare le autorizzazioni di installazione

1.  Accedere a un computer in cui è in esecuzione Lync Server 2013 nel dominio in cui si desidera revocare le autorizzazioni di installazione concesse dal cmdlet **Grant-CsSetupPermission** . Utilizzare un account membro del gruppo Domain Admins o del gruppo Enterprise Admins se l'unità organizzativa si trova in un altro dominio figlio.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

3.  Eseguire: 
    
        Revoke-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    È possibile specificare il parametro ComputerOu in base al contesto dei nomi predefinito del dominio specificato, ad esempio CN=computer. In alternativa, è possibile specificare tale parametro come nome distinto (DN) completo dell'unità organizzativa (OU), ad esempio "CN=computer,DC=Contoso,DC=com". In quest'ultimo caso, è necessario specificare un nome distinto dell'unità organizzativa che sia coerente con il dominio specificato.
    
    Se non si specifica il parametro Domain, per impostazione predefinita verrà utilizzato il dominio locale.

</div>

</div>

<span> </span>

</div>

</div>

</div>

