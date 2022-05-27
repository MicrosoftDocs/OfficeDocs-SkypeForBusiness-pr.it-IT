---
title: Abilitare o disabilitare la federazione e la connettività per la messaggistica istantanea pubblica
ms.reviewer: ''
ms:assetid: 8ec58f4b-9f6d-47b4-a187-d18a83fe4577
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182549(v=OCS.15)
ms:contentKeyID: 48184813
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
description: Il supporto della federazione è necessario per consentire agli utenti che dispongono di un account con un'organizzazione cliente o partner attendibile, inclusi i domini partner e gli utenti di provider di messaggistica istantanea pubblica supportati, di collaborare con gli utenti all'interno dell'organizzazione.
ms.openlocfilehash: 0b78eacd473422c204f8614464b406657f3dc92b
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675748"
---
# <a name="enable-or-disable-federation-and-public-im-connectivity-in-skype-for-business-server"></a>Abilitare o disabilitare la federazione e la connettività di messaggistica istantanea pubblica in Skype for Business Server

Il supporto della federazione è necessario per consentire agli utenti che dispongono di un account con un'organizzazione cliente o partner attendibile, inclusi i domini partner e gli utenti di provider di messaggistica istantanea pubblica supportati, di collaborare con gli utenti all'interno dell'organizzazione. La federazione è anche necessaria per poter utilizzare un provider di servizi di Exchange ospitato in modo da offrire il servizio di segreteria telefonica agli utenti di VoIP aziendale le cui cassette postali si trovano su un servizio di Exchange ospitato quale Microsoft Exchange Online. Dopo aver stabilito una relazione di trust con questi domini esterni, è possibile autorizzare gli utenti di tali domini ad accedere alla distribuzione e a partecipare alle comunicazioni Skype for Business Server. La relazione di trust è denominata federazione e non è correlata a una relazione di trust di Active Directory né dipende da essa.

Per supportare l'accesso da parte degli utenti dei domini federati, è necessario abilitare la federazione. Se si abilita la federazione per la propria organizzazione, è anche necessario specificare se si desidera implementare le opzioni seguenti:

  - **Abilitare l'individuazione del dominio partner**   Se si abilita questa opzione, Skype for Business Server usa record DNS (Domain Name System) per tentare di individuare i domini non elencati nell'elenco dei domini consentiti, valutando automaticamente il traffico in ingresso dai partner federati individuati e limitando o bloccando il traffico in base al livello di attendibilità, alla quantità di traffico e alle impostazioni di amministratore. Se non si seleziona questa opzione, l'accesso degli utenti federati viene abilitato solo per gli utenti dei domini inclusi nell'elenco di domini consentiti. Indipendentemente dalla selezione di questa opzione, è possibile specificare se bloccare o consentire singoli domini, nonché limitare l'accesso a server specifici che eseguono il servizio Access Edge nel dominio federato. Per informazioni dettagliate sul controllo dell'accesso da parte di domini federati, vedere [Configurare il supporto per i domini esterni consentiti](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).

  - **Invia dichiarazione di non responsabilità relativa all'archiviazione ai partner federati**. Questa opzione consente di inviare una dichiarazione ai partner federati per informarli che nella distribuzione è usata l'archiviazione. Se si supporta l'archiviazione delle comunicazioni esterne con i domini partner federati, è necessario abilitare la notifica della dichiarazione di non responsabilità relativa all'archiviazione per avvisare i partner che i loro messaggi vengono archiviati.

Se successivamente si desidera impedire, in modo temporaneo o permanente, l'accesso degli utenti dei domini federati, è possibile disabilitare la federazione per l'organizzazione. Attenersi alla procedura descritta in questa sezione per abilitare o disabilitare l'accesso degli utenti federati per l'organizzazione, nonché per specificare le opzioni di federazione appropriate da supportare per l'organizzazione.

> [!NOTE]  
> L'abilitazione della federazione per l'organizzazione consente di specificare solo che i server che eseguono il servizio Access Edge supportano il routing ai domini federati. Gli utenti dei domini federati non possono partecipare alle conferenze o alla messaggistica istantanea all'interno dell'organizzazione finché non si procede anche alla configurazione di almeno un criterio per il supporto dell'accesso degli utenti federati. Gli utenti dei provider di servizi di messaggistica istantanea pubblica non possono partecipare alle conferenze o alla messaggistica istantanea nell'organizzazione finché non si procede anche alla configurazione di almeno un criterio per il supporto della connettività di messaggistica istantanea pubblica. Skype for Business Server non è possibile usare un servizio di Exchange ospitato per fornire servizi di risposta alle chiamate, Outlook Voice Access (inclusa la segreteria telefonica) o operatore automatico per gli utenti le cui cassette postali si trovano in un servizio di Exchange ospitato fino a quando non si configura un criterio di segreteria telefonica ospitata che fornisce il routing Informazioni. Per informazioni dettagliate sulla configurazione dei criteri per la comunicazione con gli utenti di domini federati in altre organizzazioni, vedere [Gestire i domini federati SIP per l'organizzazione](../sip-domains/manage-sip-federated-domains-for-your-organization.md). Se, inoltre, si desidera supportare le comunicazioni con gli utenti dei provider di servizi di messaggistica istantanea, è necessario configurare i criteri per il relativo supporto nonché configurare il supporto per i singoli provider di servizi desiderati. Per informazioni dettagliate, vedere   [Gestire i provider federati SIP per l'organizzazione](../sip-providers/manage-sip-federated-providers-for-your-organization.md).


## <a name="to-enable-or-disable-federated-user-access-for-your-organization"></a>Per abilitare o disabilitare l'accesso degli utenti federati per l'organizzazione

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL Amministrazione per aprire il Skype for Business Server Pannello di controllo. 

3.  Sulla barra di spostamento sinistra fare clic su **Accesso utente esterno** e quindi su **Configurazione Access Edge**.

4.  Nella pagina **Configurazione Access Edge** fare clic su **Globale**, **Modifica** e quindi su **Mostra dettagli**.

5.  In **Modifica configurazione Access Edge** eseguire una delle operazioni seguenti:
    
      - Per abilitare l'accesso degli utenti federati per l'organizzazione, selezionare la casella di controllo  **Abilita comunicazioni con utenti federati**.
    
      - Per disabilitare l'accesso degli utenti federati per l'organizzazione, deselezionare la casella di controllo  **Abilita comunicazioni con utenti federati**.

6.  Se è stata selezionata la casella di controllo  **Abilita comunicazioni con utenti federati**, eseguire le operazioni seguenti:
    
    1.  Se si desidera supportare l'individuazione automatica dei domini partner, selezionare la casella di controllo  **Abilita individuazione dominio partner**.
    
    2.  Se l'organizzazione supporta l'archiviazione delle comunicazioni esterne, selezionare la casella di controllo  **Invia dichiarazione di non responsabilità relativa all'archiviazione ai partner federati**.

7.  Fare clic su  **Commit**.

Per consentire agli utenti federati di collaborare con gli utenti nella distribuzione Skype for Business Server, è anche necessario configurare almeno un criterio di accesso esterno per supportare l'accesso utente federato. Per informazioni dettagliate, vedere [Configurare i criteri per controllare l'accesso utente federato](../external-access-policies/configure-policies-to-control-federated-user-access.md). Per controllare l'accesso per domini federati specifici, vedere [Configurare il supporto per i domini esterni consentiti](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).


## <a name="enabling-or-disabling-federation-and-public-im-connectivity-by-using-windows-powershell-cmdlets"></a>Abilitazione o disabilitazione della federazione e della connettività di messaggistica istantanea pubblica tramite cmdlet di Windows PowerShell

È anche possibile gestire la connettività di messaggistica istantanea pubblica e federazione usando Windows PowerShell e il cmdlet Set-CsAccessEdgeConfiguration. Questo cmdlet può essere eseguito da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. 

## <a name="to-enable-federation-and-public-im-connectivity"></a>Per abilitare la federazione e la connettività di messaggistica istantanea pubblica

  - Per abilitare la federazione e la connettività IM pubblica, impostare il valore della proprietà **AllowFederatedUsers** su True ($True):<br/><br/>Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True



## <a name="to-disable-federation-and-public-im-connectivity"></a>Per disabilitare la federazione e la connettività di messaggistica istantanea pubblica

  - Per disabilitare la federazione e la connettività IM pubblica, impostare il valore della proprietà **AllowFederatedUsers** su False ($False):<br/><br/>Set-CsAccessEdgeConfiguration -AllowFederatedUsers $False

