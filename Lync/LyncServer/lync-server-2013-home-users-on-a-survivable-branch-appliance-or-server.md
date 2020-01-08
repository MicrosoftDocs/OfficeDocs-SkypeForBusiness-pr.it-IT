---
title: 'Lync Server 2013: Ospitare utenti in Survivable Branch Appliance o Survivable Branch Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Home users on a Survivable Branch Appliance or Server
ms:assetid: faf1ebb9-6d7d-4a58-8ff7-801b7b31d3ba
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413066(v=OCS.15)
ms:contentKeyID: 48185926
ms.date: 12/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ceabf8fe7d8f9068e60bbc20406d2496f815b04b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980833"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="home-users-on-a-survivable-branch-appliance-or-server-in-lync-server-2013"></a>Ospitare utenti in Survivable Branch Appliance o Survivable Branch Server in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-12-10_

Il processo di homing degli utenti in un Survivable Branch Appliance o in un Survivable Branch Server è simile al processo di homing degli utenti in un pool Front-end. Eseguire la procedura Survivable Branch Appliance o Survivable Branch Server nel sito centrale.

<div>

## <a name="to-home-users-on-survivable-branch-appliance-or-survivable-branch-server"></a>Per gli utenti privati su Survivable Branch Appliance o Survivable Branch Server

1.  Prima di spostare gli utenti nel Survivable Branch Server o Survivable Branch Server, aprire Lync Server Management Shell e quindi eseguire tutte le operazioni seguenti:
    
      - Eseguire il cmdlet **Test-CsPstnOutboundCall** per verificare che il Survivable Branch Server sia in esecuzione e che sia configurata la connettività PSTN (Public Switched Telephone Network). Se è necessario modificare le proprietà del gateway PSTN, usare il cmdlet **Set-CsPstnGateway**.
    
      - Eseguire il cmdlet **Get-CsVoicePolicy** per verificare che gli utenti che verranno ospitati nel Survivable Branch Server dispongano dei criteri di routing VoIP appropriati. Se è necessario modificare i criteri VoIP, usare il cmdlet **Set-CsVoicePolicy**.
    
      - Eseguire il cmdlet **Get-CsVoicemailReroutingConfiguration** per verificare che le impostazioni di reinstradamento della segreteria telefonica siano configurate. Se è necessario modificare le impostazioni di reinstradamento della segreteria telefonica, usare il cmdlet **Set-CsVoicemailReroutingConfiguration**.

2.  In Lync Server Management Shell eseguire il cmdlet **Move-CsUser** per trasferire utenti privati.

<div>


> [!NOTE]  
> È anche possibile usare il pannello di controllo di Lync Server per verificare i prerequisiti e gli utenti privati.



</div>

<div>


> [!NOTE]  
> Gli utenti ospitati in un dispositivo Survivable Branch di Lync Server non riescono a creare nuove chat room o a visualizzare la scheda della sala per le camere esistenti.



</div>

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Test-CsPstnOutboundCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnOutboundCall)  
[Get-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicePolicy)  
[Get-CsVoicemailReroutingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicemailReroutingConfiguration)  
[Move-CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

