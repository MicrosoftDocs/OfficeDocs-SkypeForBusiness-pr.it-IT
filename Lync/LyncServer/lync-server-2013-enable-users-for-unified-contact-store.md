---
title: "Lync Server 2013: abilitare gli utenti per l'archivio contatti unificato"
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
ms.openlocfilehash: fc769241059a2536ff644e6ea7b711aaa8cd342d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154888"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-users-for-unified-contact-store-in-lync-server-2013"></a>Abilitare gli utenti per l'archivio contatti unificato in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-07_

Quando si distribuisce Lync Server 2013 e si pubblica la topologia, l'archivio contatti unificato è abilitato per tutti gli utenti per impostazione predefinita. Non è necessario eseguire ulteriori operazioni per abilitare l'archivio contatti unificato dopo la distribuzione di Lync Server 2013. Tuttavia, è possibile utilizzare il cmdlet **Set-CsUserServicesPolicy** per decidere a quali utenti rendere l'archivio unificato per i contatti disponibile. È possibile abilitare questa caratteristica a livello globale, di sito, tenant, o per utenti singoli o gruppi di utenti.

<div>

## <a name="to-enable-users-for-unified-contact-store"></a>Per abilitare gli utenti all'archivio unificato contatti

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

2.  Eseguire una delle operazioni seguenti:
    
      - Per abilitare l'archivio contatti unificato a livello globale per tutti gli utenti di Lync Server, nella riga di comando digitare quanto segue:
        
            Set-CsUserServicesPolicy -Identity global -UcsAllowed $True
    
      - Per abilitare l'archivio unificato per i contatti a livello globale per gli utenti di un sito specifico, digitare quanto segue nella riga di comando:
        
            New-CsUserServicesPolicy -Identity site:<site name> -UcsAllowed $True
        
        Ad esempio:
        
            New-CsUserServicesPolicy -Identity site:Redmond -UcsAllowed $True
    
      - Per abilitare l'archivio unificato per tenant, digitare quanto segue nella riga di comando:
        
            Set-CsUserServicesPolicy -Tenant <tenantId> -UcsAllowed $True
        
        Ad esempio:
        
            Set-CsUserServicesPolicy -Tenant "38aad667-af54-4397-aaa7-e94c79ec2308" -UcsAllowed $True
    
      - Per abilitare l'archivio unificato per utente specifico, digitare quanto segue nella riga di comando:
        
            New-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $True
            Grant-CsUserServicesPolicy -Identity "<user display name>" -PolicyName <"policy name">
        
        <div>
        

        > [!NOTE]  
        > Al posto del nome visualizzato dell'utente, è inoltre possibile utilizzare alias utente o URI SIP.

        
        </div>
        
        Ad esempio:
        
            New-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $True
            Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "UCS Enabled Users"
        
        <div>
        

        > [!NOTE]  
        > Nell'esempio precedente, il primo comando crea un nuovo criterio per utente chiamato <EM>UCS Enabled Users</EM>, con il contrassegno UcsAllowed impostato su True. Il secondo comando assegna il criterio all'utente con nome visualizzato Ken Myer, e pertanto Ken Myer è ora abilitato all'archivio unificato per i contatti.

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

