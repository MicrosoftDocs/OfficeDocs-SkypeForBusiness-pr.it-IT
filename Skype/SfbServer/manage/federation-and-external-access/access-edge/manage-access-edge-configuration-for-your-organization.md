---
title: Gestire la configurazione Access Edge per l'organizzazione
ms.reviewer: ''
ms:assetid: 0145eb08-984f-4ecd-bf9c-364817619c2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552443(v=OCS.15)
ms:contentKeyID: 48679555
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Dopo la distribuzione di uno o più server perimetrali, è necessario abilitare i tipi di accesso esterno al dominio o al provider, l'accesso remoto agli utenti e l'accesso degli utenti anonimi alle conferenze tramite gli Edge Server che verranno supportati per l'organizzazione.
ms.openlocfilehash: 7308d6914f3f6d79cd217a31c0246c6f2d189516
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818347"
---
# <a name="manage-access-edge-configuration-for-your-organization"></a>Gestire la configurazione Access Edge per l'organizzazione

Dopo la distribuzione di uno o più server perimetrali, è necessario abilitare i tipi di accesso esterno al dominio o al provider, l'accesso remoto agli utenti e l'accesso degli utenti anonimi alle conferenze tramite gli Edge Server che verranno supportati per l'organizzazione.

Queste opzioni includono i seguenti tipi di Access che possono essere configurati tramite la pagina di **configurazione di Access Edge** :

  - **Abilitazione della Federazione e della connettività**   per messaggistica istantanea pubblica abilitare questa operazione se si vuole supportare l'accesso degli utenti ai domini partner federati. Questa impostazione si applica alla federazione SIP configurata per gli ambiti globali, del sito o degli utenti nella pagina dei **criteri di accesso esterno** . Per applicare le impostazioni federative, è necessario configurare il supporto federativo in entrambe le pagine.
    
    Esistono due opzioni che sono impostazioni facoltative per il modo in cui vengono individuati i partner federati e se l'archiviazione delle dichiarazioni di non conformità (notifica ai contatti federati con cui si comunica che la distribuzione ha l'archiviazione abilitata e che le comunicazioni i dettagli verranno archiviati) verranno inviati ai contatti:
    
      - **Abilitare l'individuazione**   di un dominio partner selezionando questa opzione è possibile individuare automaticamente i domini con cui si può usare la Federazione. Skype for Business Server usa i record DNS (Domain Name System) per cercare di individuare i domini non elencati nell'elenco dei domini consentiti, valutando automaticamente il traffico in entrata da partner federati individuati e limitando o bloccando il traffico basato sull'attendibilità livello, quantità di traffico e impostazioni di amministratore. Se non si seleziona questa opzione, l'accesso degli utenti federati è abilitato solo per gli utenti nei domini inclusi nell'elenco dei domini consentiti. Indipendentemente dal fatto che questa opzione sia selezionata, è possibile specificare che i singoli domini vengano bloccati o consentiti, incluso il limitare l'accesso a server specifici che gestiscono il servizio Access Edge nel dominio federato. Per informazioni dettagliate, vedere [configurare il supporto per i domini esterni consentiti](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).
    
      - **Inviare una dichiarazione di non responsabilità per i partner**   federati selezionare questa opzione consente l'invio di un messaggio di dichiarazione di non responsabilità per i partner federati che consigliano di registrare i dettagli delle comunicazioni. Se si archiviano comunicazioni esterne con domini partner federati, è necessario abilitare la notifica di dichiarazione di non responsabilità per l'archiviazione per avvisare i partner che i messaggi e i dettagli delle comunicazioni vengono archiviati dalla distribuzione. Per informazioni dettagliate sull'archiviazione, vedere [abilitare o disabilitare l'invio di una dichiarazione di non responsabilità per l'archiviazione a partner federati](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).

  - **Abilitare l'accesso**   degli utenti remoti per abilitare questa opzione se si vuole che gli utenti dell'organizzazione che si trovano all'esterno del firewall, ad esempio i telelavoratori e gli utenti che viaggiano, possano connettersi a Skype for Business Server. Per informazioni dettagliate, vedere [abilitare o disabilitare l'accesso remoto agli utenti](enable-or-disable-remote-user-access.md).

  - **Consentire agli utenti anonimi di accedere alle conferenze**   abilitare questa opzione se si vuole che gli utenti interni invitino utenti anonimi esterni alle conferenze organizzate. L'abilitazione di questa impostazione consente solo agli utenti anonimi di conferenze.

> [!NOTE]  
> Oltre a consentire il supporto degli accessi esterni agli utenti, è anche possibile configurare i criteri per controllare l'uso dell'accesso degli utenti remoti nell'organizzazione prima che l'utente sia disponibile per qualsiasi tipo di accesso da utenti esterni. Per informazioni dettagliate sulla creazione, la configurazione e l'applicazione di criteri per l'accesso degli utenti esterni, vedere [gestire i criteri di accesso esterno per l'organizzazione](../external-access-policies/manage-external-access-policy-for-your-organization.md).

**Visualizzazione delle informazioni di configurazione di Access Edge tramite i cmdlet di Windows PowerShell**

  - Le informazioni sulla configurazione di Access Edge possono essere visualizzate usando Windows PowerShell e il cmdlet **Get-CsAccessEdgeConfiguration** . Questo cmdlet può essere eseguito da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. 
    
    Per visualizzare informazioni su tutte le impostazioni di configurazione di Access Edge, digitare il comando seguente in Skype for Business Server Management Shell e quindi premere INVIO:
    
     `Get-CsAccessEdgeConfiguration`
    
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

