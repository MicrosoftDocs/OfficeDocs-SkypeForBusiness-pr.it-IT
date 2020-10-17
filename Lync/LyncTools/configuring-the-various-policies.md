---
title: Configurazione dei diversi criteri
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
ms.openlocfilehash: b0abb428dab96c09c7cd8b82d99de12ba76068eb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48505243"
---
# <a name="configuring-the-various-policies"></a><span data-ttu-id="57c60-102">Configurazione dei diversi criteri</span><span class="sxs-lookup"><span data-stu-id="57c60-102">Configuring the Various Policies</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="57c60-103">_**Ultimo argomento modificato:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="57c60-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<div>

<span data-ttu-id="57c60-104">Di seguito sono riportati i diversi criteri che è possibile configurare nella topologia di Lync Server 2013, prima di eseguire lo strumento di gestione dello stress e delle prestazioni di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="57c60-104">Here are the various policies that you can configure in your Lync Server 2013 topology, prior to running the Lync Server 2013 Stress and Performance Tool.</span></span>

<div>

## <a name="configuring-the-archiving-policy"></a><span data-ttu-id="57c60-105">Configurazione dei criteri di archiviazione</span><span class="sxs-lookup"><span data-stu-id="57c60-105">Configuring the Archiving Policy</span></span>

<span data-ttu-id="57c60-106">Vedere lo script di esempio ArchivingPolicy.ps1.</span><span class="sxs-lookup"><span data-stu-id="57c60-106">See the example script ArchivingPolicy.ps1.</span></span> <span data-ttu-id="57c60-107">È necessario utilizzare questo script solo se è stato distribuito un server di archiviazione nella topologia.</span><span class="sxs-lookup"><span data-stu-id="57c60-107">You need to use this script only if an Archiving Server is deployed in your topology.</span></span> <span data-ttu-id="57c60-108">Per informazioni dettagliate, vedere la documentazione di Lync Server 2013 e la guida per i cmdlet per l' [archiviazione e il monitoraggio dei cmdlet in Lync server 2013](https://technet.microsoft.com/library/gg415629\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="57c60-108">For details, see the Lync Server 2013 documentation and cmdlet Help for [Archiving and Monitoring cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg415629\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-the-conferencing-policy"></a><span data-ttu-id="57c60-109">Configurazione dei criteri di conferenza</span><span class="sxs-lookup"><span data-stu-id="57c60-109">Configuring the Conferencing Policy</span></span>

<span data-ttu-id="57c60-110">Vedere lo script di esempio MeetingPolicy.ps1.</span><span class="sxs-lookup"><span data-stu-id="57c60-110">See the example script MeetingPolicy.ps1.</span></span> <span data-ttu-id="57c60-111">Per informazioni dettagliate, vedere la documentazione di Lync Server 2013 e la guida per i cmdlet per le [conferenze Web in Lync server 2013](https://technet.microsoft.com/library/gg415675\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="57c60-111">For details, see the Lync Server 2013 documentation and the cmdlet Help for [Web conferencing cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg415675\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-the-contacts-policy"></a><span data-ttu-id="57c60-112">Configurazione dei criteri contatti</span><span class="sxs-lookup"><span data-stu-id="57c60-112">Configuring the Contacts Policy</span></span>

<span data-ttu-id="57c60-113">Vedere l'esempio ContactsPolicy.ps1.</span><span class="sxs-lookup"><span data-stu-id="57c60-113">See the example ContactsPolicy.ps1.</span></span> <span data-ttu-id="57c60-114">Per informazioni dettagliate, vedere la documentazione di Lync Server 2013 e la guida per i cmdlet per la [messaggistica istantanea e la presenza in Lync server 2013](https://technet.microsoft.com/library/gg398611\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="57c60-114">For details, see the Lync Server 2013 documentation and the cmdlet Help for [IM and presence cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg398611\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-the-federation-policy"></a><span data-ttu-id="57c60-115">Configurazione dei criteri di Federazione</span><span class="sxs-lookup"><span data-stu-id="57c60-115">Configuring the Federation Policy</span></span>

<span data-ttu-id="57c60-116">Vedere l'esempio FederationPolicy.ps1.</span><span class="sxs-lookup"><span data-stu-id="57c60-116">See the example FederationPolicy.ps1.</span></span> <span data-ttu-id="57c60-117">Per informazioni dettagliate, vedere la documentazione di Lync Server 2013 e la guida per i cmdlet del [server perimetrale in Lync server 2013](https://technet.microsoft.com/library/gg415635\(v=ocs.15\)) e i [cmdlet di Federazione e accesso esterno in Lync Server 2013](https://technet.microsoft.com/library/gg415651\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="57c60-117">For details, see the Lync Server 2013 documentation and the cmdlet Help for [Edge Server cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg415635\(v=ocs.15\)) and [Federation and external access cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg415651\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-the-call-admission-control-policy"></a><span data-ttu-id="57c60-118">Configurazione del criterio di controllo di ammissione di chiamata</span><span class="sxs-lookup"><span data-stu-id="57c60-118">Configuring the Call Admission Control Policy</span></span>

<span data-ttu-id="57c60-119">Vedere l'esempio BandwidthPolicy.ps1.</span><span class="sxs-lookup"><span data-stu-id="57c60-119">See the example BandwidthPolicy.ps1.</span></span> <span data-ttu-id="57c60-120">Per informazioni dettagliate, vedere la documentazione di Lync Server 2013 [Panoramica del controllo di ammissione di chiamata in Lync server 2013](https://technet.microsoft.com/library/gg398529\(v=ocs.15\)) e la guida per i cmdlet per il [controllo di ammissione di chiamata in Lync Server 2013](https://technet.microsoft.com/library/gg415676\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="57c60-120">For details, see the Lync Server 2013 documentation [Overview of call admission control in Lync Server 2013](https://technet.microsoft.com/library/gg398529\(v=ocs.15\)) and the cmdlet Help for [Call admission control cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg415676\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-the-voice-routing-rules"></a><span data-ttu-id="57c60-121">Configurazione delle regole di routing vocale</span><span class="sxs-lookup"><span data-stu-id="57c60-121">Configuring the Voice Routing Rules</span></span>

<span data-ttu-id="57c60-122">Vedere l'esempio RoutingRules.ps1.</span><span class="sxs-lookup"><span data-stu-id="57c60-122">See the example RoutingRules.ps1.</span></span> <span data-ttu-id="57c60-123">Quando si configurano le regole di routing vocale, prendere nota del contesto telefonico (ovvero/location profile o/SimpleName) e dei codici di area interni/esterni in modo da poterli specificare quando si creano gli utenti e durante la configurazione di LyncPerfTool (in particolare per PSTN-UC e UC-PSTN).</span><span class="sxs-lookup"><span data-stu-id="57c60-123">When you configure the voice routing rules, take note of the Phone Context (that is, /Location Profile or /SimpleName) and Internal/External Area Codes so that you can specify them when creating users and during LyncPerfTool configuration (specifically for PSTN-UC and UC-PSTN).</span></span> <span data-ttu-id="57c60-124">Ad esempio, il parametro SimpleName nella chiamata al cmdlet **New-CsDialPlan** nell'esempio RoutingRules.ps1 deve essere utilizzato per il valore LocationProfile nella figura seguente di UserProfileGenerator.exe.</span><span class="sxs-lookup"><span data-stu-id="57c60-124">For example, the SimpleName parameter in the call to the **New-CsDialPlan** cmdlet in the RoutingRules.ps1 example should be used for the LocationProfile value in the following figure of UserProfileGenerator.exe.</span></span>

<span data-ttu-id="57c60-125">![Regola di routing vocale di esempio.](images/JJ945610.9f34d971-4ed0-4a4c-b101-086a91c4578c(OCS.15).jpg "Regola di routing vocale di esempio.")</span><span class="sxs-lookup"><span data-stu-id="57c60-125">![Sample voice routing rule.](images/JJ945610.9f34d971-4ed0-4a4c-b101-086a91c4578c(OCS.15).jpg "Sample voice routing rule.")</span></span>

<span data-ttu-id="57c60-126">Per informazioni dettagliate, vedere la documentazione di Lync Server 2013 e la guida per i cmdlet di [VoIP aziendale in Lync server 2013](https://technet.microsoft.com/library/gg415658\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="57c60-126">For details, see the Lync Server 2013 documentation and the cmdlet Help for [Enterprise Voice cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg415658\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-conferencing-attendant-application"></a><span data-ttu-id="57c60-127">Configurazione dell'applicazione Operatore Conferenza</span><span class="sxs-lookup"><span data-stu-id="57c60-127">Configuring Conferencing Attendant application</span></span>

<span data-ttu-id="57c60-128">Vedere l'esempio ConferenceAutoAttendantConfiguration.ps1.</span><span class="sxs-lookup"><span data-stu-id="57c60-128">See the example ConferenceAutoAttendantConfiguration.ps1.</span></span> <span data-ttu-id="57c60-129">Prendere nota del numero di telefono di ConferencingAutoAttendant (1121111111, per impostazione predefinita), in modo che sia possibile digitarlo nello strumento di configurazione dello strumento di LyncPerf per la generazione di configurazione.</span><span class="sxs-lookup"><span data-stu-id="57c60-129">Take note of the ConferencingAutoAttendant phone number (1121111111, by default), so that you can type it into the LyncPerf Tool Configuration tool for configuration generation.</span></span>

<span data-ttu-id="57c60-130">![Configurazione dell'applicazione Operatore Conferenza](images/JJ945610.0618a22f-27a9-423a-9085-d2bf71e82db6(OCS.15).jpg "Configurazione dell'applicazione Operatore Conferenza")</span><span class="sxs-lookup"><span data-stu-id="57c60-130">![Configuring the Conferencing Attendant application](images/JJ945610.0618a22f-27a9-423a-9085-d2bf71e82db6(OCS.15).jpg "Configuring the Conferencing Attendant application")</span></span>

<span data-ttu-id="57c60-131">Per informazioni dettagliate, vedere la documentazione di Lync Server 2013 e la guida per i cmdlet per le [conferenze Web in Lync server 2013](https://technet.microsoft.com/library/gg415675\(v=ocs.15\)) e i cmdlet per le conferenze telefoniche con [accesso esterno in Lync Server 2013](https://technet.microsoft.com/library/gg415630\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="57c60-131">For details, see the Lync Server 2013 documentation and the cmdlet Help for [Web conferencing cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg415675\(v=ocs.15\)) and [Dial-in conferencing cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg415630\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-lync-server-call-park-service"></a><span data-ttu-id="57c60-132">Configurazione del servizio parcheggio di chiamata di Lync Server</span><span class="sxs-lookup"><span data-stu-id="57c60-132">Configuring Lync Server Call Park Service</span></span>

<span data-ttu-id="57c60-133">Il parcheggio di chiamata è disabilitato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="57c60-133">Call Park is disabled by default.</span></span> <span data-ttu-id="57c60-134">Vedere l'esempio CallParkConfiguration.ps1.</span><span class="sxs-lookup"><span data-stu-id="57c60-134">See the example CallParkConfiguration.ps1.</span></span> <span data-ttu-id="57c60-135">Per informazioni dettagliate, vedere la documentazione di Lync Server 2013 e la guida del cmdlet per i [cmdlet dell'applicazione Parcheggio di chiamata in Lync server 2013](https://technet.microsoft.com/library/gg415639\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="57c60-135">For details, see the Lync Server 2013 documentation and the cmdlet Help for [Call Park application cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg415639\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-emergency-calls"></a><span data-ttu-id="57c60-136">Configurazione delle chiamate di emergenza</span><span class="sxs-lookup"><span data-stu-id="57c60-136">Configuring Emergency Calls</span></span>

<span data-ttu-id="57c60-137">Eseguire la procedura seguente per configurare i test di stress e prestazioni per le chiamate di emergenza.</span><span class="sxs-lookup"><span data-stu-id="57c60-137">Perform the following steps to configure stress and performance testing for emergency calls.</span></span>

1.  <span data-ttu-id="57c60-138">Impostare una route vocale per le chiamate di emergenza.</span><span class="sxs-lookup"><span data-stu-id="57c60-138">Set up a voice route for emergency calls.</span></span> <span data-ttu-id="57c60-139">Vedere lo script RoutingRules.ps1 nel commento "Route E911 to PSTN" per un esempio di configurazione di questa route vocale.</span><span class="sxs-lookup"><span data-stu-id="57c60-139">See the RoutingRules.ps1 script under the comment "Route E911 to PSTN" for an example of setting up this voice route.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="57c60-140">Il comando di esempio in RoutingRules.ps1 ha un modello di numero che include il numero 119 anziché 911.</span><span class="sxs-lookup"><span data-stu-id="57c60-140">The example command in RoutingRules.ps1 has a number pattern that includes the number 119 rather than 911.</span></span> <span data-ttu-id="57c60-141">È consigliabile evitare di usare 911 (o il numero di emergenza locale effettivo) per impedire chiamate accidentali agli operatori di emergenza locali durante il test di carico.</span><span class="sxs-lookup"><span data-stu-id="57c60-141">You should avoid using 911 (or your actual local emergency number) to prevent accidental calls to your local emergency operators during load testing.</span></span> <span data-ttu-id="57c60-142">Questa configurazione è solo per scopi di simulazione.</span><span class="sxs-lookup"><span data-stu-id="57c60-142">This configuration is for simulation purposes only.</span></span>

    
    </div>

2.  <span data-ttu-id="57c60-143">Configurare gli indirizzi compilando i valori della scheda **LIS** in UserProvisioningTool, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="57c60-143">Configure addresses by filling in the values on the **LIS** tab in the UserProvisioningTool, as shown in the following figure.</span></span>
    
    <span data-ttu-id="57c60-144">![Configurazione del servizio informazioni percorso.](images/JJ945610.8ac1faa1-e9f9-40d0-b8b7-b159f4f459f7(OCS.15).jpg "Configurazione del servizio informazioni percorso.")</span><span class="sxs-lookup"><span data-stu-id="57c60-144">![Configuring the Location Information Service.](images/JJ945610.8ac1faa1-e9f9-40d0-b8b7-b159f4f459f7(OCS.15).jpg "Configuring the Location Information Service.")</span></span>  

3.  <span data-ttu-id="57c60-145">Fare clic su **genera file di configurazione LIS**.</span><span class="sxs-lookup"><span data-stu-id="57c60-145">Click **Generate LIS Config Files**.</span></span>

4.  <span data-ttu-id="57c60-146">Vengono generati i file CSV per porte, subnet, commutatori e punti di accesso wireless (WAP) e un file XML per lo strumento di stress e prestazioni di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="57c60-146">CSV files for ports, subnets, switches, and wireless access points (WAPs), and an XML file for the Lync Server 2013 Stress and Performance Tool, are generated.</span></span> <span data-ttu-id="57c60-147">I file CSV devono essere utilizzati come input (nella stessa cartella) durante la configurazione del servizio informazioni percorso (LIS) con lo script LisConfiguration.ps1.</span><span class="sxs-lookup"><span data-stu-id="57c60-147">The CSV files are to be used as inputs (in the same folder) when configuring Location Information service (LIS) with the LisConfiguration.ps1 script.</span></span> <span data-ttu-id="57c60-148">Spostare il file di Locations0.xml generato nella stessa cartella in cui si trova l'eseguibile dello strumento di stress e prestazioni di Lync Server 2013 (LyncPerfTool.exe), che eseguirà gli scenari del profilo percorso (dial plan).</span><span class="sxs-lookup"><span data-stu-id="57c60-148">Move the generated Locations0.xml file to the same folder as the Lync Server 2013 Stress and Performance Tool executable (LyncPerfTool.exe), which will run location profile (dial plan) scenarios.</span></span>

</div>

<div>

## <a name="creating-enabling-configuring-and-disabling-users"></a><span data-ttu-id="57c60-149">Creazione, abilitazione, configurazione e disabilitazione degli utenti</span><span class="sxs-lookup"><span data-stu-id="57c60-149">Creating, Enabling, Configuring and Disabling Users</span></span>

<span data-ttu-id="57c60-150">Prima di eseguire gli script seguenti, è consigliabile creare tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="57c60-150">You should create all your users before running the following scripts.</span></span> <span data-ttu-id="57c60-151">Seguire le istruzioni riportate in [creare utenti e contatti](create-users-and-contacts.md) per creare gli utenti.</span><span class="sxs-lookup"><span data-stu-id="57c60-151">Follow the instructions in [Create Users and Contacts](create-users-and-contacts.md) to create users.</span></span> <span data-ttu-id="57c60-152">Per informazioni dettagliate, vedere la documentazione relativa ai cmdlet di Lync Server 2013 per i cmdlet [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)), [Set-CsUser](https://technet.microsoft.com/library/gg398510\(v=ocs.15\))e [Disable-CsUser](https://technet.microsoft.com/library/gg398747\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="57c60-152">For details, see the Lync Server 2013 cmdlet documentation for the [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)), [Set-CsUser](https://technet.microsoft.com/library/gg398510\(v=ocs.15\)), and [Disable-CsUser](https://technet.microsoft.com/library/gg398747\(v=ocs.15\)) cmdlets.</span></span>

</div>

<div>

## <a name="configuring-response-group-application"></a><span data-ttu-id="57c60-153">Configurazione dell'applicazione Response Group</span><span class="sxs-lookup"><span data-stu-id="57c60-153">Configuring Response Group application</span></span>

<span data-ttu-id="57c60-154">Vedere l'esempio ResponseGroupConfiguration.ps1.</span><span class="sxs-lookup"><span data-stu-id="57c60-154">See the example ResponseGroupConfiguration.ps1.</span></span> <span data-ttu-id="57c60-155">Per informazioni dettagliate, vedere la documentazione di Lync Server 2013 e la guida per i cmdlet per le [applicazioni di Response Group in Lync server 2013](https://technet.microsoft.com/library/gg415654\(v=ocs.15\)). Per esaminare la configurazione dell'applicazione Response Group, vedere `https://<poolfqdn>/RgsConfig/` , come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="57c60-155">For details, see the Lync Server 2013 documentation and the cmdlet Help for [Response Group application cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg415654\(v=ocs.15\)).To review the Response Group application configuration, see `https://<poolfqdn>/RgsConfig/`, as shown in the following figure.</span></span>

<span data-ttu-id="57c60-156">![Strumento di configurazione di Response Group.](images/JJ945610.480a9440-2283-4533-98f8-86daaab4781c(OCS.15).jpg "Strumento di configurazione di Response Group.")</span><span class="sxs-lookup"><span data-stu-id="57c60-156">![The Response Group Configuration Tool.](images/JJ945610.480a9440-2283-4533-98f8-86daaab4781c(OCS.15).jpg "The Response Group Configuration Tool.")</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

