---
title: 'Lync Server 2013: configurazione della larghezza di banda video'
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
ms.openlocfilehash: 3cca8df1ea3c4c2458851da24ab8b39dbbab2d3d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734446"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-video-bandwidth-in-lync-server-2013"></a>Configurazione della larghezza di banda video in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-02_

Lync Server 2013 include diverse impostazioni per la gestione di video per le chiamate a due parti e conferenze multiparte. Quando si distribuisce Lync Server 2013, è necessario valutare se le impostazioni predefinite sono appropriate per l'organizzazione e modificarle in base alle esigenze.

I parametri descritti in questa sezione sono validi sia per le chiamate a due parti che per le conferenze multiparte. Visualizzare o modificare queste impostazioni usando uno dei cmdlet seguenti:

  - **Get-CsConferencingPolicy**

  - **Set-CsConferencingPolicy**

  - **New-CsConferencingPolicy**

Verificare le impostazioni seguenti nei criteri di conferenza:

  - **VideoBitRateKb**   questa impostazione specifica la velocità in bit video massima in kilobit al secondo (Kbps) usata per il video inviato da un utente. Il valore predefinito è 50000 kbps. I valori validi sono compresi tra 0 e 50000.
    
    Questa impostazione si applica separatamente al video principale e al video panoramico.
    
    Esempio: se si specifica 2000 kbps, Lync Server può inviare 2000 kbps per il flusso video principale e 2000 kbps per il flusso video panoramico.
    
    <div>
    

    > [!NOTE]  
    > La larghezza di banda massima della rete video per un endpoint di Lync 2013 è 8000 kbps per il video principale e 2500 kbps per il video panoramico. Questi valori massimi vengono raggiunti solo se vengono ricevuti o inviati più video. Per informazioni dettagliate, vedere la sezione "utilizzo della rete traffico multimediale" nei <A href="lync-server-2013-network-bandwidth-requirements-for-media-traffic.md">requisiti di larghezza di banda di rete per il traffico multimediale in Lync Server 2013</A>. Questa sezione elenca la larghezza di banda del flusso video massima e tipica per tutte le risoluzioni supportate.

    
    </div>

  - **TotalReceiveVideoBitRateKb**   questa impostazione, che è una novità di Lync Server 2013, specifica il bitrate massimo consentito (in kilobit al secondo) per tutti i flussi video ricevuti da un client. Questo significa che specifica il totale combinato per tutti i flussi video, ad eccezione dei flussi video panoramici, che un client può ricevere. Se ad esempio specifichi 1500 Kbps, un client può ricevere fino a 1500 kbps di video, che possono essere costituiti da più flussi video o da un singolo flusso video. Questa impostazione si applica solo ai client di Lync Server 2013.
    
    Il valore predefinito per **TotalReceiveVideoBitRateKb** è 50000 kbps. Se l'impostazione **EnableMultiviewJoin** per la visualizzazione raccolta è impostata su true, **TotalReceiveVideoBitRateKb** non deve essere impostato sotto 420 kbps. Se l'impostazione **EnableMultiviewJoin** per la visualizzazione raccolta è impostata su false, **TotalReceiveVideoBitRateKb** non deve essere impostato sotto 100 kbps. Se **EnableMultiviewJoin** è impostato su true e si imposta il valore sotto 420 Kbps, i valori verranno impostati automaticamente sul valore soglia. Questa soglia consente di evitare la disconfigurazione accidentale che potrebbe causare un'esperienza utente insufficiente.
    
    <div>
    

    > [!NOTE]  
    > Per informazioni dettagliate sull'impostazione di <STRONG>EnableMultiviewJoin</STRONG> , vedere <A href="lync-server-2013-configuring-gallery-view.md">configurazione della visualizzazione raccolta in Lync Server 2013</A>.

    
    </div>

  - **MaxVideoConferencingResolution**   questo parametro non viene più usato per i client di Lync Server 2013 nelle conferenze di Lync Server 2013. Le conferenze di Lync Server 2013 usano i controlli di velocità in bit descritti in precedenza in questa sezione. Questa impostazione viene ancora usata per i client legacy che partecipano a una conferenza di Lync Server 2013. Questo parametro determina la risoluzione massima consentita per i client legacy nelle conferenze organizzate dagli utenti residenti in Lync Server 2013. I client legacy vengono trattati nello stesso modo in cui si trovavano nelle versioni precedenti di Lync Server o Office Communications Server.

Oltre alle impostazioni dei criteri di conferenza che si applicano agli utenti, valutare le impostazioni di configurazione multimediale. Visualizzare o modificare queste impostazioni usando uno dei cmdlet seguenti:

  - **Get-CsMediaConfiguration**

  - **Set-CsMediaConfiguration**

  - **New-CsMediaConfiguration**

Verificare l'impostazione seguente:

  - **MaxVideoRateAllowed**   questa impostazione per pool specifica la frequenza massima in cui i segnali video verranno trasferiti agli endpoint client. Si applica solo alle versioni precedenti dei client di Lync Server.
    
    <div>
    

    > [!NOTE]  
    > I client di Lync Server 2013 ignorano questa impostazione e usano invece l'impostazione TotalReceiveVideoBitRateKb nei criteri di conferenza.

    
    </div>
    
    Il valore predefinito è HD720P. I valori validi sono HD720p15M, VGA600K e CIF250K.
    
    Esempio: se si specifica 1500 Kbps, tutti i client legacy del pool possono ricevere fino a 1500 kbps di video in conferenze a due o più partecipanti.

Le procedure seguenti sono esempi di utilizzo di Lync Server Management Shell per modificare le impostazioni descritte in questa sezione.

<div>

## <a name="to-modify-conferencing-policy-for-video-settings"></a>Per modificare i criteri di conferenza per le impostazioni video

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

2.  Nella riga di comando eseguire il cmdlet seguente per modificare i criteri di conferenza:
    
        Set-CsConferencingPolicy -Identity Pool01ConferencingPolicy -VideoBitRateKb 2000 -TotalReceiveVideoBitRateKb 2000 

</div>

<div>

## <a name="to-modify-media-configuration-for-legacy-clients"></a>Per modificare la configurazione multimediale per i client legacy

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

2.  Nella riga di comando eseguire il cmdlet seguente per modificare la configurazione multimediale:
    
        Set-CsMediaConfiguration -Identity site:Redmond01 -MaxVideoRateAllowed CIF250K

</div>

</div>

<span> </span>

</div>

</div>

</div>

