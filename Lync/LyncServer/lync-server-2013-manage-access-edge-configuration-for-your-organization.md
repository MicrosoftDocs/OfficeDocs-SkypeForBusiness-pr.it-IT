---
title: "Lync Server 2013: gestire la configurazione di Access Edge per l'organizzazione"
description: "Lync Server 2013: gestire la configurazione di Access Edge per l'organizzazione."
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
ms.openlocfilehash: 2161385f9c03f025bcf6f5e599b7e0276f6d592c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550642"
---
# <a name="manage-access-edge-configuration-for-your-organization-in-lync-server-2013"></a>Gestire la configurazione di Access Edge per l'organizzazione in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-11-01_

Si tratta di una documentazione preliminare e soggetta a modifiche. Gli argomenti vuoti sono inclusi come segnaposto.

Dopo la distribuzione di uno o più server perimetrali, è necessario abilitare i tipi di accesso di dominio esterno o di provider, accesso utente remoto e accesso degli utenti anonimi alle conferenze tramite i server perimetrali che saranno supportati per l'organizzazione.

Queste opzioni includono i tipi seguenti di accesso, che possono essere configurati nella pagina **Configurazione Access Edge**:

  - **Abilitare la Federazione e la connettività**     per la messaggistica istantanea pubblica Abilitare questa operazione se si desidera supportare l'accesso degli utenti ai domini partner federati. Questa impostazione si applica sia alla federazione SIP che alla Federazione XMPP configurati per gli ambiti globali, dei siti o degli utenti nella pagina **criteri di accesso esterno** . Per applicare le impostazioni di federazione, è necessario configurare il supporto federativo in entrambe le pagine.
    
    Esistono due opzioni che costituiscono impostazioni facoltative relative al modo in cui i partner federati vengono individuati e indicano se ai contatti verranno inviate le dichiarazioni di non responsabilità di archiviazione, ovvero notifiche che informano i contatti federati con cui si comunica che l’archiviazione è abilitata nella distribuzione e che i dettagli delle comunicazioni verranno archiviati.
    
      - **Abilitare l'individuazione**     del dominio del partner Selezionando questa opzione, viene abilitata l'individuazione automatica dei domini che è possibile federare con. Lync Server 2013 utilizza i record DNS (Domain Name System) per cercare di individuare i domini non elencati nell'elenco dei domini consentiti, valutando automaticamente il traffico in ingresso proveniente da partner federati individuati e limitando o bloccando il traffico in base al livello di attendibilità, alla quantità di traffico e alle impostazioni di amministratore. Se non si seleziona questa opzione, l'accesso degli utenti federati viene abilitato solo per gli utenti dei domini inclusi nell'elenco di domini consentiti. Indipendentemente dalla selezione di questa opzione, è possibile specificare se bloccare o consentire singoli domini, nonché limitare l'accesso a server specifici che eseguono il servizio Access Edge nel dominio federato. Per ulteriori informazioni, vedere [configurare il supporto per i domini esterni consentiti in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).
    
      - **Inviare la dichiarazione di non responsabilità per l'archiviazione ai partner federati**     Selezionando questa opzione, viene abilitato l'invio di un messaggio di dichiarazione di non responsabilità per l'archiviazione ai partner federati che consigliano che vengano registrati i dettagli della comunicazione. Se si archiviano comunicazioni esterne con domini partner federati, è consigliabile abilitare la dichiarazione di non responsabilità relativa all'archiviazione per avvisare i partner che i dettagli relativi a messaggi e comunicazioni vengono archiviati dalla distribuzione. Per informazioni dettagliate sull'archiviazione, vedere [definizione dei requisiti per l'archiviazione in Lync Server 2013](lync-server-2013-defining-your-requirements-for-archiving.md).

  - **Abilitare l'accesso**     degli utenti remoti Abilitare questa opzione se si desidera che gli utenti dell'organizzazione che si trovano all'esterno del firewall, ad esempio i telelavoratori e gli utenti che viaggiano, siano in grado di connettersi a Lync Server. Per ulteriori informazioni, vedere [Abilitazione o disabilitazione dell'accesso degli utenti remoti in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).

  - **Abilitazione degli utenti anonimi all'accesso alle conferenze**     Abilitare questa opzione se si desidera che gli utenti interni invitino gli utenti anonimi esterni alle conferenze organizzate. L'abilitazione di questa impostazione consente solo agli utenti anonimi per le conferenze. Per configurare l'esperienza di conferenza e le opzioni che definiscono come e cosa gli utenti possono fare con le conferenze e per l'inclusione di utenti anonimi, vedere informazioni dettagliate su [Create or modify Conferencing user experience for a site or users](https://technet.microsoft.com/library/gg429715\(v=ocs.15\)) and [Conferencing Policy Settings Reference for Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).

<div>


> [!NOTE]  
> Oltre ad abilitare il supporto per l'accesso utenti esterni, è necessario configurare anche criteri per controllare l'uso dell'accesso remoto utenti nell'organizzazione, prima che qualsiasi tipo di accesso utente esterno venga reso disponibile per gli utenti. Per informazioni dettagliate sulla creazione, la configurazione e l'applicazione di criteri per l'accesso degli utenti esterni, vedere <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">gestire i criteri di accesso esterno in Lync Server 2013</A>.



</div>

**Visualizzazione delle informazioni sulla configurazione di Access Edge tramite i cmdlet di Windows PowerShell**

  - È possibile visualizzare le informazioni di configurazione di Access Edge utilizzando Windows PowerShell e il cmdlet **Get-CsAccessEdgeConfiguration** . Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync Server 2010 using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .
    
    Per visualizzare informazioni su tutte le impostazioni di configurazione di Access Edge, digitare il comando seguente in Lync Server Management Shell e quindi premere INVIO:
    
        Get-CsAccessEdgeConfiguration
    
    Verranno restituite informazioni simili alle seguenti:
    
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

## <a name="in-this-section"></a>Argomenti della sezione

  - [Abilitare o disabilitare la Federazione e la connettività per la messaggistica istantanea pubblica in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)

  - [Abilitare o disabilitare l'individuazione dei partner federativi in Lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)

  - [Abilitare o disabilitare l'invio di una dichiarazione di non responsabilità per l'archiviazione ai partner federati in Lync Server 2013](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)

  - [Abilitazione o disabilitazione dell'accesso degli utenti remoti in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md)

  - [Abilitazione o disabilitazione dell'accesso degli utenti anonimi in Lync Server 2013](lync-server-2013-enable-or-disable-anonymous-user-access.md)

  - [Assegnare i criteri di conferenza per supportare gli utenti anonimi in Lync Server 2013](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

