---
title: 'Lync Server 2013: visualizzare le informazioni del dial plan'
description: 'Lync Server 2013: visualizzare le informazioni sul dial plan.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View dial plan information
ms:assetid: 25ed0112-a8a7-418a-8c2c-580081be692a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687997(v=OCS.15)
ms:contentKeyID: 49733587
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b4473302b182b8de4ea6aad12d7993cb5d442b7e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569692"
---
# <a name="view-dial-plan-information-in-lync-server-2013"></a>Visualizzare le informazioni sul dial plan in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-11-01_

Per visualizzare informazioni per un dial plan esistente, eseguire i passaggi illustrati nella procedura seguente. Se si desidera creare un nuovo dial plan, vedere [creare un dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md).

<div>

## <a name="to-view-information-about-a-dial-plan-from-lync-server-control-panel"></a>Per visualizzare informazioni su un dial plan dal pannello di controllo di Lync Server

1.  Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Per informazioni dettagliate, vedere [delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **Routing vocale** e quindi su **Dial plan**.

4.  Nella pagina **Dial plan** fare doppio clic sul nome di un dial plan.
    
    <div>
    

    > [!NOTE]  
    > È possibile visualizzare informazioni per un solo dial plan alla volta.

    
    </div>

</div>

<div>

## <a name="to-view-dial-plans-by-using-windows-powershell-cmdlets"></a>Per visualizzare i dial plan tramite i cmdlet di Windows PowerShell

  - I dial plan possono essere visualizzati utilizzando l'interfaccia della riga di comando di Windows PowerShell e il cmdlet **Get-CsDialPlan** . Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync Server 2010 using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .
    
    Per visualizzare informazioni su tutti i dial plan, digitare il comando seguente in Lync Server Management Shell e quindi premere INVIO:
    
        Get-CsDialPlan
    
    Tale comando restituirà informazioni simili a quelle che seguono:
    
        Identity                 : Global
        Description              :
        DialinConferencingRegion :
        NormalizationRules       : {Description=;
                                   Pattern=^(\d+)$;Translation=$1;Name=
                                   KeepAll;IsInternalExtension=False}
        CountryCode              :
        State                    :
        City                     :
        ExternalAccessPrefix     :
        SimpleName               : DefaultProfile
        OptimizeDeviceDialing    : False

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Creare un dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md)  
[Modificare un dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

