---
title: Case study su Teams per Contoso
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: Case study vocale di Teams per multi-national corporation
appliesto:
- Microsoft Teams
ms.openlocfilehash: a6ee08fa7bdeb1ded6bda384115a08048021cb67
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918732"
---
# <a name="contoso-case-study-auto-attendants-and-call-queues"></a><span data-ttu-id="95511-103">Case study contoso: Operatori automatici e code di chiamata</span><span class="sxs-lookup"><span data-stu-id="95511-103">Contoso case study: Auto attendants and call queues</span></span>

<span data-ttu-id="95511-104">Contoso aveva familiarità con gli operatori automatici e le code di chiamata dalla distribuzione skype for Business locale.</span><span class="sxs-lookup"><span data-stu-id="95511-104">Contoso was familiar with auto attendants and call queues from their on-premises Skype for Business deployment.</span></span> <span data-ttu-id="95511-105">Per comprendere come impostare gli operatori automatici cloud e le code di chiamata, hanno esaminato il piano per gli operatori automatici di Teams e [le code di chiamata.](plan-auto-attendant-call-queue.md)</span><span class="sxs-lookup"><span data-stu-id="95511-105">To understand how to set up Cloud auto attendants and call queues, they reviewed [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md).</span></span>

## <a name="requirements-depending-on-site-type"></a><span data-ttu-id="95511-106">Requisiti a seconda del tipo di sito</span><span class="sxs-lookup"><span data-stu-id="95511-106">Requirements depending on site type</span></span>

<span data-ttu-id="95511-107">A seconda del tipo di sito, Contoso ha le esigenze seguenti:</span><span class="sxs-lookup"><span data-stu-id="95511-107">Depending on the site type, Contoso had the following needs:</span></span>

- <span data-ttu-id="95511-108">Tipo di sito A: sistemi di telefonia legacy tradizionali</span><span class="sxs-lookup"><span data-stu-id="95511-108">Site Type A: Traditional legacy telephony systems</span></span> 

  <span data-ttu-id="95511-109">Tipo di sito A necessario per mantenere lo stesso numero di telefono associato all'addetto alla reception come numero per gli operatori automatici.</span><span class="sxs-lookup"><span data-stu-id="95511-109">Site Type A needed to keep the same phone number associated with the receptionist as the number for their auto attendants.</span></span> <span data-ttu-id="95511-110">I reparti principali di ognuno di questi siti hanno le proprie code di chiamata da instradare ai membri del team.</span><span class="sxs-lookup"><span data-stu-id="95511-110">The key departments for each of these sites would have their own call queues that would route to team members.</span></span> <span data-ttu-id="95511-111">Esisteva una combinazione di siti che usava Sistema telefonico con Instradamento diretto e Sistema telefonico con Piani per chiamate.</span><span class="sxs-lookup"><span data-stu-id="95511-111">There was a mixture of sites that used Phone System with Direct Routing and Phone System with Calling Plans.</span></span>  

- <span data-ttu-id="95511-112">Tipo di sito B: Skype for Business VoIP aziendale</span><span class="sxs-lookup"><span data-stu-id="95511-112">Site Type B: Skype for Business Enterprise Voice</span></span> 

  <span data-ttu-id="95511-113">Il tipo di sito B aveva già operatori automatici e code di chiamata che dovevano eseguire la migrazione a Teams.</span><span class="sxs-lookup"><span data-stu-id="95511-113">Site Type B had existing auto attendants and call queues that needed to migrate to Teams.</span></span> <span data-ttu-id="95511-114">Contoso deve mantenere i numeri di telefono associati agli operatori automatici.</span><span class="sxs-lookup"><span data-stu-id="95511-114">Contoso needed to keep the phone numbers associated with the auto attendants.</span></span> <span data-ttu-id="95511-115">Contoso ha spostato la maggior parte di questi siti nel Sistema telefonico con Piani per chiamate.</span><span class="sxs-lookup"><span data-stu-id="95511-115">Contoso moved the majority of these sites to Phone System with Calling Plans.</span></span> <span data-ttu-id="95511-116">Tuttavia, nelle poche località in cui i Piani per chiamate non erano disponibili, Contoso ha spostato questi siti in una configurazione di routing diretto.</span><span class="sxs-lookup"><span data-stu-id="95511-116">However, in the few locations where Calling Plans was not available, Contoso moved these sites to a Direct Routing configuration.</span></span>  

- <span data-ttu-id="95511-117">Tipo di sito C: Skype for Business VoIP aziendale & sistema di telefonia legacy tradizionale</span><span class="sxs-lookup"><span data-stu-id="95511-117">Site Type C: Skype for Business Enterprise Voice & traditional legacy telephony system</span></span> 

  <span data-ttu-id="95511-118">Nel tipo di sito C erano presenti operatori automatici presenti nel sistema di telefonia legacy tradizionale.</span><span class="sxs-lookup"><span data-stu-id="95511-118">Site Type C had existing auto attendants that resided in the traditional legacy telephony system.</span></span> <span data-ttu-id="95511-119">Le decisioni e le configurazioni per il sito sono uguali al tipo di sito A.</span><span class="sxs-lookup"><span data-stu-id="95511-119">The decisions and configurations for this site were the same as Site Type A.</span></span>   

- <span data-ttu-id="95511-120">Per tutti i tipi di sito, Contoso ha posto le domande seguenti:</span><span class="sxs-lookup"><span data-stu-id="95511-120">For all site types, Contoso asked the following questions:</span></span>

  - <span data-ttu-id="95511-121">D: Verranno utilizzati numeri nuovi o esistenti?</span><span class="sxs-lookup"><span data-stu-id="95511-121">Q: Will we use new or existing numbers?</span></span> 
    <span data-ttu-id="95511-122">A: Contoso ha deciso di utilizzare numeri di telefono esistenti da assegnare all'account di servizio per l'operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="95511-122">A: Contoso decided to use existing phone numbers to be assigned to the service account for the auto attendant.</span></span> 

  - <span data-ttu-id="95511-123">D: Quando sarà disponibile l'operatore automatico ad accettare le chiamate in arrivo?</span><span class="sxs-lookup"><span data-stu-id="95511-123">Q: When will the auto attendant be available to accept incoming calls?</span></span> 
    <span data-ttu-id="95511-124">A: Contoso ha deciso di impostare l'orario di ufficio e fare in modo che le chiamate ricevute dopo l'orario di ufficio vengono reindirizzate a un operatore automatico "non in orario di ufficio".</span><span class="sxs-lookup"><span data-stu-id="95511-124">A: Contoso decided to set business hours and have calls received after business hours redirected to an "after-hours" auto attendant.</span></span>  

  - <span data-ttu-id="95511-125">D: In che modo le chiamate verranno instradati ai membri in una coda di chiamata: instradamento con operatore, seriale o round robin?</span><span class="sxs-lookup"><span data-stu-id="95511-125">Q: How will the calls be routed to members in a call queue: attendant, serial, or round robin routing?</span></span> 
    <span data-ttu-id="95511-126">A: Contoso ha deciso di usare il routing di Attendant,</span><span class="sxs-lookup"><span data-stu-id="95511-126">A: Contoso decided to use Attendant routing,</span></span> 

  - <span data-ttu-id="95511-127">D: Come si determina quando un utente dovrebbe o non dovrebbe ricevere una chiamata?</span><span class="sxs-lookup"><span data-stu-id="95511-127">Q: How will we determine when a user should or should not get a call?</span></span> 
    <span data-ttu-id="95511-128">A: Contoso ha deciso di usare le opzioni di gestione delle chiamate per determinare se l'agente è disponibile: routing basato sulla presenza.</span><span class="sxs-lookup"><span data-stu-id="95511-128">A: Contoso decided to use call handling options to determine if the agent is available: presence-based routing.</span></span> 


## <a name="configuration"></a><span data-ttu-id="95511-129">Configurazione</span><span class="sxs-lookup"><span data-stu-id="95511-129">Configuration</span></span>

<span data-ttu-id="95511-130">La procedura per impostare un operatore automatico e una coda di chiamata è illustrata in [Gestisci account risorse:](manage-resource-accounts.md)</span><span class="sxs-lookup"><span data-stu-id="95511-130">The steps to set up an auto attendant and a call queue include the following outlined in [Manage resource accounts](manage-resource-accounts.md):</span></span> 

1. <span data-ttu-id="95511-131">Ottenere un numero di servizio.</span><span class="sxs-lookup"><span data-stu-id="95511-131">Obtain a service number.</span></span> 

2. <span data-ttu-id="95511-132">Ottenere una licenza Sistema telefonico gratuito - Utente virtuale o Sistema telefonico a pagamento da usare con l'account delle risorse o con una licenza Sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="95511-132">Obtain a free Phone System - Virtual User license or a paid Phone System license to use with the resource account or a Phone System license.</span></span>

3. <span data-ttu-id="95511-133">Creare l'account della risorsa.</span><span class="sxs-lookup"><span data-stu-id="95511-133">Create the resource account.</span></span> <span data-ttu-id="95511-134">Per avere un account delle risorse associato, è necessario un operatore automatico o una coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="95511-134">An auto attendant or call queue is required to have an associated resource account.</span></span> 

4. <span data-ttu-id="95511-135">Assegnare la licenza Sistema telefonico o Sistema telefonico - Utente virtuale all'account delle risorse.</span><span class="sxs-lookup"><span data-stu-id="95511-135">Assign the Phone System or a Phone System - Virtual user license to the resource account.</span></span> <span data-ttu-id="95511-136">Per ulteriori informazioni, consulta [Sistema telefonico Microsoft 365 - Licenza Utente virtuale.](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/virtual-user)</span><span class="sxs-lookup"><span data-stu-id="95511-136">For more information, see [Microsoft 365 Phone System – Virtual User license](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/virtual-user).</span></span>

5. <span data-ttu-id="95511-137">Assegnare un numero di telefono di servizio all'account delle risorse a cui sono state assegnate licenze.</span><span class="sxs-lookup"><span data-stu-id="95511-137">Assign a service phone number to the resource account you assigned licenses to.</span></span> 

6. <span data-ttu-id="95511-138">Creare una coda di chiamata o un operatore automatico del Sistema telefonico</span><span class="sxs-lookup"><span data-stu-id="95511-138">Create a Phone System call queue or auto attendant</span></span> 

7. <span data-ttu-id="95511-139">Collega l'account della risorsa a una coda di chiamata o a un operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="95511-139">Link the resource account with a call queue or auto attendant.</span></span> 


### <a name="sites-with-phone-system-with-direct-routing"></a><span data-ttu-id="95511-140">Siti con Sistema telefonico con instradamento diretto</span><span class="sxs-lookup"><span data-stu-id="95511-140">Sites with Phone System with Direct routing</span></span> 

<span data-ttu-id="95511-141">Contoso ha dovuto impostare il numero di telefono fornito dal gestore locale come numero di servizio in Office 365.</span><span class="sxs-lookup"><span data-stu-id="95511-141">Contoso had to set up the phone number provided by the local carrier as the service number in Office 365.</span></span> 

- <span data-ttu-id="95511-142">Per impostare un numero di telefono disponibile tramite instradamento diretto, Contoso ha seguito le istruzioni disponibili in [Gestisci account risorse.](manage-resource-accounts.md)</span><span class="sxs-lookup"><span data-stu-id="95511-142">To set up a phone number available through Direct Routing, Contoso followed the instructions located in [Manage Resource Accounts](manage-resource-accounts.md).</span></span> <span data-ttu-id="95511-143">Poiché Office 365 non è a conoscenza dei numeri di telefono locali, Contoso ha usato PowerShell per completare la configurazione.</span><span class="sxs-lookup"><span data-stu-id="95511-143">Because Office 365 is not aware of the on-premises phone numbers, Contoso used PowerShell to complete the setup.</span></span>   

- <span data-ttu-id="95511-144">Per configurare l'operatore automatico Cloud, Contoso ha seguito i passaggi descritti in [Configurare un operatore](create-a-phone-system-auto-attendant.md)automatico Cloud.</span><span class="sxs-lookup"><span data-stu-id="95511-144">To configure the Cloud auto attendant, Contoso followed the steps outlined in [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md).</span></span> 

- <span data-ttu-id="95511-145">Per impostare una coda di chiamata Cloud, Contoso ha seguito i passaggi descritti in [Creare una coda di chiamata Cloud.](create-a-phone-system-call-queue.md)</span><span class="sxs-lookup"><span data-stu-id="95511-145">To set up a Cloud call queue, Contoso followed the steps outlined in [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>  


### <a name="sites-with-phone-system-with-calling-plan"></a><span data-ttu-id="95511-146">Siti con Sistema telefonico con piano per chiamate</span><span class="sxs-lookup"><span data-stu-id="95511-146">Sites with Phone System with Calling plan</span></span>

<span data-ttu-id="95511-147">Contoso ha dovuto eseguire il portabilità del numero di telefono usato per gli operatori VoIP aziendale Skype for Business al Sistema telefonico Office 365.</span><span class="sxs-lookup"><span data-stu-id="95511-147">Contoso had to port the phone number that was used for Skype for Business Enterprise Voice auto attendants to Office 365 Phone System.</span></span> <span data-ttu-id="95511-148">Ciò consentiva di assegnare lo stesso numero come numero di servizio per l'uso come operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="95511-148">This allowed the same number to be assigned as a service number for use as an auto attendant.</span></span> 

- <span data-ttu-id="95511-149">Per trasferire il numero di telefono, Contoso ha seguito le istruzioni in Trasferisci numeri di telefono in [Teams](https://docs.microsoft.com/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams) e ha ottenuto altre indicazioni su Gestione dei numeri di telefono [per l'organizzazione.](https://docs.microsoft.com/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)</span><span class="sxs-lookup"><span data-stu-id="95511-149">To port the phone number, Contoso followed the instructions in [Transfer phone numbers to Teams](https://docs.microsoft.com/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams) and obtained additional guidance at [Manage phone numbers for your organization](https://docs.microsoft.com/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization).</span></span>

- <span data-ttu-id="95511-150">Per configurare un operatore automatico Cloud, Contoso ha seguito i passaggi descritti in [Configurare un operatore](create-a-phone-system-auto-attendant.md)automatico Cloud.</span><span class="sxs-lookup"><span data-stu-id="95511-150">To configure a Cloud auto attendant, Contoso followed the steps outlined in [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md).</span></span>

-  <span data-ttu-id="95511-151">Per impostare una coda di chiamata Cloud, Contoso ha seguito i passaggi descritti in [Creare una coda di chiamata Cloud.](create-a-phone-system-call-queue.md)</span><span class="sxs-lookup"><span data-stu-id="95511-151">To set up a Cloud call queue, Contoso followed the steps outlined in [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>  

 