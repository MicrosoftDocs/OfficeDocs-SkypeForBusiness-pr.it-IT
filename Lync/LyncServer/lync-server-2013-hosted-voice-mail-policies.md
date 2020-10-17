---
title: 'Lync Server 2013: criteri di segreteria telefonica ospitata'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted voice mail policies
ms:assetid: d62a35ed-cbe2-4f06-86b4-e192c18435c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398932(v=OCS.15)
ms:contentKeyID: 48185506
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e72fd57b05e618f03382a19995beaf9c542dc859
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504173"
---
# <a name="hosted-voice-mail-policies-in-lync-server-2013"></a>Criteri di segreteria telefonica ospitata in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-01_

Un *criterio di segreteria telefonica ospitata* fornisce informazioni all'applicazione di routing di Lync Server 2013 ExUM in cui instradare le chiamate per gli utenti le cui cassette postali si trovano in un servizio di Exchange ospitato.

<div>


> [!NOTE]  
> I criteri di segreteria telefonica ospitata sono necessari solo per l'integrazione di Lync Server 2013 con messaggistica unificata di Exchange ospitata Non sono necessari per l'integrazione con la messaggistica unificata di Exchange locale.



</div>

<div>

## <a name="hosted-voice-mail-policy-scope"></a>Ambito del criterio di segreteria telefonica ospitata

L'ambito dei criteri di segreteria telefonica ospitata determina il livello gerarchico a cui si applica il criterio. È possibile configurare i criteri di segreteria telefonica ospitata con i livelli di ambito seguenti:

  - Il criterio *globale* può potenzialmente influire su tutti gli utenti nella distribuzione di Lync Server 2013. Se un utente è abilitato per l'accesso alla messaggistica unificata di Exchange ospitata e non è stato assegnato un criterio per utente, e se non è stato assegnato un criterio sito al sito dell'utente, viene applicato il criterio globale. Il criterio globale viene installato con Lync Server 2013. È possibile modificarli in base a specifiche esigenze, ma non è possibile rinominarli né eliminarli.

  - Un criterio *sito* può influire su tutti gli utenti ospitati nel sito per cui è definito il criterio. Se un utente è configurato per l'accesso alla messaggistica unificata di Exchange ospitata e non è stato assegnato un criterio per utente, viene applicato il criterio sito.

  - Un criterio *per utente* può influire solo su singoli utenti o gruppi. Per applicare un criterio per utente, è necessario assegnare esplicitamente il criterio a singoli utenti, gruppi e oggetti contatto.

<div>


> [!NOTE]  
> Nella maggior parte dei casi, è necessario un solo criterio di segreteria telefonica ospitata. Spesso è possibile modificare il criterio globale per soddisfare tutte le esigenze. Se si distribuiscono più criteri di segreteria telefonica ospitata, tutti i criteri di questo tipo hanno ambito per utente.



</div>

</div>

<div>

## <a name="hosted-voice-mail-policy-attributes"></a>Attributi del criterio di segreteria telefonica ospitata

Un criterio di segreteria telefonica definisce due attributi che l'applicazione di routing di Lync Server 2013 ExUM inserisce nell'URI della richiesta di un messaggio di invito inviato all'implementazione di messaggistica unificata di Exchange ospitata:

  - **Destinazione:** Il nome di dominio completo (FQDN) del servizio di messaggistica unificata di Exchange ospitata. Questo valore viene utilizzato dal server perimetrale di Lync Server locale per scopi di routing.
    
    <div>
    

    > [!NOTE]  
    > Per Exchange Online, l'FQDN è exap.um.outlook.com.

    
    </div>

  - **Organizzazione:** Il nome di dominio completo del tenant nel servizio di messaggistica unificata di Exchange ospitato che ospita le cassette postali degli utenti di Lync Server 2013. Un criterio di segreteria telefonica può contenere più organizzazioni. Se nel criterio è inclusa più di un'organizzazione, questo attributo deve essere un elenco separato da virgole dei tenant del server Exchange che ospita le cassette postali degli utenti di Lync Server 2013.

<div>


> [!NOTE]  
> L'amministratore tenant del servizio di messaggistica unificata di Exchange ospitato fornirà i valori necessari per le impostazioni degli attributi di destinazione e dell'organizzazione. Per configurare i criteri, è necessario eseguire il cmdlet New-CsHostedVoicemailPolicy o utilizzare il cmdlet Set-CsHostedVoicemailPolicy per modificarne uno esistente, ad esempio il criterio globale.



</div>

Per informazioni dettagliate sulla gestione dei criteri di segreteria telefonica ospitata, vedere la documentazione di Lync Server Management Shell relativa ai cmdlet seguenti:

  - New-CsHostedVoicemailPolicy

  - Set-CsHostedVoicemailPolicy

  - Get-CsHostedVoicemailPolicy

</div>

<div>

## <a name="per-user-voice-mail-policy-assignment"></a>Per-User assegnazione dei criteri di segreteria telefonica

Se il criterio di segreteria telefonica ospitata è definito con ambito per utente, è necessario assegnarlo in modo esplicito. È possibile eseguire il cmdlet Grant-CsHostedVoicemailPolicy per assegnare il criterio a singoli utenti o gruppi.

Per informazioni dettagliate sull'assegnazione o la rimozione di criteri di segreteria telefonica ospitata per utente, vedere la documentazione di Lync Server Management Shell relativa ai cmdlet seguenti:

  - Grant-CsHostedVoicemailPolicy

  - Remove-CsHostedVoicemailPolicy

</div>

</div>

<span> </span>

</div>

</div>

</div>

