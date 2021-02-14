---
title: Configurazione dei criteri per lo strumento Skype for Business Server 2015 Stress and Performance
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 11/11/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7e1435e2-d073-4265-8067-ebcb5bf28835
description: Configurazione dei criteri per skype for Business Server 2015 Stress and Performance Tool.
ms.openlocfilehash: bb049d5740d74e5ebeacd8a21d00e2644da61a7c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815036"
---
# <a name="configuring-policies-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="eb861-103">Configurazione dei criteri per lo strumento Skype for Business Server 2015 Stress and Performance</span><span class="sxs-lookup"><span data-stu-id="eb861-103">Configuring policies for the Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="eb861-104">Configurazione dei criteri per skype for Business Server 2015 Stress and Performance Tool.</span><span class="sxs-lookup"><span data-stu-id="eb861-104">Policy configuration for Skype for Business Server 2015 Stress and Performance Tool.</span></span>
  
<span data-ttu-id="eb861-105">Esistono diversi criteri e altre aree che è possibile configurare in Skype for Business Server 2015, prima di eseguire lo strumento Stress and Performance:</span><span class="sxs-lookup"><span data-stu-id="eb861-105">There are several policies and other areas that you can configure in Skype for Business Server 2015, prior to running the Stress and Performance Tool:</span></span>
  
- [<span data-ttu-id="eb861-106">Criteri di archiviazione</span><span class="sxs-lookup"><span data-stu-id="eb861-106">Archiving policy</span></span>](configuring-policies.md#ArchivingPolicy)
    
- [<span data-ttu-id="eb861-107">Criteri conferenza</span><span class="sxs-lookup"><span data-stu-id="eb861-107">Conferencing policy</span></span>](configuring-policies.md#ConferencingPolicy)
    
- [<span data-ttu-id="eb861-108">Criteri contatti</span><span class="sxs-lookup"><span data-stu-id="eb861-108">Contacts policy</span></span>](configuring-policies.md#ContactsPolicy)
    
- [<span data-ttu-id="eb861-109">Criteri di federazione</span><span class="sxs-lookup"><span data-stu-id="eb861-109">Federation policy</span></span>](configuring-policies.md#FederationPolicy)
    
- [<span data-ttu-id="eb861-110">Criteri controllo di ammissione di chiamata</span><span class="sxs-lookup"><span data-stu-id="eb861-110">Call Admission Control policy</span></span>](configuring-policies.md#CACPolicy)
    
- [<span data-ttu-id="eb861-111">Regole di routing vocale</span><span class="sxs-lookup"><span data-stu-id="eb861-111">Voice Routing rules</span></span>](configuring-policies.md#VoiceRoutingRules)
    
- [<span data-ttu-id="eb861-112">Applicazione Operatore conferenza</span><span class="sxs-lookup"><span data-stu-id="eb861-112">Conference Attendant application</span></span>](configuring-policies.md#ConfAttendantApp)
    
- [<span data-ttu-id="eb861-113">Servizio Parcheggio di chiamata del server</span><span class="sxs-lookup"><span data-stu-id="eb861-113">Server Call Park service</span></span>](configuring-policies.md#ServerCallParkServ)
    
- [<span data-ttu-id="eb861-114">Chiamate di emergenza</span><span class="sxs-lookup"><span data-stu-id="eb861-114">Emergency calls</span></span>](configuring-policies.md#EmergencyCalls)
    
- [<span data-ttu-id="eb861-115">Configurazione dell'applicazione Response Group</span><span class="sxs-lookup"><span data-stu-id="eb861-115">Configuring Response Group application</span></span>](configuring-policies.md#ConfigResponseGroupApp)
    
## <a name="archiving-policy"></a><span data-ttu-id="eb861-116">Criteri di archiviazione</span><span class="sxs-lookup"><span data-stu-id="eb861-116">Archiving policy</span></span>
<span data-ttu-id="eb861-117"><a name="ArchivingPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="eb861-117"><a name="ArchivingPolicy"> </a></span></span>

<span data-ttu-id="eb861-118">Se si dispone di un server di archiviazione distribuito nella topologia di Skype for Business Server, è possibile esaminare lo script ArchivingPolicy.ps1.</span><span class="sxs-lookup"><span data-stu-id="eb861-118">If you have an Archiving server deployed in your Skype for Business Server topology, you can look at the ArchivingPolicy.ps1 script.</span></span> <span data-ttu-id="eb861-119">Per ulteriore assistenza, consultare i cmdlet di archiviazione e Web Conferencing.</span><span class="sxs-lookup"><span data-stu-id="eb861-119">If you need further assistance, check out the Archiving and Web Conferencing cmdlets.</span></span>
  
## <a name="conferencing-policy"></a><span data-ttu-id="eb861-120">Criteri conferenza</span><span class="sxs-lookup"><span data-stu-id="eb861-120">Conferencing policy</span></span>
<span data-ttu-id="eb861-121"><a name="ConferencingPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="eb861-121"><a name="ConferencingPolicy"> </a></span></span>

<span data-ttu-id="eb861-122">Per le conferenze, è stato creato lo script MeetingPolicy.ps1 conferenza.</span><span class="sxs-lookup"><span data-stu-id="eb861-122">For conferencing, we have the MeetingPolicy.ps1 script.</span></span> <span data-ttu-id="eb861-123">Se è necessaria ulteriore assistenza, consultare i cmdlet di Web Conferencing.</span><span class="sxs-lookup"><span data-stu-id="eb861-123">If you need further assistance, check out the Web Conferencing cmdlets.</span></span>
  
## <a name="contacts-policy"></a><span data-ttu-id="eb861-124">Criteri contatti</span><span class="sxs-lookup"><span data-stu-id="eb861-124">Contacts policy</span></span>
<span data-ttu-id="eb861-125"><a name="ContactsPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="eb861-125"><a name="ContactsPolicy"> </a></span></span>

<span data-ttu-id="eb861-126">ContactsPolicy.ps1 script sarà l'esempio che dovrai esaminare.</span><span class="sxs-lookup"><span data-stu-id="eb861-126">ContactsPolicy.ps1 script will be the sample you'll need to review.</span></span> <span data-ttu-id="eb861-127">I cmdlet per la messaggistica istantanea e la presenza sono utili se sono necessari ulteriori riferimenti.</span><span class="sxs-lookup"><span data-stu-id="eb861-127">The IM and Presence cmdlets will help if you need further references.</span></span>
  
## <a name="federation-policy"></a><span data-ttu-id="eb861-128">Criteri di federazione</span><span class="sxs-lookup"><span data-stu-id="eb861-128">Federation policy</span></span>
<span data-ttu-id="eb861-129"><a name="FederationPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="eb861-129"><a name="FederationPolicy"> </a></span></span>

<span data-ttu-id="eb861-130">Lo script di esempio per la federazione è FederationPolicy.ps1.</span><span class="sxs-lookup"><span data-stu-id="eb861-130">The sample script for federation is FederationPolicy.ps1.</span></span> <span data-ttu-id="eb861-131">I cmdlet da esaminare, se sono necessarie ulteriori informazioni, saranno server perimetrale, federazione e accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="eb861-131">The cmdlets to review, if you need further insight, will be Edge Server, federation, and external access.</span></span>
  
## <a name="call-admission-control-policy"></a><span data-ttu-id="eb861-132">Criteri controllo di ammissione di chiamata</span><span class="sxs-lookup"><span data-stu-id="eb861-132">Call Admission Control policy</span></span>
<span data-ttu-id="eb861-133"><a name="CACPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="eb861-133"><a name="CACPolicy"> </a></span></span>

<span data-ttu-id="eb861-134">È possibile fare riferimento BandwidthPolicy.ps1 per questo criterio.</span><span class="sxs-lookup"><span data-stu-id="eb861-134">You can reference BandwidthPolicy.ps1 for this policy.</span></span> <span data-ttu-id="eb861-135">I cmdlet per il controllo di ammissione di chiamata diverranno inoltre disponibili ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="eb861-135">The Call Admission Control cmdlets will have further information as well.</span></span>
  
## <a name="voice-routing-rules"></a><span data-ttu-id="eb861-136">Regole di routing vocale</span><span class="sxs-lookup"><span data-stu-id="eb861-136">Voice Routing rules</span></span>
<span data-ttu-id="eb861-137"><a name="VoiceRoutingRules"> </a></span><span class="sxs-lookup"><span data-stu-id="eb861-137"><a name="VoiceRoutingRules"> </a></span></span>

<span data-ttu-id="eb861-138">Sarà necessario lo script di RoutingRules.ps1 di esempio per il routing vocale.</span><span class="sxs-lookup"><span data-stu-id="eb861-138">You'll need the RoutingRules.ps1 sample script for Voice Routing.</span></span> <span data-ttu-id="eb861-139">Quando configuri queste regole, prendi nota del contesto telefonico (ovvero /Location Profile o /SimpleName) e dei codici delle aree interne/esterne, in modo da poterle specificare durante la creazione degli utenti.</span><span class="sxs-lookup"><span data-stu-id="eb861-139">When you're configuring these rules, take note of the phone context (that is, /Location Profile or /SimpleName) and Internal/External Area Codes, so that you can specify them when creating users.</span></span> <span data-ttu-id="eb861-140">Saranno necessari anche durante la configurazione di LyncPerfTool (in particolare per PSTN-UC e UC-PSTN).</span><span class="sxs-lookup"><span data-stu-id="eb861-140">You'll also need them during LyncPerfTool configuration (specifically for PSTN-UC and UC-PSTN).</span></span>
  
<span data-ttu-id="eb861-141">Ad esempio, il parametro SimpleName nella chiamata al cmdlet **New-CsDialPlan** nell'esempio RoutingRules.ps1 deve essere utilizzato per il valore LocationProfile nella figura seguente di UserProfileGenerator.exe:</span><span class="sxs-lookup"><span data-stu-id="eb861-141">For example, the SimpleName parameter in the call to the **New-CsDialPlan** cmdlet in the RoutingRules.ps1 example should be used for the LocationProfile value in the following figure of UserProfileGenerator.exe:</span></span>
  
![Skype for Business load configuration tool, voice scenarios tab, Advanced settings for Conversations.](../../media/59f42e4e-8f1e-4d43-9ae2-9e6026191951.png)
  
<span data-ttu-id="eb861-143">Per informazioni dettagliate, è possibile esaminare VoIP aziendale cmdlet.</span><span class="sxs-lookup"><span data-stu-id="eb861-143">For details, you can review the Enterprise Voice cmdlets.</span></span>
  
## <a name="conference-attendant-application"></a><span data-ttu-id="eb861-144">Applicazione Operatore conferenza</span><span class="sxs-lookup"><span data-stu-id="eb861-144">Conference Attendant application</span></span>
<span data-ttu-id="eb861-145"><a name="ConfAttendantApp"> </a></span><span class="sxs-lookup"><span data-stu-id="eb861-145"><a name="ConfAttendantApp"> </a></span></span>

<span data-ttu-id="eb861-146">Esaminare innanzitutto lo script ConferenceAutoAttendantConfiguration.ps1 seguente.</span><span class="sxs-lookup"><span data-stu-id="eb861-146">First review the ConferenceAutoAttendantConfiguration.ps1 script.</span></span> <span data-ttu-id="eb861-147">È necessario prendere nota del numero di telefono ConferencingAutoAttendant (1121111111 per impostazione predefinita), in modo da poterlo immettere nello strumento di configurazione LyncPerfTool per la generazione della configurazione, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="eb861-147">You'll want to take note of the ConferencingAutoAttendant phone number (1121111111 by default), so that you can enter it into the LyncPerfTool configuration tool for configuration generation, as below:</span></span>
  
![Scheda Scenari vocali che mostra il livello di carico di conferenza e il numero di telefono.](../../media/a3ea5fc0-8b3d-4842-b809-f137f470dbdc.png)
  
<span data-ttu-id="eb861-149">Ulteriori dettagli sono presenti nei cmdlet per conferenze telefoniche e conferenze telefoniche con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="eb861-149">You'll find more details in the Conferencing and Dial-in Conferencing cmdlets.</span></span>
  
## <a name="server-call-park-service"></a><span data-ttu-id="eb861-150">Servizio Parcheggio di chiamata del server</span><span class="sxs-lookup"><span data-stu-id="eb861-150">Server Call Park service</span></span>
<span data-ttu-id="eb861-151"><a name="ServerCallParkServ"> </a></span><span class="sxs-lookup"><span data-stu-id="eb861-151"><a name="ServerCallParkServ"> </a></span></span>

<span data-ttu-id="eb861-152">Questa funzionalità è effettivamente disabilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="eb861-152">This is actually disabled by default.</span></span> <span data-ttu-id="eb861-153">Se è necessario testare CallParkConfiguration.ps1 script di esempio, è possibile esaminare lo script di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="eb861-153">You can review the CallParkConfiguration.ps1 sample script if you need to test this.</span></span> <span data-ttu-id="eb861-154">Inoltre, consultare i cmdlet dell'applicazione Parcheggio di chiamata in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="eb861-154">Additionally, check out the Call Park Application cmdlets as needed.</span></span>
  
## <a name="emergency-calls"></a><span data-ttu-id="eb861-155">Chiamate di emergenza</span><span class="sxs-lookup"><span data-stu-id="eb861-155">Emergency calls</span></span>
<span data-ttu-id="eb861-156"><a name="EmergencyCalls"> </a></span><span class="sxs-lookup"><span data-stu-id="eb861-156"><a name="EmergencyCalls"> </a></span></span>

<span data-ttu-id="eb861-157">Dovrai eseguire i passaggi seguenti per configurare il test di stress e prestazioni per le chiamate di emergenza:</span><span class="sxs-lookup"><span data-stu-id="eb861-157">You'll need to perform the following steps to configure stress and performance testing for emergency calls:</span></span>
  
1. <span data-ttu-id="eb861-158">Configurare una route vocale per le chiamate di emergenza.</span><span class="sxs-lookup"><span data-stu-id="eb861-158">Set up a voice route for emergency calls.</span></span> <span data-ttu-id="eb861-159">È possibile utilizzare lo script RoutingRules.ps1 e controllare sotto il commento " **Route E911 to PSTN** " per un esempio di come configurare questa route vocale.</span><span class="sxs-lookup"><span data-stu-id="eb861-159">You can use the RoutingRules.ps1 script, and check under the comment " **Route E911 to PSTN** " for an example of how to set up this voice route.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="eb861-160">Il comando di esempio in RoutingRules.ps1 ha un formato numero che include il numero 119 anziché 911.</span><span class="sxs-lookup"><span data-stu-id="eb861-160">The example command in RoutingRules.ps1 has a number pattern that includes the number 119 rather than 911.</span></span> <span data-ttu-id="eb861-161">È consigliabile evitare di usare il 911 (o il numero di emergenza locale effettivo) per evitare chiamate accidentali agli operatori di emergenza locali durante i test di carico.</span><span class="sxs-lookup"><span data-stu-id="eb861-161">You should avoid using 911 (or your actual local emergency number) to prevent accidental calls to your local emergency operators during your load testing.</span></span> <span data-ttu-id="eb861-162">Tenere presente che questa configurazione è solo a scopo di simulazione.</span><span class="sxs-lookup"><span data-stu-id="eb861-162">Remember, this configuration is for simulation purposes only!</span></span> 
  
2. <span data-ttu-id="eb861-163">Configurare gli indirizzi compilando i valori nella scheda **Configurazione** servizio informazioni percorso in UserProvisioningTool, come illustrato nella figura seguente:</span><span class="sxs-lookup"><span data-stu-id="eb861-163">Configure addresses by filling in the values on the **Location Info Service Config** tab in the UserProvisioningTool, as shown in the following figure:</span></span>
    
     ![Strumento di provisioning degli utenti che mostra il numero di indirizzi, subnet, commutatori e porte.](../../media/ebe85a0c-750f-4301-97d4-d158a40ea98a.png)
  
3. <span data-ttu-id="eb861-165">Dopo aver immesso tutti gli elementi nello UserProvisioningTool, fare clic sul pulsante **Genera file di configurazione LIS.**</span><span class="sxs-lookup"><span data-stu-id="eb861-165">When you've entered everything into the UserProvisioningTool, click the **Generate LIS Config Files** button.</span></span>
    
4. <span data-ttu-id="eb861-166">Ora verranno generati file CSV per porte, subnet, commutatori e punti di accesso wireless (WAP), nonché un file XML per lo strumento Stress and Performance.</span><span class="sxs-lookup"><span data-stu-id="eb861-166">Now CSV files for ports, subnets, switches, and wireless access points (WAPs), as well as an XML file for the Stress and Performance tool will be generated.</span></span> <span data-ttu-id="eb861-167">È possibile utilizzare i file CSV per gli input durante la configurazione del servizio informazioni percorso (LIS) con lo script LisConfiguration.ps1 locale.</span><span class="sxs-lookup"><span data-stu-id="eb861-167">You can use the CSV files for inputs when configuring the Location Information service (LIS) with the LisConfiguration.ps1 script.</span></span> <span data-ttu-id="eb861-168">A tale scopo, dovrai spostare il file Locations0.xml nella stessa cartella del file eseguibile dello strumento Stress and Performance (LyncPerfTool.exe).</span><span class="sxs-lookup"><span data-stu-id="eb861-168">To do this, you'll need to move the Locations0.xml file to the same folder as the Stress and Performance Tool executable (LyncPerfTool.exe).</span></span> <span data-ttu-id="eb861-169">In questo modo sarà possibile eseguire scenari di profilo località (dial plan).</span><span class="sxs-lookup"><span data-stu-id="eb861-169">This will let you run location profile (dial plan) scenarios.</span></span>
    
## <a name="configuring-response-group-application"></a><span data-ttu-id="eb861-170">Configurazione dell'applicazione Response Group</span><span class="sxs-lookup"><span data-stu-id="eb861-170">Configuring Response Group application</span></span>
<span data-ttu-id="eb861-171"><a name="ConfigResponseGroupApp"> </a></span><span class="sxs-lookup"><span data-stu-id="eb861-171"><a name="ConfigResponseGroupApp"> </a></span></span>

<span data-ttu-id="eb861-172">Lo script di esempio è ResponseGroupConfiguration.ps1.</span><span class="sxs-lookup"><span data-stu-id="eb861-172">The sample script is ResponseGroupConfiguration.ps1.</span></span> <span data-ttu-id="eb861-173">Sono inoltre disponibili cmdlet per l'applicazione Response Group da esaminare per ulteriori dettagli sulla configurazione.</span><span class="sxs-lookup"><span data-stu-id="eb861-173">There are also Response Group application cmdlets to review for further configuration details.</span></span> <span data-ttu-id="eb861-174">Nel diagramma seguente vengono mostrati alcuni dei dettagli di configurazione:</span><span class="sxs-lookup"><span data-stu-id="eb861-174">The following diagram will show some of the configuration details:</span></span>
  
![Strumento di configurazione di Response Group che mostra i flussi di lavoro esistenti per i test.](../../media/e218a345-4813-4332-8cff-b48de05017ef.jpg)
  

