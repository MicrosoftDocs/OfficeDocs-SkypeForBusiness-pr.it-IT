---
title: Gestire i domini federati SIP per l'organizzazione
ms.reviewer: ''
ms:assetid: abc48829-e5cf-4651-bc38-899192f5c3bc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552454(v=OCS.15)
ms:contentKeyID: 48679565
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Informazioni su come gestire e configurare i domini SIP con cui è possibile eseguire la Federazione,
ms.openlocfilehash: 1a2f76f7f465401bae04b4defa2e0a1f5300ab0f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195543"
---
# <a name="manage-sip-federated-domains-for-your-organization-in-skype-for-business-server"></a>Gestire i domini federati SIP per l'organizzazione in Skype for Business Server


Per gestire e configurare i domini SIP con cui è possibile eseguire la Federazione, è possibile procedere come segue:

  - Creare o modificare un elenco di domini consentiti di Domain partner federati SIP.

  - Creare o modificare un elenco di domini bloccati di Domain federati SIP.

## <a name="configure-support-for-allowed-external-domains-in-skype-for-business-server"></a>Configurare il supporto per i domini esterni consentiti in Skype for Business Server

Se è stato configurato il supporto per i partner federati, è possibile gestire i domini specifici che possono essere federati con l'organizzazione. Si configurano uno o più domini esterni specifici come consentiti domini federati. A questo scopo, Aggiungi ogni dominio all'elenco dei domini consentiti. Anche se l'individuazione dei partner è abilitata per l'organizzazione, eseguire questa operazione se il dominio è un partner federato che potrebbe essere necessario comunicare con più di 1.000 degli utenti o potrebbe essere necessario inviare più di 20 messaggi al secondo. Se l'individuazione dei partner non è abilitata per l'organizzazione, solo gli utenti di domini esterni aggiunti all'elenco dei domini consentiti possono partecipare alla messaggistica istantanea e alle conferenze con gli utenti dell'organizzazione. Se si vuole limitare l'accesso a un dominio federato a un server specifico che usa il servizio Access Edge del partner federato, è possibile specificare il nome di dominio del server che usa il servizio Access Edge per ogni dominio nell'elenco dei domini consentiti.

> [!NOTE]  
> Questa procedura descrive come configurare il supporto per specifici domini, ma l'implementazione del supporto per gli utenti federati richiede anche l'abilitazione del supporto per gli utenti federati per l'organizzazione e la configurazione e l'applicazione di criteri per il controllo degli utenti che possono collaborare con gli utenti federati. Per informazioni dettagliate sull'abilitazione del supporto per gli utenti federati, vedere [abilitare o disabilitare l'accesso da utenti remoti](../access-edge/enable-or-disable-remote-user-access.md). Per informazioni dettagliate sulla configurazione dei criteri per il controllo della Federazione, vedere [configurare i criteri per controllare l'accesso degli utenti federati](../external-access-policies/configure-policies-to-control-federated-user-access.md).

### <a name="to-add-an-external-domain-to-the-list-of-allowed-domains"></a>Per aggiungere un dominio esterno all'elenco dei domini consentiti

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.
2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server. 
3.  Sulla barra di spostamento sinistra fare clic su **accesso utente esterno**e quindi su **domini federati**.
4.  Nella pagina **domini federati** fare clic su **nuovo**e quindi su **dominio consentito**.
5.  In **nuovi domini federati**eseguire le operazioni seguenti:
    
      - In **Domain Name (o FQDN)** Digitare il nome del dominio del partner federato.       

        > [!NOTE]  
        > Questo nome deve essere univoco e non può essere già presente come dominio consentito per il server che ha eseguito il servizio Access Edge. Il nome non può superare i 256 caratteri di lunghezza.<BR><br>La ricerca nel nome di dominio del partner federativo esegue una corrispondenza con suffisso. Ad esempio, se si digita **contoso.com**, la ricerca restituirà anche il dominio **it.contoso.com**.<BR><br>Un dominio partner federato non può essere bloccato e consentito simultaneamente. Skype for Business Server impedisce che ciò avvenga in modo da non dover sincronizzare gli elenchi.
    
      - Se si vuole limitare l'accesso per il dominio federato agli utenti di un server specifico che ha eseguito il servizio Access Edge, in **Access Edge Services (FQDN)** Digitare il nome di dominio completo del server del dominio federato in cui è in uso il servizio Access Edge.    
      - Se si vogliono aggiungere altre informazioni, in **Commento**Digitare le informazioni che si desidera condividere con altri amministratori di sistema su questa configurazione.

6.  Fare clic su **Commit**.
7.  Ripetere i passaggi da 4 a 6 per ogni dominio di partner federato che si vuole consentire.

Per abilitare l'accesso degli utenti federati, devi anche abilitare il supporto per l'accesso degli utenti federati nell'organizzazione. Per informazioni dettagliate, vedere [abilitare o disabilitare l'accesso remoto agli utenti](../access-edge/enable-or-disable-remote-user-access.md).

Inoltre, è necessario configurare e applicare il criterio agli utenti che si vuole poter collaborare con gli utenti federati. Per informazioni dettagliate, vedere [configurare i criteri per controllare l'accesso degli utenti federati](../external-access-policies/configure-policies-to-control-federated-user-access.md).

## <a name="configure-support-for-blocked-external-domains-in-skype-for-business-server"></a>Configurare il supporto per i domini esterni bloccati in Skype for Business Server 

Se è stato configurato il supporto per i partner federati, è possibile gestire i domini che verranno bloccati dalla Federazione con l'organizzazione. L'elenco dei domini bloccati fungerà da elenco di blocchi (elenco delle voci esplicite che non devono essere consentite) e verrà applicato nell'individuazione di domini federati, se questa opzione è abilitata. Per informazioni dettagliate, vedere [abilitare o disabilitare l'individuazione dei partner federativi](../access-edge/enable-or-disable-discovery-of-federation-partners.md).

Bloccare uno o più domini esterni dalla connessione alla propria organizzazione. A questo scopo, Aggiungi il dominio all'elenco dei domini bloccati.


### <a name="to-add-an-external-domain-to-the-list-of-blocked-domains"></a>Per aggiungere un dominio esterno all'elenco dei domini bloccati

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.
2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server. 
3.  Sulla barra di spostamento sinistra fare clic su **accesso utente esterno**.
4.  Fare clic su **domini federati**, su **nuovo**e quindi su **dominio bloccato**.
5.  In **nuovi domini federati**eseguire le operazioni seguenti:
    
      - In **Domain Name (o FQDN)** Digitare il nome del dominio del partner federato che si vuole bloccare.

        > [!NOTE]  
        > Il nome non può superare i 256 caratteri di lunghezza.<BR><br>La ricerca nel nome di dominio del partner federativo esegue una corrispondenza con suffisso. Ad esempio, se si digita **contoso.com**, la ricerca restituirà anche il dominio **it.contoso.com**.<BR><br>Un dominio partner federato non può essere bloccato e consentito simultaneamente. Skype for Business Server impedisce che ciò avvenga in modo da non dover sincronizzare gli elenchi.
   
      - Opzionale In **Commento**Digitare le informazioni che si desidera condividere con altri amministratori di sistema su questa configurazione.

6.  Fare clic su **Commit**.
7.  Ripetere i passaggi da 4 a 6 per ogni partner federato che si vuole bloccare.

Per abilitare l'accesso degli utenti federati, devi anche abilitare il supporto per l'accesso degli utenti federati nell'organizzazione. Per informazioni dettagliate, vedere [abilitare o disabilitare l'accesso remoto agli utenti](../access-edge/enable-or-disable-remote-user-access.md).

Inoltre, è necessario configurare e applicare il criterio agli utenti che si vuole poter collaborare con gli utenti federati. Per informazioni dettagliate, vedere [configurare i criteri per controllare l'accesso degli utenti federati](../external-access-policies/configure-policies-to-control-federated-user-access.md).


## <a name="see-also"></a>Vedere anche

[Configurare i criteri per controllare l'accesso degli utenti federati](../external-access-policies/configure-policies-to-control-federated-user-access.md)  

[Abilitare o disabilitare la federazione e la connettività per la messaggistica istantanea pubblica](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)

[Abilitare o disabilitare l'individuazione dei partner federativi](../access-edge/enable-or-disable-discovery-of-federation-partners.md)
  

