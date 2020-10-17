---
title: 'Lync Server 2013: verifica della distribuzione dei dispositivi mobili'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verifying your mobility deployment
ms:assetid: 72f9b4d3-57b0-4705-9480-cfdca313a70c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690024(v=OCS.15)
ms:contentKeyID: 48184477
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8fefcdaf1fc84151fd37d7ff29acf66d742425d7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527609"
---
# <a name="verifying-your-mobility-deployment-in-lync-server-2013"></a>Verifica della distribuzione di dispositivi mobili in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-12_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Dopo aver distribuito il servizio per dispositivi mobili Lync Server e il servizio di individuazione automatica di Lync Server, eseguire una transazione di prova per verificare che la distribuzione funzioni correttamente. È possibile eseguire **test-CsUcwaConference** per verificare la capacità di due utenti che utilizzano client mobili Lync 2013 di creare, partecipare e comunicare in una conferenza. Per utilizzare questa transazione di test, sono necessari due utenti effettivi o gli utenti di test e le loro credenziali complete.

È possibile utilizzare **Test-CsMcxP2PIM** per testare l'invio di un messaggio istantaneo tra due utenti che utilizzano Lync 2010 mobile. Analogamente a **test-CsUcwaConference**, si utilizzano due utenti effettivi o due utenti di test predefiniti.

<div>

## <a name="to-test-conferencing-for-lync-2013-mobile-clients"></a>Per testare le conferenze per i client per dispositivi mobili Lync 2013

1.  Accedere come membro del ruolo CsAdministrator in un computer in cui sono installati Lync Server Management Shell e OCSCore.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

3.  Nella riga di comando digitare:
    
        Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
    
    È possibile impostare le credenziali in un script e passarle al cmdlet di test, ad esempio:
    
        $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
        $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
        $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
        $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
        Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v

</div>

<div>

## <a name="to-test-person-to-person-instant-messaging-im-for-lync-2010-mobile"></a>Per testare la messaggistica istantanea da persona a persona per Lync 2010 Mobile

1.  Accedere come membro del ruolo CsAdministrator in un computer in cui sono installati Lync Server Management Shell e OCSCore.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

3.  Nella riga di comando digitare:
    
        Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
    
    È possibile impostare le credenziali in un script e passarle al cmdlet di test, ad esempio:
    
        $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
        $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
        $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
        $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
        Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM)  
[Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

