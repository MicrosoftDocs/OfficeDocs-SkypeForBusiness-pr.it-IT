---
title: 'Lync Server 2013: creare un criterio per la segreteria telefonica ospitata a livello di sito'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a site-level hosted voice mail policy
ms:assetid: 145892c8-a6ca-45fb-9e83-786f709dd775
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398216(v=OCS.15)
ms:contentKeyID: 48183481
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d9df91e28eeba8bc9769e4fcbeff6ebba2b3746d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984221"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-site-level-hosted-voice-mail-policy-in-lync-server-2013"></a>Creare un criterio di segreteria telefonica ospitata a livello di sito in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-24_

Un criterio di *sito* può avere un impatto su tutti gli utenti ospitati nel sito per cui sono definiti i criteri. Se un utente è configurato per l'accesso alla messaggistica unificata di Exchange ospitata e non è stato assegnato un criterio per utente, verranno applicati i criteri del sito. Se non è stato distribuito un criterio per il sito, si applicano i criteri globali.

Per informazioni dettagliate sulla configurazione dei criteri del sito, vedere la documentazione di Lync Server Management Shell per i cmdlet seguenti:

  - [New-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsHostedVoicemailPolicy)

  - [Set-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy)

  - [Get-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsHostedVoicemailPolicy)

<div>

## <a name="to-create-a-site-hosted-voice-mail-policy"></a>Per creare un criterio per la segreteria telefonica ospitata nel sito

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

2.  Eseguire il cmdlet New-CsHostedVoicemailPolicy per creare il criterio. Ad esempio, eseguire:
    
        New-CsHostedVoicemailPolicy -Identity site:Redmond -Destination ExUM.fabrikam.com -Description "Hosted voice mail policy for the Redmond site." -Organization "corp1.litwareinc.com, corp2.litwareinc.com"
    
    Questo esempio crea un criterio di segreteria telefonica ospitata con l'ambito del sito e imposta i parametri seguenti:
    
      - **Identity** specifica un identificatore univoco per il criterio, che include l'ambito. Per un criterio con ambito sito, il valore del parametro Identity deve essere specificato nel `site:` * \<nome\>* del formato, ad esempio `site:Redmond`.
    
      - **Destination** specifica il nome di dominio completo (FQDN) del servizio di messaggistica unificata di Exchange ospitata. Questo parametro è facoltativo, ma se tenti di abilitare un utente per la segreteria telefonica ospitata e il criterio assegnato dall'utente non ha un valore di destinazione, l'opzione di abilitazione avrà esito negativo.
    
      - **Descrizione** fornisce informazioni descrittive facoltative sui criteri.
    
      - **Organizzazione** specifica un elenco delimitato da virgole dei tenant di Exchange che ospitano gli utenti di Lync Server 2013. Ogni tenant deve essere specificato come FQDN del tenant nel servizio di messaggistica unificata di Exchange ospitata.

</div>

</div>

<span> </span>

</div>

</div>

</div>

