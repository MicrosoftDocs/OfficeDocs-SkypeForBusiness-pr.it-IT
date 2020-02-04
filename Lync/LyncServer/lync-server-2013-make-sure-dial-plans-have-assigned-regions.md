---
title: 'Lync Server 2013: Verificare che ai dial plan siano state assegnate aree'
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
ms.openlocfilehash: cd8790671157b823464a3b4b594ea8428a888f46
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739606"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="make-sure-dial-plans-lync-server-2013-have-assigned-regions"></a>Assicurarsi che i dial plan di Lync Server 2013 abbiano assegnato aree geografiche

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2010-11-02_

I dial plan usati per i servizi di conferenza telefonica con accesso esterno devono essere specificati nell' **area** dei servizi di conferenza telefonica con accesso esterno con il dial plan appropriato. Quando si configura un dial plan, si specifica l'area dei servizi di conferenza telefonica con accesso esterno che si applica a tale dial plan. Quando si crea il numero di accesso per la chiamata in ingresso, si selezionano le aree geografiche che associano il numero di accesso con i dial plan appropriati.

Poiché è importante specificare un'area geografica per tutti i dial plan, è consigliabile usare questa procedura per verificare che tutti i dial plan abbiano aree geografiche. Questo passaggio è facoltativo.

Usa il cmdlet **Get-CsDialPlan** per verificare se l'area geografica è impostata per tutti i piani di conferenza telefonica con accesso esterno. Se l'area non è presente nei dial plan, è possibile usare il cmdlet **Set-CsDialPlan** per impostare l'area geografica. È anche possibile usare il pannello di controllo di Lync Server per aggiornare l'area nei dial plan esistenti. Per informazioni dettagliate sull'uso del pannello di controllo di Lync Server, vedere [modificare un dial plan in Lync server 2013](lync-server-2013-modify-a-dial-plan.md).

<div>

## <a name="to-verify-whether-dial-plans-have-the-region-property-set"></a>Per verificare se i dial plan hanno la proprietà Region impostata

1.  Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo **Cs-voiceadministrator**, **Cs-ServerAdministrator**o **CsAdministrator** .

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

3.  Eseguire la procedura seguente al prompt dei comandi:
    
        Get-CsDialPlan [-Identity <Identifier of the dial plans to be retrieved>]
    
    Ad esempio:
    
        Get-CsDialPlan
    
    In questo esempio vengono restituiti tutti i dial plan configurati per l'organizzazione.

4.  Esaminare i piani di chiamata restituiti per identificare gli elementi mancanti nell'area dei servizi di conferenza telefonica con accesso esterno. Per informazioni dettagliate, vedere la documentazione di Lync Server Management Shell.

</div>

<div>

## <a name="to-set-the-region-property-for-a-dial-plan"></a>Per impostare la proprietà Region per un dial plan

1.  Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo **Cs-voiceadministrator**, **Cs-ServerAdministrator**o **CsAdministrator** .

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

3.  Per gli eventuali dial plan mancanti dell'area di conferenza telefonica con accesso esterno, eseguire:
    
        Set-CsDialPlan [-Identity <Identity of the dial plan to be modified>] -DialinConferencingRegion "<new region>"
    
    Ad esempio:
    
        Set-CsDialPlan -Identity Redmond -DialinConferencingRegion "US West Coast"
    
    In questo esempio, il dial plan con l'identità di Redmond viene modificato per impostare la proprietà DialinConferencingRegion su "US West Coast". Per informazioni dettagliate, vedere la documentazione di Lync Server Management Shell.

</div>

</div>

<span> </span>

</div>

</div>

</div>

