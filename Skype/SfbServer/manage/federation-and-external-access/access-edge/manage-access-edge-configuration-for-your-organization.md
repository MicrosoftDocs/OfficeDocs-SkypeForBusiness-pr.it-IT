---
title: Gestire la configurazione Access Edge per l'organizzazione
ms.reviewer: null
'ms:assetid': 0145eb08-984f-4ecd-bf9c-364817619c2a
'ms:mtpsurl': 'https://technet.microsoft.com/en-us/library/JJ552443(v=OCS.15)'
'ms:contentKeyID': 48679555
mtps_version: v=OCS.15
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
description: 'Dopo aver distribuito uno o più server perimetrali, è necessario abilitare i tipi di accesso al dominio o al provider esterno, l''accesso degli utenti remoti e l''accesso utente anonimo alle conferenze tramite i server perimetrali che saranno supportati per l''organizzazione.'
---

# <a name="manage-access-edge-configuration-for-your-organization"></a>Gestire la configurazione Access Edge per l'organizzazione

Dopo aver distribuito uno o più server perimetrali, è necessario abilitare i tipi di accesso al dominio o al provider esterno, l'accesso degli utenti remoti e l'accesso utente anonimo alle conferenze tramite i server perimetrali che saranno supportati per l'organizzazione.

Queste opzioni includono i tipi seguenti di accesso, che possono essere configurati nella pagina **Configurazione Access Edge**:

  - **Abilitare la federazione e la connettività di messaggistica istantanea pubblica**   Abilitare questa opzione se si desidera supportare l'accesso degli utenti ai domini partner federati. Questa impostazione si applica alla federazione SIP configurata per ambiti globali, siti o utenti nella **pagina Criteri di accesso** esterno. Per applicare le impostazioni di federazione, è necessario configurare il supporto della federazione in entrambe le pagine.
    
    Esistono due opzioni che sono impostazioni facoltative per il modo in cui vengono individuati i partner federati e se le dichiarazioni di non responsabilità di archiviazione (notifica ai contatti federati con cui si comunica che la distribuzione ha l'archiviazione abilitata e che i dettagli delle comunicazioni verranno archiviati) verranno inviate ai contatti:
    
      - **Abilitare l'individuazione del dominio partner**   Selezionando questa opzione viene abilitata l'individuazione automatica dei domini con cui è possibile eseguire la federazione. Skype for Business Server utilizza i record DNS (Domain Name System) per cercare di individuare i domini non elencati nell'elenco dei domini consentiti, valutando automaticamente il traffico in ingresso dai partner federati individuati e limitando o bloccando tale traffico in base al livello di attendibilità, alla quantità di traffico e alle impostazioni dell'amministratore. Se non si seleziona questa opzione, l'accesso degli utenti federati viene abilitato solo per gli utenti dei domini inclusi nell'elenco di domini consentiti. Indipendentemente dalla selezione di questa opzione, è possibile specificare se bloccare o consentire singoli domini, nonché limitare l'accesso a server specifici che eseguono il servizio Access Edge nel dominio federato. Per informazioni dettagliate, [vedere Configure support for allowed external domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).
    
      - **Inviare la dichiarazione di non responsabilità di archiviazione ai partner federati**   Se si seleziona questa opzione, viene abilitata l'invio di un messaggio di dichiarazione di non responsabilità di archiviazione ai partner federati che avvisa che i dettagli delle comunicazioni vengono registrati. Se si archiviano comunicazioni esterne con domini partner federati, è consigliabile abilitare la dichiarazione di non responsabilità relativa all'archiviazione per avvisare i partner che i dettagli relativi a messaggi e comunicazioni vengono archiviati dalla distribuzione. Per informazioni dettagliate sull'archiviazione, vedere [Enable or disable sending an Archiving disclaimer to federated partner](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).

  - **Abilitare l'accesso utente remoto**   Abilitare questa opzione se si desidera che gli utenti dell'organizzazione esterni al firewall, ad esempio i telelavoratori e gli utenti in viaggio, possano connettersi a Skype for Business Server. Per informazioni dettagliate, vedere [Enable or disable remote user access](enable-or-disable-remote-user-access.md).

  - **Consentire agli utenti anonimi di accedere alle conferenze**   Abilitare questa opzione se si desidera che gli utenti interni invitino utenti anonimi esterni alle conferenze che organizzano. L'abilitazione di questa impostazione consente solo agli utenti anonimi di conferenze.

> [!NOTE]  
> Oltre ad abilitare il supporto per l'accesso utenti esterni, è necessario configurare anche criteri per controllare l'uso dell'accesso remoto utenti nell'organizzazione, prima che qualsiasi tipo di accesso utente esterno venga reso disponibile per gli utenti. Per informazioni dettagliate sulla creazione, la configurazione e l'applicazione di criteri per l'accesso degli utenti esterni, vedere [Manage external access policy for your organization](../external-access-policies/manage-external-access-policy-for-your-organization.md).

**Visualizzazione delle informazioni di configurazione di Access Edge tramite Windows PowerShell cmdlet**

  - Le informazioni di configurazione di Access Edge possono essere visualizzate utilizzando Windows PowerShell e il cmdlet **Get-CsAccessEdgeConfiguration**. Questo cmdlet può essere eseguito da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. 
    
    Per visualizzare informazioni su tutte le impostazioni di configurazione di Access Edge, digitare il comando seguente in Skype for Business Server Management Shell e quindi premere INVIO:
    
     `Get-CsAccessEdgeConfiguration`
    
    Verranno restituite informazioni simili alle seguenti:
    
    Identity : Global<br/>
    AllowAnonymousUsers : False<br/>
    AllowFederatedUsers : False<br/>
    AllowOutsideUsers : True<br/>
    BeClearingHouse : False<br/>
    EnablePartnerDiscovery : False<br/>
    EnableArchivingDisclaimer : False<br/>
    EnableUserReplicator : True<br/>
    KeepCrlsUpToDateForPeers : True<br/>
    MarkSourceVerifiableOnOutgoingMessages : True<br/>
    OutgoingTlsCountForFederatedPartners : 4<br/>
    DiscoveredPartnerStandardRate : 20<br/>
    EnableDiscoveredPartnerContactsLimit : True<br/>
    MaxContactsPerDiscoveredPartner : 1000<br/>
    DiscoveredPartnerReportPeriodMinutes : 60<br/>
    MaxAcceptedCertificatesStored : 1000<br/>
    MaxRejectedCertificatesStored : 500<br/>
    CertificatesDeletedPercentage : 20<br/>
    RoutingMethod : UseDnsSrvRouting<br/>

