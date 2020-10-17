---
title: 'Lync Server 2013: configurazione della larghezza di banda video'
description: 'Lync Server 2013: configurazione della larghezza di banda video.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring video bandwidth in Lync Server
ms:assetid: 446bed91-b26f-4ab2-b2f5-36e6810b405b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204842(v=OCS.15)
ms:contentKeyID: 48183984
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 85fedbe2fb856696236e79c3bbcece34d5af4a34
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550672"
---
# <a name="configuring-video-bandwidth-in-lync-server-2013"></a>Configurazione della larghezza di banda video in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-02_

Lync Server 2013 include diverse impostazioni per la gestione del video per le chiamate a due o più partecipanti. Quando si distribuisce Lync Server 2013, è necessario valutare se le impostazioni predefinite sono appropriate per l'organizzazione e modificarle in base alle esigenze.

I parametri descritti in questa sezione si applicano sia alle chiamate con due partecipanti che alle conferenze con più partecipanti. Visualizzare o modificare queste impostazioni usando uno dei cmdlet seguenti:

  - **Get-CsConferencingPolicy**

  - **Set-CsConferencingPolicy**

  - **New-CsConferencingPolicy**

Verificare le impostazioni seguenti nei criteri conferenza:

  - **VideoBitRateKb**     Questa impostazione consente di specificare la frequenza di bit massima del video in kilobit al secondo (Kbps) utilizzata per il video inviato da un utente. Il valore predefinito è 50000 kbps. I valori validi sono compresi tra 0 e 50000.
    
    Questa impostazione si applica separatamente al video principale e alla panoramica.
    
    Esempio: se si specifica 2000 kbps, Lync Server può inviare 2000 kbps per il flusso video principale e 2000 kbps per il flusso video panoramico.
    
    <div>
    

    > [!NOTE]  
    > La larghezza di banda massima della rete video per un endpoint Lync 2013 è 8000 kbps per il video principale e 2500 kbps per il video panoramico. Questi valori massimi vengono raggiunti solo nel caso di invio o ricezione di più video. Per informazioni dettagliate, vedere la sezione "utilizzo della rete per il traffico multimediale" in <A href="lync-server-2013-network-bandwidth-requirements-for-media-traffic.md">requisiti di larghezza di banda di rete per il traffico multimediale in Lync Server 2013</A>. In questa sezione sono elencati i valori massimi e tipici della larghezza di base dei flussi video per tutte le risoluzioni supportate.

    
    </div>

  - **TotalReceiveVideoBitRateKb**     Questa impostazione, che è una novità di Lync Server 2013, specifica il bitrate massimo consentito (in kilobit al secondo) per tutti i flussi video ricevuti da un client. In altre parole, specifica il totale combinato per tutti i flussi video, ad eccezione di quelli della panoramica, che un client può ricevere. Se si specifica il valore 1500 kbps, un client può ad esempio ricevere fino a 1500 kbps di video, in cui possono essere compresi uno o più flussi video. Questa impostazione si applica solo ai client Lync Server 2013.
    
    Il valore predefinito di **TotalReceiveVideoBitRateKb** è 50000 kbps. Se l'impostazione **EnableMultiviewJoin** della visualizzazione Raccolta corrisponde a True, **TotalReceiveVideoBitRateKb** non deve essere impostato al di sotto di 420 kbps. Se l'impostazione **EnableMultiviewJoin** relativa alla visualizzazione Raccolta corrisponde a False, **TotalReceiveVideoBitRateKb** non deve essere impostato al di sotto di 100 kbps. Se **EnableMultiviewJoin** è impostato su True e il valore impostato è al di sotto di 420 kbps, i valori assumeranno per impostazione predefinita quello della soglia. Il valore della soglia impedisce un'errata configurazione accidentale che potrebbe determinare un'esperienza scarsa per gli utenti.
    
    <div>
    

    > [!NOTE]  
    > Per informazioni dettagliate sull'impostazione <STRONG>EnableMultiviewJoin</STRONG> , vedere <A href="lync-server-2013-configuring-gallery-view.md">Configuring Gallery View in Lync Server 2013</A>.

    
    </div>

  - **MaxVideoConferencingResolution**     Questo parametro non viene più utilizzato per i client di Lync Server 2013 nelle conferenze di Lync Server 2013. Le conferenze di Lync Server 2013 utilizzano i controlli di bit rate descritti in precedenza in questa sezione. Questa impostazione è ancora utilizzata per i client legacy che partecipano a una conferenza di Lync Server 2013. Questo parametro determina la risoluzione massima consentita per i client legacy nelle conferenze organizzate dagli utenti che si trovano in Lync Server 2013. Vale a dire che i client legacy vengono considerati come nelle versioni precedenti di Lync Server o Office Communications Server.

Oltre alle impostazioni dei criteri conferenza che si applicano agli utenti, prendere in considerazione l'uso delle impostazioni di configurazione multimediale. Visualizzare o modificare queste impostazioni usando uno dei cmdlet seguenti:

  - **Get-CsMediaConfiguration**

  - **Set-CsMediaConfiguration**

  - **New-CsMediaConfiguration**

Verificare l'impostazione seguente:

  - **MaxVideoRateAllowed**     Questa impostazione per pool specifica la velocità massima di trasferimento dei segnali video negli endpoint client. Si applica solo alle versioni precedenti dei client di Lync Server.
    
    <div>
    

    > [!NOTE]  
    > I client di Lync Server 2013 ignorano questa impostazione e utilizzano invece l'impostazione TotalReceiveVideoBitRateKb nei criteri di conferenza.

    
    </div>
    
    Il valore predefinito è HD720P. I valori validi sono HD720p15M, VGA600K e CIF250K.
    
    Esempio: se si specifica il valore 1500 kbps, tutti i client legacy del pool possono ricevere fino a 1500 kbps di video in conferenze con due o più partecipanti.

Nelle procedure seguenti sono riportati alcuni esempi di utilizzo di Lync Server Management Shell per modificare le impostazioni descritte in questa sezione.

<div>

## <a name="to-modify-conferencing-policy-for-video-settings"></a>Per modificare i criteri conferenza per le impostazioni video

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

2.  Alla riga di comando eseguire il cmdlet seguente per modificare i criteri conferenza:
    
        Set-CsConferencingPolicy -Identity Pool01ConferencingPolicy -VideoBitRateKb 2000 -TotalReceiveVideoBitRateKb 2000 

</div>

<div>

## <a name="to-modify-media-configuration-for-legacy-clients"></a>Per modificare la configurazione multimediale per i client legacy

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

2.  Alla riga di comando eseguire il cmdlet seguente per modificare la configurazione multimediale:
    
        Set-CsMediaConfiguration -Identity site:Redmond01 -MaxVideoRateAllowed CIF250K

</div>

</div>

<span> </span>

</div>

</div>

</div>

