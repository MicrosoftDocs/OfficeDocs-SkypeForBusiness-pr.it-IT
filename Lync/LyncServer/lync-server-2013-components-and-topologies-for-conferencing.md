---
title: Lync Server 2013 componenti e topologie per le conferenze
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
ms.openlocfilehash: cfdb6ae250e3ccb97f044892daa8ac11e7c1b99b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502583"
---
# <a name="components-and-topologies-for-conferencing-in-lync-server-2013"></a>Componenti e topologie per le conferenze in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-04_

Quando si seleziona conferenza in Generatore di topologie, le conferenze vengono distribuite come parte del front end server o del server Standard Edition. La conferenza telefonica con accesso esterno e la condivisione PowerPoint richiedono configurazioni e componenti aggiuntivi. Nelle sezioni seguenti vengono descritti i componenti e le topologie supportati per Web Conferencing, A/V Conferencing e conferenza telefonica con accesso esterno.

<div>

## <a name="supported-components"></a>Componenti supportati

Gli unici componenti Web Conferencing e A/V Conferencing require sono i front end server dell'organizzazione o i server Standard Edition. Per un elenco dei requisiti hardware e software per i Front End Server e i server Standard Edition, vedere [hardware supportato per Lync server 2013](lync-server-2013-supported-hardware.md) e [supporto dell'infrastruttura e del software server in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md).

Lync Server 2013 utilizza Office Web Apps e il server Office Web Apps per gestire la condivisione e il rendering delle presentazioni di PowerPoint. Per informazioni dettagliate sull'installazione e sulla configurazione del server Office Web Apps, vedere [configurazione dell'integrazione con Office Web Apps Server e Lync server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

Oltre ai requisiti per le conferenze Web e A/V Conferencing, le conferenze telefoniche con accesso esterno utilizzano i seguenti componenti di Lync Server 2013:

  - **Servizio applicazione**     Il servizio applicazione fornisce una piattaforma per la distribuzione, l'hosting e la gestione delle applicazioni UC (Unified Communications). Per le conferenze telefoniche con accesso esterno vengono utilizzate due applicazioni UC che richiedono il servizio applicazione: Operatore Conferenza e Annuncio conferenza. Il servizio applicazione viene installato e attivato per impostazione predefinita in ogni Front End Server in un pool Front End e in ogni server Standard Edition quando si distribuisce un carico di lavoro di conferenza e si seleziona l'opzione di conferenza telefonica con accesso esterno.

  - **Applicazione**     Operatore Conferenza L'applicazione Operatore Conferenza è un'applicazione di comunicazione unificata che accetta le chiamate PSTN (Public Switched Telephone Network), riproduce le richieste e aggiunge le chiamate a una conferenza a/V. L'applicazione Operatore Conferenza è installata e attivata per impostazione predefinita quando si distribuisce un carico di lavoro per le conferenze e si seleziona l'opzione di conferenza telefonica con accesso esterno.

  - **Applicazione**     Annuncio conferenza L'applicazione annuncio per conferenze è un'applicazione di comunicazione unificata che riproduce i toni e richiede ai partecipanti PSTN su determinate azioni, ad esempio quando i partecipanti si uniscono o lasciano una conferenza, i partecipanti sono disattivati o non sono in sordina, qualcuno entra nella sala riunioni o la conferenza è bloccata o sbloccata. L'applicazione Annuncio conferenza supporta anche i comandi DTMF (Dual-Tone Multifrequency) dalla tastiera del telefono. L'applicazione Annuncio conferenza viene automaticamente installata e attivata per impostazione predefinita quando si distribuisce un carico di lavoro per le conferenze e si seleziona l'opzione di conferenza telefonica con accesso esterno.

  - Pagina delle impostazioni **per le conferenze telefoniche con accesso esterno**     La pagina Impostazioni conferenza telefonica con accesso esterno consente di visualizzare i numeri di chiamata in conferenza con le lingue disponibili, le informazioni di conferenza assegnate (ovvero per le riunioni che non devono essere pianificate) e i controlli DTMF in-Conference e supporta la gestione del PIN (Personal Identification Number) e le informazioni di conferenza assegnate. La pagina Impostazioni conferenza telefonica con accesso esterno viene automaticamente installata come parte dei servizi Web.

  - **Lync server 2013, Mediation Server e gateway PSTN**     Per le conferenze telefoniche con accesso esterno è necessario che un Mediation Server converta la segnalazione (e il supporto, in alcune configurazioni) tra Lync Server 2013 e il gateway PSTN, e un gateway PSTN per tradurre la segnalazione e i supporti tra il Mediation Server e il gateway PSTN. Per le conferenze telefoniche con accesso esterno, è necessario distribuire almeno un server Mediation Server e almeno uno dei componenti seguenti:
    
      - Gateway PSTN
    
      - IP-PBX
    
      - SBC (Session Border Controller), per un provider di servizi di telefonia Internet a cui viene eseguita la connessione tramite la configurazione di un trunk SIP
    
    <div>
    

    > [!NOTE]  
    > Se si sta distribuendo anche VoIP aziendale, Mediation Server e gateway PSTN fanno parte della distribuzione di VoIP aziendale. Se non si distribuisce VoIP aziendale, è necessario distribuire almeno un server Mediation Server e un gateway PSTN, un sistema IP-PBX o un servizio SBC per le conferenze telefoniche con accesso esterno.

    
    </div>

  - **Archivio file**     Archivio file viene utilizzato per i file audio dei nomi registrati. Si tratta di un componente standard di ogni distribuzione Enterprise Edition o Standard Edition.

  - **Archivio utenti**     L'archivio utente viene utilizzato per archiviare i pin di Lync Server 2013 dell'utente. I PIN vengono sottoposti a hashing. Si tratta di un componente standard di ogni distribuzione Enterprise Edition o Standard Edition.

  - Pannello di controllo di **Lync Server**     Alcune impostazioni di accesso esterno possono essere configurate utilizzando il pannello di controllo di Lync Server.

  - **Lync Server Management Shell**     Tutte le impostazioni di accesso esterno possono essere configurate utilizzando i cmdlet di Lync Server Management Shell. I cmdlet di Lync Server Management Shell sono disponibili per la distribuzione, la configurazione, l'esecuzione, il monitoraggio e la risoluzione dei problemi relativi all'applicazione per i servizi di conferenza e alle applicazioni di conferenza. Per informazioni dettagliate sui cmdlet specifici, vedere la documentazione di Lync Server Management Shell.

</div>

<div>

## <a name="supported-topologies"></a>Topologie supportate

In Lync Server 2013, il server che esegue servizi di conferenza è sempre collocato con i Front End Server o i server Standard Edition. Durante la distribuzione iniziale, generatore di topologie offre la possibilità di includere le conferenze nella topologia. È inoltre possibile utilizzare Generatore di topologie per aggiungere servizi di conferenza a una distribuzione esistente. Per informazioni dettagliate, vedere [definizione e configurazione della topologia in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).

<div>

## <a name="dial-in-conferencing-toplogies"></a>Topologie di conferenza telefonica con accesso esterno

È possibile distribuire le conferenze telefoniche con accesso esterno nelle topologie e configurazioni seguenti:

  - Lync Server 2013 Standard Edition

  - Lync Server 2013 Enterprise Edition

  - Con o senza VoIP aziendale

È possibile distribuire l'applicazione servizio applicazioni, operatore conferenza e Annuncio conferenza in un sito centrale, ma non in un sito di succursale.

<div>


> [!NOTE]  
> Se si distribuiscono le conferenze telefoniche con accesso esterno, è necessario distribuirle in tutti i pool in cui si distribuisce Lync Server 2013 Conferencing. Non è necessario assegnare numeri di accesso in ogni pool, ma è necessario distribuire la caratteristica di conferenza con accesso esterno in ogni pool. Questo requisito supporta la caratteristica del nome registrato quando un utente chiama un numero di accesso da un pool per partecipare a una conferenza di Lync Server 2013 in un pool diverso.



</div>

</div>

<div>

## <a name="supported-topologies-for-lync-server-2013-and-office-web-apps"></a>Topologie supportate per Lync Server 2013 e Office Web Apps

Lync Server 2013 offre i modi seguenti per configurare il server Office Web Apps. A seconda delle esigenze, è possibile:

  - **Installare sia Lync Server 2013 che il server Office Web Apps in locale dietro il firewall dell'organizzazione e nella stessa area di rete.** Con questa topologia, l'accesso esterno al server Office Web Apps verrà fornito tramite il server proxy inverso. Sia Lync Server 2013 sia il server Office Web Apps (o una farm di server Office Web Apps) sono installati in locale e dietro il firewall dell'organizzazione. Idealmente, è necessario installare il server Office Web Apps nella stessa area di rete di Lync Server.
    
    I client Lync esterni possono connettersi a Lync Server 2013 e al server Office Web Apps utilizzando un server proxy inverso, ovvero un server che accetta richieste da Internet e le inoltra alla rete interna. (I client interni non devono utilizzare il server proxy inverso perché possono connettersi direttamente al server Office Web Apps). Questa topologia funziona meglio se si desidera utilizzare una farm di server Office Web Apps dedicata utilizzata solo da Lync Server 2013.

  - **Utilizzo di un server Office Web Apps distribuito esternamente**
    
    In questa topologia, Lync Server 2013 viene distribuito in locale e utilizza un server Office Web Apps distribuito all'esterno dell'area di rete di Lync Server. Ciò può verificarsi quando il server Office Web Apps è condiviso tra più applicazioni nella società ed è distribuito in una rete che richiede a Lync Server di utilizzare l'interfaccia esterna del server Office Web Apps e viceversa.
    
    Non è necessario installare un server proxy inverso; al contrario, tutte le richieste provenienti dal server Office Web Apps a Lync Server 2013 vengono instradate attraverso il server perimetrale. Sia i client interni che quelli esterni di Lync si connettono al server Office Web Apps utilizzando l'URL esterno.
    
    Se il server Office Web Apps è distribuito all'esterno del firewall interno, selezionare l'opzione il **Server Office Web Apps è distribuito in una rete esterna (ovvero perimetro/Internet)** in Generatore di topologie. Per ulteriori informazioni [, vedere Configurazione dell'integrazione con Office Web Apps Server e Lync server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

Indipendentemente dalla topologia selezionata, è fondamentale aprire le porte del firewall corrette. È necessario assicurarsi che i nomi DNS, gli indirizzi IP e le porte non siano bloccati dai firewall sul server Office Web Apps, sul servizio di bilanciamento del carico o su Lync Server.

<div>


> [!NOTE]  
> Un'altra opzione per fornire accesso esterno al server Office Web Apps consiste nel distribuire il server nella rete perimetrale. Se si sceglie di eseguire questa operazione, tenere presente che l'installazione del server Office Web Apps richiede che il computer server sia membro del dominio di Active Directory. A meno che il criterio di rete non consenta ai computer della rete perimetrale di essere membri del dominio Active Directory, è consigliabile non installare il server Office Web Apps nella rete perimetrale. Al contrario, è necessario installare il server Office Web Apps nella rete interna e fornire l'accesso degli utenti esterni tramite il server proxy inverso.



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

