---
title: Gestire la configurazione Access Edge per l'organizzazione
ms.reviewer: ''
ms:assetid: 0145eb08-984f-4ecd-bf9c-364817619c2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552443(v=OCS.15)
ms:contentKeyID: 48679555
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
description: Dopo aver distribuito uno o più server Perimetrali, è necessario abilitare i tipi di accesso esterno a dominio o provider, accesso utente remoto e accesso utente anonimo alle conferenze tramite i server perimetrali che saranno supportati per l'organizzazione.
ms.openlocfilehash: 228d3c2975d403422795244dafebc0138e385d89
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674598"
---
# <a name="manage-access-edge-configuration-for-your-organization"></a>Gestire la configurazione Access Edge per l'organizzazione

Dopo aver distribuito uno o più server Perimetrali, è necessario abilitare i tipi di accesso esterno a dominio o provider, accesso utente remoto e accesso utente anonimo alle conferenze tramite i server perimetrali che saranno supportati per l'organizzazione.

Queste opzioni includono i tipi seguenti di accesso, che possono essere configurati nella pagina **Configurazione Access Edge**:

  - **Abilitare la federazione e la connettività di messaggistica istantanea pubblica**   Abilita questa opzione se vuoi supportare l'accesso degli utenti ai domini partner federati. Questa impostazione si applica alla federazione SIP configurata per gli ambiti globali, del sito o dell'utente nella pagina **Criteri di accesso esterno** . Per applicare le impostazioni di federazione, è necessario configurare il supporto della federazione in entrambe le pagine.
    
    Esistono due opzioni che sono impostazioni facoltative per il modo in cui vengono individuati i partner federati e se l'archiviazione delle dichiarazioni di non responsabilità (notifica ai contatti federati con cui si comunica che la distribuzione ha abilitato l'archiviazione e che i dettagli delle comunicazioni verranno archiviati) verrà inviata ai contatti:
    
      - **Abilitare l'individuazione del dominio partner**   Se si seleziona questa opzione, viene abilitata l'individuazione automatica dei domini con cui è possibile eseguire la federazione. Skype for Business Server usa i record DNS (Domain Name System) per cercare di individuare i domini non elencati nell'elenco dei domini consentiti, valutando automaticamente il traffico in ingresso dai partner federati individuati e limitando o bloccando il traffico in base al livello di attendibilità, alla quantità di traffico e alle impostazioni di amministratore. Se non si seleziona questa opzione, l'accesso degli utenti federati viene abilitato solo per gli utenti dei domini inclusi nell'elenco di domini consentiti. Indipendentemente dalla selezione di questa opzione, è possibile specificare se bloccare o consentire singoli domini, nonché limitare l'accesso a server specifici che eseguono il servizio Access Edge nel dominio federato. Per informazioni dettagliate, vedere [Configurare il supporto per i domini esterni consentiti](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).
    
      - **Inviare la dichiarazione di non responsabilità per l'archiviazione ai partner federati**   Se si seleziona questa opzione, viene abilitato l'invio di un messaggio di dichiarazione di non responsabilità di archiviazione ai partner federati che informano che i dettagli delle comunicazioni vengono registrati. Se si archiviano comunicazioni esterne con domini partner federati, è consigliabile abilitare la dichiarazione di non responsabilità relativa all'archiviazione per avvisare i partner che i dettagli relativi a messaggi e comunicazioni vengono archiviati dalla distribuzione. Per informazioni dettagliate sull'archiviazione, vedere [Abilitare o disabilitare l'invio di una dichiarazione di non responsabilità di archiviazione al partner federato](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).

  - **Abilitare l'accesso utente remoto**   Abilitare questa opzione se si vuole che gli utenti dell'organizzazione che si trovano all'esterno del firewall, ad esempio i telecomunicazioni e gli utenti in viaggio, possano connettersi a Skype for Business Server. Per informazioni dettagliate, vedere [Abilitare o disabilitare l'accesso utente remoto](enable-or-disable-remote-user-access.md).

  - **Abilitare gli utenti anonimi per l'accesso alle conferenze**   Abilitare questa opzione se si vuole che gli utenti interni invitino utenti anonimi esterni a conferenze organizzate. L'abilitazione di questa impostazione consente solo agli utenti anonimi per le conferenze.

> [!NOTE]  
> Oltre ad abilitare il supporto per l'accesso utenti esterni, è necessario configurare anche criteri per controllare l'uso dell'accesso remoto utenti nell'organizzazione, prima che qualsiasi tipo di accesso utente esterno venga reso disponibile per gli utenti. Per informazioni dettagliate sulla creazione, la configurazione e l'applicazione di criteri per l'accesso utente esterno, vedere [Gestire i criteri di accesso esterno per l'organizzazione](../external-access-policies/manage-external-access-policy-for-your-organization.md).

**Visualizzazione delle informazioni di configurazione di Access Edge tramite i cmdlet di Windows PowerShell**

  - È possibile visualizzare le informazioni di configurazione di Access Edge usando Windows PowerShell e il cmdlet **Get-CsAccessEdgeConfiguration**. Questo cmdlet può essere eseguito da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. 
    
    Per visualizzare informazioni su tutte le impostazioni di configurazione di Access Edge, digitare il comando seguente in Skype for Business Server Management Shell e quindi premere INVIO:
    
     `Get-CsAccessEdgeConfiguration`
    
    Verranno restituite informazioni simili alle seguenti:
    
    Identità: globale<br/>
    AllowAnonymousUsers : False<br/>
    AllowFederatedUsers : False<br/>
    AllowOutsideUsers : True<br/>
    BeClearingHouse: False<br/>
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
    RoutingMethod: UseDnsSrvRouting<br/>

