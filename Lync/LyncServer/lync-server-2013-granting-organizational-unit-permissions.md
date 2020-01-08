---
title: 'Lync Server 2013: Concessioni di autorizzazioni per unità organizzative'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Granting organizational unit permissions
ms:assetid: 95ee5ffa-39b1-4d80-87a2-27bb364f7396
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398763(v=OCS.15)
ms:contentKeyID: 48184849
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c65ff483fbb9c63d4eaca31eca47c9093d229438
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982181"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="granting-organizational-unit-permissions-in-lync-server-2013"></a>Concessioni di autorizzazioni per unità organizzative in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-05-14_

Puoi usare il cmdlet **Grant-CsOUPermission** per concedere le autorizzazioni per gli oggetti in unità organizzative specificate in modo che i membri dei gruppi di RTC universale creati dalla preparazione della foresta possano accedervi senza essere membri del gruppo Domain Admins. Le autorizzazioni aggiunte all'UO specificata sono le stesse che il cmdlet **Enable-CsAdDomain** aggiunge ai contenitori computer e utenti durante la preparazione del dominio.

Utilizzare il cmdlet **Test-CsOUPermission** per verificare le autorizzazioni configurate tramite il cmdlet **Grant-CsOUPermission** .

Puoi usare il cmdlet **Revoke-CsOUPermission** per rimuovere le autorizzazioni concesse tramite il cmdlet **Grant-CsOUPermission** .

<div>

## <a name="to-grant-ou-permissions"></a>Per concedere le autorizzazioni dell'unità organizzativa

1.  Accedere a un computer in cui è in uso Lync Server 2013 nel dominio in cui si desidera concedere le autorizzazioni dell'unità organizzativa. Usare un account membro del gruppo Domain Admins o dell'Enterprise Admins se l'unità organizzativa si trova in un dominio figlio diverso.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

3.  Eseguire
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    Se non specifichi il parametro Domain, il valore predefinito è il dominio locale.

</div>

<div>

## <a name="to-verify-ou-permissions"></a>Per verificare le autorizzazioni dell'unità organizzativa

1.  Accedere a un computer in cui è in uso Lync Server 2013 nel dominio in cui si vogliono verificare le autorizzazioni dell'unità organizzativa concesse tramite il cmdlet **Grant-CsOUPermission** . Usare un account membro del gruppo Domain Admins o dell'Enterprise Admins se l'unità organizzativa si trova in un dominio figlio diverso.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

3.  Eseguire
    
        Test-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    Se non specifichi il parametro Domain, il valore predefinito è il dominio locale.

</div>

<div>

## <a name="to-revoke-ou-permissions"></a>Per revocare le autorizzazioni dell'unità organizzativa

1.  Accedere a un computer in cui è in uso Lync Server 2013 nel dominio in cui si desidera revocare le autorizzazioni dell'unità organizzativa concesse dal cmdlet **Grant-CsOUPermission** . Usare un account membro del gruppo Domain Admins o dell'Enterprise Admins se l'unità organizzativa si trova in un dominio figlio diverso.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

3.  Eseguire
    
        Revoke-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    Se non specifichi il parametro Domain, il valore predefinito è il dominio locale.

</div>

</div>

<span> </span>

</div>

</div>

</div>

