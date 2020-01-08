---
title: Gestione delle impostazioni di configurazione del servizio di registrazione centralizzata
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing the Centralized Logging Service configuration settings
ms:assetid: f455c3aa-0061-413d-bdfb-a3e78f82723d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721938(v=OCS.15)
ms:contentKeyID: 49733875
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1ce13f34a5a48c80c1f825e225a20c96ebfa2db
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981894"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-the-centralized-logging-service-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="69636-102">Gestione delle impostazioni di configurazione del servizio di registrazione centralizzata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69636-102">Managing the Centralized Logging Service configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="69636-103">_**Argomento Ultima modifica:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="69636-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="69636-104">Il servizio di registrazione centralizzato viene controllato e configurato tramite le impostazioni e i parametri creati e usati dal controller del servizio di registrazione centralizzato (CLSController) per inviare comandi all'agente del servizio di registrazione centralizzato del singolo computer ( CLSAgent).</span><span class="sxs-lookup"><span data-stu-id="69636-104">The Centralized Logging Service is controlled and configured by settings and parameters that are created and used by the Centralized Logging Service Controller (CLSController) to send commands to the individual computer’s Centralized Logging Service Agent (CLSAgent).</span></span> <span data-ttu-id="69636-105">L'agente elabora i comandi inviati e (nel caso di un comando Start) usa la configurazione degli scenari, i provider, le dimensioni del log, la durata della traccia e i contrassegni per iniziare a raccogliere i log di traccia in base alle informazioni di configurazione fornite.</span><span class="sxs-lookup"><span data-stu-id="69636-105">The agent processes the commands that are sent to it and (in the case of a Start command) uses the configuration of the scenarios, providers, log size, trace duration, and flags to begin collecting trace logs according to the configuration information provided.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="69636-106">Non tutti i cmdlet di Windows PowerShell elencati per il servizio di registrazione centralizzata sono progettati per l'uso con le distribuzioni locali di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="69636-106">Not all Windows PowerShell cmdlets listed for the Centralized Logging Service are intended for use with Lync Server 2013 on-premises deployments.</span></span> <span data-ttu-id="69636-107">Anche se potrebbero sembrare utili, i cmdlet seguenti non sono progettati per funzionare con le distribuzioni locali di Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="69636-107">Although they may appear to work, the following cmdlets are not designed to function with Lync Server 2013 on-premises deployments:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="69636-108"><STRONG>Cmdlet CsClsRegion:</STRONG> <A href="https://technet.microsoft.com/en-us/library/JJ204879(v=OCS.15)">Get-CsClsRegion</A>, <A href="https://technet.microsoft.com/en-us/library/JJ204746(v=OCS.15)">Set-CsClsRegion</A>, <A href="https://technet.microsoft.com/en-us/library/JJ204658(v=OCS.15)">New-CsClsRegion</A>e <A href="https://technet.microsoft.com/en-us/library/JJ204971(v=OCS.15)">Remove-CsClsRegion</A>.</span><span class="sxs-lookup"><span data-stu-id="69636-108"><STRONG>CsClsRegion cmdlets:</STRONG> <A href="https://technet.microsoft.com/en-us/library/JJ204879(v=OCS.15)">Get-CsClsRegion</A>, <A href="https://technet.microsoft.com/en-us/library/JJ204746(v=OCS.15)">Set-CsClsRegion</A>, <A href="https://technet.microsoft.com/en-us/library/JJ204658(v=OCS.15)">New-CsClsRegion</A>, and <A href="https://technet.microsoft.com/en-us/library/JJ204971(v=OCS.15)">Remove-CsClsRegion</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="69636-109"><STRONG>Cmdlet CsClsSearchTerm:</STRONG> <A href="https://technet.microsoft.com/en-us/library/JJ205061(v=OCS.15)">Get-CsClsSearchTerm</A> e <A href="https://technet.microsoft.com/en-us/library/JJ204911(v=OCS.15)">Set-CsClsSearchTerm</A>.</span><span class="sxs-lookup"><span data-stu-id="69636-109"><STRONG>CsClsSearchTerm cmdlets:</STRONG> <A href="https://technet.microsoft.com/en-us/library/JJ205061(v=OCS.15)">Get-CsClsSearchTerm</A> and <A href="https://technet.microsoft.com/en-us/library/JJ204911(v=OCS.15)">Set-CsClsSearchTerm</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="69636-110"><STRONG>Cmdlet CsClsSecurityGroup:</STRONG> <A href="https://technet.microsoft.com/en-us/library/JJ205285(v=OCS.15)">Get-CsClsSecurityGroup</A>, <A href="https://technet.microsoft.com/en-us/library/JJ204700(v=OCS.15)">Set-CsClsSecurityGroup</A>, <A href="https://technet.microsoft.com/en-us/library/JJ205359(v=OCS.15)">New-CsClsSecurityGroup</A>e <A href="https://technet.microsoft.com/en-us/library/JJ204958(v=OCS.15)">Remove-CsClsSecurityGroup</A>.</span><span class="sxs-lookup"><span data-stu-id="69636-110"><STRONG>CsClsSecurityGroup cmdlets:</STRONG> <A href="https://technet.microsoft.com/en-us/library/JJ205285(v=OCS.15)">Get-CsClsSecurityGroup</A>, <A href="https://technet.microsoft.com/en-us/library/JJ204700(v=OCS.15)">Set-CsClsSecurityGroup</A>, <A href="https://technet.microsoft.com/en-us/library/JJ205359(v=OCS.15)">New-CsClsSecurityGroup</A>, and <A href="https://technet.microsoft.com/en-us/library/JJ204958(v=OCS.15)">Remove-CsClsSecurityGroup</A>.</span></span></P></LI></UL><span data-ttu-id="69636-111">Le impostazioni definite in questi cmdlet non impediscono o causano alcun comportamento indesiderato, ma sono progettate per l'uso con Microsoft Office 365 e non restituiscono i risultati previsti nelle distribuzioni locali.</span><span class="sxs-lookup"><span data-stu-id="69636-111">The settings defined in these cmdlets will not hinder or cause any adverse behavior, but they are designed for use with Microsoft Office 365 and will not yield the expected results in on-premises deployments.</span></span> <span data-ttu-id="69636-112">Questo non significa che non sia possibile usare questi cmdlet in distribuzioni locali, ma il loro uso è un argomento più avanzato che non è incluso in questa documentazione.</span><span class="sxs-lookup"><span data-stu-id="69636-112">This is not to say that there is no use for these cmdlets in on-premises deployments, but their use is a more advanced topic that is not covered in this documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="69636-113">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="69636-113">In This Section</span></span>

<span data-ttu-id="69636-114">Gli argomenti in questa sezione definiscono le opzioni di configurazione, i parametri e le impostazioni per il servizio di registrazione centralizzato.</span><span class="sxs-lookup"><span data-stu-id="69636-114">The topics in this section define the configuration options, parameters, and settings for the Centralized Logging Service.</span></span> <span data-ttu-id="69636-115">Le informazioni su come configurare il servizio di registrazione centralizzato, su come recuperare le impostazioni di configurazione, la creazione di scenari, la gestione dei gruppi di sicurezza per il servizio di registrazione centralizzato, la ricerca e altro sono contenute negli argomenti seguenti.</span><span class="sxs-lookup"><span data-stu-id="69636-115">Information about how to configure the Centralized Logging Service, how to retrieve the configuration settings, creation of scenarios, management of security groups for Centralized Logging Service, searching, and more is contained in the following topics.</span></span>

  - [<span data-ttu-id="69636-116">Gestione della configurazione del servizio di registrazione centralizzata di computer, siti e globale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69636-116">Managing computer, site and global Centralized Logging Service configuration in Lync Server 2013</span></span>](lync-server-2013-managing-computer-site-and-global-centralized-logging-service-configuration.md)

  - [<span data-ttu-id="69636-117">Configurazione dei provider per il servizio di registrazione centralizzato in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69636-117">Configuring providers for Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-configuring-providers-for-centralized-logging-service.md)

  - [<span data-ttu-id="69636-118">Configurazione di scenari per il servizio di registrazione centralizzato in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69636-118">Configuring scenarios for the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-configuring-scenarios-for-the-centralized-logging-service.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="69636-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="69636-119">See Also</span></span>


[<span data-ttu-id="69636-120">Panoramica del servizio di registrazione centralizzato in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69636-120">Overview of the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-centralized-logging-service.md)  
[<span data-ttu-id="69636-121">Cmdlet di registrazione centralizzati in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69636-121">Centralized Logging cmdlets in Lync Server 2013</span></span>](lync-server-2013-centralized-logging-cmdlets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

