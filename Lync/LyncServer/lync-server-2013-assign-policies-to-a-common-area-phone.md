---
title: 'Lync Server 2013: assegnare criteri a un telefono di area comune'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign policies to a common area phone
ms:assetid: f0554fd1-b237-49b3-9eb4-26f4b91f5604
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994082(v=OCS.15)
ms:contentKeyID: 51803993
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7a6403092daa1a8cd84d246f2bd3bdece7661fef
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499463"
---
# <a name="assign-policies-in-lync-server-2013-to-a-common-area-phone"></a>Assegnare criteri in Lync Server 2013 a un telefono di area comune

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-20_

Dopo aver creato i criteri per i telefoni delle aree comuni (per informazioni dettagliate, vedere [creare un criterio vocale e configurare i record di utilizzo PSTN in Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)), è possibile assegnare il criterio a un telefono di area comune utilizzando Windows PowerShell e il cmdlet **Grant-CS** appropriato. Questi cmdlet possono essere eseguiti da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync Server 2010 using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>


<div>

## <a name="assigning-a-policy-to-a-single-common-area-phone"></a>Assegnazione di un criterio a un singolo telefono di area comune

  - Il comando seguente assegna il criterio vocale per utente RedmondVoice al telefono di area comune con la lobby Identity Building 14.
    
        Grant-CsVoicePolicy -Identity "Building 14 Lobby" -PolicyName "RedmondVoicePolicy"

</div>

<div>

## <a name="assigning-a-policy-to-multiple-common-area-phones"></a>Assegnazione di un criterio a più telefoni delle aree comuni

  - In questo esempio, il criterio vocale per utente RedmondVoice viene assegnato a tutti i telefoni delle aree comuni configurati per l'utilizzo nell'organizzazione.
    
        Get-CsCommonAreaPhone | Grant-CsVoicePolicy  -PolicyName "RedmondVoicePolicy"

</div>

Per informazioni dettagliate, vedere gli argomenti della Guida relativi a [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsVoicePolicy).

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Get-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

