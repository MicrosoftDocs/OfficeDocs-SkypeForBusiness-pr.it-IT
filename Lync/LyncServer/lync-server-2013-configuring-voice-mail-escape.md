---
title: 'Lync Server 2013: configurazione della posta in uscita della segreteria telefonica'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring voice mail escape
ms:assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688157(v=OCS.15)
ms:contentKeyID: 49733761
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f08e12b97c51d68b4b08d10692802cb035ce8f0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974331"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-voice-mail-escape-in-lync-server-2013"></a>Configurazione della posta in uscita della segreteria telefonica in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-22_

Quando un utente configura lo squillo simultaneo su un telefono cellulare, il chiamante viene in genere instradato alla segreteria telefonica personale dell'utente se il telefono cellulare è disattivato, non è più alimentato dalla batteria o fuori portata. Con Lync Server 2013, gli utenti possono scegliere di avere le chiamate correlate alle aziende instradate al sistema di segreteria telefonica aziendale. In particolare, è possibile configurare un timer e, se la chiamata viene risolta dalla segreteria telefonica del vettore entro l'intervallo di tempo definito, Lync Server si disconnette dal sistema di segreteria telefonica del gestore (e dalla segreteria telefonica personale dell'utente), mentre l'utente rimane gli endpoint nel sistema aziendale continuano a squillare. In questo modo, il chiamante viene indirizzato automaticamente alla segreteria telefonica aziendale dell'utente.

Questa configurazione viene eseguita usando il cmdlet Lync Server Management Shell, **Set-CsVoicePolicy**, a livello di criteri vocali, con i parametri seguenti.

<div>

## <a name="to-configure-voice-mail-escape"></a>Per configurare l'escape della segreteria telefonica

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

2.  Specificare i parametri seguenti per **Set-CsVoicePolicy**:
    
      - **EnableVoicemailEscapeTimer** -Abilita o Disabilita il timer di escape.
    
      - **PSTNVoicemailEscapeTimer** -specifica il valore di timeout in millisecondi. Il valore predefinito è 1500 millisecondi e il valore può variare da 0 millisecondi a 8000 millisecondi.

</div>

<div>

## <a name="example"></a>Esempio

    Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000
    
    Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Configurazione di criteri vocali e record utilizzo PSTN per autorizzare privilegi e funzionalità di chiamata in Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

