---
title: 'Lync Server 2013: attivazione o disattivazione della scrivania calda'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable hot desking
ms:assetid: 93a7fed6-f61a-4b41-9336-a8320afa87cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994057(v=OCS.15)
ms:contentKeyID: 51803968
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cc3350d2d67318741ad3b3e515f93fce66002ff7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146909"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-hot-desking-in-lync-server-2013"></a>Abilitare o disabilitare l'hot desking in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-20_

È possibile configurare i telefoni delle aree comuni come *telefoni da tavolo caldo*. Con i telefoni Hot-Desk, gli utenti possono accedere al proprio account utente e, dopo aver effettuato l'accesso, utilizzare le funzionalità di Lync Server e le proprie impostazioni del profilo utente. La gestione delle chiamate a caldo è gestita utilizzando i criteri client: per abilitare o disabilitare la scrivania calda, è necessario modificare i criteri client utilizzati dai telefoni delle aree comuni. Per informazioni dettagliate su come determinare i criteri di conferenza assegnati ai telefoni delle aree comuni, vedere [View common area Phone Information in Lync Server 2013](lync-server-2013-view-common-area-phone-information.md).

È possibile utilizzare il parametro EnableHotdesking del cmdlet **New-CsClientPolicy** o il cmdlet **Set-CsClientPolicy** per abilitare o disabilitare la scrivania calda su un telefono, come indicato di seguito. Eseguire questi cmdlet da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 using Remote PowerShell" at.

<div>


<div>

## <a name="enabling-hot-desking"></a>Abilitazione di Hot desking

  - Per abilitare il servizio di desktop attivo per un telefono di area comune, è necessario modificare il criterio client assegnato al telefono (o all'insieme di telefoni).
    
    Dopo aver identificato il criterio che deve essere modificato, il passaggio successivo consiste nell'utilizzare il cmdlet **Set-CsClientPolicy** per impostare il parametro EnableHotdesking su true. Ad esempio:
    
        Set-CsClientPolicy -Identity "CommonAreaPhonePolicy" - EnableHotdesking $True

  - In alternativa, è possibile utilizzare il cmdlet **New-CsClientPolicy** per creare un nuovo criterio client che consenta l'utilizzo di Hot Desk. Ad esempio:
    
        New-CsClientPolicy -Identity "NewCommonAreaPhonePolicy" - EnableHotdesking $True

</div>

<div>


> [!IMPORTANT]  
> Dopo aver creato questo criterio, è necessario assegnarlo ai telefoni delle aree comuni appropriate. Per ulteriori informazioni, vedere <A href="lync-server-2013-assign-policies-to-a-common-area-phone.md">assegnare criteri in Lync Server 2013 a un telefono di area comune</A>.



</div>

<div>

## <a name="disabling-hot-desking"></a>Disabilitazione di Hot desking

  - Per disabilitare l'hot desking per un telefono di area comune, reimpostare il parametro EnableHotdesking del cmdlet **Set-CsClientPolicy** sul valore predefinito false. Ad esempio:
    
        Set-CsClientPolicy -Identity "CommonAreaPhonePolicy" - EnableHotdesking $False

</div>

Per informazioni dettagliate, vedere gli argomenti della Guida per il cmdlet [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) e il cmdlet [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

