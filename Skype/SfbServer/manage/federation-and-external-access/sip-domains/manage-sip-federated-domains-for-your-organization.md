---
title: Gestire i domini federati SIP per l'organizzazione
ms.reviewer: ''
ms:assetid: abc48829-e5cf-4651-bc38-899192f5c3bc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552454(v=OCS.15)
ms:contentKeyID: 48679565
mtps_version: v=OCS.15
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Informazioni su come gestire e configurare i domini SIP con cui è possibile eseguire la federazione,
ms.openlocfilehash: 455cac695ead7f073269fe3df0e70ea5b26ccb0e
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60743542"
---
# <a name="manage-sip-federated-domains-for-your-organization-in-skype-for-business-server"></a>Gestire i domini federati SIP per l'organizzazione in Skype for Business Server


Per gestire e configurare i domini SIP con cui è possibile stabilire la federazione, è possibile eseguire le operazioni seguenti:

  - Creare o modificare un elenco dei domini consentiti per i domini partner federati SIP.

  - Creare o modificare un elenco dei domini bloccati per i domini federati SIP.

## <a name="configure-support-for-allowed-external-domains-in-skype-for-business-server"></a>Configurare il supporto per i domini esterni consentiti in Skype for Business Server

Se è stato configurato il supporto per i partner federati, è possibile specificare i domini che possono eseguire la federazione con l'organizzazione. Configurare uno o più domini esterni specifici come domini federati consentiti. A tale scopo, aggiungere ogni dominio all'elenco dei domini consentiti. Anche se per l'organizzazione è abilitata l'individuazione del partner, eseguire questa operazione se il dominio è un partner federato che potrebbe dover comunicare con oltre 1.000 utenti dell'organizzazione o inviare più di 20 messaggi al secondo. Se per l'organizzazione non è abilitata l'individuazione del partner, solo gli utenti dei domini esterni aggiunti all'elenco dei domini consentiti potranno partecipare alla messaggistica istantanea e alle conferenze con gli utenti dell'organizzazione. Se si desidera limitare l'accesso di un dominio federato a un server specifico che esegue il servizio Access Edge del partner federato, è possibile specificare il nome di dominio del server che esegue il servizio Access Edge per ogni dominio incluso nell'elenco dei domini consentiti.

> [!NOTE]  
> Questa procedura descrive come configurare il supporto per domini specifici, ma l'implementazione del supporto per gli utenti federati richiede inoltre di abilitare il supporto per gli utenti federati dell'organizzazione, nonché di configurare e applicare criteri per specificare quali utenti possono collaborare con gli utenti federati. Per informazioni dettagliate sull'abilitazione del supporto per gli utenti federati, vedere [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md). Per informazioni dettagliate sulla configurazione dei criteri per controllare la federazione, vedere [Configure policies to control federated user access](../external-access-policies/configure-policies-to-control-federated-user-access.md).

### <a name="to-add-an-external-domain-to-the-list-of-allowed-domains"></a>Per aggiungere un dominio esterno all'elenco dei domini consentiti

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.
2.  Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello Skype for Business Server controllo. 
3.  Nella barra di spostamento sinistra fare clic su **Accesso utente esterno** e quindi su **Domini federati**.
4.  Nella pagina **Domini federati** fare clic su **Nuovo** e quindi su **Dominio consentito**.
5.  In **Nuovi domini federati** eseguire le operazioni seguenti:
    
      - In **Nome di dominio (o FQDN)** digitare il nome del dominio del partner federato.       

        > [!NOTE]  
        > Il nome deve essere univoco e non deve esistere già come dominio consentito per il server che esegue il servizio Access Edge. Il nome può essere costituito da un massimo di 256 caratteri.<BR><br>La ricerca in base al nome di dominio del partner federato si basa sulla corrispondenza del suffisso. Se ad esempio si digita **contoso.com**, la ricerca restituirà anche il dominio **it.contoso.com**.<BR><br>Un dominio di partner federato non può essere contemporaneamente bloccato e consentito. Skype for Business Server impedisce che ciò accada in modo che non sia necessario sincronizzare gli elenchi.
    
      - Se si desidera limitare l'accesso per questo dominio federato agli utenti di un server specifico che esegue il servizio Access Edge, in **Servizio Access Edge (FQDN)** digitare l'FQDN del server del dominio federato che esegue il servizio Access Edge.    
      - Se si desidera fornire ulteriori informazioni, in **Commento** digitare le informazioni che si desidera condividere con altri amministratori di sistema sulla configurazione.

6.  Fare clic su **Commit**.
7.  Ripetere i passaggi da 4 a 6 per ogni dominio di partner federato che si desidera consentire.

Per consentire l'accesso degli utenti federati, è inoltre necessario abilitare il supporto per l'accesso degli utenti federati nell'organizzazione. Per informazioni dettagliate, vedere [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md).

È inoltre necessario configurare e applicare il criterio agli utenti per i quali si desidera consentire la collaborazione con gli utenti federati. Per informazioni dettagliate, vedere [Configure policies to control federated user access](../external-access-policies/configure-policies-to-control-federated-user-access.md).

## <a name="configure-support-for-blocked-external-domains-in-skype-for-business-server"></a>Configurare il supporto per i domini esterni bloccati in Skype for Business Server 

Se il supporto per i partner federati è configurato, è possibile gestire i domini ai quali impedire di federarsi con l'organizzazione. L'elenco dei domini bloccati svolgerà la funzione di elenco blocchi (elenco di una serie di voci esplicite da non consentire) e verrà applicato nell'individuazione di domini federati, se questa opzione è abilitata. Per informazioni dettagliate, vedere [Enable or disable discovery of federation partners](../access-edge/enable-or-disable-discovery-of-federation-partners.md).

Impedire a uno o più domini esterni di connettersi all'organizzazione. A tale scopo, aggiungere il dominio all'elenco dei domini bloccati.


### <a name="to-add-an-external-domain-to-the-list-of-blocked-domains"></a>Per aggiungere un dominio esterno all'elenco dei domini bloccati

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.
2.  Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello Skype for Business Server controllo. 
3.  Nella barra di spostamento sinistra fare clic su **Accesso utente esterno**.
4.  Fare clic su **Domini federati**, su **Nuovo** e quindi su **Dominio bloccato**.
5.  In **Nuovi domini federati** eseguire le operazioni seguenti:
    
      - In **Nome di dominio (o FQDN)** digitare il nome del dominio del partner federato che si desidera bloccare.

        > [!NOTE]  
        > Il nome può essere costituito da un massimo di 256 caratteri.<BR><br>La ricerca in base al nome di dominio del partner federato si basa sulla corrispondenza del suffisso. Se ad esempio si digita **contoso.com**, la ricerca restituirà anche il dominio **it.contoso.com**.<BR><br>Un dominio di partner federato non può essere contemporaneamente bloccato e consentito. Skype for Business Server impedisce che ciò accada in modo che non sia necessario sincronizzare gli elenchi.
   
      - (Facoltativo) In **Commento** digitare le informazioni che si desidera condividere con gli altri amministratori di sistema su questa configurazione.

6.  Fare clic su **Commit**.
7.  Ripetere i passaggi da 4 a 6 per ogni partner federato che si desidera bloccare.

Per consentire l'accesso degli utenti federati, è inoltre necessario abilitare il supporto per l'accesso degli utenti federati nell'organizzazione. Per informazioni dettagliate, vedere [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md).

È inoltre necessario configurare e applicare il criterio agli utenti per i quali si desidera consentire la collaborazione con gli utenti federati. Per informazioni dettagliate, vedere [Configure policies to control federated user access](../external-access-policies/configure-policies-to-control-federated-user-access.md).


## <a name="see-also"></a>Vedere anche

[Configurare i criteri per controllare l'accesso degli utenti federati](../external-access-policies/configure-policies-to-control-federated-user-access.md)  

[Abilitare o disabilitare la federazione e la connettività per la messaggistica istantanea pubblica](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)

[Abilitare o disabilitare l'individuazione di partner federativi](../access-edge/enable-or-disable-discovery-of-federation-partners.md)
  

