---
title: "Lync Server 2013: Abilitare gli utenti per l'archivio contatti unificato"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable users for unified contact store
ms:assetid: 7b46a01f-beb5-4a33-adb0-35f0502b168d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205024(v=OCS.15)
ms:contentKeyID: 48184599
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3df3cbd4d71a1decc3607263f2e98b159dc29b2e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735866"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-users-for-unified-contact-store-in-lync-server-2013"></a>Abilitare gli utenti per l'archivio contatti unificato in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-07_

Quando si distribuisce Lync Server 2013 e si pubblica la topologia, per impostazione predefinita l'archivio contatti unificato è abilitato per tutti gli utenti. Non è necessario eseguire altre azioni per abilitare l'archiviazione di contatti unificati dopo la distribuzione di Lync Server 2013. Tuttavia, puoi usare il cmdlet **Set-CsUserServicesPolicy** per personalizzare gli utenti che dispongono di un archivio contatti unificato disponibile. Puoi abilitare questa funzionalità a livello globale, per sito, per tenant o per singoli o gruppi di persone.

<div>

## <a name="to-enable-users-for-unified-contact-store"></a>Per abilitare gli utenti per l'archivio contatti unificato

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

2.  Eseguire una delle operazioni seguenti:
    
      - Per abilitare l'archivio contatti unificato a livello globale per tutti gli utenti di Lync Server, nella riga di comando digitare:
        
            Set-CsUserServicesPolicy -Identity global -UcsAllowed $True
    
      - Per abilitare l'archivio contatti unificato per gli utenti di un sito specifico, nella riga di comando digitare:
        
            New-CsUserServicesPolicy -Identity site:<site name> -UcsAllowed $True
        
        Ad esempio:
        
            New-CsUserServicesPolicy -Identity site:Redmond -UcsAllowed $True
    
      - Per abilitare l'archivio contatti unificato dal tenant, nella riga di comando digitare:
        
            Set-CsUserServicesPolicy -Tenant <tenantId> -UcsAllowed $True
        
        Ad esempio:
        
            Set-CsUserServicesPolicy -Tenant "38aad667-af54-4397-aaa7-e94c79ec2308" -UcsAllowed $True
    
      - Per abilitare l'archivio contatti unificato per utenti specifici, nella riga di comando digitare:
        
            New-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $True
            Grant-CsUserServicesPolicy -Identity "<user display name>" -PolicyName <"policy name">
        
        <div>
        

        > [!NOTE]  
        > È anche possibile usare l'alias utente o l'URI SIP anziché il nome visualizzato dell'utente.

        
        </div>
        
        Ad esempio:
        
            New-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $True
            Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "UCS Enabled Users"
        
        <div>
        

        > [!NOTE]  
        > Nell'esempio precedente il primo comando crea un nuovo criterio per utente denominato <EM>UCS abilitato agli utenti</EM> con il flag UcsAllowed impostato su true. Il secondo comando assegna i criteri all'utente con il nome visualizzato Ken di riferimento, il che significa che Ken è ora abilitato per l'archivio contatti unificato.

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

