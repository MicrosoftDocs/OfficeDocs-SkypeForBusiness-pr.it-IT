---
title: 'Lync Server 2013: configurazione della funzionalità di escape per la posta vocale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring voice mail escape
ms:assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688157(v=OCS.15)
ms:contentKeyID: 49733761
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 43e5ec9a9f932b9c8970886daf439bae6934d36b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154128"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-voice-mail-escape-in-lync-server-2013"></a>Configurazione della funzionalità di escape della segreteria telefonica in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-22_

Quando un utente configura lo squillo simultaneo su un telefono cellulare, un chiamante in genere viene instradato alla segreteria telefonica personale dell'utente se il telefono cellulare è spento, scarico o in una zona senza copertura. Con Lync Server 2013, gli utenti possono scegliere di fare in modo che le chiamate relative alle aziende vengano instradate al sistema di segreteria telefonica aziendale. In particolare, è possibile configurare un timer e, se la chiamata viene risolta dalla segreteria telefonica del gestore entro l'intervallo di tempo definito, Lync Server si disconnette dal sistema di caselle vocali del gestore e dalla segreteria telefonica personale dell'utente, mentre l'utente rimane gli endpoint nel sistema aziendale continuano a squillare. In questo modo il chiamante viene instradato automaticamente alla segreteria telefonica aziendale dell'utente.

Questa configurazione viene eseguita utilizzando il cmdlet di Lync Server Management Shell, **Set-CsVoicePolicy**, a livello di criteri vocali, con i parametri seguenti.

<div>

## <a name="to-configure-voice-mail-escape"></a>Per configurare l'escape per la posta vocale

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

2.  Specificare i parametri seguenti per **Set-CsVoicePolicy**:
    
      - **EnableVoicemailEscapeTimer** - Consente di abilitare o disabilitare il timer di escape.
    
      - **PSTNVoicemailEscapeTimer** - Consente di specificare il valore di timeout in millisecondi. Il valore predefinito è 1500 millisecondi e i valori consentiti sono compresi tra 0 e 8000 millisecondi.

</div>

<div>

## <a name="example"></a>Esempio

    Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000
    
    Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Configurazione di criteri vocali e record utilizzo PSTN per autorizzare le funzionalità e i privilegi di chiamata in Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

