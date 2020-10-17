---
title: 'Lync Server 2013: concessione di autorizzazioni per le unità organizzative'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Granting organizational unit permissions
ms:assetid: 95ee5ffa-39b1-4d80-87a2-27bb364f7396
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398763(v=OCS.15)
ms:contentKeyID: 48184849
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d17715718d66530686009fdc4b2b9e2acebfceaf
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498903"
---
# <a name="granting-organizational-unit-permissions-in-lync-server-2013"></a>Concessione di autorizzazioni per le unità organizzative in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-05-14_

È possibile utilizzare il cmdlet **Grant-CsOUPermission** per concedere le autorizzazioni per gli oggetti nelle unità organizzative specificate, in modo che i membri dei gruppi universali RTC creati dalla preparazione della foresta possano accedervi senza essere membri del gruppo Domain Admins. Le autorizzazioni aggiunte all'unità organizzativa specificata sono le stesse autorizzazioni che il cmdlet **Enable-CsAdDomain** aggiunge ai contenitori dei computer e degli utenti durante la preparazione del dominio.

Utilizzare il cmdlet **Test-CsOUPermission** per verificare le autorizzazioni impostate utilizzando il cmdlet **Grant-CsOUPermission** .

È possibile utilizzare il cmdlet **Revoke-CsOUPermission** per rimuovere le autorizzazioni concesse utilizzando il cmdlet **Grant-CsOUPermission** .

<div>

## <a name="to-grant-ou-permissions"></a>Per concedere le autorizzazioni per le unità organizzative

1.  Accedere a un computer in cui è in esecuzione Lync Server 2013 nel dominio in cui si desidera concedere le autorizzazioni per l'unità organizzativa. Utilizzare un account membro del gruppo Domain Admins o del gruppo Enterprise Admins se l'unità organizzativa si trova in un altro dominio figlio.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

3.  Eseguire: 
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    Se non si specifica il parametro Domain, per impostazione predefinita verrà utilizzato il dominio locale.

</div>

<div>

## <a name="to-verify-ou-permissions"></a>Per verificare le autorizzazioni dell'unità organizzativa

1.  Accedere a un computer in cui è in esecuzione Lync Server 2013 nel dominio in cui si desidera verificare le autorizzazioni dell'unità organizzativa concesse utilizzando il cmdlet **Grant-CsOUPermission** . Utilizzare un account membro del gruppo Domain Admins o del gruppo Enterprise Admins se l'unità organizzativa si trova in un altro dominio figlio.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

3.  Eseguire: 
    
        Test-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    Se non si specifica il parametro Domain, per impostazione predefinita verrà utilizzato il dominio locale.

</div>

<div>

## <a name="to-revoke-ou-permissions"></a>Per revocare le autorizzazioni per le unità organizzative

1.  Accedere a un computer in cui è in esecuzione Lync Server 2013 nel dominio in cui si desidera revocare le autorizzazioni dell'unità organizzativa concesse dal cmdlet **Grant-CsOUPermission** . Utilizzare un account membro del gruppo Domain Admins o del gruppo Enterprise Admins se l'unità organizzativa si trova in un altro dominio figlio.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

3.  Eseguire: 
    
        Revoke-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    Se non si specifica il parametro Domain, per impostazione predefinita verrà utilizzato il dominio locale.

</div>

</div>

<span> </span>

</div>

</div>

</div>

