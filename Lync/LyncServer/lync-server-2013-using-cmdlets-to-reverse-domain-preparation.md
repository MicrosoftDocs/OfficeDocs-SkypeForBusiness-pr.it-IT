---
title: 'Lync Server 2013: Utilizzo di cmdlet per ripristinare la preparazione del dominio'
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
ms.openlocfilehash: d72c135e7daccd677f8e42ea93a2aace8d7cafb8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744196"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-cmdlets-to-reverse-domain-preparation-for-lync-server-2013"></a>Utilizzo di cmdlet per ripristinare la preparazione del dominio per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-29_

Usa il cmdlet **Disable-CsAdDomain** per invertire il passaggio di preparazione del dominio.

<div>

## <a name="to-use-cmdlets-to-reverse-domain-preparation"></a>Per usare i cmdlet per invertire la preparazione del dominio

1.  Accedere a qualsiasi server del dominio come membro del gruppo Domain Admins.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

3.  Eseguire
    
        Disable-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-Force <SwitchParameter>] 
        [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>] 
    
    Ad esempio:
    
        Disable-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.net -Force
    
    Se il parametro Force è presente, viene eseguito il rollback della preparazione del dominio, anche se vengono attivati uno o più server front-end o un/V Conferencing Servers nel dominio. Se il parametro Force non è presente, il rollback della preparazione del dominio viene terminato se i server front-end o i server di conferenza a/V nel dominio vengono attivati.
    
    <div>
    

    > [!NOTE]  
    > Il parametro GlobalSettingsDomainController consente di indicare dove sono archiviate le impostazioni globali. Se le impostazioni sono archiviate nel contenitore di sistema (tipico delle distribuzioni di aggiornamento che non hanno eseguito la migrazione dell'impostazione globale al contenitore di configurazione), si definisce un controller di dominio nella radice della foresta di Active Directory. Se invece le impostazioni globali sono incluse nel contenitore Configuration, come avviene in genere con le distribuzioni nuove o di aggiornamento per cui è stata eseguita la migrazione delle impostazioni nel contenitore Configuration, definire un controller di dominio nella foresta. Se non specifichi questo parametro, il cmdlet presuppone che le impostazioni siano archiviate nel contenitore di configurazione e faccia riferimento a qualsiasi controller di dominio in&nbsp;Active Directory.

    
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

