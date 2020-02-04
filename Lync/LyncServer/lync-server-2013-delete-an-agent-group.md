---
title: 'Lync Server 2013: eliminare un gruppo di agenti'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an agent group
ms:assetid: df385fd1-62f4-42b7-a349-4eb38dea50c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182597(v=OCS.15)
ms:contentKeyID: 48185670
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eb8ebde61d1ba59952741bffd14e29ae87d482f8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736436"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-agent-group-in-lync-server-2013"></a>Eliminare un gruppo di agenti in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-11-01_

Per eliminare un gruppo di agenti, usare una delle procedure seguenti.

<div>

## <a name="to-use-lync-server-control-panel-to-delete-an-agent-group"></a>Per usare il pannello di controllo di Lync Server per eliminare un gruppo di agenti

1.  Accedere come membro del gruppo RTCUniversalServerAdmins o come membro di uno dei ruoli amministrativi predefiniti che supportano il gruppo di risposte.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Nella barra di spostamento sinistra fare clic su **gruppi di risposte**e quindi su **raggruppa**.

4.  Nella pagina **Response Groups** digitare tutto o parte del nome del gruppo di agenti che si desidera eliminare nel campo di ricerca.

5.  Nell'elenco risultante fare clic sul gruppo che si desidera eliminare, fare clic su **modifica**e quindi su **Elimina**.

6.  Fare clic su **OK**.

</div>

<div>

## <a name="to-use-windows-powershell-to-delete-an-agent-group"></a>Per usare Windows PowerShell per eliminare un gruppo di agenti

1.  Accedere come membro del gruppo RTCUniversalServerAdmins o come membro di uno dei ruoli amministrativi predefiniti che supportano il gruppo di risposte.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

3.  Nella riga di comando eseguire:
    
        Get-CsRgsAgentGroup -Identity <Application Server service> -Name "<name of agent group>" | Remove-CsRgsAgentGroup
    
    Ad esempio:
    
        Get-CsRgsAgentGroup -Identity service:ApplicationServer:redmond.contoso.com -Name "Human Resources" | Remove-CsRgsAgentGroup

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Creare o modificare un gruppo di agenti in Lync Server 2013](lync-server-2013-create-or-modify-an-agent-group.md)  


[Remove-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/Remove-CsRgsAgentGroup)  
[Get-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsAgentGroup)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

