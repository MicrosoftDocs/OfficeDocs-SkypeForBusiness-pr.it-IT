---
title: 'Lync Server 2013: Definizione dei requisiti per le conferenze'
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
ms.openlocfilehash: c19269ef06fc2aa7ec19e2ede53f406b345536b3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739956"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-conferencing-in-lync-server-2013"></a>Definizione dei requisiti per le conferenze in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-30_

Quando si determina quali funzionalità di conferenza distribuire, è necessario prendere in considerazione le funzionalità che si desidera siano disponibili per gli utenti e le funzionalità di larghezza di banda della rete. L'elenco seguente di domande guida l'utente attraverso il processo di pianificazione dei servizi di conferenza per determinare quali funzionalità di conferenza è necessario distribuire, in base ai requisiti dell'organizzazione.

  - **Si desidera abilitare le conferenze Web, che includono la collaborazione tra documenti e la condivisione di applicazioni?**
    
    In questo caso, è necessario abilitare i servizi di conferenza per il pool Front-end in Microsoft Lync Server 2013, strumento di pianificazione o generatore di topologie. Quando si Abilita la conferenza, è possibile abilitare sia le conferenze Web che le conferenze A/V.
    
    La condivisione delle applicazioni richiede e usa più larghezza di banda della collaborazione tra documenti. Lync Server 2013 offre un meccanismo di limitazione per controllare ogni sessione di condivisione dell'applicazione. Per impostazione predefinita, questa opzione è impostata su 1,5 KB/secondo per ogni sessione.
    
    Se non si vuole abilitare la condivisione delle applicazioni ma si vuole collaborare con i documenti, è possibile abilitare i servizi di conferenza e usare i criteri di riunione per disabilitare la condivisione delle applicazioni. Per informazioni dettagliate sulla configurazione dei criteri di riunione, vedere [criteri di conferenza in Lync Server 2013](lync-server-2013-conferencing-policies.md).
    
    Per consentire agli utenti di condividere presentazioni di PowerPoint, è necessario configurare Office Web Apps Server. Per informazioni dettagliate sulla configurazione di Office Web Apps Server, vedere [configurazione dell'integrazione con Office Web Apps Server e Lync server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

  - **Si desidera abilitare una conferenza telefonica A/V?**
    
    In questo caso, è necessario abilitare i servizi di conferenza per il pool Front-end in Lync Server 2013, strumento di pianificazione o generatore di topologie. Quando si Abilita la conferenza, è possibile abilitare sia le conferenze Web che le conferenze A/V.
    
    A/V Conferencing richiede e usa più larghezza di banda della rete rispetto alle conferenze Web (che includono la collaborazione tra documenti e la condivisione delle applicazioni). Se non si vuole abilitare servizi di conferenza A/V ma si vuole abilitare le conferenze Web, è possibile abilitare i servizi di conferenza e usare i criteri di riunione per disabilitare le riunioni a/V.
    
    Se si vuole abilitare le conferenze audio ma non le conferenze video, è possibile abilitare servizi di conferenza a/V e usare i criteri di riunione per evitare videoconferenze. In alternativa, puoi abilitare i servizi di conferenza A/V e consentire solo a determinati utenti di avviare o partecipare a conferenze A/V.
    
    <div>
    

    > [!NOTE]  
    > Enterprise Voice non è necessaria per l'uso di servizi di conferenza A/V. Se si abilita una conferenza telefonica A/V, gli utenti possono aggiungere audio alle loro conferenze se hanno dispositivi audio, anche se si usa un PBX per la soluzione telefono.

    
    </div>

  - **Si vuole consentire agli utenti di partecipare alla parte audio delle conferenze quando si usa un telefono PSTN?**
    
    In caso affermativo, distribuire e abilitare i servizi di conferenza telefonica con accesso esterno. Gli utenti invitati, sia all'interno che all'esterno dell'organizzazione, possono quindi partecipare alla parte audio delle conferenze usando un telefono PSTN.

  - **Si desidera consentire agli utenti esterni con i client di Lync Server 2013 di partecipare ai tipi di conferenza abilitati?**
    
    In questo caso, devi distribuire Edge Server. Consentendo la partecipazione esterna alle riunioni, è possibile massimizzare l'investimento in Lync Server 2013. Ad esempio, gli utenti con computer portatili con Lync Server 2013 possono partecipare a conferenze ovunque si trovino, a casa, in aeroporto o nei siti del cliente.
    
    Inoltre, con i server perimetrali distribuiti è possibile creare relazioni federate con altre organizzazioni, ad esempio i clienti o i fornitori, e gli utenti di tali organizzazioni possono collaborare più facilmente con gli utenti.
    
    Per informazioni dettagliate sulla distribuzione di Edge Server, vedere [pianificazione per l'accesso degli utenti esterni in Lync server 2013](lync-server-2013-planning-for-external-user-access.md) e [distribuzione dell'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-deploying-external-user-access.md). Per informazioni dettagliate sull'abilitazione dell'accesso esterno per il server Office Web Apps, vedere [pubblicazione di Office Web Apps Server in Lync server 2013 con un server proxy inverso](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md).

  - **Si desidera controllare i client che possono partecipare alle riunioni di Lync Server 2013?**
    
    In questo caso, devi configurare la pagina di partecipazione alla riunione in modo che siano disponibili solo le opzioni client che vuoi supportare. Ogni volta che un utente fa clic su un collegamento per partecipare a una riunione pianificata, Lync Server 2013 rileva se un client è già installato nel computer. Avvia quindi il client predefinito e apre la pagina di partecipazione alla riunione, che contiene i collegamenti per i client alternativi. La pagina di partecipazione alla riunione contiene sempre l'opzione per l'uso di Microsoft Lync Web App. Oltre a questa opzione, è possibile decidere se includere i collegamenti per il partecipante e le versioni precedenti di Communicator. Per informazioni dettagliate, vedere [configurazione della pagina di partecipazione alla riunione in Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md).

<div>

## <a name="in-this-section"></a>Contenuto della sezione

  - [Requisiti per i servizi di conferenza Web in Lync Server 2013](lync-server-2013-web-conferencing-requirements.md)

  - [Requisiti di conferenza a/V in Lync Server 2013](lync-server-2013-a-v-conferencing-requirements.md)

  - [Requisiti per i servizi di conferenza telefonica con accesso esterno in Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md)

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Pianificazione dei servizi di conferenza in Lync Server 2013](lync-server-2013-planning-for-conferencing.md)  
[Elenco di controllo di distribuzione per le conferenze in Lync Server 2013](lync-server-2013-deployment-checklist-for-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

