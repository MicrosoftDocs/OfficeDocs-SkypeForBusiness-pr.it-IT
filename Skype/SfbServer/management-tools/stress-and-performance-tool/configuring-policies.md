---
title: Configurazione dei criteri per lo strumento di stress e prestazioni di Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 11/11/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7e1435e2-d073-4265-8067-ebcb5bf28835
description: Configurazione dei criteri per lo strumento di stress e prestazioni di Skype for Business Server 2015.
ms.openlocfilehash: 5c8e4c296d06c736519a12da5b5e34c6f48e9ee2
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195085"
---
# <a name="configuring-policies-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="99300-103">Configurazione dei criteri per lo strumento di stress e prestazioni di Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="99300-103">Configuring policies for the Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="99300-104">Configurazione dei criteri per lo strumento di stress e prestazioni di Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="99300-104">Policy configuration for Skype for Business Server 2015 Stress and Performance Tool.</span></span>
  
<span data-ttu-id="99300-105">Esistono diversi criteri e altre aree che è possibile configurare in Skype for Business Server 2015, prima di eseguire lo strumento di stress e prestazioni:</span><span class="sxs-lookup"><span data-stu-id="99300-105">There are several policies and other areas that you can configure in Skype for Business Server 2015, prior to running the Stress and Performance Tool:</span></span>
  
- [<span data-ttu-id="99300-106">Criteri di archiviazione</span><span class="sxs-lookup"><span data-stu-id="99300-106">Archiving policy</span></span>](configuring-policies.md#ArchivingPolicy)
    
- [<span data-ttu-id="99300-107">Criteri di conferenza</span><span class="sxs-lookup"><span data-stu-id="99300-107">Conferencing policy</span></span>](configuring-policies.md#ConferencingPolicy)
    
- [<span data-ttu-id="99300-108">Criteri contatti</span><span class="sxs-lookup"><span data-stu-id="99300-108">Contacts policy</span></span>](configuring-policies.md#ContactsPolicy)
    
- [<span data-ttu-id="99300-109">Criteri federativi</span><span class="sxs-lookup"><span data-stu-id="99300-109">Federation policy</span></span>](configuring-policies.md#FederationPolicy)
    
- [<span data-ttu-id="99300-110">Criteri di controllo dell'ammissione alle chiamate</span><span class="sxs-lookup"><span data-stu-id="99300-110">Call Admission Control policy</span></span>](configuring-policies.md#CACPolicy)
    
- [<span data-ttu-id="99300-111">Regole di routing vocale</span><span class="sxs-lookup"><span data-stu-id="99300-111">Voice Routing rules</span></span>](configuring-policies.md#VoiceRoutingRules)
    
- [<span data-ttu-id="99300-112">Applicazione Operatore Conferenza</span><span class="sxs-lookup"><span data-stu-id="99300-112">Conference Attendant application</span></span>](configuring-policies.md#ConfAttendantApp)
    
- [<span data-ttu-id="99300-113">Servizio parcheggio di chiamata del server</span><span class="sxs-lookup"><span data-stu-id="99300-113">Server Call Park service</span></span>](configuring-policies.md#ServerCallParkServ)
    
- [<span data-ttu-id="99300-114">Chiamate di emergenza</span><span class="sxs-lookup"><span data-stu-id="99300-114">Emergency calls</span></span>](configuring-policies.md#EmergencyCalls)
    
- [<span data-ttu-id="99300-115">Configurazione dell'applicazione Response Group</span><span class="sxs-lookup"><span data-stu-id="99300-115">Configuring Response Group application</span></span>](configuring-policies.md#ConfigResponseGroupApp)
    
## <a name="archiving-policy"></a><span data-ttu-id="99300-116">Criteri di archiviazione</span><span class="sxs-lookup"><span data-stu-id="99300-116">Archiving policy</span></span>
<span data-ttu-id="99300-117"><a name="ArchivingPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="99300-117"></span></span>

<span data-ttu-id="99300-118">Se si dispone di un server di archiviazione distribuito nella topologia di Skype for Business Server, è possibile esaminare lo script ArchivingPolicy. ps1.</span><span class="sxs-lookup"><span data-stu-id="99300-118">If you have an Archiving server deployed in your Skype for Business Server topology, you can look at the ArchivingPolicy.ps1 script.</span></span> <span data-ttu-id="99300-119">Per ulteriori informazioni, vedere i cmdlet per l'archiviazione e la Web Conferencing.</span><span class="sxs-lookup"><span data-stu-id="99300-119">If you need further assistance, check out the Archiving and Web Conferencing cmdlets.</span></span>
  
## <a name="conferencing-policy"></a><span data-ttu-id="99300-120">Criteri di conferenza</span><span class="sxs-lookup"><span data-stu-id="99300-120">Conferencing policy</span></span>
<span data-ttu-id="99300-121"><a name="ConferencingPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="99300-121"></span></span>

<span data-ttu-id="99300-122">Per i servizi di conferenza abbiamo lo script MeetingPolicy. ps1.</span><span class="sxs-lookup"><span data-stu-id="99300-122">For conferencing, we have the MeetingPolicy.ps1 script.</span></span> <span data-ttu-id="99300-123">Se è necessaria ulteriore assistenza, vedere i cmdlet di Web Conferencing.</span><span class="sxs-lookup"><span data-stu-id="99300-123">If you need further assistance, check out the Web Conferencing cmdlets.</span></span>
  
## <a name="contacts-policy"></a><span data-ttu-id="99300-124">Criteri contatti</span><span class="sxs-lookup"><span data-stu-id="99300-124">Contacts policy</span></span>
<span data-ttu-id="99300-125"><a name="ContactsPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="99300-125"></span></span>

<span data-ttu-id="99300-126">Lo script ContactsPolicy. ps1 sarà l'esempio che è necessario rivedere.</span><span class="sxs-lookup"><span data-stu-id="99300-126">ContactsPolicy.ps1 script will be the sample you'll need to review.</span></span> <span data-ttu-id="99300-127">I cmdlet di messaggistica istantanea e presenza ti aiuteranno se hai bisogno di ulteriori riferimenti.</span><span class="sxs-lookup"><span data-stu-id="99300-127">The IM and Presence cmdlets will help if you need further references.</span></span>
  
## <a name="federation-policy"></a><span data-ttu-id="99300-128">Criteri federativi</span><span class="sxs-lookup"><span data-stu-id="99300-128">Federation policy</span></span>
<span data-ttu-id="99300-129"><a name="FederationPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="99300-129"></span></span>

<span data-ttu-id="99300-130">Lo script di esempio per la Federazione è FederationPolicy. ps1.</span><span class="sxs-lookup"><span data-stu-id="99300-130">The sample script for federation is FederationPolicy.ps1.</span></span> <span data-ttu-id="99300-131">I cmdlet da rivedere, se sono necessarie ulteriori informazioni, saranno Edge Server, Federation e Access esterno.</span><span class="sxs-lookup"><span data-stu-id="99300-131">The cmdlets to review, if you need further insight, will be Edge Server, federation, and external access.</span></span>
  
## <a name="call-admission-control-policy"></a><span data-ttu-id="99300-132">Criteri di controllo dell'ammissione alle chiamate</span><span class="sxs-lookup"><span data-stu-id="99300-132">Call Admission Control policy</span></span>
<span data-ttu-id="99300-133"><a name="CACPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="99300-133"></span></span>

<span data-ttu-id="99300-134">Puoi fare riferimento a BandwidthPolicy. ps1 per questo criterio.</span><span class="sxs-lookup"><span data-stu-id="99300-134">You can reference BandwidthPolicy.ps1 for this policy.</span></span> <span data-ttu-id="99300-135">I cmdlet per il controllo dell'ammissione alle chiamate avranno anche altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="99300-135">The Call Admission Control cmdlets will have further information as well.</span></span>
  
## <a name="voice-routing-rules"></a><span data-ttu-id="99300-136">Regole di routing vocale</span><span class="sxs-lookup"><span data-stu-id="99300-136">Voice Routing rules</span></span>
<span data-ttu-id="99300-137"><a name="VoiceRoutingRules"> </a></span><span class="sxs-lookup"><span data-stu-id="99300-137"></span></span>

<span data-ttu-id="99300-138">È necessario lo script di esempio RoutingRules. ps1 per il routing vocale.</span><span class="sxs-lookup"><span data-stu-id="99300-138">You'll need the RoutingRules.ps1 sample script for Voice Routing.</span></span> <span data-ttu-id="99300-139">Quando si configurano queste regole, prendere nota del contesto telefonico (ovvero/location profile o/SimpleName) e dei codici di area interni/esterni, in modo da poterli specificare quando si creano utenti.</span><span class="sxs-lookup"><span data-stu-id="99300-139">When you're configuring these rules, take note of the phone context (that is, /Location Profile or /SimpleName) and Internal/External Area Codes, so that you can specify them when creating users.</span></span> <span data-ttu-id="99300-140">Sarà inoltre necessario durante la configurazione di LyncPerfTool (in particolare per PSTN-UC e UC-PSTN).</span><span class="sxs-lookup"><span data-stu-id="99300-140">You'll also need them during LyncPerfTool configuration (specifically for PSTN-UC and UC-PSTN).</span></span>
  
<span data-ttu-id="99300-141">Ad esempio, il parametro SimpleName nella chiamata al cmdlet **New-CsDialPlan** nell'esempio RoutingRules. ps1 deve essere usato per il valore LocationProfile nella figura seguente di UserProfileGenerator. exe:</span><span class="sxs-lookup"><span data-stu-id="99300-141">For example, the SimpleName parameter in the call to the **New-CsDialPlan** cmdlet in the RoutingRules.ps1 example should be used for the LocationProfile value in the following figure of UserProfileGenerator.exe:</span></span>
  
![Strumento di configurazione del carico di Skype for business, scheda scenari vocali, impostazioni avanzate per le conversazioni.](../../media/59f42e4e-8f1e-4d43-9ae2-9e6026191951.png)
  
<span data-ttu-id="99300-143">Per informazioni dettagliate, è possibile esaminare i cmdlet di VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="99300-143">For details, you can review the Enterprise Voice cmdlets.</span></span>
  
## <a name="conference-attendant-application"></a><span data-ttu-id="99300-144">Applicazione Operatore Conferenza</span><span class="sxs-lookup"><span data-stu-id="99300-144">Conference Attendant application</span></span>
<span data-ttu-id="99300-145"><a name="ConfAttendantApp"> </a></span><span class="sxs-lookup"><span data-stu-id="99300-145"></span></span>

<span data-ttu-id="99300-146">Esaminare prima di tutto lo script ConferenceAutoAttendantConfiguration. ps1.</span><span class="sxs-lookup"><span data-stu-id="99300-146">First review the ConferenceAutoAttendantConfiguration.ps1 script.</span></span> <span data-ttu-id="99300-147">Si vorrà prendere nota del numero di telefono di ConferencingAutoAttendant (1121111111 per impostazione predefinita), in modo che sia possibile immetterlo nello strumento di configurazione di LyncPerfTool per la generazione di configurazione, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="99300-147">You'll want to take note of the ConferencingAutoAttendant phone number (1121111111 by default), so that you can enter it into the LyncPerfTool configuration tool for configuration generation, as below:</span></span>
  
![Scheda scenari vocali che mostra il livello di carico e il numero di telefono di conferenza.](../../media/a3ea5fc0-8b3d-4842-b809-f137f470dbdc.png)
  
<span data-ttu-id="99300-149">Sono disponibili altri dettagli nei cmdlet per i servizi di conferenza telefonica con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="99300-149">You'll find more details in the Conferencing and Dial-in Conferencing cmdlets.</span></span>
  
## <a name="server-call-park-service"></a><span data-ttu-id="99300-150">Servizio parcheggio di chiamata del server</span><span class="sxs-lookup"><span data-stu-id="99300-150">Server Call Park service</span></span>
<span data-ttu-id="99300-151"><a name="ServerCallParkServ"> </a></span><span class="sxs-lookup"><span data-stu-id="99300-151"></span></span>

<span data-ttu-id="99300-152">Questo è effettivamente disabilitato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="99300-152">This is actually disabled by default.</span></span> <span data-ttu-id="99300-153">Se necessario, è possibile verificare lo script di esempio CallParkConfiguration. ps1.</span><span class="sxs-lookup"><span data-stu-id="99300-153">You can review the CallParkConfiguration.ps1 sample script if you need to test this.</span></span> <span data-ttu-id="99300-154">Controlla inoltre i cmdlet delle applicazioni di Call Park in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="99300-154">Additionally, check out the Call Park Application cmdlets as needed.</span></span>
  
## <a name="emergency-calls"></a><span data-ttu-id="99300-155">Chiamate di emergenza</span><span class="sxs-lookup"><span data-stu-id="99300-155">Emergency calls</span></span>
<span data-ttu-id="99300-156"><a name="EmergencyCalls"> </a></span><span class="sxs-lookup"><span data-stu-id="99300-156"></span></span>

<span data-ttu-id="99300-157">È necessario eseguire la procedura seguente per configurare i test di stress e prestazioni per le chiamate di emergenza:</span><span class="sxs-lookup"><span data-stu-id="99300-157">You'll need to perform the following steps to configure stress and performance testing for emergency calls:</span></span>
  
1. <span data-ttu-id="99300-158">Configurare una route vocale per le chiamate di emergenza.</span><span class="sxs-lookup"><span data-stu-id="99300-158">Set up a voice route for emergency calls.</span></span> <span data-ttu-id="99300-159">Puoi usare lo script RoutingRules. ps1 e selezionare il commento " **Route E911 to PSTN** " per un esempio di come configurare questa route vocale.</span><span class="sxs-lookup"><span data-stu-id="99300-159">You can use the RoutingRules.ps1 script, and check under the comment " **Route E911 to PSTN** " for an example of how to set up this voice route.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="99300-160">Il comando di esempio in RoutingRules. ps1 contiene un modello di numero che include il numero 119 anziché 911.</span><span class="sxs-lookup"><span data-stu-id="99300-160">The example command in RoutingRules.ps1 has a number pattern that includes the number 119 rather than 911.</span></span> <span data-ttu-id="99300-161">È consigliabile evitare di usare 911 (o il numero di emergenza locale effettivo) per evitare chiamate accidentali agli operatori di emergenza locali durante il test di carico.</span><span class="sxs-lookup"><span data-stu-id="99300-161">You should avoid using 911 (or your actual local emergency number) to prevent accidental calls to your local emergency operators during your load testing.</span></span> <span data-ttu-id="99300-162">Tenere presente che questa configurazione è solo per scopi di simulazione.</span><span class="sxs-lookup"><span data-stu-id="99300-162">Remember, this configuration is for simulation purposes only!</span></span> 
  
2. <span data-ttu-id="99300-163">Configurare gli indirizzi compilando i valori della scheda **config del servizio informazioni sulla posizione** in UserProvisioningTool, come illustrato nella figura seguente:</span><span class="sxs-lookup"><span data-stu-id="99300-163">Configure addresses by filling in the values on the **Location Info Service Config** tab in the UserProvisioningTool, as shown in the following figure:</span></span>
    
     ![Strumento di provisioning degli utenti che mostra il numero di indirizzi, sottoreti, interruttori e porte.](../../media/ebe85a0c-750f-4301-97d4-d158a40ea98a.png)
  
3. <span data-ttu-id="99300-165">Dopo aver immesso tutto nel UserProvisioningTool, fare clic sul pulsante **genera file di configurazione LIS** .</span><span class="sxs-lookup"><span data-stu-id="99300-165">When you've entered everything into the UserProvisioningTool, click the **Generate LIS Config Files** button.</span></span>
    
4. <span data-ttu-id="99300-166">Ora vengono generati file CSV per porte, subnet, switch e punti di accesso wireless (WAP), oltre a un file XML per lo strumento stress e prestazioni.</span><span class="sxs-lookup"><span data-stu-id="99300-166">Now CSV files for ports, subnets, switches, and wireless access points (WAPs), as well as an XML file for the Stress and Performance tool will be generated.</span></span> <span data-ttu-id="99300-167">È possibile usare i file CSV per gli input quando si configura il servizio informazioni sulla posizione con lo script LisConfiguration. ps1.</span><span class="sxs-lookup"><span data-stu-id="99300-167">You can use the CSV files for inputs when configuring the Location Information service (LIS) with the LisConfiguration.ps1 script.</span></span> <span data-ttu-id="99300-168">A tale scopo, è necessario trasferire il file Locations0. XML nella stessa cartella dello strumento eseguibile di stress e prestazioni (LyncPerfTool. exe).</span><span class="sxs-lookup"><span data-stu-id="99300-168">To do this, you'll need to move the Locations0.xml file to the same folder as the Stress and Performance Tool executable (LyncPerfTool.exe).</span></span> <span data-ttu-id="99300-169">In questo modo si consente di eseguire gli scenari del profilo posizione (dial plan).</span><span class="sxs-lookup"><span data-stu-id="99300-169">This will let you run location profile (dial plan) scenarios.</span></span>
    
## <a name="configuring-response-group-application"></a><span data-ttu-id="99300-170">Configurazione dell'applicazione Response Group</span><span class="sxs-lookup"><span data-stu-id="99300-170">Configuring Response Group application</span></span>
<span data-ttu-id="99300-171"><a name="ConfigResponseGroupApp"> </a></span><span class="sxs-lookup"><span data-stu-id="99300-171"></span></span>

<span data-ttu-id="99300-172">Lo script di esempio è ResponseGroupConfiguration. ps1.</span><span class="sxs-lookup"><span data-stu-id="99300-172">The sample script is ResponseGroupConfiguration.ps1.</span></span> <span data-ttu-id="99300-173">Ci sono anche cmdlet di Response Group Application da rivedere per ulteriori dettagli sulla configurazione.</span><span class="sxs-lookup"><span data-stu-id="99300-173">There are also Response Group application cmdlets to review for further configuration details.</span></span> <span data-ttu-id="99300-174">Il diagramma seguente mostra alcuni dettagli della configurazione:</span><span class="sxs-lookup"><span data-stu-id="99300-174">The following diagram will show some of the configuration details:</span></span>
  
![Strumento di configurazione di Response Group che mostra i flussi di lavoro esistenti per i test.](../../media/e218a345-4813-4332-8cff-b48de05017ef.jpg)
  

