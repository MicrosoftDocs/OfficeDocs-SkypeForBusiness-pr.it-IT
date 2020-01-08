---
title: 'Lync Server 2013: configurare una route vocale E9-1-1'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure an E9-1-1 voice route
ms:assetid: 6933b840-0e7b-4509-ae43-bc9065677547
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398496(v=OCS.15)
ms:contentKeyID: 48184384
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 59f4e2a6707d270f66a66663b19f975ac69961c2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978074"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-an-e9-1-1-voice-route-in-lync-server-2013"></a>Configurare una route vocale E9-1-1 in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-17_

Per distribuire E9-1-1, è prima di tutto necessario configurare una route vocale per le chiamate di emergenza. Per informazioni dettagliate sulla creazione di route vocali, vedere [creare una route vocale in Lync Server 2013](lync-server-2013-create-a-voice-route.md). Puoi definire più di una route se, ad esempio, la distribuzione include un trunk SIP principale e un trunk SIP secondario.

<div>


> [!NOTE]  
> Per includere le informazioni sulla posizione in un invito di E9-1-1, è necessario configurare il trunk SIP che si connette al provider di servizi E9-1-1 per instradare le chiamate di emergenza tramite il gateway. A questo scopo, imposta il contrassegno EnablePIDFLOSupport sul cmdlet <STRONG>Set-CsTrunkConfiguration</STRONG> su true. Il valore predefinito per EnablePIDFLOSupport è false. Per esempio:<CODE>Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.</CODE><BR>Non è necessario abilitare le posizioni di ricezione per i gateway PSTN (Public Switched Telephone Network) di fallback e i gateway ELIN (Emergency Location Identification Number).



</div>

Per informazioni dettagliate sull'uso delle route vocali, vedere la documentazione di Lync Server Management Shell per i cmdlet seguenti:

  - **Set-CsPstnUsage**

  - **Get-CsPstnUsage**

  - **New-CsVoiceRoute**

  - **Get-CsVoiceRoute**

  - **Set-CsVoiceRoute**

  - **Remove-CsVoiceRoute**

<div>

## <a name="to-configure-an-e9-1-1-voice-route"></a>Per configurare una route vocale E9-1-1

1.  Accedere al computer con un account membro dei gruppi RTCUniversalServerAdmins o un membro del ruolo di amministratore di CsVoiceAdministrator.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

3.  Eseguire il cmdlet seguente per creare un nuovo record di utilizzo PSTN.
    
    Deve essere lo stesso nome che verrà usato per l'impostazione **PSTN** nei criteri di posizione. Anche se la distribuzione avrà più record utilizzo telefono, nell'esempio seguente viene aggiunto "utilizzo delle emergenze" all'elenco corrente degli usi PSTN disponibili. Per informazioni dettagliate, vedere [configurazione di criteri vocali e record di utilizzo PSTN per autorizzare le funzionalità e i privilegi di chiamata in Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).
    
        Set-CsPstnUsage -Usage @{add='EmergencyUsage'}

4.  Eseguire il cmdlet seguente per creare una nuova route vocale usando il record di utilizzo PSTN creato nel passaggio precedente.
    
    Il pattern numerico deve essere lo stesso modello di numero usato nell'impostazione della **stringa di chiamata di emergenza** nei criteri di posizione. È necessario un segno "+" perché Lync aggiunge "+" alle chiamate di emergenza. "Co1-pstngateway-1" è l'ID del servizio trunk SIP per il provider di servizi E9-1-1 o per l'ID del servizio gateway ELIN. L'esempio seguente usa "EmergencyRoute" come nome della route vocale.
    
        New-CsVoiceRoute -Name "EmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="EmergencyUsage"} -PstnGatewayList @{add="co1-pstngateway-1"}

5.  Facoltativamente, per le connessioni trunk SIP, è consigliabile eseguire il cmdlet seguente per creare una route locale per le chiamate non gestite dal trunk SIP del provider di servizi E9-1-1. Questa route verrà usata se la connessione al provider di servizi E9-1-1 non è disponibile.
    
    L'esempio seguente presuppone che l'utente abbia un uso "locale" nei criteri vocali.
    
        New-CsVoiceRoute -Name "LocalEmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="Local"} -PstnGatewayList @{add="co1-pstngateway-2"}

</div>

</div>

<span> </span>

</div>

</div>

</div>

