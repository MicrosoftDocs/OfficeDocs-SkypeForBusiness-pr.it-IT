---
title: 'Lync Server 2013: Componenti e topologie per le conferenze'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for conferencing
ms:assetid: eb83052a-3360-4ba1-a6a0-6ee419942809
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399061(v=OCS.15)
ms:contentKeyID: 48185707
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: db44e7c8430865fcf8138c9b51f6e700ff85dd7b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742636"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-conferencing-in-lync-server-2013"></a>Componenti e topologie per le conferenze in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-04_

Quando si seleziona conferenza in Generatore di topologia, le conferenze vengono distribuite come parte del server front-end o Standard Edition. I servizi di conferenza telefonica con accesso esterno e la condivisione di PowerPoint richiedono componenti e configurazioni aggiuntivi. Nelle sezioni seguenti vengono descritti i componenti e le topologie supportate per le conferenze Web, i servizi di conferenza A/V e i servizi di conferenza telefonica con accesso esterno.

<div>

## <a name="supported-components"></a>Componenti supportati

Gli unici componenti per le conferenze Web e le conferenze A/V richiedono i server front-end dell'organizzazione o i server Standard Edition. Per un elenco dei requisiti hardware e software per i server front-end e Standard Edition, vedere [hardware supportato per il supporto di Lync server 2013](lync-server-2013-supported-hardware.md) e [del software server e dell'infrastruttura in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md).

Lync Server 2013 usa Office Web Apps e il server Office Web Apps per gestire la condivisione e il rendering delle presentazioni di PowerPoint. Per informazioni dettagliate sull'installazione e la configurazione del server Office Web Apps, vedere [configurazione dell'integrazione con Office Web Apps Server e Lync server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

Oltre ai requisiti per le conferenze Web e le conferenze telefoniche con accesso esterno, i servizi di conferenza telefonica per i servizi di audioconferenza utilizzano i seguenti componenti di Lync Server 2013:

  - **Application Service**   Application Service offre una piattaforma per la distribuzione, l'hosting e la gestione delle applicazioni UC (Unified Communications). I servizi di conferenza telefonica con accesso esterno usano due applicazioni UC che richiedono il servizio applicazione: Assistente conferenza e Annuncio conferenza. Il servizio applicazione viene installato e attivato per impostazione predefinita in ogni server front-end in un pool Front-end e in ogni server Standard Edition quando si distribuisce un carico di lavoro per le conferenze e si seleziona l'opzione di conferenza telefonica con accesso esterno.

  - ****   L'applicazione per i servizi di conferenza con operatore di conferenza è un'applicazione di comunicazioni unificata che accetta chiamate PSTN (Public Switched Telephone Network), riproduce le richieste e partecipa alle chiamate a una conferenza a/V. L'applicazione Operatore Conferenza viene installata e attivata per impostazione predefinita quando si distribuisce un carico di lavoro per conferenze e si seleziona l'opzione conferenza telefonica con accesso esterno.

  - **** L'applicazione per l'annuncio di servizi di conferenza telefonica per l'annuncio di conferenza è un'applicazione di comunicazioni unificata che riproduce i toni e chiede ai partecipanti PSTN su determinate azioni, ad esempio quando i partecipanti partecipano o abbandonano una conferenza, i partecipanti vengono disattivati o riabilitati, qualcuno entra nella sala di conferenza o la conferenza è bloccata o sbloccata.    L'applicazione di annunci conferenza supporta anche i comandi DTMF (Dual-Tone Multifrequency) dalla tastiera del telefono. L'applicazione di annunci conferenza viene automaticamente installata e attivata per impostazione predefinita quando si distribuisce un carico di lavoro per le conferenze e si seleziona l'opzione conferenza telefonica con accesso esterno.

  - **Pagina delle impostazioni**   dei servizi di conferenza telefonica con accesso esterno la pagina delle impostazioni per i servizi di conferenza telefonica con accesso esterno consente di visualizzare i numeri di accesso esterno con le lingue disponibili, le informazioni sulla conferenza assegnate, ovvero per le riunioni che non devono essere pianificate, e i controlli DTMF in conferenza e supporta la gestione del PIN (Personal Identification Number) e delle informazioni di conferenza assegnate. La pagina Impostazioni conferenza telefonica con accesso esterno viene installata automaticamente come parte dei servizi Web.

  - **I servizi di conferenza telefonica con accesso esterno a Lync Server 2013, Mediation Server e PSTN Gateway**   richiedono un Mediation Server per tradurre i segnali (e gli elementi multimediali, in alcune configurazioni) tra Lync Server 2013 e il gateway PSTN, oltre a un gateway PSTN per la traduzione di segnali e elementi multimediali tra il server Mediation e il gateway PSTN. Per i servizi di conferenza telefonica con accesso esterno, è necessario distribuire almeno un Mediation Server e almeno una delle opzioni seguenti:
    
      - Gateway PSTN
    
      - IP-PBX
    
      - Session Border Controller (SBC) (per un provider di servizi di telefonia Internet a cui ci si connette configurando un trunk SIP)
    
    <div>
    

    > [!NOTE]  
    > Se si sta distribuendo anche VoIP aziendale, Mediation Server e gateway PSTN fanno parte della distribuzione VoIP aziendale. Se non si sta distribuendo VoIP aziendale, è necessario distribuire almeno un Mediation Server e almeno un gateway PSTN, IP-PBX o SBC per i servizi di conferenza telefonica con accesso esterno.

    
    </div>

  - ****   Archivio file Store viene usato per i file audio dei nomi registrati. File Store è un componente standard in tutte le distribuzioni Enterprise Edition o Standard Edition.

  - **** L'archivio utente dell'archivio utente viene usato per archiviare i pin di 2013 di Lync Server.    Vengono hashati i pin. L'archivio utenti è un componente standard in tutte le distribuzioni Enterprise Edition o Standard Edition.

  - **Pannello di controllo di Lync Server**   alcune impostazioni di accesso esterno possono essere configurate tramite il pannello di controllo di Lync Server.

  - **Lync Server Management Shell**   tutte le impostazioni di accesso esterno possono essere configurate usando i cmdlet di Lync Server Management Shell. I cmdlet di Lync Server Management Shell sono disponibili per la distribuzione, la configurazione, l'uso, il monitoraggio e la risoluzione dei problemi relativi all'applicazione per i servizi di conferenza. Per informazioni dettagliate sui cmdlet specifici, vedere documentazione di Lync Server Management Shell.

</div>

<div>

## <a name="supported-topologies"></a>Topologie supportate

In Lync Server 2013 il server che gestisce i servizi di conferenza viene sempre collocato con i server front-end o i server Standard Edition. Durante la distribuzione iniziale, generatore di topologia offre la possibilità di includere i servizi di conferenza nella topologia. È anche possibile usare generatore di topologie per aggiungere servizi di conferenza a una distribuzione esistente. Per informazioni dettagliate, vedere [definizione e configurazione della topologia in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).

<div>

## <a name="dial-in-conferencing-toplogies"></a>Chiamata in conferenza Toplogies

È possibile distribuire i servizi di conferenza telefonica con accesso esterno nelle topologie e nelle configurazioni seguenti:

  - Lync Server 2013 Standard Edition

  - Lync Server 2013 Enterprise Edition

  - Con o senza VoIP aziendale

È possibile distribuire il servizio applicazione, l'applicazione per i servizi di conferenza e l'applicazione di annunci di conferenza in un sito centrale, ma non in un sito di succursale.

<div>


> [!NOTE]  
> Se si distribuiscono i servizi di conferenza telefonica con accesso esterno, è necessario distribuirla in tutti i pool in cui si distribuiscono le conferenze di Lync Server 2013. Non è necessario assegnare numeri di accesso in tutti i pool, ma è necessario distribuire la funzionalità di conferenza telefonica tramite accesso esterno in tutti i pool. Questo requisito supporta la caratteristica nome registrato quando un utente chiama un numero di accesso da un pool per partecipare a una conferenza di Lync Server 2013 in un pool diverso.



</div>

</div>

<div>

## <a name="supported-topologies-for-lync-server-2013-and-office-web-apps"></a>Topologie supportate per Lync Server 2013 e Office Web Apps

Lync Server 2013 offre i modi seguenti per configurare Office Web Apps Server. A seconda delle proprie esigenze, è possibile:

  - **Installare sia Lync Server 2013 che Office Web Apps Server in locale dietro il firewall dell'organizzazione e nella stessa area di rete.** Con questa topologia, l'accesso esterno a Office Web Apps Server verrà fornito tramite il server proxy inverso. Sia Lync Server 2013 che Office Web Apps Server (o una farm di Office Web Apps Server) sono installati in locale e dietro il firewall dell'organizzazione. In teoria, è consigliabile installare Office Web Apps Server nella stessa area di rete di Lync Server.
    
    I client Lync esterni possono connettersi a Lync Server 2013 e a Office Web Apps Server usando un server proxy inverso, che è un server che accetta richieste da Internet e le inoltra alla rete interna. I client interni non devono usare il server proxy inverso perché possono connettersi direttamente a Office Web Apps Server. Questa topologia funziona meglio se si vuole usare una farm di server Office Web Apps dedicata che viene usata solo da Lync Server 2013.

  - **Uso di un server Office Web Apps distribuito esternamente**
    
    In questa topologia Lync Server 2013 viene distribuito in locale e usa un server di Office Web Apps distribuito all'esterno dell'area di rete di Lync Server. Questo problema può verificarsi quando il server Office Web Apps è condiviso tra più applicazioni della società e viene distribuito in una rete che richiede a Lync Server di usare l'interfaccia esterna di Office Web Apps Server e viceversa.
    
    Non è necessario installare un server proxy inverso; tutte le richieste di Office Web Apps Server a Lync Server 2013 vengono invece instradate tramite il server perimetrale. Sia i client Lync interni che quelli esterni si connettono a Office Web Apps Server usando l'URL esterno.
    
    Se il server Office Web Apps è distribuito all'esterno del firewall interno, selezionare l'opzione **Office Web Apps Server è distribuito in una rete esterna (ovvero perimetro/Internet)** in Generatore di topologie. Per altri dettagli [, vedere Configurazione dell'integrazione con Office Web Apps Server e Lync server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

Indipendentemente dalla topologia selezionata, è fondamentale che vengano aperte le porte del firewall corrette. È necessario assicurarsi che i nomi DNS, gli indirizzi IP e le porte non vengano bloccati dai firewall nel server Office Web Apps, nel servizio di bilanciamento del carico o in Lync Server.

<div>


> [!NOTE]  
> Un'altra opzione per fornire l'accesso esterno a Office Web Apps Server consiste nel distribuire il server nella rete perimetrale. Se si sceglie di eseguire questa operazione, tieni presente che la configurazione del server Office Web Apps richiede che il computer server sia membro del dominio Active Directory. A meno che i criteri di rete non consentano ai computer della rete perimetrale di essere membri del dominio Active Directory, è consigliabile non installare Office Web Apps Server nella rete perimetrale. È invece necessario installare Office Web Apps Server nella rete interna e consentire l'accesso degli utenti esterni tramite il server proxy inverso.



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

