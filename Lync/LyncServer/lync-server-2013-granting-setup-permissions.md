---
title: 'Lync Server 2013: Concessione di autorizzazioni di installazione'
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
ms.openlocfilehash: 2a4642a9e0c77d9cf3aa77c146ff692a7fa7a6c2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763890"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="granting-setup-permissions-in-lync-server-2013"></a>Concessione di autorizzazioni di installazione in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-08-27_

Puoi usare il cmdlet **Grant-CsSetupPermission** per aggiungere autorizzazioni di lettura, scrittura, ReadSPN e WriteSPN al gruppo RTCUniversalServerAdmins per un'unità organizzativa di Active Directory specificata. I membri del gruppo RTCUniversalServerAdmins dell'unità organizzativa possono quindi installare i server che utilizzano Lync Server 2013 nel dominio specificato senza essere membri del gruppo Domain Admins.

Utilizzare il cmdlet **Test-CsSetupPermission** per verificare le autorizzazioni configurate tramite il cmdlet **Grant-CsSetupPermission** .

Puoi usare il cmdlet **Revoke-CsSetupPermission** per rimuovere le autorizzazioni concesse tramite il cmdlet **Grant-CsSetupPermission** .

<div>

## <a name="to-grant-setup-permissions"></a>Per concedere le autorizzazioni di configurazione

1.  Accedere a un computer in cui è in uso Lync Server 2013 nel dominio in cui si desidera concedere le autorizzazioni di configurazione. Usare un account membro del gruppo Domain Admins o dell'Enterprise Admins se l'unità organizzativa si trova in un dominio figlio diverso.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

3.  Eseguire
    
        Grant-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    Puoi specificare il parametro ComputerOu in relazione al contesto di denominazione predefinito del dominio specificato, ad esempio CN = Computers. In alternativa, puoi specificare questo parametro come nome distinto OU completo (DN), ad esempio "CN = Computers, DC = contoso, DC = com". In quest'ultimo caso, devi specificare un DN di OU coerente con il dominio specificato.
    
    Se non specifichi il parametro Domain, il valore predefinito è il dominio locale.

</div>

<div>

## <a name="to-verify-setup-permissions"></a>Per verificare le autorizzazioni di configurazione

1.  Accedere a un computer che usa Lync Server 2013 nel dominio in cui si vogliono verificare le autorizzazioni di configurazione concesse tramite il cmdlet **Grant-CsSetupPermission** . Usare un account membro del gruppo Domain Admins o dell'Enterprise Admins se l'unità organizzativa si trova in un dominio figlio diverso.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

3.  Eseguire
    
        Test-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside> [-Domain <Domain FQDN>]
    
    Puoi specificare il parametro ComputerOu in relazione al contesto di denominazione predefinito del dominio specificato, ad esempio CN = Computers. In alternativa, puoi specificare questo parametro come nome distinto OU completo (DN), ad esempio "CN = Computers, DC = contoso, DC = com". In quest'ultimo caso, devi specificare un DN di OU coerente con il dominio specificato.
    
    Se non specifichi il parametro Domain, il valore predefinito è il dominio locale.

</div>

<div>

## <a name="to-revoke-setup-permissions"></a>Per revocare le autorizzazioni di configurazione

1.  Accedere a un computer in cui è in uso Lync Server 2013 nel dominio in cui si desidera revocare le autorizzazioni di configurazione concesse dal cmdlet **Grant-CsSetupPermission** . Usare un account membro del gruppo Domain Admins o dell'Enterprise Admins se l'unità organizzativa si trova in un dominio figlio diverso.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

3.  Eseguire
    
        Revoke-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    Puoi specificare il parametro ComputerOu in relazione al contesto di denominazione predefinito del dominio specificato, ad esempio CN = Computers. In alternativa, puoi specificare questo parametro come nome distinto OU completo (DN), ad esempio "CN = Computers, DC = contoso, DC = com". In quest'ultimo caso, devi specificare un DN di OU coerente con il dominio specificato.
    
    Se non specifichi il parametro Domain, il valore predefinito è il dominio locale.

</div>

</div>

<span> </span>

</div>

</div>

</div>

