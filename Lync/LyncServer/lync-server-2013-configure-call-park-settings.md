---
title: 'Lync Server 2013: configurare le impostazioni del parcheggio di chiamata'
description: 'Lync Server 2013: configurare le impostazioni del parcheggio di chiamata.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Call Park settings
ms:assetid: 3bed9d09-8363-4fff-a220-f0f6d3a81241
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425886(v=OCS.15)
ms:contentKeyID: 48183922
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e8862208a68c89151096349508a4c849a5649b70
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546642"
---
# <a name="configure-call-park-settings-in-lync-server-2013"></a>Configurare le impostazioni del parcheggio di chiamata in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-11-01_

Se non si desidera utilizzare le impostazioni predefinite del parcheggio di chiamata, è possibile personalizzarle. Quando si installa l'applicazione Parcheggio di chiamata, le impostazioni globali sono configurate per impostazione predefinita. È possibile modificarle, nonché specificare impostazioni specifiche del sito. Usare il cmdlet **New-CsCpsConfiguration** per creare nuove impostazioni specifiche del sito. Usare il cmdlet **Set-CsCpsConfiguration** per modificare le impostazioni esistenti.

<div>


> [!NOTE]  
> È consigliabile configurare come minimo l'opzione <STRONG>OnTimeoutURI</STRONG> per la destinazione di fallback da utilizzare quando si verifica il timeout di una chiamata parcheggiata e la richiamata ha esito negativo.



</div>

Usare il cmdlet **New-CsCpsConfiguration** o il cmdlet **Set-CsCpsConfiguration** per configurare una delle impostazioni seguenti:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Opzione:</th>
<th>Descrizione:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>CallPickupTimeoutThreshold</strong></p></td>
<td><p>Specifica quanto tempo deve trascorrere dopo che una chiamata è stata parcheggiata prima che squilli sul telefono da cui è stata effettuata la risposta.</p>
<p>Il valore deve essere immesso nel formato hh:mm:ss per specificare le ore, i minuti e i secondi. Il valore minimo è 10 secondi e il valore massimo è 10 minuti. Il valore predefinito è 00:01:30.</p></td>
</tr>
<tr class="even">
<td><p><strong>EnableMusicOnHold</strong></p></td>
<td><p>Specifica se viene riprodotto un brano musicale per il chiamante mentre una chiamata è parcheggiata.</p>
<p>I valori consentiti sono True o False. Il valore predefinito è True.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MaxCallPickupAttempts</strong></p></td>
<td><p>Specifica per una chiamata parcheggiata il numero di squilli sul telefono da cui è stata effettuata la risposta prima che la chiamata venga inoltrata all'URI (Uniform Resource Identifier) di fallback indicato per <strong>OnTimeoutURI</strong>. Il valore predefinito è 1.</p></td>
</tr>
<tr class="even">
<td><p><strong>OnTimeoutURI</strong></p></td>
<td><p>Specifica l'indirizzo SIP dell'utente o del Response Group a cui viene instradata una chiamata parcheggiata senza risposta quando viene superato il valore specificato per <strong>MaxCallPickupAttempts</strong>.</p>
<p>Il valore deve essere un URI SIP che inizia con la stringa sip:, ad esempio sip:bob@contoso.com. Per impostazione predefinita, non viene specificato un indirizzo di inoltro.</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-call-park-settings"></a>Per configurare le impostazioni del parcheggio di chiamata

1.  Accedere al computer in cui è installato Lync Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari, come descritto in [delegate Setup Permissions in Lync server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

3.  Eseguire: 
    
        New-CsCpsConfiguration -Identity site:<sitename to apply settings> [-CallPickupTimeoutThreshold <hh:mm:ss>] -[EnableMusicOnHold <$true | $false>] [-MaxCallPickupAttempts <number of rings>] [-OnTimeoutURI sip:<sip URI for routing unanswered call>]
    
    <div>
    

    > [!TIP]  
    > Utilizzare il cmdlet <STRONG>Get-CsSite</STRONG> per identificare il sito. Per informazioni dettagliate, vedere Lync Server Management Shell Documentation.

    
    </div>
    
    Ad esempio:
    
        New-CsCpsConfiguration -Identity site:Redmond1 -CallPickupTimeoutThreshold 00:01:00 -EnableMusicOnHold $false -MaxCallPickupAttempts 2 -OnTimeoutURI sip:bob@contoso.com

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Personalizzare la musica del parcheggio di chiamata in attesa in Lync Server 2013](lync-server-2013-customize-call-park-music-on-hold.md)  


[New-CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCpsConfiguration)  
[Set-CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCpsConfiguration)  
[Get-CsSite](https://docs.microsoft.com/powershell/module/skype/Get-CsSite)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

