---
title: "Lync Server 2013: rimuovere l'autenticazione Kerberos da un sito"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remove Kerberos authentication from a site
ms:assetid: 93171b02-bb36-42dc-943d-86d9dde45b59
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398749(v=OCS.15)
ms:contentKeyID: 48184806
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6546ac3e13795871461dcdd425e96e801ee19e9d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042908"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="in-lync-server-2013-remove-kerberos-authentication-from-a-site"></a><span data-ttu-id="2cfbb-102">In Lync Server 2013 rimuovere l'autenticazione Kerberos da un sito</span><span class="sxs-lookup"><span data-stu-id="2cfbb-102">In Lync Server 2013 remove Kerberos authentication from a site</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2cfbb-103">_**Ultimo argomento modificato:** 2012-01-16_</span><span class="sxs-lookup"><span data-stu-id="2cfbb-103">_**Topic Last Modified:** 2012-01-16_</span></span>

<span data-ttu-id="2cfbb-104">Per eseguire correttamente questa procedura, è necessario essere connessi come utenti membri del gruppo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="2cfbb-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="2cfbb-105">Per rimuovere l'autenticazione Kerberos da un sito o ritirare un sito, è necessario rimuovere l'assegnazione dell'account di autenticazione Kerberos dal sito utilizzando il cmdlet **Remove-CsKerberosAccountAssignment**.</span><span class="sxs-lookup"><span data-stu-id="2cfbb-105">If you need to remove Kerberos authentication from a site or retire a site, you must remove the Kerberos authentication account assignment from the site by using the **Remove-CsKerberosAccountAssignment** cmdlet.</span></span> <span data-ttu-id="2cfbb-106">Utilizzare la procedura seguente per rimuovere l'assegnazione dell'account di autenticazione Kerberos, rimuovendo così l'assegnazione da tutti i computer del sito.</span><span class="sxs-lookup"><span data-stu-id="2cfbb-106">Use the following procedure to remove the Kerberos authentication account assignment, which removes the assignment from all computers in the site.</span></span>

<div class=" ">


> [!WARNING]  
> <span data-ttu-id="2cfbb-107">Se si sta definitivamente ritirando l'account abilitato per Kerberos, è necessario utilizzare utenti e computer di Active Directory per eliminarlo da servizi di dominio Active Directory dopo che è stata rimossa l'assegnazione.</span><span class="sxs-lookup"><span data-stu-id="2cfbb-107">If you are permanently retiring the Kerberos-enabled account, you should use Active Directory Users and Computers to delete it from Active Directory Domain Services after you have removed the assignment.</span></span> <span data-ttu-id="2cfbb-108">Se al contrario si prevede di utilizzare l'oggetto in futuro, è possibile conservare l'oggetto Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2cfbb-108">If you plan to use the object in the future, you might want to keep the Active Directory object.</span></span>



</div>

<div>

## <a name="to-remove-kerberos-authentication-from-a-site"></a><span data-ttu-id="2cfbb-109">Rimuovere l'autenticazione Kerberos da un sito</span><span class="sxs-lookup"><span data-stu-id="2cfbb-109">To remove Kerberos authentication from a site</span></span>

1.  <span data-ttu-id="2cfbb-110">Come membri del gruppo RTCUniversalServerAdmins, accedere a un computer nel dominio in cui è in esecuzione Lync Server 2013 o a un computer in cui sono installati gli strumenti di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="2cfbb-110">As a member of the RTCUniversalServerAdmins group, log on to a computer in the domain running Lync Server 2013 or on to a computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="2cfbb-111">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="2cfbb-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="2cfbb-112">Nella riga di comando eseguire i due comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="2cfbb-112">From the command line, run the following two commands:</span></span>
    
       ```PowerShell
        Remove-CsKerberosAccountAssignment -Identity "site:SiteName"
       ```
    
       ```PowerShell
        Enable-CsTopology
       ```
    
    <span data-ttu-id="2cfbb-113">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="2cfbb-113">For example:</span></span>
    
       ```PowerShell
        Remove-CsKerberosAccountAssignment -Identity "site:Redmond"
       ```
    
       ```PowerShell
        Enable-CsTopology
       ```
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="2cfbb-114">Dopo aver apportato le modifiche all'autenticazione Kerberos, ad esempio l'aggiunta di un account o la rimozione di un account, è necessario eseguire <STRONG>Enable-CsTopology</STRONG> dal prompt dei comandi di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="2cfbb-114">After making any changes to Kerberos authentication, such as adding an account or removing an account, you must run <STRONG>Enable-CsTopology</STRONG> from the Lync Server Management Shell command prompt.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

