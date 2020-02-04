---
title: 'Lync Server 2013: configurazione della messaggistica unificata di Microsoft Exchange Server 2013 per Lync Server 2013 segreteria telefonica'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Exchange Server 2013 Unified Messaging for Lync Server 2013 voice mail
ms:assetid: 1be9c4f4-fd8e-4d64-9798-f8737b12e2ab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687983(v=OCS.15)
ms:contentKeyID: 49733573
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 367f4cc517771f51d7a1452293ad9803075d285f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755930"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-exchange-server-2013-unified-messaging-for-microsoft-lync-server-2013-voice-mail"></a>Configurazione della messaggistica unificata di Microsoft Exchange Server 2013 per Microsoft Lync Server 2013 Voice mail

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-04_

Microsoft Lync Server 2013 consente di archiviare i messaggi della segreteria telefonica in Microsoft Exchange Server 2013; i messaggi della segreteria telefonica verranno quindi visualizzati come messaggi di posta elettronica nelle cassette postali degli utenti. Questa funzionalità è stata trovata anche nelle edizioni 2010 di Lync Server e Exchange. Tuttavia, il processo di configurazione di questa "messaggistica unificata" è stato semplificato nelle edizioni 2013 grazie all'introduzione del componente router di chiamata di messaggistica unificata. Questo componente è installato nel server di accesso client di Exchange 2013 e tutte le chiamate alla messaggistica unificata di Exchange (ad esempio un messaggio vocale) vengono prima instradate tramite il router di chiamata e quindi vengono reindirizzate al server di cassette postali appropriato.

Se è già stata configurata l'autenticazione da server a server tra Lync Server 2013 ed Exchange 2013, si è pronti per la configurazione della messaggistica unificata. A tale scopo, è necessario prima di tutto creare e assegnare un nuovo dial plan di messaggistica unificata nel server Exchange. Ad esempio, questi due comandi (eseguiti da Exchange Management Shell) configurano un nuovo dial plan a 3 cifre per Exchange:

    New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
    Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"

Nel primo comando dell'esempio, il parametro VoIPSecurity e il valore del parametro "Secured" indicano che il canale di segnalazione viene crittografato con Transport Layer Security (TLS). URIType "SipName" indica che i messaggi verranno inviati e ricevuti usando il protocollo SIP e il CountryOrRegionCode di 1 indica che il dial plan si applica agli Stati Uniti.

Nel secondo comando, il valore del parametro passato al parametro ConfiguredInCountryOrRegionGroups specifica i gruppi in-Country che possono essere usati con questo dial plan. Il valore del parametro "Anywhere\*,\*,\*," imposta le operazioni seguenti:

  - Nome gruppo ("ovunque")

  - AllowedNumberString (\*, un carattere jolly che indica che è consentita una stringa di numero qualsiasi)

  - DialNumberString (\*, un carattere jolly che indica che è consentito qualsiasi numero composto)

  - TextComment (\*, un carattere jolly che indica che è consentito qualsiasi comando di testo)

<div>


> [!NOTE]  
> La creazione di un nuovo dial plan creerà anche un criterio predefinito per le cassette postali.



</div>

Dopo aver creato e configurato il nuovo piano di chiamata, è necessario aggiungere il nuovo dial plan al server Messaggistica unificata e quindi modificare la modalità di avvio del server. in particolare, devi impostare la modalità di avvio su "Dual". È possibile eseguire entrambe le attività dall'interno di Exchange Management Shell:

    Set-UmService -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"

Dopo aver configurato il server Messaggistica unificata, è consigliabile eseguire il cmdlet Enable-ExchangeCertificate per verificare che il certificato di Exchange venga applicato al servizio di messaggistica unificata:

    Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "EA5A332496CC05DA69B75B66111C0F78A110D22d" -Services "SMTP","IIS","UM"

Dopo che il certificato è stato assegnato correttamente, è necessario arrestare e riavviare il servizio MsExchangeum nel server Messaggistica unificata. Questo servizio deve essere interrotto e riavviato ogni volta che si modifica la modalità di avvio.

Dopo aver terminato la configurazione del server Messaggistica unificata, è possibile configurare il router di chiamata di messaggistica unificata:

    Set-UMCallRouterSettings -Server "atl-exchange-001.litwareinc.com" -UMStartupMode "Dual" -DialPlans "RedmondDialPlan" 
    Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "45BAA32496CC891169B75B9811320F78A1075DDA" -Services "IIS","UMCallRouter"

Poiché la modalità di avvio è cambiata, è necessario interrompere e riavviare il servizio MsExchangeUMCR nel computer che ospita il router di chiamata di messaggistica unificata.

Per completare la configurazione della messaggistica unificata, è necessario creare un criterio cassetta postale di messaggistica unificata e quindi usare questo criterio per consentire agli utenti la messaggistica unificata. È possibile creare un criterio cassetta postale usando un comando simile al seguente:

    New-UMMailboxPolicy -Name "RedmondMailboxPolicy" -AllowedInCountryOrRegionGroups "Anywhere"

Puoi abilitare un utente per la messaggistica unificata usando un comando simile al seguente:

    Enable-UMMailbox -Extensions 100 -SIPResourceIdentifier "kenmyer@litwareinc.com" -Identity "litwareinc\kenmyer" -UMMailboxPolicy "RedmondMailboxPolicy"

Nel comando precedente il parametro Extensions rappresenta il numero di interno telefonico per l'utente. In questo esempio l'utente ha il numero di interno 100.

Dopo aver abilitato la cassetta postale, l'utente kenmyer@litwareinc.com dovrebbe essere in grado di usare la messaggistica unificata di Exchange. Puoi verificare che l'utente possa connettersi alla messaggistica unificata di Exchange eseguendo il cmdlet [test-CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMConnectivity) da Lync Server Management Shell:

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Se si ha un secondo utente abilitato per la messaggistica unificata, è possibile usare il cmdlet [test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMVoiceMail) per verificare che il secondo utente possa uscire da un messaggio della segreteria telefonica per il primo utente.

    $credential = Get-Credential "litwareinc\pilar"
    
    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential

</div>

<span> </span>

</div>

</div>

</div>

