---
title: 'Lync Server 2013: creare un criterio di segreteria telefonica ospitata per utente'
description: 'Lync Server 2013: creare un criterio di segreteria telefonica ospitata per utente.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a per-user hosted voice mail policy
ms:assetid: 39018a7c-e0c3-46a2-be4e-05604ec67a50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425867(v=OCS.15)
ms:contentKeyID: 48183902
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de528ceb9bc01114948c276c27f99039658aee38
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563192"
---
# <a name="create-a-per-user-hosted-voice-mail-policy-in-lync-server-2013"></a>Creare criteri di segreteria telefonica ospitata per utente in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-24_

Un criterio *per utente* può avere effetto solo su singoli utenti, gruppi e oggetti contatto. Per distribuire un criterio per utente, è necessario assegnarlo esplicitamente a uno o più utenti, gruppi o oggetti contatto. Per ulteriori informazioni, vedere [assegnare criteri di segreteria telefonica ospitata per utente in Lync Server 2013](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md).

Per informazioni dettagliate sull'utilizzo dei criteri di segreteria telefonica ospitata per utente, vedere la documentazione di Lync Server Management Shell relativa ai cmdlet seguenti:

  - [New-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsHostedVoicemailPolicy)

  - [Set-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy)

  - [Get-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsHostedVoicemailPolicy)

<div>

## <a name="to-create-a-per-user-hosted-voice-mail-policy"></a>Per creare un criterio segreteria telefonica ospitata per utente

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

2.  Eseguire il cmdlet New-CsHostedVoicemailPolicy per creare il criterio, ad esempio:
    
        New-CsHostedVoicemailPolicy -Identity ExRedmond -Destination ExUM.fabrikam.com -Description "Hosted voice mail policy for Redmond users." -Organization "corp1.litwareinc.com, corp2.litwareinc.com"
    
    Nell'esempio precedente viene creato un criterio segreteria telefonica ospitata con ambito per utente e vengono impostati i parametri seguenti:
    
      - **Identity** specifica un identificatore univoco per il criterio, che include l'ambito. Per un criterio con ambito per utente, questo valore di parametro viene specificato come stringa semplice, ad esempio ExRedmond.
    
      - **Destination** specifica il nome di dominio completo (FQDN) del servizio Messaggistica unificata di Exchange ospitato. Questo parametro è facoltativo, ma se si tenta di abilitare un utente per la segreteria telefonica ospitata e il criterio assegnato all'utente non dispone di un valore Destination, l'abilitazione avrà esito negativo.
    
      - **Description** fornisce informazioni descrittive facoltative sul criterio.
    
      - L' **organizzazione** specifica un elenco delimitato da virgole dei tenant di Exchange che ospitano gli utenti di Lync Server 2013. Ogni tenant deve essere specificato come FQDN del tenant nel servizio Messaggistica unificata di Exchange ospitato.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Assegnare criteri di segreteria telefonica ospitata per utente in Lync Server 2013](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

