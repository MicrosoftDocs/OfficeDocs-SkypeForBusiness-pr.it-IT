---
title: 'Lync Server 2013: segnalare le assegnazioni degli account Kerberos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Report Kerberos account assignments
ms:assetid: 523231f6-81b3-454b-996d-663d9bd5cf83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398343(v=OCS.15)
ms:contentKeyID: 48184151
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9576d772aa340e7d578186974fb00418479ea691
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138757"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="report-kerberos-account-assignments-in-lync-server-2013"></a><span data-ttu-id="9deb5-102">Segnalare le assegnazioni degli account Kerberos in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9deb5-102">Report Kerberos account assignments in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9deb5-103">_**Ultimo argomento modificato:** 2012-01-16_</span><span class="sxs-lookup"><span data-stu-id="9deb5-103">_**Topic Last Modified:** 2012-01-16_</span></span>

<span data-ttu-id="9deb5-104">Per eseguire correttamente questa procedura, è necessario essere connessi come utenti membri del gruppo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="9deb5-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="9deb5-105">È possibile utilizzare il cmdlet **Get-CsKerberosAccountAssignment** per richiedere informazioni sulle assegnazioni di account di autenticazione Kerberos e restituire informazioni sulle assegnazioni correnti nella distribuzione.</span><span class="sxs-lookup"><span data-stu-id="9deb5-105">You can use the **Get-CsKerberosAccountAssignment** cmdlet to query information about the Kerberos authentication account assignments and report information about the current assignments in your deployment.</span></span>

<div>

## <a name="to-query-kerberos-authentication-account-assignments-for-a-site"></a><span data-ttu-id="9deb5-106">Per recuperare le assegnazioni di account di autenticazione Kerberos per un sito</span><span class="sxs-lookup"><span data-stu-id="9deb5-106">To query Kerberos authentication account assignments for a site</span></span>

1.  <span data-ttu-id="9deb5-107">Come membri del gruppo RTCUniversalServerAdmins, accedere a un computer nel dominio in cui è in esecuzione Lync Server 2013 o a un computer in cui sono installati gli strumenti di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="9deb5-107">As a member of the RTCUniversalServerAdmins group, log on to a computer in the domain running Lync Server 2013 or on to a computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="9deb5-108">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="9deb5-108">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="9deb5-109">Eseguire uno dei comandi seguenti dalla riga di comando:</span><span class="sxs-lookup"><span data-stu-id="9deb5-109">From the command line, run one of the following commands:</span></span>
    
      - <span data-ttu-id="9deb5-110">Per recuperare tutte le assegnazioni di account di autenticazione Kerberos nell'organizzazione e restituire informazioni sulle assegnazioni per ognuna, eseguire il cmdlet senza parametri:</span><span class="sxs-lookup"><span data-stu-id="9deb5-110">To query all Kerberos authentication account assignments in your organization and return assignment information about each of them, run the cmdlet without any parameters:</span></span>
        
            Get-CsKerberosAccountAssignment
    
      - <span data-ttu-id="9deb5-111">Per recuperare tutte le assegnazioni di account di autenticazione Kerberos nella distribuzione e restituire informazioni sulle assegnazioni del sito per ognuna, eseguire il cmdlet con il parametro Identity:</span><span class="sxs-lookup"><span data-stu-id="9deb5-111">To query all Kerberos authentication account assignments in your deployment and return site assignment information about each of them, run the cmdlet with the Identity parameter:</span></span>
        
            Get-CsKerberosAccountAssignment -Identity "site:SiteName"
        
        <span data-ttu-id="9deb5-112">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="9deb5-112">For example:</span></span>
        
            Get-CsKerberosAccountAssignment -Identity "site:Redmond"
    
      - <span data-ttu-id="9deb5-113">Per recuperare tutte le assegnazioni di account di autenticazione Kerberos in un singolo sito e restituire informazioni sulle assegnazioni per ognuna, eseguire il cmdlet con il parametro Filter:</span><span class="sxs-lookup"><span data-stu-id="9deb5-113">To query all Kerberos authentication account assignments in a single site and return assignment information about each of them, run the cmdlet with the Filter parameter:</span></span>
        
            Get-CsKerberosAccountAssignment -Filter "SiteName"
        
        <span data-ttu-id="9deb5-114">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="9deb5-114">For example:</span></span>
        
            Get-CsKerberosAccountAssignment -Filter "*Redmond"
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="9deb5-115">Se si specifica \*NomeSito per il parametro Filter vengono restituite informazioni su tutti i siti che contengono il nome di sito specificato in qualsiasi posizione nell'identificatore di sito (ad esempio, tutti i siti che contengono la stringa Redmond nell'identificatore di sito).</span><span class="sxs-lookup"><span data-stu-id="9deb5-115">Specifying \*SiteName for the Filter parameter returns information about all sites that contain the specified site name anywhere in the site identifier (for example, all sites that contain the string Redmond in the site identifier).</span></span>

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

