---
title: 'Lync Server 2013: verifica della distribuzione dei dispositivi mobili'
description: 'Lync Server 2013: verifica della distribuzione di dispositivi mobili.'
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
ms.openlocfilehash: eadda35438961e469fdd5fa7976762141b26a385
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564442"
---
# <a name="verifying-your-mobility-deployment-in-lync-server-2013"></a><span data-ttu-id="e785b-103">Verifica della distribuzione di dispositivi mobili in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e785b-103">Verifying your mobility deployment in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e785b-104">_**Ultimo argomento modificato:** 2013-02-12_</span><span class="sxs-lookup"><span data-stu-id="e785b-104">_**Topic Last Modified:** 2013-02-12_</span></span>

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="e785b-105">Dopo aver distribuito il servizio per dispositivi mobili Lync Server e il servizio di individuazione automatica di Lync Server, eseguire una transazione di prova per verificare che la distribuzione funzioni correttamente.</span><span class="sxs-lookup"><span data-stu-id="e785b-105">After you deploy the Lync Server Mobility Service and Lync Server Autodiscover Service, run a test transaction to verify that your deployment works correctly.</span></span> <span data-ttu-id="e785b-106">È possibile eseguire **test-CsUcwaConference** per verificare la capacità di due utenti che utilizzano client mobili Lync 2013 di creare, partecipare e comunicare in una conferenza.</span><span class="sxs-lookup"><span data-stu-id="e785b-106">You can run **Test-CsUcwaConference** to test the ability of two users who are using Lync 2013 Mobile clients to create, join and communicate in a conference.</span></span> <span data-ttu-id="e785b-107">Per utilizzare questa transazione di test, sono necessari due utenti effettivi o gli utenti di test e le loro credenziali complete.</span><span class="sxs-lookup"><span data-stu-id="e785b-107">To use this test transaction, you need two actual users or test users, and their full credentials.</span></span>

<span data-ttu-id="e785b-108">È possibile utilizzare **Test-CsMcxP2PIM** per testare l'invio di un messaggio istantaneo tra due utenti che utilizzano Lync 2010 mobile.</span><span class="sxs-lookup"><span data-stu-id="e785b-108">You use **Test-CsMcxP2PIM** to test sending an instant message between two users who are using Lync 2010 Mobile.</span></span> <span data-ttu-id="e785b-109">Analogamente a **test-CsUcwaConference**, si utilizzano due utenti effettivi o due utenti di test predefiniti.</span><span class="sxs-lookup"><span data-stu-id="e785b-109">Similar to **Test-CsUcwaConference**, you use two actual users or two predefined test users.</span></span>

<div>

## <a name="to-test-conferencing-for-lync-2013-mobile-clients"></a><span data-ttu-id="e785b-110">Per testare le conferenze per i client per dispositivi mobili Lync 2013</span><span class="sxs-lookup"><span data-stu-id="e785b-110">To test conferencing for Lync 2013 Mobile clients</span></span>

1.  <span data-ttu-id="e785b-111">Accedere come membro del ruolo CsAdministrator in un computer in cui sono installati Lync Server Management Shell e OCSCore.</span><span class="sxs-lookup"><span data-stu-id="e785b-111">Log on as a member of the CsAdministrator role on any computer where Lync Server Management Shell and Ocscore are installed.</span></span>

2.  <span data-ttu-id="e785b-112">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="e785b-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="e785b-113">Nella riga di comando digitare:</span><span class="sxs-lookup"><span data-stu-id="e785b-113">At the command line, type:</span></span>
    
        Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
    
    <span data-ttu-id="e785b-p103">È possibile impostare le credenziali in un script e passarle al cmdlet di test, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="e785b-p103">You can set credentials in a script and pass them to the test cmdlet. For example:</span></span>
    
        $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
        $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
        $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
        $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
        Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v

</div>

<div>

## <a name="to-test-person-to-person-instant-messaging-im-for-lync-2010-mobile"></a><span data-ttu-id="e785b-116">Per testare la messaggistica istantanea da persona a persona per Lync 2010 Mobile</span><span class="sxs-lookup"><span data-stu-id="e785b-116">To test person-to-person instant messaging (IM) for Lync 2010 Mobile</span></span>

1.  <span data-ttu-id="e785b-117">Accedere come membro del ruolo CsAdministrator in un computer in cui sono installati Lync Server Management Shell e OCSCore.</span><span class="sxs-lookup"><span data-stu-id="e785b-117">Log on as a member of the CsAdministrator role on any computer where Lync Server Management Shell and Ocscore are installed.</span></span>

2.  <span data-ttu-id="e785b-118">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="e785b-118">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="e785b-119">Nella riga di comando digitare:</span><span class="sxs-lookup"><span data-stu-id="e785b-119">At the command line, type:</span></span>
    
        Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
    
    <span data-ttu-id="e785b-p104">È possibile impostare le credenziali in un script e passarle al cmdlet di test, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="e785b-p104">You can set credentials in a script and pass them to the test cmdlet. For example:</span></span>
    
        $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
        $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
        $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
        $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
        Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e785b-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e785b-122">See Also</span></span>


[<span data-ttu-id="e785b-123">Test-CsMcxP2PIM</span><span class="sxs-lookup"><span data-stu-id="e785b-123">Test-CsMcxP2PIM</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM)  
[<span data-ttu-id="e785b-124">Test-CsUcwaConference</span><span class="sxs-lookup"><span data-stu-id="e785b-124">Test-CsUcwaConference</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

