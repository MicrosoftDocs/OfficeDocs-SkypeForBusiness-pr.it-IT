---
title: 'Lync Server 2013: configurazione della messaggistica unificata di Microsoft Exchange Server 2013 per la segreteria telefonica di Lync Server 2013'
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
ms.openlocfilehash: 33c506e8b9f1201ad9382e361afc376590c6feca
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134772"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-exchange-server-2013-unified-messaging-for-microsoft-lync-server-2013-voice-mail"></a>Configurazione della messaggistica unificata di Microsoft Exchange Server 2013 per la segreteria telefonica di Microsoft Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-04_

Microsoft Lync Server 2013 consente di archiviare i messaggi in segreteria telefonica in Microsoft Exchange Server 2013; i messaggi vocali verranno quindi visualizzati come messaggi di posta elettronica nelle cassette postali degli utenti. Questa funzionalità è stata trovata anche nelle edizioni 2010 di Lync Server e Exchange; Tuttavia, il processo di configurazione di questa "messaggistica unificata" è stato semplificato nelle edizioni 2013 grazie all'introduzione del componente del router di chiamata di messaggistica unificata. Questo componente è installato sul server Accesso client di Exchange 2013 e tutte le chiamate alla messaggistica unificata di Exchange (ad esempio una segreteria telefonica) vengono prima instradate attraverso il router di chiamata e quindi vengono reindirizzate al server cassette postali appropriato.

Se è già stata configurata l'autenticazione da server a server tra Lync Server 2013 ed Exchange 2013, si è pronti per l'installazione della messaggistica unificata. A tale scopo, è necessario innanzitutto creare e assegnare un nuovo dial plan di messaggistica unificata nel server Exchange. Ad esempio, questi due comandi (eseguiti dall'interno di Exchange Management Shell) configurano un nuovo dial plan a tre cifre per Exchange:

    New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
    Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"

Nel primo comando dell'esempio, il parametro VoIPSecurity e il valore del parametro "Secured" indicano che il canale di segnale è crittografato tramite Transport Layer Security (TLS). Il parametro URIType "SipName" indica che i messaggi verranno inviati e ricevuti tramite il protocollo SIP e il valore 1 per CountryOrRegionCode indica che il dial plan si applica agli Stati Uniti.

Nel secondo comando il valore di parametro passato al parametro ConfiguredInCountryOrRegionGroups specifica quali gruppi nazionali è possibile utilizzare con questo dial plan. Il valore del parametro "Anywhere\*,\*,\*" consente di impostare gli elementi seguenti:

  - Nome gruppo

  - AllowedNumberString (\*un carattere jolly che indica che è consentita una stringa di numero qualsiasi)

  - DialNumberString (\*un carattere jolly che indica che è consentito qualsiasi numero composto)

  - TextComment (\*un carattere jolly che indica che è consentito qualsiasi comando di testo)

<div>


> [!NOTE]  
> Se si crea un nuovo dial plan, verrà creato anche un criterio cassetta postale predefinito.



</div>

Dopo aver creato e configurato il nuovo dial plan, è necessario aggiungerlo al server di messaggistica unificata, quindi impostare la modalità di avvio su "Doppio". È possibile eseguire entrambe queste attività dall'interno di Exchange Management Shell:

    Set-UmService -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"

Dopo aver configurato il server Messaggistica unificata, è necessario eseguire il cmdlet Enable-ExchangeCertificate per verificare che il certificato di Exchange venga applicato al servizio di messaggistica unificata:

    Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "EA5A332496CC05DA69B75B66111C0F78A110D22d" -Services "SMTP","IIS","UM"

Dopo avere assegnato correttamente il certificato, è quindi necessario arrestare e riavviare il servizio MsExchangeUM sul server di messaggistica unificata. È necessario arrestare e riavviare il servizio ogni volta che si modifica la modalità di avvio.

Al termine della configurazione del server di messaggistica unificata, è quindi possibile configurare il Router chiamate di messaggistica unificata:

    Set-UMCallRouterSettings -Server "atl-exchange-001.litwareinc.com" -UMStartupMode "Dual" -DialPlans "RedmondDialPlan" 
    Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "45BAA32496CC891169B75B9811320F78A1075DDA" -Services "IIS","UMCallRouter"

Dato che la modalità di avvio è stata modificata, è necessario arrestare e riavviare il servizio MsExchangeUMCR nel computer che ospita il router chiamate di messaggistica unificata.

Per completare l'impostazione della messaggistica unificata, è quindi necessario creare criteri di cassetta postale di messaggistica unificata e utilizzare tali criteri per abilitare la messaggistica unificata per gli utenti. È possibile creare criteri di cassetta postale tramite un comando simile al seguente:

    New-UMMailboxPolicy -Name "RedmondMailboxPolicy" -AllowedInCountryOrRegionGroups "Anywhere"

È possibile abilitare la messaggistica unificata per un utente tramite un comando simile al seguente:

    Enable-UMMailbox -Extensions 100 -SIPResourceIdentifier "kenmyer@litwareinc.com" -Identity "litwareinc\kenmyer" -UMMailboxPolicy "RedmondMailboxPolicy"

Nel comando precedente, il parametro Extensions rappresenta il numero di interno telefonico dell'utente. In questo esempio l'utente ha l'interno 100.

Dopo averne abilitato la cassetta postale, l'utente kenmyer@litwareinc.com dovrebbe essere in grado di utilizzare la messaggistica unificata di Exchange. È possibile verificare che l'utente possa connettersi alla messaggistica unificata di Exchange eseguendo il cmdlet [test-CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMConnectivity) dall'interno di Lync Server Management Shell:

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Se è presente un secondo utente per cui è stata abilitata la messaggistica unificata, è possibile utilizzare il cmdlet [Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMVoiceMail) per verificare che possa lasciare un messaggio della segreteria telefonica per il primo utente.

    $credential = Get-Credential "litwareinc\pilar"
    
    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential

</div>

<span> </span>

</div>

</div>

</div>

