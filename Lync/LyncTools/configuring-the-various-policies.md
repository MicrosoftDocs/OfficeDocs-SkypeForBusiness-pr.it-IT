---
title: Configurazione dei diversi criteri
description: Configurazione dei diversi criteri.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Configuring the Various Policies
ms:assetid: e3b3cbda-7c17-470b-acb0-82fdcc473184
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945610(v=OCS.15)
ms:contentKeyID: 51541436
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 746d299ac605c7dfe89a957246d47309dfbc0a5d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548842"
---
# <a name="configuring-the-various-policies"></a><span data-ttu-id="2323a-103">Configurazione dei diversi criteri</span><span class="sxs-lookup"><span data-stu-id="2323a-103">Configuring the Various Policies</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2323a-104">_**Ultimo argomento modificato:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="2323a-104">_**Topic Last Modified:** 2013-02-24_</span></span>

<div>

<span data-ttu-id="2323a-105">Di seguito sono riportati i diversi criteri che è possibile configurare nella topologia di Lync Server 2013, prima di eseguire lo strumento di gestione dello stress e delle prestazioni di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2323a-105">Here are the various policies that you can configure in your Lync Server 2013 topology, prior to running the Lync Server 2013 Stress and Performance Tool.</span></span>

<div>

## <a name="configuring-the-archiving-policy"></a><span data-ttu-id="2323a-106">Configurazione dei criteri di archiviazione</span><span class="sxs-lookup"><span data-stu-id="2323a-106">Configuring the Archiving Policy</span></span>

<span data-ttu-id="2323a-107">Vedere lo script di esempio ArchivingPolicy.ps1.</span><span class="sxs-lookup"><span data-stu-id="2323a-107">See the example script ArchivingPolicy.ps1.</span></span> <span data-ttu-id="2323a-108">È necessario utilizzare questo script solo se è stato distribuito un server di archiviazione nella topologia.</span><span class="sxs-lookup"><span data-stu-id="2323a-108">You need to use this script only if an Archiving Server is deployed in your topology.</span></span> <span data-ttu-id="2323a-109">Per informazioni dettagliate, vedere la documentazione di Lync Server 2013 e la guida per i cmdlet per l' [archiviazione e il monitoraggio dei cmdlet in Lync server 2013](https://technet.microsoft.com/library/gg415629\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="2323a-109">For details, see the Lync Server 2013 documentation and cmdlet Help for [Archiving and Monitoring cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg415629\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-the-conferencing-policy"></a><span data-ttu-id="2323a-110">Configurazione dei criteri di conferenza</span><span class="sxs-lookup"><span data-stu-id="2323a-110">Configuring the Conferencing Policy</span></span>

<span data-ttu-id="2323a-111">Vedere lo script di esempio MeetingPolicy.ps1.</span><span class="sxs-lookup"><span data-stu-id="2323a-111">See the example script MeetingPolicy.ps1.</span></span> <span data-ttu-id="2323a-112">Per informazioni dettagliate, vedere la documentazione di Lync Server 2013 e la guida per i cmdlet per le [conferenze Web in Lync server 2013](https://technet.microsoft.com/library/gg415675\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="2323a-112">For details, see the Lync Server 2013 documentation and the cmdlet Help for [Web conferencing cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg415675\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-the-contacts-policy"></a><span data-ttu-id="2323a-113">Configurazione dei criteri contatti</span><span class="sxs-lookup"><span data-stu-id="2323a-113">Configuring the Contacts Policy</span></span>

<span data-ttu-id="2323a-114">Vedere l'esempio ContactsPolicy.ps1.</span><span class="sxs-lookup"><span data-stu-id="2323a-114">See the example ContactsPolicy.ps1.</span></span> <span data-ttu-id="2323a-115">Per informazioni dettagliate, vedere la documentazione di Lync Server 2013 e la guida per i cmdlet per la [messaggistica istantanea e la presenza in Lync server 2013](https://technet.microsoft.com/library/gg398611\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="2323a-115">For details, see the Lync Server 2013 documentation and the cmdlet Help for [IM and presence cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg398611\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-the-federation-policy"></a><span data-ttu-id="2323a-116">Configurazione dei criteri di Federazione</span><span class="sxs-lookup"><span data-stu-id="2323a-116">Configuring the Federation Policy</span></span>

<span data-ttu-id="2323a-117">Vedere l'esempio FederationPolicy.ps1.</span><span class="sxs-lookup"><span data-stu-id="2323a-117">See the example FederationPolicy.ps1.</span></span> <span data-ttu-id="2323a-118">Per informazioni dettagliate, vedere la documentazione di Lync Server 2013 e la guida per i cmdlet del [server perimetrale in Lync server 2013](https://technet.microsoft.com/library/gg415635\(v=ocs.15\)) e i [cmdlet di Federazione e accesso esterno in Lync Server 2013](https://technet.microsoft.com/library/gg415651\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="2323a-118">For details, see the Lync Server 2013 documentation and the cmdlet Help for [Edge Server cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg415635\(v=ocs.15\)) and [Federation and external access cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg415651\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-the-call-admission-control-policy"></a><span data-ttu-id="2323a-119">Configurazione del criterio di controllo di ammissione di chiamata</span><span class="sxs-lookup"><span data-stu-id="2323a-119">Configuring the Call Admission Control Policy</span></span>

<span data-ttu-id="2323a-120">Vedere l'esempio BandwidthPolicy.ps1.</span><span class="sxs-lookup"><span data-stu-id="2323a-120">See the example BandwidthPolicy.ps1.</span></span> <span data-ttu-id="2323a-121">Per informazioni dettagliate, vedere la documentazione di Lync Server 2013 [Panoramica del controllo di ammissione di chiamata in Lync server 2013](https://technet.microsoft.com/library/gg398529\(v=ocs.15\)) e la guida per i cmdlet per il [controllo di ammissione di chiamata in Lync Server 2013](https://technet.microsoft.com/library/gg415676\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="2323a-121">For details, see the Lync Server 2013 documentation [Overview of call admission control in Lync Server 2013](https://technet.microsoft.com/library/gg398529\(v=ocs.15\)) and the cmdlet Help for [Call admission control cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg415676\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-the-voice-routing-rules"></a><span data-ttu-id="2323a-122">Configurazione delle regole di routing vocale</span><span class="sxs-lookup"><span data-stu-id="2323a-122">Configuring the Voice Routing Rules</span></span>

<span data-ttu-id="2323a-123">Vedere l'esempio RoutingRules.ps1.</span><span class="sxs-lookup"><span data-stu-id="2323a-123">See the example RoutingRules.ps1.</span></span> <span data-ttu-id="2323a-124">Quando si configurano le regole di routing vocale, prendere nota del contesto telefonico (ovvero/location profile o/SimpleName) e dei codici di area interni/esterni in modo da poterli specificare quando si creano gli utenti e durante la configurazione di LyncPerfTool (in particolare per PSTN-UC e UC-PSTN).</span><span class="sxs-lookup"><span data-stu-id="2323a-124">When you configure the voice routing rules, take note of the Phone Context (that is, /Location Profile or /SimpleName) and Internal/External Area Codes so that you can specify them when creating users and during LyncPerfTool configuration (specifically for PSTN-UC and UC-PSTN).</span></span> <span data-ttu-id="2323a-125">Ad esempio, il parametro SimpleName nella chiamata al cmdlet **New-CsDialPlan** nell'esempio RoutingRules.ps1 deve essere utilizzato per il valore LocationProfile nella figura seguente di UserProfileGenerator.exe.</span><span class="sxs-lookup"><span data-stu-id="2323a-125">For example, the SimpleName parameter in the call to the **New-CsDialPlan** cmdlet in the RoutingRules.ps1 example should be used for the LocationProfile value in the following figure of UserProfileGenerator.exe.</span></span>

<span data-ttu-id="2323a-126">![Regola di routing vocale di esempio.](images/JJ945610.9f34d971-4ed0-4a4c-b101-086a91c4578c(OCS.15).jpg "Regola di routing vocale di esempio.")</span><span class="sxs-lookup"><span data-stu-id="2323a-126">![Sample voice routing rule.](images/JJ945610.9f34d971-4ed0-4a4c-b101-086a91c4578c(OCS.15).jpg "Sample voice routing rule.")</span></span>

<span data-ttu-id="2323a-127">Per informazioni dettagliate, vedere la documentazione di Lync Server 2013 e la guida per i cmdlet di [VoIP aziendale in Lync server 2013](https://technet.microsoft.com/library/gg415658\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="2323a-127">For details, see the Lync Server 2013 documentation and the cmdlet Help for [Enterprise Voice cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg415658\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-conferencing-attendant-application"></a><span data-ttu-id="2323a-128">Configurazione dell'applicazione Operatore Conferenza</span><span class="sxs-lookup"><span data-stu-id="2323a-128">Configuring Conferencing Attendant application</span></span>

<span data-ttu-id="2323a-129">Vedere l'esempio ConferenceAutoAttendantConfiguration.ps1.</span><span class="sxs-lookup"><span data-stu-id="2323a-129">See the example ConferenceAutoAttendantConfiguration.ps1.</span></span> <span data-ttu-id="2323a-130">Prendere nota del numero di telefono di ConferencingAutoAttendant (1121111111, per impostazione predefinita), in modo che sia possibile digitarlo nello strumento di configurazione dello strumento di LyncPerf per la generazione di configurazione.</span><span class="sxs-lookup"><span data-stu-id="2323a-130">Take note of the ConferencingAutoAttendant phone number (1121111111, by default), so that you can type it into the LyncPerf Tool Configuration tool for configuration generation.</span></span>

<span data-ttu-id="2323a-131">![Configurazione dell'applicazione Operatore Conferenza](images/JJ945610.0618a22f-27a9-423a-9085-d2bf71e82db6(OCS.15).jpg "Configurazione dell'applicazione Operatore Conferenza")</span><span class="sxs-lookup"><span data-stu-id="2323a-131">![Configuring the Conferencing Attendant application](images/JJ945610.0618a22f-27a9-423a-9085-d2bf71e82db6(OCS.15).jpg "Configuring the Conferencing Attendant application")</span></span>

<span data-ttu-id="2323a-132">Per informazioni dettagliate, vedere la documentazione di Lync Server 2013 e la guida per i cmdlet per le [conferenze Web in Lync server 2013](https://technet.microsoft.com/library/gg415675\(v=ocs.15\)) e i cmdlet per le conferenze telefoniche con [accesso esterno in Lync Server 2013](https://technet.microsoft.com/library/gg415630\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="2323a-132">For details, see the Lync Server 2013 documentation and the cmdlet Help for [Web conferencing cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg415675\(v=ocs.15\)) and [Dial-in conferencing cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg415630\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-lync-server-call-park-service"></a><span data-ttu-id="2323a-133">Configurazione del servizio parcheggio di chiamata di Lync Server</span><span class="sxs-lookup"><span data-stu-id="2323a-133">Configuring Lync Server Call Park Service</span></span>

<span data-ttu-id="2323a-134">Il parcheggio di chiamata è disabilitato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="2323a-134">Call Park is disabled by default.</span></span> <span data-ttu-id="2323a-135">Vedere l'esempio CallParkConfiguration.ps1.</span><span class="sxs-lookup"><span data-stu-id="2323a-135">See the example CallParkConfiguration.ps1.</span></span> <span data-ttu-id="2323a-136">Per informazioni dettagliate, vedere la documentazione di Lync Server 2013 e la guida del cmdlet per i [cmdlet dell'applicazione Parcheggio di chiamata in Lync server 2013](https://technet.microsoft.com/library/gg415639\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="2323a-136">For details, see the Lync Server 2013 documentation and the cmdlet Help for [Call Park application cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg415639\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-emergency-calls"></a><span data-ttu-id="2323a-137">Configurazione delle chiamate di emergenza</span><span class="sxs-lookup"><span data-stu-id="2323a-137">Configuring Emergency Calls</span></span>

<span data-ttu-id="2323a-138">Eseguire la procedura seguente per configurare i test di stress e prestazioni per le chiamate di emergenza.</span><span class="sxs-lookup"><span data-stu-id="2323a-138">Perform the following steps to configure stress and performance testing for emergency calls.</span></span>

1.  <span data-ttu-id="2323a-139">Impostare una route vocale per le chiamate di emergenza.</span><span class="sxs-lookup"><span data-stu-id="2323a-139">Set up a voice route for emergency calls.</span></span> <span data-ttu-id="2323a-140">Vedere lo script RoutingRules.ps1 nel commento "Route E911 to PSTN" per un esempio di configurazione di questa route vocale.</span><span class="sxs-lookup"><span data-stu-id="2323a-140">See the RoutingRules.ps1 script under the comment "Route E911 to PSTN" for an example of setting up this voice route.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="2323a-141">Il comando di esempio in RoutingRules.ps1 ha un modello di numero che include il numero 119 anziché 911.</span><span class="sxs-lookup"><span data-stu-id="2323a-141">The example command in RoutingRules.ps1 has a number pattern that includes the number 119 rather than 911.</span></span> <span data-ttu-id="2323a-142">È consigliabile evitare di usare 911 (o il numero di emergenza locale effettivo) per impedire chiamate accidentali agli operatori di emergenza locali durante il test di carico.</span><span class="sxs-lookup"><span data-stu-id="2323a-142">You should avoid using 911 (or your actual local emergency number) to prevent accidental calls to your local emergency operators during load testing.</span></span> <span data-ttu-id="2323a-143">Questa configurazione è solo per scopi di simulazione.</span><span class="sxs-lookup"><span data-stu-id="2323a-143">This configuration is for simulation purposes only.</span></span>

    
    </div>

2.  <span data-ttu-id="2323a-144">Configurare gli indirizzi compilando i valori della scheda **LIS** in UserProvisioningTool, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="2323a-144">Configure addresses by filling in the values on the **LIS** tab in the UserProvisioningTool, as shown in the following figure.</span></span>
    
    <span data-ttu-id="2323a-145">![Configurazione del servizio informazioni percorso.](images/JJ945610.8ac1faa1-e9f9-40d0-b8b7-b159f4f459f7(OCS.15).jpg "Configurazione del servizio informazioni percorso.")</span><span class="sxs-lookup"><span data-stu-id="2323a-145">![Configuring the Location Information Service.](images/JJ945610.8ac1faa1-e9f9-40d0-b8b7-b159f4f459f7(OCS.15).jpg "Configuring the Location Information Service.")</span></span>  

3.  <span data-ttu-id="2323a-146">Fare clic su **genera file di configurazione LIS**.</span><span class="sxs-lookup"><span data-stu-id="2323a-146">Click **Generate LIS Config Files**.</span></span>

4.  <span data-ttu-id="2323a-147">Vengono generati i file CSV per porte, subnet, commutatori e punti di accesso wireless (WAP) e un file XML per lo strumento di stress e prestazioni di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2323a-147">CSV files for ports, subnets, switches, and wireless access points (WAPs), and an XML file for the Lync Server 2013 Stress and Performance Tool, are generated.</span></span> <span data-ttu-id="2323a-148">I file CSV devono essere utilizzati come input (nella stessa cartella) durante la configurazione del servizio informazioni percorso (LIS) con lo script LisConfiguration.ps1.</span><span class="sxs-lookup"><span data-stu-id="2323a-148">The CSV files are to be used as inputs (in the same folder) when configuring Location Information service (LIS) with the LisConfiguration.ps1 script.</span></span> <span data-ttu-id="2323a-149">Spostare il file di Locations0.xml generato nella stessa cartella in cui si trova l'eseguibile dello strumento di stress e prestazioni di Lync Server 2013 (LyncPerfTool.exe), che eseguirà gli scenari del profilo percorso (dial plan).</span><span class="sxs-lookup"><span data-stu-id="2323a-149">Move the generated Locations0.xml file to the same folder as the Lync Server 2013 Stress and Performance Tool executable (LyncPerfTool.exe), which will run location profile (dial plan) scenarios.</span></span>

</div>

<div>

## <a name="creating-enabling-configuring-and-disabling-users"></a><span data-ttu-id="2323a-150">Creazione, abilitazione, configurazione e disabilitazione degli utenti</span><span class="sxs-lookup"><span data-stu-id="2323a-150">Creating, Enabling, Configuring and Disabling Users</span></span>

<span data-ttu-id="2323a-151">Prima di eseguire gli script seguenti, è consigliabile creare tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="2323a-151">You should create all your users before running the following scripts.</span></span> <span data-ttu-id="2323a-152">Seguire le istruzioni riportate in [creare utenti e contatti](create-users-and-contacts.md) per creare gli utenti.</span><span class="sxs-lookup"><span data-stu-id="2323a-152">Follow the instructions in [Create Users and Contacts](create-users-and-contacts.md) to create users.</span></span> <span data-ttu-id="2323a-153">Per informazioni dettagliate, vedere la documentazione relativa ai cmdlet di Lync Server 2013 per i cmdlet [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)), [Set-CsUser](https://technet.microsoft.com/library/gg398510\(v=ocs.15\))e [Disable-CsUser](https://technet.microsoft.com/library/gg398747\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="2323a-153">For details, see the Lync Server 2013 cmdlet documentation for the [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)), [Set-CsUser](https://technet.microsoft.com/library/gg398510\(v=ocs.15\)), and [Disable-CsUser](https://technet.microsoft.com/library/gg398747\(v=ocs.15\)) cmdlets.</span></span>

</div>

<div>

## <a name="configuring-response-group-application"></a><span data-ttu-id="2323a-154">Configurazione dell'applicazione Response Group</span><span class="sxs-lookup"><span data-stu-id="2323a-154">Configuring Response Group application</span></span>

<span data-ttu-id="2323a-155">Vedere l'esempio ResponseGroupConfiguration.ps1.</span><span class="sxs-lookup"><span data-stu-id="2323a-155">See the example ResponseGroupConfiguration.ps1.</span></span> <span data-ttu-id="2323a-156">Per informazioni dettagliate, vedere la documentazione di Lync Server 2013 e la guida per i cmdlet per le [applicazioni di Response Group in Lync server 2013](https://technet.microsoft.com/library/gg415654\(v=ocs.15\)). Per esaminare la configurazione dell'applicazione Response Group, vedere `https://<poolfqdn>/RgsConfig/` , come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="2323a-156">For details, see the Lync Server 2013 documentation and the cmdlet Help for [Response Group application cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg415654\(v=ocs.15\)).To review the Response Group application configuration, see `https://<poolfqdn>/RgsConfig/`, as shown in the following figure.</span></span>

<span data-ttu-id="2323a-157">![Strumento di configurazione di Response Group.](images/JJ945610.480a9440-2283-4533-98f8-86daaab4781c(OCS.15).jpg "Strumento di configurazione di Response Group.")</span><span class="sxs-lookup"><span data-stu-id="2323a-157">![The Response Group Configuration Tool.](images/JJ945610.480a9440-2283-4533-98f8-86daaab4781c(OCS.15).jpg "The Response Group Configuration Tool.")</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

