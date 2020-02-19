---
title: 'Lync Server 2013: definizione dei requisiti per le conferenze'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your requirements for conferencing
ms:assetid: 5c83e268-22bf-42b2-bac3-3237b5e02e03
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204935(v=OCS.15)
ms:contentKeyID: 48184255
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee3b7631a3c05fb497ee7fcdf37b6db984361845
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137817"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-conferencing-in-lync-server-2013"></a>Definizione dei requisiti per le conferenze in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-30_

Per determinare le funzionalità di conferenza da distribuire, è necessario considerare le funzionalità che si desidera rendere disponibili agli utenti e le caratteristiche di larghezza di banda della rete. L'elenco di domande seguenti rappresenta una guida per il processo di pianificazione allo scopo di determinare le funzionalità di conferenza da distribuire, in base ai requisiti dell'organizzazione.

  - **Si desiderano abilitare le conferenze Web, che includono funzionalità di collaborazione sui documenti e condivisione di applicazioni?**
    
    In caso affermativo, è necessario abilitare le conferenze per il pool Front end in Microsoft Lync Server 2013, Planning Tool o in Generatore di topologie. L'abilitazione delle conferenze consente di abilitare sia le conferenze Web che le conferenze audio/video.
    
    Per la condivisione di applicazioni è richiesta e viene utilizzata più larghezza di banda di rete rispetto alla collaborazione sui documenti. Lync Server 2013 fornisce un meccanismo di limitazione per controllare ogni sessione di condivisione delle applicazioni. Per impostazione predefinita, il limite è impostato su 1,5 Kb/secondo per ogni sessione.
    
    Se non si desidera abilitare la condivisione di applicazioni, ma si desidera utilizzare la collaborazione sui documenti, è possibile abilitare le conferenze e utilizzare i criteri relativi alle riunioni per disabilitare la condivisione di applicazioni. Per informazioni dettagliate sulla configurazione dei criteri di riunione, vedere [Conferencing Policies in Lync Server 2013](lync-server-2013-conferencing-policies.md).
    
    Per consentire agli utenti di condividere le presentazioni di PowerPoint, è necessario configurare il server Office Web Apps. Per informazioni dettagliate sulla configurazione del server Office Web Apps, vedere [configurazione dell'integrazione con Office Web Apps Server e Lync server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

  - **Si desidera abilitare le conferenze audio/video?**
    
    In caso affermativo, è necessario abilitare le conferenze per il pool Front end in Lync Server 2013, strumento di pianificazione o in Generatore di topologie. L'abilitazione delle conferenze consente di abilitare sia le conferenze Web che le conferenze audio/video.
    
    Per le conferenze audio/video è richiesta e viene utilizzata maggiore larghezza di banda di rete rispetto alle conferenze Web (che includono le funzionalità di collaborazione sui documenti e condivisione di applicazioni). Se non si desidera abilitare le conferenze audio/video, ma si desidera abilitare le conferenze Web, è possibile abilitare le conferenze e utilizzare i criteri relativi alle riunioni per disabilitare le conferenze audio/video.
    
    Se si desidera abilitare le conferenze audio, ma non le conferenze video, è possibile abilitare le conferenze audio/video e utilizzare i criteri relativi alle riunioni per impedire le conferenze video. In alternativa, è possibile abilitare le conferenze audio/video e consentire solo a particolari utenti audio di avviare o partecipare a conferenze audio/video.
    
    <div>
    

    > [!NOTE]  
    > VoIP aziendale non è necessario per l'utilizzo di A/V Conferencing. Se si abilitano le conferenze audio/video, gli utenti possono aggiungere l'audio alle conferenze nel caso dispongano di dispositivi audio, anche se si utilizza una soluzione telefonica PBX.

    
    </div>

  - **Si desidera consentire agli utenti di partecipare alla parte audio delle conferenze quando si utilizza un telefono PSTN?**
    
    In caso affermativo, distribuire e abilitare le conferenze telefoniche con accesso esterno. Gli utenti invitati, sia all'interno che all'esterno dell'organizzazione, potranno quindi partecipare alla parte audio delle conferenze tramite un telefono PSTN.

  - **Si desidera consentire agli utenti esterni con i client di Lync Server 2013 di partecipare ai tipi di conferenza abilitati?**
    
    In caso affermativo, è consigliabile distribuire server perimetrali. Consentendo la partecipazione esterna alle riunioni, è possibile massimizzare gli investimenti in Lync Server 2013. Ad esempio, gli utenti con computer portatili con Lync Server 2013 possono partecipare a conferenze da qualsiasi luogo, a casa, in aeroporto o nei siti dei clienti.
    
    Con la distribuzione di server perimetrali, inoltre, è possibile creare relazioni federate con altre organizzazioni, ad esempio clienti o fornitori, e gli utenti di tali organizzazioni possono collaborare più facilmente con gli utenti della propria organizzazione.
    
    Per informazioni dettagliate sulla distribuzione di server perimetrali, vedere [Planning for External User Access in Lync server 2013](lync-server-2013-planning-for-external-user-access.md) e [Deploying External User Access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md). Per informazioni dettagliate sull'abilitazione dell'accesso esterno per il server Office Web Apps, vedere [pubblicazione di Office Web Apps Server in Lync server 2013 utilizzando un server proxy inverso](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md).

  - **Si desidera controllare i client che possono partecipare alle riunioni di Lync Server 2013?**
    
    In caso affermativo, è necessario configurare la pagina di partecipazione alle riunioni in modo che siano disponibili solo le opzioni client che si desidera supportare. Ogni volta che un utente fa clic su un collegamento per partecipare a una riunione pianificata, Lync Server 2013 rileva se un client è già installato nel computer. Viene quindi avviato il client predefinito e viene aperta la pagina di partecipazione alla riunione, che contiene i collegamenti per i client alternativi. Nella pagina di partecipazione alle riunioni è sempre contenuta l'opzione per l'utilizzo di Microsoft Lync Web App. Oltre a questa opzione, è possibile decidere se includere i collegamenti per il partecipante e le versioni precedenti di Communicator. Per informazioni dettagliate, vedere [Configuring the meeting join page in Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md).

<div>

## <a name="in-this-section"></a>Argomenti della sezione

  - [Requisiti di Web Conferencing in Lync Server 2013](lync-server-2013-web-conferencing-requirements.md)

  - [Requisiti di a/V Conferencing in Lync Server 2013](lync-server-2013-a-v-conferencing-requirements.md)

  - [Requisiti per le conferenze telefoniche con accesso esterno in Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md)

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Pianificazione per le conferenze in Lync Server 2013](lync-server-2013-planning-for-conferencing.md)  
[Elenco di controllo di distribuzione per le conferenze in Lync Server 2013](lync-server-2013-deployment-checklist-for-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

