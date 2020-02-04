---
title: 'Lync Server 2013: configurazione della visualizzazione raccolta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Gallery View
ms:assetid: 4a609178-47d8-4682-ac8d-29f882801924
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204871(v=OCS.15)
ms:contentKeyID: 48184069
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06054e1728245c87e8bf35419d3890f4e379543a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728846"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-gallery-view-in-lync-server-2013"></a>Configurazione della visualizzazione raccolta in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-30_

In Lync Server 2013 configurare le videoconferenze per la visualizzazione raccolta in criteri di conferenza. La visualizzazione raccolta è attivata per impostazione predefinita. Se non si vuole consentire la visualizzazione raccolta o se si vuole consentire solo ad alcuni utenti, è necessario disattivare la caratteristica dei criteri di conferenza.

Quando il video di un partecipante a una conferenza non è disponibile, è possibile migliorare l'esperienza della visualizzazione raccolta degli utenti se si distribuiscono foto ad alta risoluzione, una nuova funzionalità in Lync Server 2013. Le foto ad alta risoluzione rappresentano un'alternativa alle foto di contatto più piccole e limitate archiviate in servizi di dominio Active Directory. Le foto ad alta risoluzione sono archiviate nella cassetta postale di Exchange 2013 dell'utente e, pertanto, richiedono l'integrazione di Lync Server 2013 con Exchange 2013. Per informazioni dettagliate, vedere l'articolo su Blog di NextHop "integrazione di [http://go.microsoft.com/fwlink/p/?LinkId=260987](http://go.microsoft.com/fwlink/p/?linkid=260987)Exchange 2013 e Lync Server 2013".

<div>


> [!NOTE]  
> Il contenuto di ogni blog e il relativo URL sono soggetti a modifiche senza preavviso.



</div>

È possibile visualizzare o modificare i parametri della visualizzazione raccolta usando il pannello di controllo di Lync Server 2013 o usando uno dei cmdlet seguenti:

  - **Get-CsConferencingPolicy**

  - **Set-CsConferencingPolicy**

  - **New-CsConferencingPolicy**

Configurare la visualizzazione raccolta con le impostazioni dei criteri di conferenza seguenti:

  - **AllowMultiview**   questo parametro controlla se un utente può organizzare conferenze video per la visualizzazione raccolta. Questo parametro si applica alle riunioni pianificate e ad-hoc create dall'utente.
    
    Esempi
    
      - Questo parametro è impostato su true per l'utente A, che è ospitato in un pool di Lync Server 2013. Riunioni organizzate dall'utente A consentire agli utenti di partecipare e ricevere più flussi video.
    
      - Questo parametro è impostato su false per l'utente B, che è ospitato in un pool di Lync Server 2013. Le riunioni organizzate dall'utente B hanno un singolo flusso video simile all'esperienza di conferenza video fornita da Lync Server 2010.
    
    Questo parametro determina chi può organizzare riunioni che consentano più flussi video. I partecipanti alle riunioni che consentono a più flussi video possono o meno essere autorizzati a ricevere più flussi video, in base alle singole autorizzazioni (vedere la descrizione del parametro EnableMultiviewJoin).

  - **EnableMultiviewJoin**   questo parametro controlla se un partecipante a una riunione riceve l'esperienza video della visualizzazione raccolta in riunioni che lo consentono. Questo parametro controlla l'esperienza dell'utente in qualsiasi riunione in cui partecipa.
    
    Esempi
    
      - Questo parametro è impostato su true per l'utente C. l'utente c può ricevere più flussi video durante la partecipazione a una riunione organizzata o avviata dall'utente A. l'utente C riceve un singolo flusso video simile all'esperienza di conferenza video fornita da Lync Server 2010 quando partecipare a una riunione organizzata o avviata dall'utente B.
    
      - Questo parametro è impostato su false per l'utente D. l'utente D riceve un singolo flusso video simile all'esperienza di conferenza video fornita da Lync Server 2010 quando partecipa a una riunione organizzata dall'utente A o dall'utente B.

La procedura seguente è un esempio di utilizzo di Lync Server Management Shell per abilitare la visualizzazione della raccolta di videoconferenze.

<div>

## <a name="to-modify-conferencing-policy-for-gallery-view-video-conferencing"></a>Per modificare i criteri di conferenza per le videoconferenze per la visualizzazione raccolta

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

2.  Nella riga di comando eseguire il cmdlet seguente per modificare i criteri di conferenza:
    
        Set-CsConferencingPolicy -Identity Pool01ConferencingPolicy -AllowMultiview $true -EnableMultiviewJoin $true 

</div>

</div>

<span> </span>

</div>

</div>

</div>

