---
title: Testare e segnalare la disponibilità funzionale per l'autenticazione Kerberos
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test and report functional readiness for Kerberos authentication
ms:assetid: d52c39e5-747d-4f29-88aa-30fd6f26b99c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398925(v=OCS.15)
ms:contentKeyID: 48185519
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 30dda07eb0152f43f60627fcee3a75b14745eea2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980015"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-and-report-functional-readiness-for-kerberos-authentication-in-lync-server-2013"></a><span data-ttu-id="8e97d-102">Testare e segnalare la disponibilità funzionale per l'autenticazione Kerberos in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8e97d-102">Test and report functional readiness for Kerberos authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8e97d-103">_**Argomento Ultima modifica:** 2012-01-16_</span><span class="sxs-lookup"><span data-stu-id="8e97d-103">_**Topic Last Modified:** 2012-01-16_</span></span>

<span data-ttu-id="8e97d-104">Per completare correttamente questa procedura, è necessario avere effettuato l'accesso come utente membro del gruppo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="8e97d-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="8e97d-105">Puoi usare il cmdlet **Test-CsKerberosAccountAssignment** di Windows PowerShell per testare e segnalare la disponibilità funzionale di un'assegnazione di sito per l'autenticazione Kerberos.</span><span class="sxs-lookup"><span data-stu-id="8e97d-105">You can use the **Test-CsKerberosAccountAssignment** Windows PowerShell cmdlet to test and report the functional readiness of a site assignment for Kerberos authentication.</span></span> <span data-ttu-id="8e97d-106">Questo comando esegue una query sul sito specificato nel parametro Identity obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="8e97d-106">This command queries the site specified in the required Identity parameter.</span></span> <span data-ttu-id="8e97d-107">Il parametro facoltativo report fa sì che il cmdlet scriva un report HTML in C\\: log nel computer in cui viene eseguito il comando.</span><span class="sxs-lookup"><span data-stu-id="8e97d-107">The optional Report parameter causes the cmdlet to write an HTML report to C:\\Logs on the computer on which the command is run.</span></span> <span data-ttu-id="8e97d-108">Il parametro Verbose facoltativo riporta le informazioni sull'attività sullo schermo.</span><span class="sxs-lookup"><span data-stu-id="8e97d-108">The optional Verbose parameter reports activity information to the screen.</span></span>

<div>

## <a name="to-test-and-report-functional-readiness-for-kerberos-authentication-for-a-site"></a><span data-ttu-id="8e97d-109">Per testare e segnalare la disponibilità funzionale per l'autenticazione Kerberos per un sito</span><span class="sxs-lookup"><span data-stu-id="8e97d-109">To test and report functional readiness for Kerberos authentication for a site</span></span>

1.  <span data-ttu-id="8e97d-110">Come membro del gruppo RTCUniversalServerAdmins, accedere a un computer nel dominio in cui è in uso Lync Server 2013 o nel computer in cui sono installati gli strumenti di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="8e97d-110">As a member of the RTCUniversalServerAdmins group, log on to a computer in the domain running Lync Server 2013 or on to the computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="8e97d-111">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="8e97d-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="8e97d-112">Nella riga di comando eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="8e97d-112">From the command line, run the following command:</span></span>
    
        Test-CsKerberosAccountAssignment -Identity "site:SiteName" -Report "c:\logs\FileName.htm" -Verbose
    
    <span data-ttu-id="8e97d-113">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="8e97d-113">For example:</span></span>
    
        Test-CsKerberosAccountAssignment -Identity "site:Redmond" -Report "c:\logs\KerberosReport.htm" -Verbose

</div>

</div>

<span> </span>

</div>

</div>

</div>

