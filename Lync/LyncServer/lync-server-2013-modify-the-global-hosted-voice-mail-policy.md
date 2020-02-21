---
title: 'Lync Server 2013: modificare il criterio di segreteria telefonica ospitata globalmente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify the global hosted voice mail policy
ms:assetid: f059b3ce-a7d8-4ea9-b10b-0052222ec2ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412994(v=OCS.15)
ms:contentKeyID: 48185757
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 88d0e29981df18ed883d6c33fb810d86da09d255
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184799"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="modify-the-global-hosted-voice-mail-policy-in-lync-server-2013"></a>Modificare i criteri globali di segreteria telefonica ospitata in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-24_

I criteri di segreteria telefonica *globale* ospitati sono installati con Lync Server 2013. È possibile modificarli in base a specifiche esigenze, ma non è possibile rinominarli né eliminarli. Per modificare i criteri globali, utilizzare il cmdlet Set-CsHostedVoicemailPolicy per impostare i parametri sui valori appropriati per la distribuzione.

Per informazioni dettagliate sul cmdlet [Set-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy) , vedere la documentazione di Lync Server Management Shell.

<div>

## <a name="to-modify-the-global-hosted-voice-mail-policy"></a>Per modificare i criteri globali di segreteria telefonica ospitata

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

2.  Eseguire il cmdlet Set-CsHostedVoicemailPolicy per impostare i parametri dei criteri globali per l'ambiente. Ad esempio, eseguire:
    
        Set-CsHostedVoicemailPolicy -Destination ExUM.fabrikam.com -Organization "corp1.litwareinc.com"
    
    Poiché questo comando non specifica il parametro Identity del criterio, l'interfaccia della riga di comando di Windows PowerShell imposta i seguenti valori sui criteri di segreteria telefonica ospitata globale:
    
      - **Destination** specifica il nome di dominio completo (FQDN) del servizio Messaggistica unificata di Exchange ospitato. Questo parametro è facoltativo, ma se si tenta di abilitare un utente per la segreteria telefonica ospitata e il criterio assegnato all'utente non dispone di un valore Destination, l'abilitazione avrà esito negativo.
    
      - L' **organizzazione** specifica un elenco delimitato da virgole dei tenant di Exchange che gli utenti di Lync Server Home. Ogni tenant deve essere specificato come FQDN sul tenant nel servizio di messaggistica unificata di Exchange ospitato.
    
    <div>
    

    > [!NOTE]  
    > Nell'esempio di cmdlet precedente, il valore "corp1.litwareinc.com" sostituisce eventuali valori già presenti nel parametro Organization. Se ad esempio i criteri contengono già un elenco di organizzazioni delimitate da virgola, l'elenco completo verrà sostituito. Se si desidera aggiungere un'organizzazione all'elenco anziché sostituire l'intero elenco, eseguire un comando analogo al seguente.

    
    </div>
    
        $a = Get-CsHostedVoicemailPolicy
        $a.Organization += ",corp3.litwareinc.com"
        Set-CsHostedVoicemailPolicy -Organization $a.Organization

</div>

</div>

<span> </span>

</div>

</div>

</div>

