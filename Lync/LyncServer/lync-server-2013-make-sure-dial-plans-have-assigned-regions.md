---
title: 'Lync Server 2013: accertarsi che i dial plan abbiano assegnato aree geografiche'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Make sure dial plans have assigned regions
ms:assetid: 3da3a907-0dbf-4440-b12f-370f94dd4c17
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425903(v=OCS.15)
ms:contentKeyID: 48183937
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4f9f9a67a65b870edd75259bca7c74a1fae2749f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534563"
---
# <a name="make-sure-dial-plans-lync-server-2013-have-assigned-regions"></a>Assicurarsi che i dial plan Lync Server 2013 abbiano assegnato aree geografiche

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2010-11-02_

Per i dial plan utilizzati per le conferenze telefoniche con accesso esterno deve essere specificata un'**Area per conferenze telefoniche con accesso esterno**, in modo che i numeri di accesso a tali conferenze vengano associati al dial plan appropriato. Quando si imposta un dial plan, si specifica l'area per conferenze telefoniche con accesso esterno applicabile. Quando quindi si crea il numero di accesso esterno, si selezionano le aree che associano il numero di accesso ai dial plan appropriati.

Poiché è importante specificare un'area per tutti i dial plan, è consigliabile utilizzare questa procedura per verificare che tutti i dial plan siano associati ad aree. Questo passaggio è facoltativo.

Utilizzare il cmdlet **Get-CsDialPlan** per verificare se l'area è impostata per tutti i dial plan di conferenza telefonica con accesso esterno. Se l'area non è inclusa nei dial plan, è possibile utilizzare il cmdlet **Set-CsDialPlan** per impostarla. È inoltre possibile utilizzare il pannello di controllo di Lync Server per aggiornare l'area in dial plan esistenti. Per informazioni dettagliate sull'utilizzo del pannello di controllo di Lync Server, vedere [Modify a dial plan in Lync server 2013](lync-server-2013-modify-a-dial-plan.md).

<div>

## <a name="to-verify-whether-dial-plans-have-the-region-property-set"></a>Per verificare se nei dial plan è impostata la proprietà relativa all'area

1.  Eseguire l'accesso al computer come membro del gruppo RTCUniversalServerAdmins oppure del ruolo **Cs-VoiceAdministrator**, **Cs-ServerAdministrator** o **CsAdministrator**.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

3.  Al prompt dei comandi eseguire il comando seguente:
    
        Get-CsDialPlan [-Identity <Identifier of the dial plans to be retrieved>]
    
    Ad esempio:
    
        Get-CsDialPlan
    
    In questo esempio vengono restituiti tutti i dial plan configurati per l'organizzazione.

4.  Esaminare i dial plan restituiti per identificare eventualmente quelli che non includono l'area di conferenza telefonica con accesso esterno. Per informazioni dettagliate, vedere la documentazione relativa a Lync Server Management Shell.

</div>

<div>

## <a name="to-set-the-region-property-for-a-dial-plan"></a>Per impostare la proprietà relativa all'area per un dial plan

1.  Eseguire l'accesso al computer come membro del gruppo RTCUniversalServerAdmins oppure del ruolo **Cs-VoiceAdministrator**, **Cs-ServerAdministrator** o **CsAdministrator**.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

3.  Per gli eventuali dial plan che non includono l'area di conferenza telefonica con accesso esterno, eseguire:
    
        Set-CsDialPlan [-Identity <Identity of the dial plan to be modified>] -DialinConferencingRegion "<new region>"
    
    Ad esempio:
    
        Set-CsDialPlan -Identity Redmond -DialinConferencingRegion "US West Coast"
    
    In questo esempio il dial plan con Identity Redmond viene modificato per impostare la proprietà DialinConferencingRegion su "US West Coast". Per informazioni dettagliate, vedere la documentazione relativa a Lync Server Management Shell.

</div>

</div>

<span> </span>

</div>

</div>

</div>

