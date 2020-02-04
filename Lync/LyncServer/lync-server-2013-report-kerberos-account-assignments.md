---
title: 'Lync Server 2013: Generare un rapporto sulle assegnazioni degli account Kerberos'
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
ms.openlocfilehash: f4c5a6c118596acd406c3741c4dd2ee780fd381b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746696"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="report-kerberos-account-assignments-in-lync-server-2013"></a><span data-ttu-id="e96b0-102">Generare un rapporto sulle assegnazioni degli account Kerberos in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e96b0-102">Report Kerberos account assignments in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e96b0-103">_**Argomento Ultima modifica:** 2012-01-16_</span><span class="sxs-lookup"><span data-stu-id="e96b0-103">_**Topic Last Modified:** 2012-01-16_</span></span>

<span data-ttu-id="e96b0-104">Per completare correttamente questa procedura, è necessario avere effettuato l'accesso come utente membro del gruppo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="e96b0-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="e96b0-105">Puoi usare il cmdlet **Get-CsKerberosAccountAssignment** per eseguire query sulle assegnazioni degli account di autenticazione Kerberos e segnalare informazioni sulle assegnazioni correnti nella distribuzione.</span><span class="sxs-lookup"><span data-stu-id="e96b0-105">You can use the **Get-CsKerberosAccountAssignment** cmdlet to query information about the Kerberos authentication account assignments and report information about the current assignments in your deployment.</span></span>

<div>

## <a name="to-query-kerberos-authentication-account-assignments-for-a-site"></a><span data-ttu-id="e96b0-106">Per eseguire query sulle assegnazioni degli account di autenticazione Kerberos per un sito</span><span class="sxs-lookup"><span data-stu-id="e96b0-106">To query Kerberos authentication account assignments for a site</span></span>

1.  <span data-ttu-id="e96b0-107">Come membro del gruppo RTCUniversalServerAdmins, accedere a un computer nel dominio in cui è in uso Lync Server 2013 o in un computer in cui sono installati gli strumenti di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="e96b0-107">As a member of the RTCUniversalServerAdmins group, log on to a computer in the domain running Lync Server 2013 or on to a computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="e96b0-108">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="e96b0-108">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="e96b0-109">Nella riga di comando eseguire uno dei comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="e96b0-109">From the command line, run one of the following commands:</span></span>
    
      - <span data-ttu-id="e96b0-110">Per eseguire query su tutte le assegnazioni degli account di autenticazione Kerberos nell'organizzazione e restituire informazioni sulle assegnazioni su ognuno di essi, Esegui il cmdlet senza parametri:</span><span class="sxs-lookup"><span data-stu-id="e96b0-110">To query all Kerberos authentication account assignments in your organization and return assignment information about each of them, run the cmdlet without any parameters:</span></span>
        
            Get-CsKerberosAccountAssignment
    
      - <span data-ttu-id="e96b0-111">Per eseguire query su tutte le assegnazioni degli account di autenticazione Kerberos nella distribuzione e restituire informazioni sulle assegnazioni del sito su ognuna di esse, Esegui il cmdlet con il parametro Identity:</span><span class="sxs-lookup"><span data-stu-id="e96b0-111">To query all Kerberos authentication account assignments in your deployment and return site assignment information about each of them, run the cmdlet with the Identity parameter:</span></span>
        
            Get-CsKerberosAccountAssignment -Identity "site:SiteName"
        
        <span data-ttu-id="e96b0-112">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="e96b0-112">For example:</span></span>
        
            Get-CsKerberosAccountAssignment -Identity "site:Redmond"
    
      - <span data-ttu-id="e96b0-113">Per eseguire query su tutte le assegnazioni degli account di autenticazione Kerberos in un singolo sito e restituire informazioni sulle assegnazioni su ognuna di esse, Esegui il cmdlet con il parametro Filter:</span><span class="sxs-lookup"><span data-stu-id="e96b0-113">To query all Kerberos authentication account assignments in a single site and return assignment information about each of them, run the cmdlet with the Filter parameter:</span></span>
        
            Get-CsKerberosAccountAssignment -Filter "SiteName"
        
        <span data-ttu-id="e96b0-114">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="e96b0-114">For example:</span></span>
        
            Get-CsKerberosAccountAssignment -Filter "*Redmond"
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="e96b0-115">Specificando \* nomesito per il parametro Filter vengono restituite informazioni su tutti i siti che contengono il nome del sito specificato in un punto qualsiasi dell'identificatore del sito, ad esempio tutti i siti che contengono la stringa Redmond nell'identificatore del sito.</span><span class="sxs-lookup"><span data-stu-id="e96b0-115">Specifying \*SiteName for the Filter parameter returns information about all sites that contain the specified site name anywhere in the site identifier (for example, all sites that contain the string Redmond in the site identifier).</span></span>

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

