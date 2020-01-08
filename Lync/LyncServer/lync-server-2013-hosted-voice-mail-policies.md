---
title: 'Lync Server 2013: Criteri di segreteria telefonica ospitata'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Hosted voice mail policies
ms:assetid: d62a35ed-cbe2-4f06-86b4-e192c18435c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398932(v=OCS.15)
ms:contentKeyID: 48185506
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a23f5fa67a34d479bbc5b9d5c9bf55071b187c1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985057"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-voice-mail-policies-in-lync-server-2013"></a>Criteri di segreteria telefonica ospitata in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-01_

Un criterio di segreteria *telefonica ospitata* fornisce informazioni all'applicazione di routing di Lync Server 2013 ExUM su dove instradare le chiamate per gli utenti le cui cassette postali si trovano in un servizio di Exchange ospitata.

<div>


> [!NOTE]  
> I criteri di segreteria telefonica ospitati sono obbligatori solo per l'integrazione di Lync Server 2013 con messaggistica unificata ospitata. Non sono necessarie per l'integrazione con la messaggistica unificata di Exchange locale.



</div>

<div>

## <a name="hosted-voice-mail-policy-scope"></a>Ambito dei criteri di segreteria telefonica ospitata

L'ambito dei criteri di segreteria telefonica ospitata determina il livello gerarchico a cui si applicano i criteri. È possibile configurare i criteri di segreteria telefonica ospitata con i livelli di ambito seguenti:

  - Il criterio *globale* può potenzialmente interessare tutti gli utenti della distribuzione di Lync Server 2013. Se un utente è abilitato per l'accesso alla messaggistica unificata di Exchange ospitata e non è stato assegnato un criterio per utente e se al sito dell'utente non è stato assegnato un criterio per il sito, viene applicato il criterio globale. Il criterio globale viene installato con Lync Server 2013. È possibile modificarla in base alle proprie esigenze, ma non è possibile rinominarla o eliminarla.

  - I criteri del *sito* possono influire su tutti gli utenti ospitati nel sito per cui sono definiti i criteri. Se un utente è configurato per l'accesso alla messaggistica unificata di Exchange ospitata e non è stato assegnato un criterio per utente, verranno applicati i criteri del sito.

  - Un criterio *per utente* può interessare solo singoli utenti o gruppi. Per applicare un criterio per utente, è necessario assegnare esplicitamente il criterio a singoli utenti, gruppi e oggetti contatto.

<div>


> [!NOTE]  
> Nella maggior parte dei casi è necessario un solo criterio di segreteria telefonica ospitata. È spesso possibile modificare il criterio globale in base alle proprie esigenze. Se si distribuiscono più criteri per la segreteria telefonica ospitata, tutti questi criteri hanno un ambito per utente.



</div>

</div>

<div>

## <a name="hosted-voice-mail-policy-attributes"></a>Attributi dei criteri di segreteria telefonica ospitata

Un criterio per la segreteria telefonica definisce due attributi che l'applicazione di routing di Lync Server 2013 ExUM viene inserita nell'URI della richiesta di un messaggio di invito inviato all'implementazione della messaggistica unificata di Exchange ospitata:

  - **Destinazione:** Il nome di dominio completo (FQDN) del servizio di messaggistica unificata di Exchange ospitata. Questo valore viene usato dal server perimetrale locale di Lync Server per scopi di routing.
    
    <div>
    

    > [!NOTE]  
    > Il nome di dominio completo per Exchange Online è exap.um.outlook.com.

    
    </div>

  - **Organizzazione:** Il nome di dominio completo del tenant nel servizio di messaggistica unificata di Exchange ospitata per le cassette postali degli utenti di Lync Server 2013. Un criterio per la segreteria telefonica può contenere più organizzazioni. Se nel criterio è inclusa più di un'organizzazione, questo attributo deve essere un elenco delimitato da virgole dei tenant di Exchange Server che ospitano le cassette postali degli utenti di Lync Server 2013.

<div>


> [!NOTE]  
> L'amministratore del tenant del servizio di messaggistica unificata di Exchange ospitata fornirà i valori necessari per le impostazioni dell'attributo di destinazione e organizzazione. Per configurare i criteri, è necessario eseguire il cmdlet New-CsHostedVoicemailPolicy o usare il cmdlet Set-CsHostedVoicemailPolicy per modificarne uno esistente, ad esempio il criterio globale.



</div>

Per informazioni dettagliate sulla gestione dei criteri di segreteria telefonica ospitata, vedere la documentazione di Lync Server Management Shell per i cmdlet seguenti:

  - New-CsHostedVoicemailPolicy

  - Set-CsHostedVoicemailPolicy

  - Get-CsHostedVoicemailPolicy

</div>

<div>

## <a name="per-user-voice-mail-policy-assignment"></a>Assegnazione dei criteri per la segreteria telefonica per utente

Se i criteri per la segreteria telefonica ospitata sono definiti con ambito per utente, è necessario assegnarlo esplicitamente. Puoi eseguire il cmdlet Grant-CsHostedVoicemailPolicy per assegnare i criteri a singoli utenti o gruppi.

Per informazioni dettagliate sull'assegnazione o la rimozione di un criterio di segreteria telefonica ospitata per utente, vedere la documentazione di Lync Server Management Shell per i cmdlet seguenti:

  - Grant-CsHostedVoicemailPolicy

  - Remove-CsHostedVoicemailPolicy

</div>

</div>

<span> </span>

</div>

</div>

</div>

