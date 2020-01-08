---
title: 'Lync Server 2013: abilitare o disabilitare la scrivania a caldo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable or disable hot desking
ms:assetid: 93a7fed6-f61a-4b41-9336-a8320afa87cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994057(v=OCS.15)
ms:contentKeyID: 51803968
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f5d9f2d168a06b5624375dcd005da58b4d3d5fd8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976475"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-hot-desking-in-lync-server-2013"></a>Abilitare o disabilitare le scrivanie a caldo in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-20_

È possibile configurare telefoni per l'area comune come *telefoni da tavolo caldo*. Con i telefoni da tavolo caldo, gli utenti possono accedere al proprio account utente e, dopo aver effettuato l'accesso, usare le caratteristiche di Lync Server e le proprie impostazioni del profilo utente. L'uso di scrivanie a caldo viene gestito con i criteri client: per abilitare o disabilitare il servizio di desktop caldo, è necessario modificare i criteri client usati dai telefoni delle aree comuni. Per informazioni dettagliate su come determinare i criteri di conferenza assegnati ai telefoni delle aree comuni, vedere visualizzare le [informazioni sul telefono per le aree comuni in Lync Server 2013](lync-server-2013-view-common-area-phone-information.md).

Puoi usare il parametro EnableHotdesking del cmdlet **New-CsClientPolicy** o il cmdlet **Set-CsClientPolicy** per abilitare o disabilitare il servizio di desktop a caldo in un telefono, come indicato di seguito. Eseguire questi cmdlet da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.

<div>


<div>

## <a name="enabling-hot-desking"></a>Abilitazione del desktop a caldo

  - Per abilitare il desktop a caldo per un telefono con area comune, è necessario modificare i criteri client assegnati al telefono o alla raccolta di telefoni.
    
    Dopo aver identificato i criteri che devono essere modificati, il passaggio successivo consiste nell'usare il cmdlet **Set-CsClientPolicy** per impostare il parametro EnableHotdesking su true. Ad esempio:
    
        Set-CsClientPolicy -Identity "CommonAreaPhonePolicy" - EnableHotdesking $True

  - In alternativa, puoi usare il cmdlet **New-CsClientPolicy** per creare un nuovo criterio client che consente la creazione di scrivanie a caldo. Ad esempio:
    
        New-CsClientPolicy -Identity "NewCommonAreaPhonePolicy" - EnableHotdesking $True

</div>

<div>


> [!IMPORTANT]  
> Dopo aver creato questo criterio, è necessario assegnarlo ai telefoni dell'area comune appropriati. Per informazioni dettagliate, vedere <A href="lync-server-2013-assign-policies-to-a-common-area-phone.md">assegnare criteri in Lync Server 2013 a un telefono con area comune</A>.



</div>

<div>

## <a name="disabling-hot-desking"></a>Disabilitazione della scrivania calda

  - Per disabilitare il desktop caldo per un telefono con area comune, reimpostare il parametro EnableHotdesking del cmdlet **Set-CsClientPolicy** sul valore predefinito false. Ad esempio:
    
        Set-CsClientPolicy -Identity "CommonAreaPhonePolicy" - EnableHotdesking $False

</div>

Per informazioni dettagliate, vedere gli argomenti della Guida relativi al cmdlet [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) e al cmdlet [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

