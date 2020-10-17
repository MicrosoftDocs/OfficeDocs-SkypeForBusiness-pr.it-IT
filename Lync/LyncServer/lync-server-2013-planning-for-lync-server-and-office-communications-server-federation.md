---
title: Pianificazione della Federazione di Lync Server e Office Communications Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Lync Server and Office Communications Server federation
ms:assetid: c9eaf06b-054f-41a4-ad0c-499400d6c4c7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205335(v=OCS.15)
ms:contentKeyID: 48185640
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 801237e4390cd81ac634a928f4963be1c930d01e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522023"
---
# <a name="planning-for-lync-server-2013-and-office-communications-server-federation"></a>Planning for Lync Server 2013 e Office Communications Server Federation

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-13_

La Federazione tra Microsoft Lync Server 2013, Lync Server 2010 e Office Communications Server supporta le comunicazioni peer-to-peer e multi-party. È possibile effettuare l'escalation delle conversazioni peer-to-peer a conversazioni tra più parti, consentendo l'esecuzione di riunioni ad hoc. Le riunioni, che possono essere conferenze Web o conferenze audio/video, possono essere pianificate in modo da includere contatti all'interno dell'organizzazione e contatti partner con cui si attua la federazione.

La Federazione è stata introdotta per la prima volta in Microsoft Office Live Communications Server 2005 e ha supportato un tipo di federazione, Direct Federation. Direct Federation richiede di conoscere il dominio SIP (Session Initiation Protocol) del partner federativo e il nome di dominio completo (FQDN) del server perimetrale del partner. In Live Communications Server 2005 con SP1 sono stati introdotti altri tipi di federazione, tutti i quali sono necessari record SRV DNS (Domain Name System) che devono essere pubblicati dal partner federato per individuare il server perimetrale. La terminologia relativa a tale versione è stata la seguente:

  - *Aprire Federazione avanzata*: accettare qualsiasi nome di dominio SIP e utilizzare DNS SRV per individuare il server perimetrale partner

  - *Federazione avanzata*: configurare il nome di dominio SIP del partner come partner federativo per l'organizzazione e utilizzare DNS SRV per trovare il server perimetrale del partner

  - *Federazione diretta*: configurare il nome di dominio SIP del partner e l'FQDN nel server perimetrale del partner

  - *Elenco Consenti server*: accettare qualsiasi dominio, utilizzare DNS SRV per individuare il server perimetrale di un provider di hosting o di un provider di connettività per la messaggistica istantanea pubblica

Microsoft Office Communications Server 2007 ha introdotto la denominazione aggiornata per i tipi di federazione per definire meglio ciò che ogni tipo di Federazione ha effettivamente ottenuto:

  - La federazione avanzata aperta è stata denominata *dominio individuato del partner*.

  - La federazione avanzata è stata denominata *dominio partner consentito*.

  - La federazione diretta è stata denominata *server partner consentito*.

  - L'elenco dei server consentiti è stato denominato *provider di hosting* e *provider di servizi di messaggistica istantanea pubblica*.

Microsoft Lync Server 2010 ha introdotto una definizione più restrittiva del provider di hosting in conformità con Microsoft Lync Online 2010 e Microsoft Office 365 e ha anche reso soggetto allo stesso elenco consentito definito dal tipo di Federazione del dominio del partner consentito.

L'abilitazione della Federazione tra Microsoft Lync Server 2013, Lync Server 2010 e Office Communications Server utilizza i server perimetrali e i proxy inversi per applicare le regole e i domini partner consentiti definiti. Da un punto di vista della pianificazione, la Federazione con altri Lync Server, Office Communications Server richiede quanto segue:

  - Abilitare la federazione in Generatore di topologie. Per informazioni dettagliate, vedere la sezione relativa alla distribuzione di [federazione SIP, Federazione XMPP e messaggistica istantanea pubblica in Lync Server 2013](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md).

  - Determinare i propri requisiti per l'individuazione del dominio federato:
    
      - <span></span>  
        Per la configurazione manuale della Federazione, è necessario disporre del nome di dominio completo (FQDN) del server perimetrale e del nome di dominio del partner oppure del nome di dominio online, immesso nel pannello di controllo di Lync Server, nella **Federazione e nell'accesso esterno**, ovvero nei **domini federati SIP**. Creare nuovi criteri facendo clic su **Nuovo** oppure modificare criteri esistenti facendo clic su **Modifica** in modo da consentire o bloccare i domini in base all'FQDN.
        
        <div>
        

        > [!WARNING]
        > La configurazione manuale del server perimetrale di un partner federativo è soggetta a un errore nel caso in cui il partner modifichi l'indirizzo IP del server perimetrale.

        
        </div>
        
        <div>
        

        > [!NOTE]
        > Per i <STRONG>nuovi domini federati SIP</STRONG>, è necessario fornire il <STRONG>nome di dominio (o FQDN)</STRONG> per Microsoft Lync Online e microsoft 365 o Office 365. Per Microsoft Lync Server 2013, Lync Server 2010 e Office Communications Server è inoltre necessario fornire un <STRONG>servizio Access Edge (FQDN)</STRONG>

        
        </div>
    
      - <span></span>  
        Per la Federazione partner individuata, in cui i partner possono individuare il server perimetrale, è necessario creare un record SRV nel DNS esterno- \_ sipfederationtls. \_ tcp.contoso.com – che punta alla porta 5061 e al record host (A) del server perimetrale
        
        <div>
        

        > [!IMPORTANT]
        > Se si supportano client Microsoft Lync Mobile su Windows Phone o Apple iPhone, iPad o altri dispositivi Apple e si utilizza il servizio di notifica push o di notifica push, è necessario pianificare _sipfederationtls. _tcp. &lt;&gt;Record SRV di dominio SIP per ogni dominio SIP di cui si dispone di client mobili di Lync. Android e Nokia Symbian Lync mobile non utilizzano la notifica push e non sono soggetti a questo requisito.

        
        </div>

  - Configurare criteri di accesso utenti esterni per il supporto dei domini federati.

  - Aprire le porte del firewall per il protocollo SIP (Session Initiation Protocol), le conferenze Web e le conferenze audio/video per supportare la federazione o i contatti abilitati. Per informazioni dettagliate, vedere: [determinare i requisiti di porte e firewall a/V esterni per Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)

Le informazioni seguenti consentono di definire il certificato, il protocollo e i requisiti DNS per la Federazione con Microsoft Lync Server 2013 e Lync Server 2010.

La pianificazione per i certificati, i requisiti del firewall e del protocollo di trasporto e i requisiti DNS è in genere un processo diretto se sono stati pianificati o distribuiti i server perimetrali di Microsoft Lync Server 2013. Poiché la Federazione è una funzionalità aggiuntiva che utilizza il server perimetrale esistente, i requisiti di pianificazione vengono in genere soddisfatti dalla pianificazione e dalla distribuzione del server perimetrale. È consigliabile utilizzare le tabelle seguenti per verificare che i requisiti vengano soddisfatti e apportare eventuali modifiche a porte/protocolli e DNS in base alle esigenze.

<div>


> [!IMPORTANT]
> Se si dispone di un pool di server perimetrali e si esegue la Federazione con i partner di Lync Server 2013 o Lync Server 2010, è possibile utilizzare il bilanciamento del carico DNS o i dispositivi di bilanciamento del carico hardware sui lati interni ed esterni dei server perimetrali. Se si sta effettuando la Federazione con Office Communications Server 2007 o Office Communications Server 2007 R2, il bilanciamento del carico hardware fornirà supporto per il failover nel caso di un server perimetrale. Office Communications Server 2007 e Office Communications Server 2007 R2 non sono compatibili con il bilanciamento del carico DNS. I server perimetrali partner stabiliranno la comunicazione con il primo server perimetrale del pool che risponde. Se il server perimetrale ha esito negativo, la comunicazione non esegue automaticamente il failover.



</div>

I requisiti dei certificati vengono in genere soddisfatti tramite la pianificazione di certificati per il server perimetrale o il piano server perimetrale scelto.

<div>

## <a name="in-this-section"></a>Argomenti della sezione

  - [Riepilogo del certificato-SIP, Federazione XMPP e messaggistica istantanea pubblica in Lync Server 2013](lync-server-2013-certificate-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - [Riepilogo delle porte-SIP, Federazione XMPP e messaggistica istantanea pubblica in Lync Server 2013](lync-server-2013-port-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - [Riepilogo DNS-SIP, Federazione XMPP e messaggistica istantanea pubblica in Lync Server 2013](lync-server-2013-dns-summary-sip-xmpp-federation-and-public-instant-messaging.md)

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Configurare criteri per controllare l'accesso degli utenti federati in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md)  


[Scenari per l'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)  
[Determinare i requisiti di porte e firewall A/V esterni per Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
[Determinare i requisiti DNS per Lync Server 2013](lync-server-2013-determine-dns-requirements.md)  


[Gestire la configurazione di Access Edge per l'organizzazione in Lync Server 2013](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)  
[Gestire i domini federati SIP per l'organizzazione in Lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[Gestire i provider federati SIP per l'organizzazione in Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

