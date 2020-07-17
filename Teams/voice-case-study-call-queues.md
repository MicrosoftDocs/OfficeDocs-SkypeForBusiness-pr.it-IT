---
title: Case Study di teams Voice contoso
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
description: Case Study di teams Voice per società multinazionali
appliesto:
- Microsoft Teams
ms.openlocfilehash: 780d812b4e6e56b28b867ace14dbf1d5f6170302
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786023"
---
# <a name="contoso-case-study-auto-attendants-and-call-queues"></a><span data-ttu-id="1dd65-103">Case Study di Contoso: operatori automatici e code di chiamata</span><span class="sxs-lookup"><span data-stu-id="1dd65-103">Contoso case study: Auto attendants and call queues</span></span>

<span data-ttu-id="1dd65-104">Contoso ha familiarità con gli operatori automatici e le code di chiamata dalla distribuzione di Skype for business locale.</span><span class="sxs-lookup"><span data-stu-id="1dd65-104">Contoso was familiar with auto attendants and call queues from their on-premises Skype for Business deployment.</span></span> <span data-ttu-id="1dd65-105">Per informazioni su come configurare gli operatori automatici del cloud, hanno esaminato gli [operatori automatici del cloud](what-are-phone-system-auto-attendants.md) e l' [esempio Small Business-configurare l'esercitazione](tutorial-org-aa.yml)per l'operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="1dd65-105">To understand how to set up Cloud auto attendants, they reviewed [What are Cloud auto attendants?](what-are-phone-system-auto-attendants.md) and [Small business  example - Set up auto attendant tutorial](tutorial-org-aa.yml).</span></span> <span data-ttu-id="1dd65-106">Per informazioni sulle opzioni disponibili per la configurazione delle code di chiamata, contoso Recensito [Crea una coda di chiamata cloud](create-a-phone-system-call-queue.md).</span><span class="sxs-lookup"><span data-stu-id="1dd65-106">To learn about the options available to set up call queues, Contoso reviewed [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>  

## <a name="requirements-depending-on-site-type"></a><span data-ttu-id="1dd65-107">Requisiti a seconda del tipo di sito</span><span class="sxs-lookup"><span data-stu-id="1dd65-107">Requirements depending on site type</span></span>

<span data-ttu-id="1dd65-108">A seconda del tipo di sito, Contoso ha le seguenti esigenze:</span><span class="sxs-lookup"><span data-stu-id="1dd65-108">Depending on the site type, Contoso had the following needs:</span></span>

- <span data-ttu-id="1dd65-109">Tipo di sito A: sistemi di telefonia legacy tradizionali</span><span class="sxs-lookup"><span data-stu-id="1dd65-109">Site Type A: Traditional legacy telephony systems</span></span> 

  <span data-ttu-id="1dd65-110">Tipo di sito A necessario per conservare lo stesso numero di telefono associato al receptionist come numero per gli operatori automatici.</span><span class="sxs-lookup"><span data-stu-id="1dd65-110">Site Type A needed to keep the same phone number associated with the receptionist as the number for their auto attendants.</span></span> <span data-ttu-id="1dd65-111">I reparti chiave per ognuno di questi siti avrebbero le proprie code di chiamata che instradano i membri del team.</span><span class="sxs-lookup"><span data-stu-id="1dd65-111">The key departments for each of these sites would have their own call queues that would route to team members.</span></span> <span data-ttu-id="1dd65-112">C'era una combinazione di siti che usavano sistema telefonico con routing diretto e sistema telefonico con piani di chiamata.</span><span class="sxs-lookup"><span data-stu-id="1dd65-112">There was a mixture of sites that used Phone System with Direct Routing and Phone System with Calling Plans.</span></span>  

- <span data-ttu-id="1dd65-113">Tipo di sito B: Skype for Business Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="1dd65-113">Site Type B: Skype for Business Enterprise Voice</span></span> 

  <span data-ttu-id="1dd65-114">Il tipo di sito B aveva gli operatori automatici esistenti e le code di chiamata necessarie per eseguire la migrazione a teams.</span><span class="sxs-lookup"><span data-stu-id="1dd65-114">Site Type B had existing auto attendants and call queues that needed to migrate to Teams.</span></span> <span data-ttu-id="1dd65-115">Contoso necessario per conservare i numeri di telefono associati agli operatori automatici.</span><span class="sxs-lookup"><span data-stu-id="1dd65-115">Contoso needed to keep the phone numbers associated with the auto attendants.</span></span> <span data-ttu-id="1dd65-116">Contoso ha spostato la maggior parte di questi siti nel sistema telefonico con piani di chiamata.</span><span class="sxs-lookup"><span data-stu-id="1dd65-116">Contoso moved the majority of these sites to Phone System with Calling Plans.</span></span> <span data-ttu-id="1dd65-117">Tuttavia, nelle poche posizioni in cui i piani per le chiamate non erano disponibili, Contoso ha spostato questi siti in una configurazione di routing diretta.</span><span class="sxs-lookup"><span data-stu-id="1dd65-117">However, in the few locations where Calling Plans was not available, Contoso moved these sites to a Direct Routing configuration.</span></span>  

- <span data-ttu-id="1dd65-118">Tipo di sito C: Skype for Business Enterprise Voice & sistema tradizionale di telefonia legacy</span><span class="sxs-lookup"><span data-stu-id="1dd65-118">Site Type C: Skype for Business Enterprise Voice & traditional legacy telephony system</span></span> 

  <span data-ttu-id="1dd65-119">Il tipo di sito C aveva gli operatori automatici esistenti che risiedevano nel sistema tradizionale di telefonia legacy.</span><span class="sxs-lookup"><span data-stu-id="1dd65-119">Site Type C had existing auto attendants that resided in the traditional legacy telephony system.</span></span> <span data-ttu-id="1dd65-120">Le decisioni e le configurazioni per questo sito erano le stesse del tipo di sito A.</span><span class="sxs-lookup"><span data-stu-id="1dd65-120">The decisions and configurations for this site were the same as Site Type A.</span></span>   

- <span data-ttu-id="1dd65-121">Per tutti i tipi di sito, Contoso ha richiesto le seguenti domande:</span><span class="sxs-lookup"><span data-stu-id="1dd65-121">For all site types, Contoso asked the following questions:</span></span>

  - <span data-ttu-id="1dd65-122">D: useremo numeri nuovi o esistenti?</span><span class="sxs-lookup"><span data-stu-id="1dd65-122">Q: Will we use new or existing numbers?</span></span> 
    <span data-ttu-id="1dd65-123">A: Contoso ha deciso di usare i numeri di telefono esistenti da assegnare all'account del servizio per l'operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="1dd65-123">A: Contoso decided to use existing phone numbers to be assigned to the service account for the auto attendant.</span></span> 

  - <span data-ttu-id="1dd65-124">D: quando l'operatore automatico sarà disponibile ad accettare le chiamate in arrivo?</span><span class="sxs-lookup"><span data-stu-id="1dd65-124">Q: When will the auto attendant be available to accept incoming calls?</span></span> 
    <span data-ttu-id="1dd65-125">A: Contoso ha deciso di impostare l'orario di ufficio e di ricevere chiamate ricevute dopo l'orario di ufficio reindirizzato a un operatore automatico "after-hours".</span><span class="sxs-lookup"><span data-stu-id="1dd65-125">A: Contoso decided to set business hours and have calls received after business hours redirected to an "after-hours" auto attendant.</span></span>  

  - <span data-ttu-id="1dd65-126">D: in che modo le chiamate verranno instradate ai membri in una coda di chiamata: il routing di Attendant, seriale o Round Robin?</span><span class="sxs-lookup"><span data-stu-id="1dd65-126">Q: How will the calls be routed to members in a call queue: attendant, serial, or round robin routing?</span></span> 
    <span data-ttu-id="1dd65-127">A: Contoso ha deciso di usare il routing di Attendant</span><span class="sxs-lookup"><span data-stu-id="1dd65-127">A: Contoso decided to use Attendant routing,</span></span> 

  - <span data-ttu-id="1dd65-128">D: come si determina quando un utente deve o non deve ricevere una chiamata?</span><span class="sxs-lookup"><span data-stu-id="1dd65-128">Q: How will we determine when a user should or should not get a call?</span></span> 
    <span data-ttu-id="1dd65-129">A: Contoso ha deciso di usare le opzioni di gestione delle chiamate per determinare se l'agente è disponibile: routing basato sulla presenza.</span><span class="sxs-lookup"><span data-stu-id="1dd65-129">A: Contoso decided to use call handling options to determine if the agent is available: presence-based routing.</span></span> 


## <a name="configuration"></a><span data-ttu-id="1dd65-130">Configurazione</span><span class="sxs-lookup"><span data-stu-id="1dd65-130">Configuration</span></span>

<span data-ttu-id="1dd65-131">I passaggi per configurare un operatore automatico e una coda di chiamata includono gli elementi seguenti descritti in [gestire gli account delle risorse](manage-resource-accounts.md):</span><span class="sxs-lookup"><span data-stu-id="1dd65-131">The steps to set up an auto attendant and a call queue include the following outlined in [Manage resource accounts](manage-resource-accounts.md):</span></span> 

1. <span data-ttu-id="1dd65-132">Ottenere un numero di servizio.</span><span class="sxs-lookup"><span data-stu-id="1dd65-132">Obtain a service number.</span></span> 

2. <span data-ttu-id="1dd65-133">Ottenere un sistema telefonico gratuito-licenza per gli utenti virtuali o una licenza per il sistema telefonico a pagamento da usare con l'account delle risorse o con una licenza per il sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="1dd65-133">Obtain a free Phone System - Virtual User license or a paid Phone System license to use with the resource account or a Phone System license.</span></span>

3. <span data-ttu-id="1dd65-134">Creare l'account delle risorse.</span><span class="sxs-lookup"><span data-stu-id="1dd65-134">Create the resource account.</span></span> <span data-ttu-id="1dd65-135">Per avere un account di risorse associato è necessario un operatore automatico o una coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="1dd65-135">An auto attendant or call queue is required to have an associated resource account.</span></span> 

4. <span data-ttu-id="1dd65-136">Assegnare il sistema telefonico o un sistema telefonico-licenza utente virtuale per l'account delle risorse.</span><span class="sxs-lookup"><span data-stu-id="1dd65-136">Assign the Phone System or a Phone System - Virtual user license to the resource account.</span></span> <span data-ttu-id="1dd65-137">Per altre informazioni, vedere [sistema telefonico Microsoft 365-licenza per gli utenti virtuali](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/virtual-user).</span><span class="sxs-lookup"><span data-stu-id="1dd65-137">For more information, see [Microsoft 365 Phone System – Virtual User license](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/virtual-user).</span></span>

5. <span data-ttu-id="1dd65-138">Assegnare un numero di telefono del servizio all'account della risorsa a cui sono state assegnate le licenze.</span><span class="sxs-lookup"><span data-stu-id="1dd65-138">Assign a service phone number to the resource account you assigned licenses to.</span></span> 

6. <span data-ttu-id="1dd65-139">Creare una coda di chiamata di sistema telefonico o un operatore automatico</span><span class="sxs-lookup"><span data-stu-id="1dd65-139">Create a Phone System call queue or auto attendant</span></span> 

7. <span data-ttu-id="1dd65-140">Collegare l'account delle risorse con una coda di chiamata o un operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="1dd65-140">Link the resource account with a call queue or auto attendant.</span></span> 


### <a name="sites-with-phone-system-with-direct-routing"></a><span data-ttu-id="1dd65-141">Siti con sistema telefonico con routing diretto</span><span class="sxs-lookup"><span data-stu-id="1dd65-141">Sites with Phone System with Direct routing</span></span> 

<span data-ttu-id="1dd65-142">Contoso ha dovuto configurare il numero di telefono fornito dal vettore locale come numero di servizio in Office 365.</span><span class="sxs-lookup"><span data-stu-id="1dd65-142">Contoso had to set up the phone number provided by the local carrier as the service number in Office 365.</span></span> 

- <span data-ttu-id="1dd65-143">Per configurare un numero di telefono disponibile tramite routing diretto, Contoso ha seguito le istruzioni disponibili in [Gestisci account risorse](manage-resource-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="1dd65-143">To set up a phone number available through Direct Routing, Contoso followed the instructions located in [Manage Resource Accounts](manage-resource-accounts.md).</span></span> <span data-ttu-id="1dd65-144">Poiché Office 365 non è a conoscenza dei numeri di telefono locali, Contoso ha usato PowerShell per completare la configurazione.</span><span class="sxs-lookup"><span data-stu-id="1dd65-144">Because Office 365 is not aware of the on-premises phone numbers, Contoso used PowerShell to complete the setup.</span></span>   

- <span data-ttu-id="1dd65-145">Per configurare l'operatore automatico cloud, Contoso ha seguito i passaggi descritti in [configurare un operatore automatico cloud](create-a-phone-system-auto-attendant.md).</span><span class="sxs-lookup"><span data-stu-id="1dd65-145">To configure the Cloud auto attendant, Contoso followed the steps outlined in [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md).</span></span> 

- <span data-ttu-id="1dd65-146">Per configurare una coda di chiamata cloud, Contoso ha seguito i passaggi illustrati in [creare una coda di chiamata cloud](create-a-phone-system-call-queue.md).</span><span class="sxs-lookup"><span data-stu-id="1dd65-146">To set up a Cloud call queue, Contoso followed the steps outlined in [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>  


### <a name="sites-with-phone-system-with-calling-plan"></a><span data-ttu-id="1dd65-147">Siti con sistema telefonico con un piano per le chiamate</span><span class="sxs-lookup"><span data-stu-id="1dd65-147">Sites with Phone System with Calling plan</span></span>

<span data-ttu-id="1dd65-148">Contoso ha dovuto trasferire il numero di telefono usato per gli operatori automatici di Skype for Business VoIP per Office 365 Phone System.</span><span class="sxs-lookup"><span data-stu-id="1dd65-148">Contoso had to port the phone number that was used for Skype for Business Enterprise Voice auto attendants to Office 365 Phone System.</span></span> <span data-ttu-id="1dd65-149">Ciò ha consentito di assegnare lo stesso numero come numero di servizio da usare come operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="1dd65-149">This allowed the same number to be assigned as a service number for use as an auto attendant.</span></span> 

- <span data-ttu-id="1dd65-150">Per trasferire il numero di telefono, Contoso ha seguito le istruzioni in [trasferimento di numeri di telefono a teams](https://docs.microsoft.com/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams) e ha ottenuto ulteriori indicazioni [per gestire i numeri di telefono per l'organizzazione](https://docs.microsoft.com/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization).</span><span class="sxs-lookup"><span data-stu-id="1dd65-150">To port the phone number, Contoso followed the instructions in [Transfer phone numbers to Teams](https://docs.microsoft.com/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams) and obtained additional guidance at [Manage phone numbers for your organization](https://docs.microsoft.com/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization).</span></span>

- <span data-ttu-id="1dd65-151">Per configurare un operatore automatico cloud, Contoso ha seguito i passaggi descritti in [configurare un operatore automatico cloud](create-a-phone-system-auto-attendant.md).</span><span class="sxs-lookup"><span data-stu-id="1dd65-151">To configure a Cloud auto attendant, Contoso followed the steps outlined in [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md).</span></span>

-  <span data-ttu-id="1dd65-152">Per configurare una coda di chiamata cloud, Contoso ha seguito i passaggi illustrati in [creare una coda di chiamata cloud](create-a-phone-system-call-queue.md).</span><span class="sxs-lookup"><span data-stu-id="1dd65-152">To set up a Cloud call queue, Contoso followed the steps outlined in [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>  

 