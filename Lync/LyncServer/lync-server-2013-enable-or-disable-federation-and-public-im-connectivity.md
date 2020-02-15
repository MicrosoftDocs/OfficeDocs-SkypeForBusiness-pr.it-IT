---
title: 'Lync Server 2013: abilitare o disabilitare la Federazione e la connettività per la messaggistica istantanea pubblica'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable federation and public IM connectivity
ms:assetid: 8ec58f4b-9f6d-47b4-a187-d18a83fe4577
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182549(v=OCS.15)
ms:contentKeyID: 48184813
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9281b4dab225ddb336dbc74a5d2892f0f4a015d5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42040204"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-federation-and-public-im-connectivity-in-lync-server-2013"></a>Abilitare o disabilitare la Federazione e la connettività per la messaggistica istantanea pubblica in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-06-24_

Il supporto della federazione è necessario per consentire agli utenti che dispongono di un account con un'organizzazione cliente o partner attendibile, inclusi i domini partner e gli utenti di provider di messaggistica istantanea pubblica supportati, di collaborare con gli utenti all'interno dell'organizzazione. La federazione è anche necessaria per poter utilizzare un provider di servizi di Exchange ospitato in modo da offrire il servizio di segreteria telefonica agli utenti di VoIP aziendale le cui cassette postali si trovano su un servizio di Exchange ospitato quale Microsoft Exchange Online. Dopo aver stabilito una relazione di trust con questi domini esterni, è possibile autorizzare gli utenti di tali domini ad accedere alla distribuzione e a partecipare alle comunicazioni di Lync Server. La relazione di trust è denominata federazione e non è correlata a una relazione di trust di Active Directory né dipende da essa.

Per supportare l'accesso da parte degli utenti dei domini federati, è necessario abilitare la federazione. Se si abilita la federazione per la propria organizzazione, è anche necessario specificare se si desidera implementare le opzioni seguenti:

  - **Abilita individuazione**   dominio partner se si abilita questa opzione, Lync Server utilizza i record DNS (Domain Name System) per cercare di individuare i domini non elencati nell'elenco dei domini consentiti, valutando automaticamente il traffico in ingresso proveniente da partner federati individuati e limitando o bloccando il traffico in base al livello di attendibilità, alla quantità di traffico e alle impostazioni di amministratore. Se non si seleziona questa opzione, l'accesso degli utenti federati viene abilitato solo per gli utenti dei domini inclusi nell'elenco di domini consentiti. Indipendentemente dalla selezione di questa opzione, è possibile specificare se bloccare o consentire singoli domini, nonché limitare l'accesso a server specifici che eseguono il servizio Access Edge nel dominio federato. Per informazioni dettagliate sul controllo dell'accesso da parte di domini federati, vedere [configurare il supporto per i domini esterni consentiti in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).

  - **Invio di una dichiarazione di non responsabilità di archiviazione per**     i partner federati l'avviso di dichiarazione di non responsabilità viene inviato ai partner federati che l'archiviazione nella distribuzione è sul posto. Se si supporta l'archiviazione delle comunicazioni esterne con i domini partner federati, è necessario abilitare la notifica della dichiarazione di non responsabilità relativa all'archiviazione per avvisare i partner che i loro messaggi vengono archiviati.

Se successivamente si desidera impedire, in modo temporaneo o permanente, l'accesso degli utenti dei domini federati, è possibile disabilitare la federazione per l'organizzazione. Attenersi alla procedura descritta in questa sezione per abilitare o disabilitare l'accesso degli utenti federati per l'organizzazione, nonché per specificare le opzioni di federazione appropriate da supportare per l'organizzazione.

<div>


> [!NOTE]  
> L'abilitazione della federazione per l'organizzazione consente di specificare solo che i server che eseguono il servizio Access Edge supportano il routing ai domini federati. Gli utenti dei domini federati non possono partecipare alle conferenze o alla messaggistica istantanea all'interno dell'organizzazione finché non si procede anche alla configurazione di almeno un criterio per il supporto dell'accesso degli utenti federati. Gli utenti dei provider di servizi di messaggistica istantanea pubblica non possono partecipare alle conferenze o alla messaggistica istantanea nell'organizzazione finché non si procede anche alla configurazione di almeno un criterio per il supporto della connettività di messaggistica istantanea pubblica. Lync Server non può utilizzare un servizio di Exchange ospitato per fornire servizi di risposta alle chiamate, Outlook Voice Access (inclusa la segreteria telefonica) o servizi con operatori automatici agli utenti le cui cassette postali si trovano su un servizio di Exchange ospitato finché non si procede anche alla configurazione di un criterio per la segreteria telefonica ospitata che fornisca informazioni sul routing. Per informazioni dettagliate sulla configurazione dei criteri per la comunicazione con gli utenti di domini federati in altre organizzazioni, vedere <A href="lync-server-2013-manage-sip-federated-domains-for-your-organization.md">gestire i domini federati SIP per l'organizzazione in Lync Server 2013</A> nella documentazione relativa alle operazioni. Se, inoltre, si desidera supportare le comunicazioni con gli utenti dei provider di servizi di messaggistica istantanea, è necessario configurare i criteri per il relativo supporto nonché configurare il supporto per i singoli provider di servizi desiderati. Per informazioni dettagliate, vedere <A href="lync-server-2013-manage-sip-federated-providers-for-your-organization.md">gestire i provider federati SIP per l'organizzazione in Lync Server 2013</A> nella documentazione relativa alle operazioni. Per informazioni dettagliate sulla creazione di un criterio di segreteria telefonica ospitata, vedere gestire i criteri di segreteria <A href="lync-server-2013-manage-hosted-voice-mail-policies.md">telefonica ospitata in Lync Server 2013</A> nella documentazione relativa alla distribuzione.



</div>

<div>

## <a name="to-enable-or-disable-federated-user-access-for-your-organization"></a>Per abilitare o disabilitare l'accesso degli utenti federati per l'organizzazione

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **Accesso utente esterno** e quindi su **Configurazione Access Edge**.

4.  Nella pagina **Configurazione Access Edge** fare clic su **Globale**, **Modifica** e quindi su **Mostra dettagli**.

5.  In **Modifica configurazione Access Edge** eseguire una delle operazioni seguenti:
    
      - Per abilitare l'accesso degli utenti federati per l'organizzazione, selezionare la casella di controllo  **Abilita comunicazioni con utenti federati **.
    
      - Per disabilitare l'accesso degli utenti federati per l'organizzazione, deselezionare la casella di controllo  **Abilita comunicazioni con utenti federati **.

6.  Se è stata selezionata la casella di controllo  **Abilita comunicazioni con utenti federati **, eseguire le operazioni seguenti:
    
    1.  Se si desidera supportare l'individuazione automatica dei domini partner, selezionare la casella di controllo  **Abilita individuazione dominio partner **.
    
    2.  Se l'organizzazione supporta l'archiviazione delle comunicazioni esterne, selezionare la casella di controllo  **Invia dichiarazione di non responsabilità relativa all'archiviazione ai partner federati **.

7.  Fare clic su  **Commit **.

Per consentire agli utenti federati di collaborare con gli utenti nella distribuzione di Lync Server 2013, è inoltre necessario configurare almeno un criterio di accesso esterno per supportare l'accesso degli utenti federati. Per informazioni dettagliate, vedere [Configure policies to Control Federated User Access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md) nella documentazione relativa alla distribuzione o nella documentazione relativa alle operazioni. Per controllare l'accesso per specifici domini federati, vedere [Configure support for allowed External Domains in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md) nella documentazione relativa alla distribuzione o alla documentazione relativa alle operazioni.

</div>

<div>

## <a name="enabling-or-disabling-federation-and-public-im-connectivity-by-using-windows-powershell-cmdlets"></a>Abilitazione o disabilitazione della Federazione e della connettività per la messaggistica istantanea pubblica tramite i cmdlet di Windows PowerShell

La Federazione e la connettività per la messaggistica istantanea pubblica possono essere gestite anche utilizzando Windows PowerShell e il cmdlet Set-CsAccessEdgeConfiguration. Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 using Remote PowerShell" at.

<div>

## <a name="to-enable-federation-and-public-im-connectivity"></a>Per abilitare la Federazione e la connettività per la messaggistica istantanea pubblica

  - Per abilitare la federazione e la connettività IM pubblica, impostare il valore della proprietà **AllowFederatedUsers** su True ($True):
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

</div>

<div>

## <a name="to-disable-federation-and-public-im-connectivity"></a>Per disabilitare la Federazione e la connettività per la messaggistica istantanea pubblica

  - Per disabilitare la federazione e la connettività IM pubblica, impostare il valore della proprietà **AllowFederatedUsers** su False ($False):
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

