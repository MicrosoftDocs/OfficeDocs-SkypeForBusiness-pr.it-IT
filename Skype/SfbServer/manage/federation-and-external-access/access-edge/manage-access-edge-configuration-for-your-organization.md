---
title: Gestire la configurazione Access Edge per l'organizzazione
ms.reviewer: ''
ms:assetid: 0145eb08-984f-4ecd-bf9c-364817619c2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552443(v=OCS.15)
ms:contentKeyID: 48679555
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Dopo la distribuzione di uno o più server perimetrali, è necessario abilitare i tipi di accesso di dominio esterno o di provider, accesso utente remoto e accesso degli utenti anonimi alle conferenze tramite i server perimetrali che saranno supportati per l'organizzazione.
ms.openlocfilehash: 63d33a5dd3459aef5f657d8ab5772515a16e7915
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817336"
---
# <a name="manage-access-edge-configuration-for-your-organization"></a>Gestire la configurazione Access Edge per l'organizzazione

Dopo la distribuzione di uno o più server perimetrali, è necessario abilitare i tipi di accesso di dominio esterno o di provider, accesso utente remoto e accesso degli utenti anonimi alle conferenze tramite i server perimetrali che saranno supportati per l'organizzazione.

Queste opzioni includono i tipi seguenti di accesso, che possono essere configurati nella pagina **Configurazione Access Edge**:

  - **Abilitare la Federazione e la connettività per la messaggistica istantanea pubblica**   Abilitare questa operazione se si desidera supportare l'accesso degli utenti ai domini partner federati. Questa impostazione si applica alla federazione SIP configurata per gli ambiti globali, del sito o degli utenti nella pagina **criteri di accesso esterno** . Per applicare le impostazioni di federazione, è necessario configurare il supporto federativo in entrambe le pagine.
    
    Esistono due opzioni che sono impostazioni facoltative per la modalità di scoperta dei partner federati e se le dichiarazioni di non responsabilità per l'archiviazione (notifica ai contatti federati che comunicano con il fatto che la distribuzione ha l'archiviazione abilitata e che verranno archiviati i dettagli della comunicazione) verranno inviate ai contatti:
    
      - **Abilitare l'individuazione del dominio del partner**   Selezionando questa opzione, viene abilitata l'individuazione automatica dei domini che è possibile federare con. Skype for Business Server utilizza i record DNS (Domain Name System) per cercare di individuare i domini non elencati nell'elenco dei domini consentiti, valutando automaticamente il traffico in ingresso proveniente da partner federati individuati e limitando o bloccando il traffico in base al livello di attendibilità, alla quantità di traffico e alle impostazioni di amministratore. Se non si seleziona questa opzione, l'accesso degli utenti federati viene abilitato solo per gli utenti dei domini inclusi nell'elenco di domini consentiti. Indipendentemente dalla selezione di questa opzione, è possibile specificare se bloccare o consentire singoli domini, nonché limitare l'accesso a server specifici che eseguono il servizio Access Edge nel dominio federato. Per ulteriori informazioni, vedere [configurare il supporto per i domini esterni consentiti](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).
    
      - **Inviare la dichiarazione di non responsabilità per l'archiviazione ai partner federati**   Selezionando questa opzione, viene abilitato l'invio di un messaggio di dichiarazione di non responsabilità per l'archiviazione ai partner federati che consigliano che vengano registrati i dettagli della comunicazione. Se si archiviano comunicazioni esterne con domini partner federati, è consigliabile abilitare la dichiarazione di non responsabilità relativa all'archiviazione per avvisare i partner che i dettagli relativi a messaggi e comunicazioni vengono archiviati dalla distribuzione. Per informazioni dettagliate sull'archiviazione, vedere [Abilitazione o disabilitazione dell'invio di una dichiarazione di non responsabilità per l'archiviazione a un partner federato](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).

  - **Abilitare l'accesso degli utenti remoti**   Abilitare questa opzione se si desidera che gli utenti dell'organizzazione che si trovano all'esterno del firewall, ad esempio i telelavoratori e gli utenti che viaggiano, siano in grado di connettersi a Skype for Business Server. Per ulteriori informazioni, vedere [Abilitazione o disabilitazione dell'accesso degli utenti remoti](enable-or-disable-remote-user-access.md).

  - **Abilitazione degli utenti anonimi all'accesso alle conferenze**   Abilitare questa opzione se si desidera che gli utenti interni invitino gli utenti anonimi esterni alle conferenze organizzate. L'abilitazione di questa impostazione consente solo agli utenti anonimi per le conferenze.

> [!NOTE]  
> Oltre ad abilitare il supporto per l'accesso utenti esterni, è necessario configurare anche criteri per controllare l'uso dell'accesso remoto utenti nell'organizzazione, prima che qualsiasi tipo di accesso utente esterno venga reso disponibile per gli utenti. Per informazioni dettagliate sulla creazione, la configurazione e l'applicazione di criteri per l'accesso degli utenti esterni, vedere [gestire i criteri di accesso esterno per l'organizzazione](../external-access-policies/manage-external-access-policy-for-your-organization.md).

**Visualizzazione delle informazioni sulla configurazione di Access Edge tramite i cmdlet di Windows PowerShell**

  - È possibile visualizzare le informazioni di configurazione di Access Edge utilizzando Windows PowerShell e il cmdlet **Get-CsAccessEdgeConfiguration** . Questo cmdlet può essere eseguito da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. 
    
    Per visualizzare informazioni su tutte le impostazioni di configurazione di Access Edge, digitare il comando seguente in Skype for Business Server Management Shell e quindi premere INVIO:
    
     `Get-CsAccessEdgeConfiguration`
    
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

