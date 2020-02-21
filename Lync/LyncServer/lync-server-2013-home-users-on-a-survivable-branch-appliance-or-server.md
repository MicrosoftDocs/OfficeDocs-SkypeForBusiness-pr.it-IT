---
title: 'Lync Server 2013: Home Users on a Survivable Branch Appliance o server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Home users on a Survivable Branch Appliance or Server
ms:assetid: faf1ebb9-6d7d-4a58-8ff7-801b7b31d3ba
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413066(v=OCS.15)
ms:contentKeyID: 48185926
ms.date: 12/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f6fb176025dd7f075429833e48b53eb1f7a5b07
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204624"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="home-users-on-a-survivable-branch-appliance-or-server-in-lync-server-2013"></a>Utenti domestici in un Survivable Branch Appliance o server in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-12-10_

Il processo di homing degli utenti in un Survivable Branch Appliance o Survivable Branch Server è simile al processo di homing degli utenti in un pool Front end. Eseguire la procedura Survivable Branch Appliance o Survivable Branch Server nel sito centrale.

<div>

## <a name="to-home-users-on-survivable-branch-appliance-or-survivable-branch-server"></a>Per gli utenti privati di Survivable Branch Appliance o Survivable Branch Server

1.  Prima di spostare gli utenti nel Survivable Branch Server o nel Survivable Branch Server, aprire Lync Server Management Shell e quindi eseguire tutte le operazioni seguenti:
    
      - Eseguire il cmdlet **Test-CsPstnOutboundCall** per verificare che il Survivable Branch Server sia in esecuzione e che sia configurata la connettività PSTN (Public Switched Telephone Network). Se è necessario modificare le proprietà del gateway PSTN, utilizzare il cmdlet **Set-CsPstnGateway**.
    
      - Eseguire il cmdlet **Get-CsVoicePolicy** per verificare che gli utenti che verranno ospitati nel Survivable Branch Server dispongano del criterio di routing VoIP appropriato. Se è necessario modificare il criterio VoIP, utilizzare il cmdlet **Set-CsVoicePolicy**.
    
      - Eseguire il cmdlet **Get-CsVoicemailReroutingConfiguration** per verificare che le impostazioni di reinstradamento della segreteria telefonica siano configurate. Se è necessario modificare le impostazioni di reinstradamento della segreteria telefonica, utilizzare il cmdlet **Set-CsVoicemailReroutingConfiguration**.

2.  In Lync Server Management Shell, eseguire il cmdlet **Move-CsUser** per spostare gli utenti privati.

<div>


> [!NOTE]  
> È inoltre possibile utilizzare il pannello di controllo di Lync Server per verificare i prerequisiti e gli utenti privati.



</div>

<div>


> [!NOTE]  
> Gli utenti ospitati in un Survivable Branch Appliance di Lync Server non sono in grado di creare nuove chat room o di visualizzare la scheda sala per le sale esistenti.



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

