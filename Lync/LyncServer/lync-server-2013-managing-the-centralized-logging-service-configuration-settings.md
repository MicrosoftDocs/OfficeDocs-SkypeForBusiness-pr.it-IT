---
title: Gestione delle impostazioni di configurazione del servizio di registrazione centralizzato
description: Gestione delle impostazioni di configurazione del servizio di registrazione centralizzata.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing the Centralized Logging Service configuration settings
ms:assetid: f455c3aa-0061-413d-bdfb-a3e78f82723d
ms:mtpsurl: https://technet.microsoft.com/library/JJ721938(v=OCS.15)
ms:contentKeyID: 49733875
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e25294e096b8368aa06a11e4ad851fe5d1a84c0f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572602"
---
# <a name="managing-the-centralized-logging-service-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="dd1d1-103">Gestione delle impostazioni di configurazione del servizio di registrazione centralizzato in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dd1d1-103">Managing the Centralized Logging Service configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dd1d1-104">_**Ultimo argomento modificato:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="dd1d1-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="dd1d1-105">Il servizio di registrazione centralizzato è controllato e configurato dalle impostazioni e dai parametri creati e utilizzati dal controller del servizio di registrazione centralizzato (CLSController) per inviare comandi all'agente di servizio di registrazione centralizzato del singolo computer (CLSAgent).</span><span class="sxs-lookup"><span data-stu-id="dd1d1-105">The Centralized Logging Service is controlled and configured by settings and parameters that are created and used by the Centralized Logging Service Controller (CLSController) to send commands to the individual computer’s Centralized Logging Service Agent (CLSAgent).</span></span> <span data-ttu-id="dd1d1-106">L'agente elabora i comandi che riceve e, in caso di un comando Start, utilizza la configurazione di scenari, provider, dimensione del log, durata della traccia e flag per iniziare a raccogliere i log di traccia in base alle informazioni di configurazione fornite.</span><span class="sxs-lookup"><span data-stu-id="dd1d1-106">The agent processes the commands that are sent to it and (in the case of a Start command) uses the configuration of the scenarios, providers, log size, trace duration, and flags to begin collecting trace logs according to the configuration information provided.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="dd1d1-107">Non tutti i cmdlet di Windows PowerShell elencati per il servizio di registrazione centralizzato sono progettati per essere utilizzati con le distribuzioni locali di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dd1d1-107">Not all Windows PowerShell cmdlets listed for the Centralized Logging Service are intended for use with Lync Server 2013 on-premises deployments.</span></span> <span data-ttu-id="dd1d1-108">Sebbene possano sembrare utili, i cmdlet seguenti non sono stati creati per funzionare con le distribuzioni locali di Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="dd1d1-108">Although they may appear to work, the following cmdlets are not designed to function with Lync Server 2013 on-premises deployments:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="dd1d1-109"><STRONG>Cmdlet CsClsRegion:</STRONG> <A href="https://technet.microsoft.com/library/JJ204879(v=OCS.15)">Get-CsClsRegion</A>, <A href="https://technet.microsoft.com/library/JJ204746(v=OCS.15)">Set-CsClsRegion</A>, <A href="https://technet.microsoft.com/library/JJ204658(v=OCS.15)">New-CsClsRegion</A> e <A href="https://technet.microsoft.com/library/JJ204971(v=OCS.15)">Remove-CsClsRegion</A>.</span><span class="sxs-lookup"><span data-stu-id="dd1d1-109"><STRONG>CsClsRegion cmdlets:</STRONG> <A href="https://technet.microsoft.com/library/JJ204879(v=OCS.15)">Get-CsClsRegion</A>, <A href="https://technet.microsoft.com/library/JJ204746(v=OCS.15)">Set-CsClsRegion</A>, <A href="https://technet.microsoft.com/library/JJ204658(v=OCS.15)">New-CsClsRegion</A>, and <A href="https://technet.microsoft.com/library/JJ204971(v=OCS.15)">Remove-CsClsRegion</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="dd1d1-110"><STRONG>Cmdlet CsClsSearchTerm:</STRONG> <A href="https://technet.microsoft.com/library/JJ205061(v=OCS.15)">Get-CsClsSearchTerm</A> e <A href="https://technet.microsoft.com/library/JJ204911(v=OCS.15)">Set-CsClsSearchTerm</A>.</span><span class="sxs-lookup"><span data-stu-id="dd1d1-110"><STRONG>CsClsSearchTerm cmdlets:</STRONG> <A href="https://technet.microsoft.com/library/JJ205061(v=OCS.15)">Get-CsClsSearchTerm</A> and <A href="https://technet.microsoft.com/library/JJ204911(v=OCS.15)">Set-CsClsSearchTerm</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="dd1d1-111"><STRONG>Cmdlet CsClsSecurityGroup:</STRONG> <A href="https://technet.microsoft.com/library/JJ205285(v=OCS.15)">Get-CsClsSecurityGroup</A>, <A href="https://technet.microsoft.com/library/JJ204700(v=OCS.15)">Set-CsClsSecurityGroup</A>, <A href="https://technet.microsoft.com/library/JJ205359(v=OCS.15)">New-CsClsSecurityGroup</A> e <A href="https://technet.microsoft.com/library/JJ204958(v=OCS.15)">Remove-CsClsSecurityGroup</A>.</span><span class="sxs-lookup"><span data-stu-id="dd1d1-111"><STRONG>CsClsSecurityGroup cmdlets:</STRONG> <A href="https://technet.microsoft.com/library/JJ205285(v=OCS.15)">Get-CsClsSecurityGroup</A>, <A href="https://technet.microsoft.com/library/JJ204700(v=OCS.15)">Set-CsClsSecurityGroup</A>, <A href="https://technet.microsoft.com/library/JJ205359(v=OCS.15)">New-CsClsSecurityGroup</A>, and <A href="https://technet.microsoft.com/library/JJ204958(v=OCS.15)">Remove-CsClsSecurityGroup</A>.</span></span></P></LI></UL><span data-ttu-id="dd1d1-112">Le impostazioni definite in questi cmdlet non impediscono o causano un comportamento avverso, ma sono progettate per l'utilizzo con Microsoft 365 e non restituiscono i risultati previsti nelle distribuzioni locali.</span><span class="sxs-lookup"><span data-stu-id="dd1d1-112">The settings defined in these cmdlets will not hinder or cause any adverse behavior, but they are designed for use with Microsoft 365 and will not yield the expected results in on-premises deployments.</span></span> <span data-ttu-id="dd1d1-113">Questo non significa che non si possono utilizzare nelle distribuzioni locali, ma il loro utilizzo è descritto in un argomento più avanzato che non è incluso in questa documentazione.</span><span class="sxs-lookup"><span data-stu-id="dd1d1-113">This is not to say that there is no use for these cmdlets in on-premises deployments, but their use is a more advanced topic that is not covered in this documentation.</span></span>


</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="dd1d1-114">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="dd1d1-114">In This Section</span></span>

<span data-ttu-id="dd1d1-115">Negli argomenti di questa sezione vengono definite le opzioni di configurazione, i parametri e le impostazioni per il servizio di registrazione centralizzato.</span><span class="sxs-lookup"><span data-stu-id="dd1d1-115">The topics in this section define the configuration options, parameters, and settings for the Centralized Logging Service.</span></span> <span data-ttu-id="dd1d1-116">Informazioni su come configurare il servizio di registrazione centralizzato, su come recuperare le impostazioni di configurazione, la creazione di scenari, la gestione dei gruppi di sicurezza per il servizio di registrazione centralizzato, la ricerca e altro ancora è contenuto negli argomenti seguenti.</span><span class="sxs-lookup"><span data-stu-id="dd1d1-116">Information about how to configure the Centralized Logging Service, how to retrieve the configuration settings, creation of scenarios, management of security groups for Centralized Logging Service, searching, and more is contained in the following topics.</span></span>

  - [<span data-ttu-id="dd1d1-117">Gestione del computer, del sito e della configurazione del servizio di registrazione centralizzata globale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dd1d1-117">Managing computer, site and global Centralized Logging Service configuration in Lync Server 2013</span></span>](lync-server-2013-managing-computer-site-and-global-centralized-logging-service-configuration.md)

  - [<span data-ttu-id="dd1d1-118">Configurazione dei provider per il servizio di registrazione centralizzato in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dd1d1-118">Configuring providers for Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-configuring-providers-for-centralized-logging-service.md)

  - [<span data-ttu-id="dd1d1-119">Configurazione degli scenari per il servizio di registrazione centralizzato in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dd1d1-119">Configuring scenarios for the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-configuring-scenarios-for-the-centralized-logging-service.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="dd1d1-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dd1d1-120">See Also</span></span>


[<span data-ttu-id="dd1d1-121">Panoramica del servizio di registrazione centralizzato in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dd1d1-121">Overview of the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-centralized-logging-service.md)  
[<span data-ttu-id="dd1d1-122">Cmdlet per la registrazione centralizzata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dd1d1-122">Centralized Logging cmdlets in Lync Server 2013</span></span>](lync-server-2013-centralized-logging-cmdlets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

