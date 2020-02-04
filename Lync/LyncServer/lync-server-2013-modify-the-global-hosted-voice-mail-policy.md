---
title: 'Lync Server 2013: modificare i criteri di segreteria telefonica ospitata globale'
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
ms.openlocfilehash: e930e0b1f9a6e2d246a8011c59e2c92c75ba138d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756880"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-the-global-hosted-voice-mail-policy-in-lync-server-2013"></a>Modificare i criteri di segreteria telefonica ospitata globale in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-24_

Il criterio di segreteria telefonica ospitata *globale* viene installato con Lync Server 2013. È possibile modificarla in base alle proprie esigenze, ma non è possibile rinominarla o eliminarla. Per modificare il criterio globale, puoi usare il cmdlet Set-CsHostedVoicemailPolicy per impostare i parametri per i valori appropriati per la tua specifica distribuzione.

Per informazioni dettagliate sul cmdlet [Set-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy) , vedere la documentazione di Lync Server Management Shell.

<div>

## <a name="to-modify-the-global-hosted-voice-mail-policy"></a>Per modificare il criterio di segreteria telefonica ospitata globale

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

2.  Eseguire il cmdlet Set-CsHostedVoicemailPolicy per impostare i parametri di criteri globali per l'ambiente. Ad esempio, eseguire:
    
        Set-CsHostedVoicemailPolicy -Destination ExUM.fabrikam.com -Organization "corp1.litwareinc.com"
    
    Poiché questo comando non specifica il parametro Identity del criterio, l'interfaccia della riga di comando di Windows PowerShell imposta i valori seguenti nel criterio della segreteria telefonica ospitata globale:
    
      - **Destination** specifica il nome di dominio completo (FQDN) del servizio di messaggistica unificata di Exchange ospitata. Questo parametro è facoltativo, ma se tenti di abilitare un utente per la segreteria telefonica ospitata e il criterio assegnato dall'utente non ha un valore di destinazione, l'opzione di abilitazione avrà esito negativo.
    
      - L' **organizzazione** specifica un elenco delimitato da virgole dei tenant di Exchange che ospitano utenti di Lync Server. Ogni tenant deve essere specificato come FQDN del tenant nel servizio di messaggistica unificata di Exchange ospitata.
    
    <div>
    

    > [!NOTE]  
    > Nel cmdlet di esempio precedente il valore "corp1.litwareinc.com" sostituisce qualsiasi valore che potrebbe essere già presente nel parametro Organization. Ad esempio, se il criterio contiene già un elenco delimitato da virgole di organizzazioni, l'elenco completo verrebbe sostituito. Se si vuole aggiungere un'organizzazione all'elenco anziché sostituire l'intero elenco, eseguire un comando simile al seguente.

    
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

