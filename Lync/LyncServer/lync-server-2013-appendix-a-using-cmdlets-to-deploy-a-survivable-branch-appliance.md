---
title: 'Lync Server 2013: Appendice A: utilizzo dei cmdlet per distribuire un Survivable Branch Appliance'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Appendix A: Using cmdlets to deploy a Survivable Branch Appliance'
ms:assetid: 796a26cf-7ec9-453b-8757-6153a6dd86c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398598(v=OCS.15)
ms:contentKeyID: 48184569
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4a2da84e03cc05607a47f1fe5af4a8b7987946df
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737796"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appendix-a-using-cmdlets-to-deploy-a-survivable-branch-appliance-in-lync-server-2013"></a><span data-ttu-id="51e99-102">Appendice A: utilizzo dei cmdlet per distribuire un Survivable Branch Appliance in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="51e99-102">Appendix A: Using cmdlets to deploy a Survivable Branch Appliance in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="51e99-103">_**Argomento Ultima modifica:** 2012-10-07_</span><span class="sxs-lookup"><span data-stu-id="51e99-103">_**Topic Last Modified:** 2012-10-07_</span></span>

<span data-ttu-id="51e99-104">Questo argomento descrive come distribuire un Survivable Branch Appliance tramite Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="51e99-104">This topic describes how to deploy a Survivable Branch Appliance using the Lync Server Management Shell.</span></span> <span data-ttu-id="51e99-105">Eseguire questa procedura nel sito centrale.</span><span class="sxs-lookup"><span data-stu-id="51e99-105">Perform this procedure at the central site.</span></span>

<div>

## <a name="to-deploy-a-survivable-branch-appliance-remotely"></a><span data-ttu-id="51e99-106">Per distribuire un Survivable Branch Appliance in remoto</span><span class="sxs-lookup"><span data-stu-id="51e99-106">To deploy a Survivable Branch Appliance remotely</span></span>

1.  <span data-ttu-id="51e99-107">Seguire la procedura descritta in [aggiungere siti di succursale alla topologia in Lync Server 2013](lync-server-2013-add-branch-sites-to-your-topology.md) per aggiungere un nuovo sito di succursale.</span><span class="sxs-lookup"><span data-stu-id="51e99-107">Follow the procedure in [Add branch sites to your topology in Lync Server 2013](lync-server-2013-add-branch-sites-to-your-topology.md) to add a new branch site.</span></span>

2.  <span data-ttu-id="51e99-108">Partecipare al sito della filiale al dominio.</span><span class="sxs-lookup"><span data-stu-id="51e99-108">Join the branch site to the domain.</span></span>

3.  <span data-ttu-id="51e99-109">Aggiungere il gruppo RTCUniversalSBATechnicians al gruppo Administrators locale.</span><span class="sxs-lookup"><span data-stu-id="51e99-109">Add the RTCUniversalSBATechnicians group to the local Administrators group.</span></span>

4.  <span data-ttu-id="51e99-110">Riavviare il server ed eseguire l'accesso come membro del gruppo RTCUniversalSBATechnicians.</span><span class="sxs-lookup"><span data-stu-id="51e99-110">Restart the server, and log on to it as a member of the RTCUniversalSBATechnicians group.</span></span>

5.  <span data-ttu-id="51e99-111">In Lync Server Management Shell digitare i comandi seguenti, sostituendo i segnaposto con le informazioni corrette per l'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="51e99-111">In the Lync Server Management Shell, type the following commands, replacing the placeholders with the correct information for your organization:</span></span>
    
        Export-CsConfiguration -FileName C:\CSConfig.zip
        Import-CsConfiguration -LocalStore -FileName C:\CSConfig.zip -Verbose
        Enable-CSReplica -Verbose
        Enable-CsComputer -Verbose
        Request-CsCertificate -New -Type default -CA <YourCA> -Verbose
        Set-CsCertificate -Type Default -Thumbprint <YourCertThumbprint>
        Start-cswindowsservice -verbose

</div>

</div>

<span> </span>

</div>

</div>

</div>

