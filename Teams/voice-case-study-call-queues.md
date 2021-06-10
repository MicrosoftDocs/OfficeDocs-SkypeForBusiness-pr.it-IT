---
title: Teams caso di studio contoso vocale
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
description: Teams caso di studio vocale per multinazionali
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0cb8029a8f4e979a76afe069ee9b22e7be897913
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121294"
---
# <a name="contoso-case-study-auto-attendants-and-call-queues"></a><span data-ttu-id="ed75a-103">Case study contoso: Operatori automatici e code di chiamata</span><span class="sxs-lookup"><span data-stu-id="ed75a-103">Contoso case study: Auto attendants and call queues</span></span>

<span data-ttu-id="ed75a-104">Contoso aveva familiarità con gli operatori automatici e le code di chiamata dalla distribuzione Skype for Business locale.</span><span class="sxs-lookup"><span data-stu-id="ed75a-104">Contoso was familiar with auto attendants and call queues from their on-premises Skype for Business deployment.</span></span> <span data-ttu-id="ed75a-105">Per informazioni su come configurare gli operatori automatici cloud e le code di chiamata, hanno esaminato Pianificare gli operatori automatici Teams e [le code di chiamata.](plan-auto-attendant-call-queue.md)</span><span class="sxs-lookup"><span data-stu-id="ed75a-105">To understand how to set up Cloud auto attendants and call queues, they reviewed [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md).</span></span>

## <a name="requirements-depending-on-site-type"></a><span data-ttu-id="ed75a-106">Requisiti a seconda del tipo di sito</span><span class="sxs-lookup"><span data-stu-id="ed75a-106">Requirements depending on site type</span></span>

<span data-ttu-id="ed75a-107">A seconda del tipo di sito, Contoso ha le esigenze seguenti:</span><span class="sxs-lookup"><span data-stu-id="ed75a-107">Depending on the site type, Contoso had the following needs:</span></span>

- <span data-ttu-id="ed75a-108">Tipo di sito A: sistemi di telefonia legacy tradizionali</span><span class="sxs-lookup"><span data-stu-id="ed75a-108">Site Type A: Traditional legacy telephony systems</span></span> 

  <span data-ttu-id="ed75a-109">Tipo di sito A necessario per mantenere lo stesso numero di telefono associato all'addetto alla ricezione del numero per gli operatori automatici.</span><span class="sxs-lookup"><span data-stu-id="ed75a-109">Site Type A needed to keep the same phone number associated with the receptionist as the number for their auto attendants.</span></span> <span data-ttu-id="ed75a-110">I reparti chiave di ognuno di questi siti avrebbero code di chiamata che verrebbero indirizzate ai membri del team.</span><span class="sxs-lookup"><span data-stu-id="ed75a-110">The key departments for each of these sites would have their own call queues that would route to team members.</span></span> <span data-ttu-id="ed75a-111">C'era una combinazione di siti che usava Sistema telefonico routing diretto e Sistema telefonico con i piani per chiamate.</span><span class="sxs-lookup"><span data-stu-id="ed75a-111">There was a mixture of sites that used Phone System with Direct Routing and Phone System with Calling Plans.</span></span>  

- <span data-ttu-id="ed75a-112">Tipo di sito B: Skype for Business VoIP aziendale</span><span class="sxs-lookup"><span data-stu-id="ed75a-112">Site Type B: Skype for Business Enterprise Voice</span></span> 

  <span data-ttu-id="ed75a-113">Il tipo di sito B aveva operatori automatici e code di chiamata esistenti che dovevano eseguire la migrazione a Teams.</span><span class="sxs-lookup"><span data-stu-id="ed75a-113">Site Type B had existing auto attendants and call queues that needed to migrate to Teams.</span></span> <span data-ttu-id="ed75a-114">Contoso doveva mantenere i numeri di telefono associati agli operatori automatici.</span><span class="sxs-lookup"><span data-stu-id="ed75a-114">Contoso needed to keep the phone numbers associated with the auto attendants.</span></span> <span data-ttu-id="ed75a-115">Contoso ha spostato la maggior parte di questi siti Sistema telefonico piani per chiamate.</span><span class="sxs-lookup"><span data-stu-id="ed75a-115">Contoso moved the majority of these sites to Phone System with Calling Plans.</span></span> <span data-ttu-id="ed75a-116">Tuttavia, nelle poche posizioni in cui i piani per chiamate non erano disponibili, Contoso ha spostato questi siti in una configurazione Di routing diretto.</span><span class="sxs-lookup"><span data-stu-id="ed75a-116">However, in the few locations where Calling Plans was not available, Contoso moved these sites to a Direct Routing configuration.</span></span>  

- <span data-ttu-id="ed75a-117">Tipo di sito C: Skype for Business VoIP aziendale & tradizionale sistema di telefonia legacy</span><span class="sxs-lookup"><span data-stu-id="ed75a-117">Site Type C: Skype for Business Enterprise Voice & traditional legacy telephony system</span></span> 

  <span data-ttu-id="ed75a-118">Il tipo di sito C aveva operatori automatici esistenti che risiedevano nel sistema di telefonia legacy tradizionale.</span><span class="sxs-lookup"><span data-stu-id="ed75a-118">Site Type C had existing auto attendants that resided in the traditional legacy telephony system.</span></span> <span data-ttu-id="ed75a-119">Le decisioni e le configurazioni per questo sito sono state le stesse del tipo di sito A.</span><span class="sxs-lookup"><span data-stu-id="ed75a-119">The decisions and configurations for this site were the same as Site Type A.</span></span>   

- <span data-ttu-id="ed75a-120">Per tutti i tipi di sito, Contoso ha posto le domande seguenti:</span><span class="sxs-lookup"><span data-stu-id="ed75a-120">For all site types, Contoso asked the following questions:</span></span>

  - <span data-ttu-id="ed75a-121">D: Verranno utilizzati numeri nuovi o esistenti?</span><span class="sxs-lookup"><span data-stu-id="ed75a-121">Q: Will we use new or existing numbers?</span></span> 
    <span data-ttu-id="ed75a-122">A: Contoso ha deciso di usare i numeri di telefono esistenti da assegnare all'account del servizio per l'operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="ed75a-122">A: Contoso decided to use existing phone numbers to be assigned to the service account for the auto attendant.</span></span> 

  - <span data-ttu-id="ed75a-123">D: Quando sarà disponibile l'operatore automatico per accettare le chiamate in arrivo?</span><span class="sxs-lookup"><span data-stu-id="ed75a-123">Q: When will the auto attendant be available to accept incoming calls?</span></span> 
    <span data-ttu-id="ed75a-124">A: Contoso ha deciso di impostare l'orario di ufficio e di ricevere chiamate dopo l'orario di ufficio reindirizzate a un operatore automatico "dopo l'orario di ufficio".</span><span class="sxs-lookup"><span data-stu-id="ed75a-124">A: Contoso decided to set business hours and have calls received after business hours redirected to an "after-hours" auto attendant.</span></span>  

  - <span data-ttu-id="ed75a-125">D: Come verranno instradati le chiamate ai membri di una coda di chiamata: instradamento operatore, seriale o round robin?</span><span class="sxs-lookup"><span data-stu-id="ed75a-125">Q: How will the calls be routed to members in a call queue: attendant, serial, or round robin routing?</span></span> 
    <span data-ttu-id="ed75a-126">A: Contoso ha deciso di usare il routing dell'operatore,</span><span class="sxs-lookup"><span data-stu-id="ed75a-126">A: Contoso decided to use Attendant routing,</span></span> 

  - <span data-ttu-id="ed75a-127">D: Come verrà determinato quando un utente deve o meno ricevere una chiamata?</span><span class="sxs-lookup"><span data-stu-id="ed75a-127">Q: How will we determine when a user should or should not get a call?</span></span> 
    <span data-ttu-id="ed75a-128">A: Contoso ha deciso di usare le opzioni di gestione delle chiamate per determinare se l'agente è disponibile: routing basato sulla presenza.</span><span class="sxs-lookup"><span data-stu-id="ed75a-128">A: Contoso decided to use call handling options to determine if the agent is available: presence-based routing.</span></span> 


## <a name="configuration"></a><span data-ttu-id="ed75a-129">Configurazione</span><span class="sxs-lookup"><span data-stu-id="ed75a-129">Configuration</span></span>

<span data-ttu-id="ed75a-130">I passaggi per configurare un operatore automatico e una coda di chiamata sono i seguenti descritti in [Gestire gli account delle risorse:](manage-resource-accounts.md)</span><span class="sxs-lookup"><span data-stu-id="ed75a-130">The steps to set up an auto attendant and a call queue include the following outlined in [Manage resource accounts](manage-resource-accounts.md):</span></span> 

1. <span data-ttu-id="ed75a-131">Ottenere un numero di servizio.</span><span class="sxs-lookup"><span data-stu-id="ed75a-131">Obtain a service number.</span></span> 

2. <span data-ttu-id="ed75a-132">Ottenere una licenza Sistema telefonico - Utente virtuale o una licenza Sistema telefonico a pagamento da usare con l'account della risorsa o una Sistema telefonico licenza.</span><span class="sxs-lookup"><span data-stu-id="ed75a-132">Obtain a free Phone System - Virtual User license or a paid Phone System license to use with the resource account or a Phone System license.</span></span>

3. <span data-ttu-id="ed75a-133">Creare l'account della risorsa.</span><span class="sxs-lookup"><span data-stu-id="ed75a-133">Create the resource account.</span></span> <span data-ttu-id="ed75a-134">Un operatore automatico o una coda di chiamata deve avere un account di risorsa associato.</span><span class="sxs-lookup"><span data-stu-id="ed75a-134">An auto attendant or call queue is required to have an associated resource account.</span></span> 

4. <span data-ttu-id="ed75a-135">Assegnare la Sistema telefonico o una Sistema telefonico - Licenza utente virtuale all'account della risorsa.</span><span class="sxs-lookup"><span data-stu-id="ed75a-135">Assign the Phone System or a Phone System - Virtual user license to the resource account.</span></span> <span data-ttu-id="ed75a-136">Per altre informazioni, vedere Microsoft 365 Sistema telefonico [- Licenza utente virtuale](./teams-add-on-licensing/virtual-user.md).</span><span class="sxs-lookup"><span data-stu-id="ed75a-136">For more information, see [Microsoft 365 Phone System – Virtual User license](./teams-add-on-licensing/virtual-user.md).</span></span>

5. <span data-ttu-id="ed75a-137">Assegnare un numero di telefono del servizio all'account della risorsa a cui sono state assegnate le licenze.</span><span class="sxs-lookup"><span data-stu-id="ed75a-137">Assign a service phone number to the resource account you assigned licenses to.</span></span> 

6. <span data-ttu-id="ed75a-138">Creare una coda Sistema telefonico chiamata o un operatore automatico</span><span class="sxs-lookup"><span data-stu-id="ed75a-138">Create a Phone System call queue or auto attendant</span></span> 

7. <span data-ttu-id="ed75a-139">Collegare l'account della risorsa a una coda di chiamata o a un operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="ed75a-139">Link the resource account with a call queue or auto attendant.</span></span> 


### <a name="sites-with-phone-system-with-direct-routing"></a><span data-ttu-id="ed75a-140">Siti con Sistema telefonico con routing diretto</span><span class="sxs-lookup"><span data-stu-id="ed75a-140">Sites with Phone System with Direct routing</span></span> 

<span data-ttu-id="ed75a-141">Contoso ha dovuto configurare il numero di telefono fornito dal gestore locale come numero di servizio in Office 365.</span><span class="sxs-lookup"><span data-stu-id="ed75a-141">Contoso had to set up the phone number provided by the local carrier as the service number in Office 365.</span></span> 

- <span data-ttu-id="ed75a-142">Per configurare un numero di telefono disponibile tramite Routing diretto, Contoso ha seguito le istruzioni disponibili in [Gestire gli account delle risorse.](manage-resource-accounts.md)</span><span class="sxs-lookup"><span data-stu-id="ed75a-142">To set up a phone number available through Direct Routing, Contoso followed the instructions located in [Manage Resource Accounts](manage-resource-accounts.md).</span></span> <span data-ttu-id="ed75a-143">Poiché Office 365 non è a conoscenza dei numeri di telefono locali, Contoso ha usato PowerShell per completare la configurazione.</span><span class="sxs-lookup"><span data-stu-id="ed75a-143">Because Office 365 is not aware of the on-premises phone numbers, Contoso used PowerShell to complete the setup.</span></span>   

- <span data-ttu-id="ed75a-144">Per configurare l'operatore automatico cloud, Contoso ha seguito i passaggi descritti in [Configurare un operatore automatico cloud.](create-a-phone-system-auto-attendant.md)</span><span class="sxs-lookup"><span data-stu-id="ed75a-144">To configure the Cloud auto attendant, Contoso followed the steps outlined in [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md).</span></span> 

- <span data-ttu-id="ed75a-145">Per configurare una coda di chiamate cloud, Contoso ha seguito i passaggi descritti in [Creare una coda di chiamata cloud.](create-a-phone-system-call-queue.md)</span><span class="sxs-lookup"><span data-stu-id="ed75a-145">To set up a Cloud call queue, Contoso followed the steps outlined in [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>  


### <a name="sites-with-phone-system-with-calling-plan"></a><span data-ttu-id="ed75a-146">Siti con Sistema telefonico piano chiamate</span><span class="sxs-lookup"><span data-stu-id="ed75a-146">Sites with Phone System with Calling plan</span></span>

<span data-ttu-id="ed75a-147">Contoso ha dovuto convertire il numero di telefono usato per Skype for Business VoIP aziendale operatori automatici in Sistema telefonico di Office 365.</span><span class="sxs-lookup"><span data-stu-id="ed75a-147">Contoso had to port the phone number that was used for Skype for Business Enterprise Voice auto attendants to Office 365 Phone System.</span></span> <span data-ttu-id="ed75a-148">In questo modo è possibile assegnare lo stesso numero come numero di servizio da usare come operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="ed75a-148">This allowed the same number to be assigned as a service number for use as an auto attendant.</span></span> 

- <span data-ttu-id="ed75a-149">Per trasferire il numero di telefono, Contoso ha seguito le istruzioni [in](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md) Trasferire i numeri di telefono in Teams e ha ottenuto altre indicazioni in Gestire i numeri di telefono [per l'organizzazione.](./manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)</span><span class="sxs-lookup"><span data-stu-id="ed75a-149">To port the phone number, Contoso followed the instructions in [Transfer phone numbers to Teams](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md) and obtained additional guidance at [Manage phone numbers for your organization](./manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).</span></span>

- <span data-ttu-id="ed75a-150">Per configurare un operatore automatico cloud, Contoso ha seguito i passaggi descritti in [Configurare un operatore automatico cloud.](create-a-phone-system-auto-attendant.md)</span><span class="sxs-lookup"><span data-stu-id="ed75a-150">To configure a Cloud auto attendant, Contoso followed the steps outlined in [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md).</span></span>

-  <span data-ttu-id="ed75a-151">Per configurare una coda di chiamate cloud, Contoso ha seguito i passaggi descritti in [Creare una coda di chiamata cloud.](create-a-phone-system-call-queue.md)</span><span class="sxs-lookup"><span data-stu-id="ed75a-151">To set up a Cloud call queue, Contoso followed the steps outlined in [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>  

