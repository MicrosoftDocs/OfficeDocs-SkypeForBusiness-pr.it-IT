---
title: 'Lync Server 2013: utilizzo dei cmdlet per annullare la preparazione del dominio'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using cmdlets to reverse domain preparation
ms:assetid: 014dba5d-fcb3-44c9-9d63-ae0755276dac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398071(v=OCS.15)
ms:contentKeyID: 48183227
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ac26e17ad9e0ab13529da438bc2e12bec210808d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212902"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-cmdlets-to-reverse-domain-preparation-for-lync-server-2013"></a>Utilizzo dei cmdlet per annullare la preparazione del dominio per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-29_

Utilizzare il cmdlet **Disable-CsAdDomain** per annullare il passaggio di preparazione di un dominio.

<div>

## <a name="to-use-cmdlets-to-reverse-domain-preparation"></a>Per utilizzare i cmdlet per annullare la preparazione di un dominio

1.  Eseguire l'accesso a qualsiasi server del dominio come membri del gruppo Domain Admins.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

3.  Eseguire: 
    
        Disable-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-Force <SwitchParameter>] 
        [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>] 
    
    Ad esempio:
    
        Disable-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.net -Force
    
    Se il parametro Force è presente, viene eseguito il rollback della preparazione del dominio, anche se uno o più server front end o A/V Conferencing Server nel dominio vengono attivati. Se il parametro Force non è presente, il rollback della preparazione del dominio viene interrotto se i server front end o i server a/V Conferencing nel dominio vengono attivati.
    
    <div>
    

    > [!NOTE]  
    > Il parametro GlobalSettingsDomainController consente di indicare dove vengono archiviate le impostazioni globali. Se le impostazioni sono archiviate nel contenitore System, come avviene in genere con le distribuzioni di aggiornamento per cui non è stata eseguita la migrazione dell'impostazione globale nel contenitore Configuration, definire un controller di dominio nella radice della foresta di Active Directory. Se invece le impostazioni globali sono incluse nel contenitore Configuration, come avviene in genere con le distribuzioni nuove o di aggiornamento per cui è stata eseguita la migrazione delle impostazioni nel contenitore Configuration, definire un controller di dominio nella foresta. Se non si specifica questo parametro, il cmdlet presuppone che le impostazioni siano archiviate nel contenitore di configurazione e si riferisca a qualsiasi controller&nbsp;di dominio in ad DS.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Esecuzione della preparazione del dominio per Lync Server 2013](lync-server-2013-running-domain-preparation.md)  


[Preparazione dei domini per Lync Server 2013](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

