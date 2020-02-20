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
ms.openlocfilehash: 02c13f2b1fa312394edfaba01ecd05179f86a0c9
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151426"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-gallery-view-in-lync-server-2013"></a>Configurazione della visualizzazione raccolta in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-30_

In Lync Server 2013, è possibile configurare le conferenze video della visualizzazione raccolta nei criteri di conferenza. La visualizzazione Raccolta è attivata per impostazione predefinita. Se non si vuole consentire la visualizzazione Raccolta o la si vuole consentire solo per alcuni utenti, è necessario disattivarla nei criteri di conferenza.

Quando il video di un partecipante a una conferenza non è disponibile, è possibile migliorare l'esperienza di visualizzazione della raccolta degli utenti se si distribuiscono foto ad alta risoluzione, una nuova funzionalità di Lync Server 2013. Le foto ad alta risoluzione offrono un'alternativa alle foto dei contatti a risoluzione limitata più piccole e limitate archiviate in servizi di dominio Active Directory. Le foto ad alta risoluzione sono archiviate nella cassetta postale di Exchange 2013 di un utente e, pertanto, richiedono l'integrazione di Lync Server 2013 con Exchange 2013. Per informazioni dettagliate, vedere l'articolo del Blog di NextHop "integrazione di Exchange 2013 e Lync Server 2013" [https://go.microsoft.com/fwlink/p/?LinkId=260987](https://go.microsoft.com/fwlink/p/?linkid=260987)all'indirizzo.

<div>


> [!NOTE]  
> Il contenuto di ogni blog e il relativo URL sono soggetti a modifica senza preavviso.



</div>

È possibile visualizzare o modificare i parametri della visualizzazione raccolta mediante il pannello di controllo di Lync Server 2013 oppure utilizzando uno dei seguenti cmdlet:

  - **Get-CsConferencingPolicy**

  - **Set-CsConferencingPolicy**

  - **New-CsConferencingPolicy**

Configurare la visualizzazione Raccolta con le impostazioni dei criteri di conferenza seguenti:

  - **AllowMultiview**   questo parametro consente di controllare se un utente è autorizzato a organizzare le conferenze video della visualizzazione raccolta. Si applica a riunioni programmate e ad hoc create dall'utente.
    
    Esempi:
    
      - Questo parametro è impostato su true per l'utente A, che è ospitato in un pool di Lync Server 2013. Le riunioni organizzate dall'utente A consentono agli utenti di partecipare e ricevere più flussi video.
    
      - Questo parametro è impostato su false per l'utente B, che è ospitato in un pool di Lync Server 2013. Le riunioni organizzate dall'utente B dispongono di un unico flusso video analogo all'esperienza di conferenza video fornita da Lync Server 2010.
    
    Questo parametro determina chi può organizzare riunioni con più flussi video. I partecipanti di riunioni che consentono più flussi video possono o non possono ricevere più flussi video, a seconda delle autorizzazioni individuali. Vedere la descrizione del parametro EnableMultiviewJoin.

  - **EnableMultiviewJoin**   questo parametro consente di controllare se un partecipante a una riunione riceve la visualizzazione della raccolta video in riunioni che lo consentono. Il parametro controlla l'esperienza utente per tutte le riunioni a cui gli utenti partecipano.
    
    Esempi:
    
      - Questo parametro è impostato su true per l'utente C. gli utenti possono ricevere più flussi video quando partecipano a una riunione organizzata o avviata dall'utente A. User C riceve un singolo flusso video analogo all'esperienza di conferenza video fornita da Lync Server 2010 quando partecipare a una riunione organizzata o avviata dall'utente B.
    
      - Questo parametro è impostato su false per l'utente D. utente D riceve un singolo flusso video analogo all'esperienza di conferenza video fornita da Lync Server 2010 quando si partecipa a una riunione organizzata dall'utente A o dall'utente B.

La procedura seguente è un esempio di utilizzo di Lync Server Management Shell per abilitare le conferenze video della visualizzazione raccolta.

<div>

## <a name="to-modify-conferencing-policy-for-gallery-view-video-conferencing"></a>Per modificare i criteri di conferenza per le conferenze video della visualizzazione Raccolta

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

2.  Per modificare i criteri di conferenza, dalla riga di comando eseguire il cmdlet seguente:
    
        Set-CsConferencingPolicy -Identity Pool01ConferencingPolicy -AllowMultiview $true -EnableMultiviewJoin $true 

</div>

</div>

<span> </span>

</div>

</div>

</div>

