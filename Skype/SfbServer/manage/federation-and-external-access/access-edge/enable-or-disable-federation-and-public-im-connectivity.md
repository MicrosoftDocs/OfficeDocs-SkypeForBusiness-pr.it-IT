---
title: Abilitare o disabilitare la federazione e la connettività per la messaggistica istantanea pubblica
ms.reviewer: ''
ms:assetid: 8ec58f4b-9f6d-47b4-a187-d18a83fe4577
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182549(v=OCS.15)
ms:contentKeyID: 48184813
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Il supporto per la Federazione è necessario per consentire agli utenti che hanno un account con un cliente o un'organizzazione partner attendibile, inclusi i domini partner e gli utenti di utenti del provider di messaggistica istantanea pubblici supportati, di collaborare con gli utenti del proprio organizzazione.
ms.openlocfilehash: 86cc3e66b2e3252b6b25ff4bef09d3abeb4badf0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188885"
---
# <a name="enable-or-disable-federation-and-public-im-connectivity-in-skype-for-business-server"></a>Abilitare o disabilitare la connettività per la messaggistica istantanea pubblica e la Federazione in Skype for Business Server

Il supporto per la Federazione è necessario per consentire agli utenti che hanno un account con un cliente o un'organizzazione partner attendibile, inclusi i domini partner e gli utenti di utenti del provider di messaggistica istantanea pubblici supportati, di collaborare con gli utenti del proprio organizzazione. Alla Federazione è anche richiesto di usare un provider di servizi di Exchange ospitati per consentire agli utenti di VoIP aziendale le cassette postali si trovano in un servizio di Exchange ospitato, ad esempio Microsoft Exchange Online. Dopo aver stabilito una relazione di trust con questi domini esterni, è possibile autorizzare gli utenti di tali domini ad accedere alla distribuzione e partecipare alle comunicazioni di Skype for Business Server. Questa relazione di trust viene chiamata Federazione e non è correlata o dipendente da una relazione di trust di Active Directory.

Per supportare l'accesso da parte di utenti di domini federati, è necessario abilitare la Federazione. Se si Abilita la Federazione per l'organizzazione, è necessario specificare anche se implementare le opzioni seguenti:

  - **Abilitare l'individuazione**   dei domini partner se si abilita questa opzione, Skype for Business Server usa i record DNS (Domain Name System) per cercare di individuare i domini non elencati nell'elenco dei domini consentiti, valutando automaticamente il traffico in entrata da scoperto partner federati che limitano o bloccano il traffico in base al livello di attendibilità, alla quantità di traffico e alle impostazioni di amministratore. Se non si seleziona questa opzione, l'accesso degli utenti federati è abilitato solo per gli utenti nei domini inclusi nell'elenco dei domini consentiti. Indipendentemente dal fatto che questa opzione sia selezionata, è possibile specificare che i singoli domini vengano bloccati o consentiti, incluso il limitare l'accesso a server specifici che gestiscono il servizio Access Edge nel dominio federato. Per informazioni dettagliate sul controllo dell'accesso da domini federati, vedere [configurare il supporto per i domini esterni](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)consentiti.

  - **Inviare una dichiarazione di non responsabilità per l'archiviazione per**     i partner federati l'avviso di non responsabilità viene inviato ai partner federati che l'archiviazione nella distribuzione è a posto. Se si supporta l'archiviazione di comunicazioni esterne con i domini partner federati, è necessario abilitare la notifica di dichiarazione di non responsabilità per l'archiviazione per avvisare i partner che i loro messaggi vengono archiviati.

Se in seguito si vuole impedire temporaneamente o definitivamente l'accesso da parte di utenti di domini federati, è possibile disabilitare la Federazione per l'organizzazione. Usare la procedura descritta in questa sezione per abilitare o disabilitare l'accesso degli utenti federati per l'organizzazione, ad esempio specificando le opzioni federative appropriate da supportare per l'organizzazione.

> [!NOTE]  
> L'abilitazione della Federazione per l'organizzazione specifica solo che i server che utilizzano il servizio Access Edge supportano il routing a domini federati. Gli utenti nei domini federati non possono partecipare alla messaggistica istantanea o alle conferenze dell'organizzazione fino a quando non vengono configurati almeno un criterio per supportare l'accesso degli utenti federati. Gli utenti dei provider di servizi di messaggistica istantanea pubblica non possono partecipare a messaggi istantanei o conferenze nell'organizzazione finché non si configura almeno un criterio per supportare la connettività di messaggistica istantanea pubblica. Skype for Business Server non può usare un servizio di Exchange ospitato per fornire risposte alle chiamate, Outlook Voice Access (inclusa la segreteria telefonica) o servizi di operatore automatico per gli utenti le cui cassette postali si trovano in un servizio di Exchange ospitata finché non si configura una voce ospitata criteri di posta elettronica che forniscono informazioni di routing. Per informazioni dettagliate sulla configurazione dei criteri per la comunicazione con gli utenti di domini federati in altre organizzazioni, vedere [gestire i domini federati SIP per l'organizzazione](../sip-domains/manage-sip-federated-domains-for-your-organization.md). Inoltre, se si vuole supportare la comunicazione con gli utenti dei provider di servizi di messaggistica istantanea, è necessario configurare i criteri per supportarlo e configurare il supporto per i singoli provider di servizi che si desidera supportare. Per informazioni dettagliate, vedere [gestire provider federati SIP per l'organizzazione](../sip-providers/manage-sip-federated-providers-for-your-organization.md).


## <a name="to-enable-or-disable-federated-user-access-for-your-organization"></a>Per abilitare o disabilitare l'accesso degli utenti federati per l'organizzazione

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server. 

3.  Sulla barra di spostamento sinistra fare clic su **accesso utente esterno**e quindi su **configurazione bordo di Access**.

4.  Nella pagina **configurazione di Access Edge** fare clic su **globale**, fare clic su **modifica**e quindi su **Mostra dettagli**.

5.  In **modifica configurazione di Access Edge**eseguire una delle operazioni seguenti:
    
      - Per abilitare l'accesso degli utenti federati per l'organizzazione, selezionare la casella di controllo **Abilita comunicazioni con gli utenti federati** .
    
      - Per disabilitare l'accesso degli utenti federati per l'organizzazione, deselezionare la casella di controllo **Abilita comunicazioni con gli utenti federati** .

6.  Se è stata selezionata la casella **di controllo Abilita comunicazioni con gli utenti federati** , eseguire le operazioni seguenti:
    
    1.  Se si vuole supportare l'individuazione automatica dei domini partner, selezionare la casella di controllo **Abilita individuazione dominio partner** .
    
    2.  Se l'organizzazione supporta l'archiviazione di comunicazioni esterne, selezionare la casella **di controllo Invia Disclaimer per l'archiviazione ai partner federati** .

7.  Fare clic su **Commit**.

Per consentire agli utenti federati di collaborare con gli utenti nella distribuzione di Skype for Business Server, devi anche configurare almeno un criterio di accesso esterno per supportare l'accesso degli utenti federati. Per informazioni dettagliate, vedere [configurare i criteri per controllare l'accesso degli utenti federati](../external-access-policies/configure-policies-to-control-federated-user-access.md). Per controllare l'accesso per specifici domini federati, vedere [configurare il supporto per i domini esterni](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)consentiti.


## <a name="enabling-or-disabling-federation-and-public-im-connectivity-by-using-windows-powershell-cmdlets"></a>Abilitare o disabilitare la connettività per la messaggistica istantanea e la Federazione usando i cmdlet di Windows PowerShell

La connettività di messaggistica istantanea pubblica e della Federazione può essere gestita anche tramite Windows PowerShell e il cmdlet Set-CsAccessEdgeConfiguration. Questo cmdlet può essere eseguito da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. 

## <a name="to-enable-federation-and-public-im-connectivity"></a>Per abilitare la connettività per la messaggistica istantanea pubblica e la Federazione

  - Per abilitare la connettività per la messaggistica istantanea pubblica e la Federazione, imposta il valore della proprietà **AllowFederatedUsers** su True ($true):
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True



## <a name="to-disable-federation-and-public-im-connectivity"></a>Per disabilitare la connettività per la messaggistica istantanea pubblica e la Federazione

  - Per disabilitare la connettività per la messaggistica istantanea pubblica e la Federazione, imposta il valore della proprietà **AllowFederatedUsers** su False ($false):
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $False

