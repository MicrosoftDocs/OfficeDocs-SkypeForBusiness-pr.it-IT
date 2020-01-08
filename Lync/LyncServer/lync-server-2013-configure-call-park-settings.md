---
title: 'Lync Server 2013: configurare le impostazioni del parcheggio delle chiamate'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure Call Park settings
ms:assetid: 3bed9d09-8363-4fff-a220-f0f6d3a81241
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425886(v=OCS.15)
ms:contentKeyID: 48183922
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9acbd44acf2ca78042452d2c1f52d4c5fa26056f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981050"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-call-park-settings-in-lync-server-2013"></a>Configurare le impostazioni di Call Park in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-11-01_

Se non si vogliono usare le impostazioni predefinite di Call Park, è possibile personalizzarle. Quando si installa l'applicazione Call Park, le impostazioni globali sono configurate per impostazione predefinita. È possibile modificare le impostazioni globali ed è anche possibile specificare impostazioni specifiche del sito. Usa il cmdlet **New-CsCpsConfiguration** per creare nuove impostazioni specifiche del sito. Usare il cmdlet **Set-CsCpsConfiguration** per modificare le impostazioni esistenti.

<div>


> [!NOTE]  
> È consigliabile configurare almeno l'opzione <STRONG>OnTimeoutURI</STRONG> per la destinazione di fallback da usare quando si verifica un timeout per una chiamata parcheggiata e la risponderia non riesce.



</div>

USA cmdlet **New-CsCpsConfiguration** o il cmdlet **Set-CsCpsConfiguration** per configurare una delle impostazioni seguenti:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Questa opzione:</th>
<th>Specifica questo:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>CallPickupTimeoutThreshold</strong></p></td>
<td><p>La quantità di tempo che trascorre dopo il parcheggio di una chiamata prima che ritorni al telefono in cui è stata risolta la chiamata.</p>
<p>Il valore deve essere immesso nel formato HH: mm: SS per specificare le ore, i minuti e i secondi. Il valore minimo è di 10 secondi e il valore massimo è di 10 minuti. Il valore predefinito è 00:01:30.</p></td>
</tr>
<tr class="even">
<td><p><strong>EnableMusicOnHold</strong></p></td>
<td><p>Se la musica viene riprodotta per un chiamante mentre viene parcheggiata una chiamata.</p>
<p>I valori sono true o false. Il valore predefinito è true.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MaxCallPickupAttempts</strong></p></td>
<td><p>Il numero di squilli di una chiamata parcheggiata torna al telefono che risponde prima che venga inoltrato all'URI (Uniform Resource Identifier) di fallback specificato per <strong>OnTimeoutURI</strong>. Il valore predefinito è 1.</p></td>
</tr>
<tr class="even">
<td><p><strong>OnTimeoutURI</strong></p></td>
<td><p>Indirizzo SIP dell'utente o del gruppo di risposte a cui viene instradata una chiamata parcheggiata senza risposta quando viene superato <strong>MaxCallPickupAttempts</strong> .</p>
<p>Value deve essere un URI SIP che inizia con la stringa SIP:. Ad esempio, sip:bob@contoso.com. L'impostazione predefinita non è l'indirizzo di inoltro.</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-call-park-settings"></a>Per configurare le impostazioni di Call Park

1.  Accedere al computer in cui è installato Lync Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari, come descritto in autorizzazioni di [configurazione delegate in Lync server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

3.  Eseguire
    
        New-CsCpsConfiguration -Identity site:<sitename to apply settings> [-CallPickupTimeoutThreshold <hh:mm:ss>] -[EnableMusicOnHold <$true | $false>] [-MaxCallPickupAttempts <number of rings>] [-OnTimeoutURI sip:<sip URI for routing unanswered call>]
    
    <div>
    

    > [!TIP]  
    > Usa il cmdlet <STRONG>Get-CsSite</STRONG> per identificare il sito. Per informazioni dettagliate, vedere documentazione di Lync Server Management Shell.

    
    </div>
    
    Ad esempio:
    
        New-CsCpsConfiguration -Identity site:Redmond1 -CallPickupTimeoutThreshold 00:01:00 -EnableMusicOnHold $false -MaxCallPickupAttempts 2 -OnTimeoutURI sip:bob@contoso.com

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Personalizzare la musica di Call Park in attesa in Lync Server 2013](lync-server-2013-customize-call-park-music-on-hold.md)  


[New-CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCpsConfiguration)  
[Set-CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCpsConfiguration)  
[Get-CsSite](https://docs.microsoft.com/powershell/module/skype/Get-CsSite)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

