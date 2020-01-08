---
title: Pianificazione per Lync Server e Office Communications Server Federation
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for Lync Server and Office Communications Server federation
ms:assetid: c9eaf06b-054f-41a4-ad0c-499400d6c4c7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205335(v=OCS.15)
ms:contentKeyID: 48185640
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c683092b61d278d380ad68cef86795d496498fbf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978575"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-lync-server-2013-and-office-communications-server-federation"></a>Pianificazione per Lync Server 2013 e Office Communications Server Federation

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-13_

La Federazione tra Microsoft Lync Server 2013, Lync Server 2010 e Office Communications Server supporta le comunicazioni peer-to-peer e multiparty. Le conversazioni peer-to-peer possono essere Escalate in conversazioni multiparte, consentendo riunioni ad hoc. Riunioni-conferenza Web o conferenze audio/visive-può essere programmato per includere i contatti all'interno dell'organizzazione e i contatti nei partner con cui si federa.

La Federazione è stata pubblicata per la prima volta in Microsoft Office Live Communications Server 2005 e ha supportato un tipo di federazione, Direct Federation. Direct Federation richiede di conoscere il dominio SIP (Session Initiation Protocol) del partner federativo e il nome di dominio completo (FQDN) del server Edge del partner. In Live Communications Server 2005 con SP1 sono stati introdotti altri tipi di federazione, tutti i quali sono necessari record SRV DNS (Domain Name System) che devono essere pubblicati dal partner federativo per individuare il proprio Edge Server. La terminologia relativa a tale versione è stata:

  - *Aprire la federazione avanzata*: accettare qualsiasi nome di dominio SIP e usare DNS SRV per individuare il server Edge partner

  - *Federazione avanzata*: configurare il nome di dominio SIP del partner come partner federativo per l'organizzazione e usare DNS SRV per trovare il server Edge partner

  - *Federazione diretta*: configurare il nome di dominio SIP del partner e l'FQDN nel server perimetrale del partner

  - *Elenco Consenti server*: accettare qualsiasi dominio, usare DNS SRV per trovare il server perimetrale di un provider di hosting o di un provider di connettività messaggistica istantanea pubblica

Microsoft Office Communications Server 2007 ha introdotto la denominazione aggiornata per i tipi di federazione per definire in modo più efficace il risultato di ogni tipo di Federazione:

  - Aprire la federazione avanzata divenne nota come *dominio del partner individuato*

  - La federazione avanzata divenne nota come *dominio del partner consentito*

  - La Federazione diretta divenne nota come *server partner consentiti*

  - L'elenco dei server consentiti divenne noto come *provider di hosting* e *provider di messaggistica istantanea pubblica*

Microsoft Lync Server 2010 ha introdotto una definizione più ristretta del provider di hosting in conformità con Microsoft Lync Online 2010 e Microsoft Office 365 e lo ha anche reso soggetto allo stesso elenco consentiti definito dal tipo di Federazione del dominio partner consentito.

L'abilitazione della Federazione tra Microsoft Lync Server 2013, Lync Server 2010 e Office Communications Server usa gli Edge Server e i proxy inversi per applicare le regole e i domini partner consentiti che si definiscono. Da un punto di vista della pianificazione, la Federazione con altri server Lync, Office Communications Server richiede quanto segue:

  - Abilitare la Federazione in Generatore di topologie. Per informazioni dettagliate, vedere l'argomento sulla distribuzione [configurazione della Federazione SIP, della Federazione XMPP e della messaggistica istantanea pubblica in Lync Server 2013](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md).

  - Determinare i requisiti per l'individuazione di domini federati:
    
      - <span></span>  
        Per la configurazione manuale della Federazione, è necessario avere il nome di dominio completo (FQDN) del server perimetrale e del nome di dominio del partner oppure il nome di dominio online, che viene immesso nel pannello di controllo di Lync Server, nella **Federazione e nell'accesso esterno**, i **domini federati SIP**. Creare un **nuovo** criterio o **modificare** un criterio esistente per consentire o bloccare i domini in base al nome di dominio completo.
        
        <div>
        

        > [!WARNING]
        > La configurazione manuale di un Edge Server del partner federativo è soggetta a un errore se il partner cambia l'indirizzo IP del server perimetrale.

        
        </div>
        
        <div>
        

        > [!NOTE]
        > Per i <STRONG>nuovi domini federati SIP</STRONG>, è necessario specificare il <STRONG>nome di dominio (o FQDN)</STRONG> per Microsoft Lync Online, Microsoft Office 365. Per Microsoft Lync Server 2013, Lync Server 2010 e Office Communications Server è necessario specificare anche un <STRONG>servizio di Access Edge (FQDN)</STRONG>

        
        </div>
    
      - <span></span>  
        Per la Federazione partner scoperta, in cui i partner possono individuare l'Edge Server, è possibile creare un record SRV nel \_DNS esterno-sipfederationtls. \_TCP.contoso.com-che punta alla porta 5061 e al record host (a) del server perimetrale
        
        <div>
        

        > [!IMPORTANT]
        > Se si supportano i client Microsoft Lync Mobile su Windows Phone o Apple iPhone, iPad o altri dispositivi Apple e si usa il servizio di notifica push o il servizio di notifica push, è necessario pianificare _sipfederationtls. _tcp. &lt;SIP Domain&gt; record SRV per ogni dominio SIP in cui sono presenti client mobili Lync. Android e Nokia Symbian Lync mobile non usano la notifica push e non sono soggetti a questo requisito.

        
        </div>

  - Configurare i criteri di accesso degli utenti esterni per supportare i domini federati

  - Aprire le porte del firewall per SIP (Session Initiation Protocol), Web Conferencing e Audio/Visual per supportare la Federazione o i contatti che si stanno abilitando. Per informazioni dettagliate, vedere: [determinare i requisiti per il firewall e la porta esterni a/V per Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)

Le informazioni seguenti ti aiuteranno a definire i requisiti di certificato, porta/protocollo e DNS per la Federazione con Microsoft Lync Server 2013 e Lync Server 2010.

La pianificazione per i certificati, i requisiti per il firewall e la porta/protocollo e i requisiti DNS è in genere un processo semplice se si è pianificato o distribuito i server Edge di Microsoft Lync Server 2013. Dato che Federation è una funzionalità aggiuntiva che usa il server perimetrale esistente, i requisiti di pianificazione vengono in genere soddisfatti dalla pianificazione e distribuzione di Edge Server. È consigliabile usare le tabelle seguenti per determinare che i requisiti sono soddisfatti e apportare le modifiche in porta/protocollo e DNS di conseguenza.

<div>


> [!IMPORTANT]
> Se si dispone di un pool di Edge Server e si esegue la Federazione con i partner di Lync Server 2013 o Lync Server 2010, è possibile usare i dispositivi di bilanciamento del carico DNS o di bilanciamento del carico hardware sui lati interni ed esterni degli Edge Server. Se si esegue la Federazione con Office Communications Server 2007 o Office Communications Server 2007 R2, il bilanciamento del carico hardware fornirà il supporto per il failover in caso di un server perimetrale. Office Communications Server 2007 e Office Communications Server 2007 R2 non supportano il bilanciamento del carico DNS. I server Edge partner stabiliscono le comunicazioni con il primo Edge Server nel pool che risponde. Se il server perimetrale non riesce, la comunicazione non esegue automaticamente il failover.



</div>

I requisiti di certificato vengono in genere soddisfatti tramite la pianificazione di certificati per il piano server Edge o pooled Edge scelto.

<div>

## <a name="in-this-section"></a>Contenuto della sezione

  - [Riepilogo del certificato-SIP, Federazione XMPP e messaggistica istantanea pubblica in Lync Server 2013](lync-server-2013-certificate-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - [Riepilogo della porta-SIP, Federazione XMPP e messaggistica istantanea pubblica in Lync Server 2013](lync-server-2013-port-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - [Riepilogo DNS-SIP, Federazione XMPP e messaggistica istantanea pubblica in Lync Server 2013](lync-server-2013-dns-summary-sip-xmpp-federation-and-public-instant-messaging.md)

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Configurare criteri per controllare l'accesso utente federato in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md)  


[Scenari per l'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)  
[Determinare i requisiti di porte e firewall A/V esterni per Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
[Determinare i requisiti di DNS per Lync Server 2013](lync-server-2013-determine-dns-requirements.md)  


[Gestire la configurazione Access Edge per l'organizzazione in Lync Server 2013](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)  
[Gestire i domini federati SIP per l'organizzazione in Lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[Gestire i provider federati SIP per l'organizzazione in Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

