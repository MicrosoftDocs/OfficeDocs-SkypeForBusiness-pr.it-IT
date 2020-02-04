---
title: "Lync Server 2013: Gestire la configurazione Access Edge per l'organizzazione"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manage Access Edge Configuration for your organization
ms:assetid: 0145eb08-984f-4ecd-bf9c-364817619c2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552443(v=OCS.15)
ms:contentKeyID: 48679555
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4739599f92b9189a208e1bb320a53b82d66a3a9c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733446"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-access-edge-configuration-for-your-organization-in-lync-server-2013"></a>Gestire la configurazione Access Edge per l'organizzazione in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-11-01_

Questa è la documentazione preliminare ed è soggetta a modifiche. Gli argomenti vuoti sono inclusi come segnaposto.

Dopo la distribuzione di uno o più server perimetrali, è necessario abilitare i tipi di accesso esterno al dominio o al provider, l'accesso remoto agli utenti e l'accesso degli utenti anonimi alle conferenze tramite gli Edge Server che verranno supportati per l'organizzazione.

Queste opzioni includono i seguenti tipi di Access che possono essere configurati tramite la pagina di **configurazione di Access Edge** :

  - **Abilitazione della Federazione e della connettività**   per messaggistica istantanea pubblica abilitare questa operazione se si vuole supportare l'accesso degli utenti ai domini partner federati. Questa impostazione si applica sia alla federazione SIP che alla Federazione XMPP configurate per gli ambiti globali, per i siti o per gli utenti nella pagina **criteri di accesso esterno** . Per applicare le impostazioni federative, è necessario configurare il supporto federativo in entrambe le pagine.
    
    Esistono due opzioni che sono impostazioni facoltative per il modo in cui vengono individuati i partner federati e se l'archiviazione delle dichiarazioni di non conformità (notifica ai contatti federati con cui si comunica che la distribuzione ha l'archiviazione abilitata e che le comunicazioni i dettagli verranno archiviati) verranno inviati ai contatti
    
      - **Abilitare l'individuazione**   di un dominio partner selezionando questa opzione è possibile individuare automaticamente i domini con cui si può usare la Federazione. Lync Server 2013 USA i record DNS (Domain Name System) per cercare di individuare i domini non elencati nell'elenco dei domini consentiti, valutando automaticamente il traffico in entrata da partner federati individuati e limitando o bloccando il traffico in base al livello di attendibilità. quantità di traffico e impostazioni di amministratore. Se non si seleziona questa opzione, l'accesso degli utenti federati è abilitato solo per gli utenti nei domini inclusi nell'elenco dei domini consentiti. Indipendentemente dal fatto che questa opzione sia selezionata, è possibile specificare che i singoli domini vengano bloccati o consentiti, incluso il limitare l'accesso a server specifici che gestiscono il servizio Access Edge nel dominio federato. Per informazioni dettagliate, vedere [configurare il supporto per i domini esterni consentiti in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).
    
      - **Inviare una dichiarazione di non responsabilità per i partner**   federati selezionare questa opzione consente l'invio di un messaggio di dichiarazione di non responsabilità per i partner federati che consigliano di registrare i dettagli delle comunicazioni. Se si archiviano comunicazioni esterne con domini partner federati, è necessario abilitare la notifica di dichiarazione di non responsabilità per l'archiviazione per avvisare i partner che i messaggi e i dettagli delle comunicazioni vengono archiviati dalla distribuzione. Per informazioni dettagliate sull'archiviazione, vedere [definizione dei requisiti per l'archiviazione in Lync Server 2013](lync-server-2013-defining-your-requirements-for-archiving.md).

  - **Abilitare l'accesso**   degli utenti remoti per abilitare questa opzione se si vuole che gli utenti dell'organizzazione che si trovano all'esterno del firewall, ad esempio i telelavoratori e gli utenti che viaggiano, possano connettersi a Lync Server. Per informazioni dettagliate, vedere [abilitare o disabilitare l'accesso remoto agli utenti in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).

  - **Consentire agli utenti anonimi di accedere alle conferenze**   abilitare questa opzione se si vuole che gli utenti interni invitino utenti anonimi esterni alle conferenze organizzate. L'abilitazione di questa impostazione consente solo agli utenti anonimi di conferenze. Per configurare l'esperienza e le opzioni per i servizi di conferenza che definiscono come e cosa possono fare gli utenti con le conferenze e per l'inclusione di utenti anonimi, vedere dettagli su come [creare o modificare l'esperienza utente dei servizi di conferenza per un sito o gli utenti](https://technet.microsoft.com/en-us/library/gg429715\(v=ocs.15\)) e [le impostazioni dei criteri di conferenza per Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).

<div>


> [!NOTE]  
> Oltre a consentire il supporto degli accessi esterni agli utenti, è anche possibile configurare i criteri per controllare l'uso dell'accesso degli utenti remoti nell'organizzazione prima che l'utente sia disponibile per qualsiasi tipo di accesso da utenti esterni. Per informazioni dettagliate sulla creazione, la configurazione e l'applicazione di criteri per l'accesso degli utenti esterni, vedere <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">gestire i criteri di accesso esterno in Lync Server 2013</A>.



</div>

**Visualizzazione delle informazioni di configurazione di Access Edge tramite i cmdlet di Windows PowerShell**

  - Le informazioni sulla configurazione di Access Edge possono essere visualizzate usando Windows PowerShell e il cmdlet **Get-CsAccessEdgeConfiguration** . Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.
    
    Per visualizzare informazioni su tutte le impostazioni di configurazione di Access Edge, digitare il comando seguente in Lync Server Management Shell e quindi premere INVIO:
    
        Get-CsAccessEdgeConfiguration
    
    Questo restituirà informazioni simili alla seguente:
    
        Identity                               : Global
        AllowAnonymousUsers                    : False
        AllowFederatedUsers                    : False
        AllowOutsideUsers                      : True
        BeClearingHouse                        : False
        EnablePartnerDiscovery                 : False
        EnableArchivingDisclaimer              : False
        EnableUserReplicator                   : True
        KeepCrlsUpToDateForPeers               : True
        MarkSourceVerifiableOnOutgoingMessages : True
        OutgoingTlsCountForFederatedPartners   : 4
        DiscoveredPartnerStandardRate          : 20
        EnableDiscoveredPartnerContactsLimit   : True
        MaxContactsPerDiscoveredPartner        : 1000
        DiscoveredPartnerReportPeriodMinutes   : 60
        MaxAcceptedCertificatesStored          : 1000
        MaxRejectedCertificatesStored          : 500
        CertificatesDeletedPercentage          : 20
        RoutingMethod                          : UseDnsSrvRouting

<div>

## <a name="in-this-section"></a>Contenuto della sezione

  - [Abilitare o disabilitare la federazione e la connettività per la messaggistica istantanea pubblica in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)

  - [Abilitare o disabilitare l'individuazione dei partner della federazione in Lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)

  - [Abilitare o disabilitare l'invio di una dichiarazione di non responsabilità relativa all'archiviazione ai partner federati in Lync Server 2013](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)

  - [Abilitare o disabilitare l'accesso degli utenti remoti in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md)

  - [Abilitare o disabilitare l'accesso degli utenti anonimi in Lync Server 2013](lync-server-2013-enable-or-disable-anonymous-user-access.md)

  - [Assegnare i criteri di conferenza per supportare gli utenti anonimi in Lync Server 2013](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

