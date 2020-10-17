---
title: 'Lync Server 2013: creare un criterio di segreteria telefonica ospitata a livello di sito'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a site-level hosted voice mail policy
ms:assetid: 145892c8-a6ca-45fb-9e83-786f709dd775
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398216(v=OCS.15)
ms:contentKeyID: 48183481
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e23f14b1db7c846d5dbaa0aa6861274a7b6a2611
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501883"
---
# <a name="create-a-site-level-hosted-voice-mail-policy-in-lync-server-2013"></a>Creare un criterio di segreteria telefonica ospitata a livello di sito in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-24_

Un criterio a livello di *sito* può influire su tutti gli utenti situati nel sito per cui il criterio viene definito. Se un utente è configurato per l'accesso alla messaggistica unificata di Exchange ospitata e non gli è stato assegnato un criterio per utente, verrà applicato il criterio a livello di sito. Se non è stato distribuito un criterio a livello di sito, verrà applicato il criterio globale.

Per informazioni dettagliate sulla configurazione dei criteri di sito, vedere la documentazione di Lync Server Management Shell relativa ai cmdlet seguenti:

  - [New-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsHostedVoicemailPolicy)

  - [Set-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy)

  - [Get-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsHostedVoicemailPolicy)

<div>

## <a name="to-create-a-site-hosted-voice-mail-policy"></a>Per creare un criterio segreteria telefonica ospitata con ambito sito

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

2.  Eseguire il cmdlet New-CsHostedVoicemailPolicy per creare il criterio. Ad esempio, eseguire:
    
        New-CsHostedVoicemailPolicy -Identity site:Redmond -Destination ExUM.fabrikam.com -Description "Hosted voice mail policy for the Redmond site." -Organization "corp1.litwareinc.com, corp2.litwareinc.com"
    
    In questo esempio viene creato un criterio segreteria telefonica ospitata con ambito sito e vengono impostati i parametri seguenti:
    
      - **Identity** specifica un identificatore univoco per il criterio, che include l'ambito. Per un criterio con ambito sito, è necessario specificare il valore del parametro Identity nel formato `site:` *\<name\>* , ad esempio `site:Redmond` .
    
      - **Destination** specifica il nome di dominio completo (FQDN) del servizio Messaggistica unificata di Exchange ospitato. Questo parametro è facoltativo, ma se si tenta di abilitare un utente per la segreteria telefonica ospitata e il criterio assegnato all'utente non dispone di un valore Destination, l'abilitazione avrà esito negativo.
    
      - **Description** fornisce informazioni descrittive facoltative sul criterio.
    
      - L' **organizzazione** specifica un elenco delimitato da virgole dei tenant di Exchange che ospitano gli utenti di Lync Server 2013. Ogni tenant deve essere specificato come FQDN di quel tenant nel servizio di messaggistica unificata di Exchange ospitata.

</div>

</div>

<span> </span>

</div>

</div>

</div>

