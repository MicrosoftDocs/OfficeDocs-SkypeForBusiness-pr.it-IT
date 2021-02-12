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
ms.openlocfilehash: 7431515d40550a3f731c34f97ed8c10586424901
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786024"
---
# <a name="contoso-case-study-phone-system"></a><span data-ttu-id="4d35f-103">Case study Contoso: Sistema telefonico</span><span class="sxs-lookup"><span data-stu-id="4d35f-103">Contoso case study: Phone System</span></span>

<span data-ttu-id="4d35f-104">A seconda della posizione geografica e di altri fattori, Contoso aveva uffici che usavano le seguenti soluzioni di telefonia:</span><span class="sxs-lookup"><span data-stu-id="4d35f-104">Depending on geographic location and other factors, Contoso had offices using the following telephony solutions:</span></span>

- <span data-ttu-id="4d35f-105">Tipo di sito A: Skype for Business VoIP aziendale</span><span class="sxs-lookup"><span data-stu-id="4d35f-105">Site Type A: Skype for Business Enterprise Voice</span></span>

- <span data-ttu-id="4d35f-106">Tipo di sito B: sistemi di telefonia legacy tradizionali</span><span class="sxs-lookup"><span data-stu-id="4d35f-106">Site Type B: Traditional legacy telephony systems</span></span>

- <span data-ttu-id="4d35f-107">Tipo di sito C: Combinazione dei sistemi di telefonia legacy VoIP aziendale Skype for Business</span><span class="sxs-lookup"><span data-stu-id="4d35f-107">Site Type C: A combination of Skype for Business Enterprise Voice and traditional legacy telephony systems</span></span>


<span data-ttu-id="4d35f-108">Per implementare una soluzione Sistema telefonico Microsoft per l'intera organizzazione, Contoso ha dovuto determinare per ogni tipo di sito quale delle seguenti opzioni verrebbe usata con il Sistema telefonico per connettersi alla rete &mdash; &mdash; PSTN (Public Switched Telephone Network):</span><span class="sxs-lookup"><span data-stu-id="4d35f-108">To implement a Microsoft Phone System solution for their entire organization, Contoso had to determine&mdash;for each site type&mdash;which of the following options would be used with Phone System to connect to the Public Switched Telephone Network (PSTN):</span></span>

- <span data-ttu-id="4d35f-109">Sistema telefonico con piano per chiamate</span><span class="sxs-lookup"><span data-stu-id="4d35f-109">Phone System with Calling Plan</span></span> 

- <span data-ttu-id="4d35f-110">Sistema telefonico con gestore PSTN tramite routing diretto</span><span class="sxs-lookup"><span data-stu-id="4d35f-110">Phone System with own PSTN carrier through Direct Routing</span></span> 

- <span data-ttu-id="4d35f-111">Combinazione di Sistema telefonico con Piano per chiamate e Sistema telefonico con un proprio gestore PSTN attraverso l'instradamento diretto</span><span class="sxs-lookup"><span data-stu-id="4d35f-111">Combination of Phone System with Calling Plan and Phone System with own PSTN carrier through Direct Routing</span></span>
 
<span data-ttu-id="4d35f-112">Per determinare la soluzione giusta per la propria organizzazione, Contoso ha utilizzato le soluzioni di telefonia [Microsoft](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions) e le chiamate di sessione di Ignite 2019 [in Microsoft Teams.](https://myignite.techcommunity.microsoft.com/sessions/83170?source=sessions)</span><span class="sxs-lookup"><span data-stu-id="4d35f-112">To determine the right solution for their organization, Contoso used [Microsoft telephony solutions](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions) and the Ignite 2019 session [Calling in Microsoft Teams](https://myignite.techcommunity.microsoft.com/sessions/83170?source=sessions).</span></span>  

## <a name="site-type-a-skype-for-business-enterprise-voice"></a><span data-ttu-id="4d35f-113">Tipo di sito A: Skype for Business VoIP aziendale</span><span class="sxs-lookup"><span data-stu-id="4d35f-113">Site Type A: Skype for Business Enterprise Voice</span></span> 

<span data-ttu-id="4d35f-114">Contoso Skype for Business VoIP aziendale è stato configurato come hub e parla.</span><span class="sxs-lookup"><span data-stu-id="4d35f-114">Contoso Skype for Business Enterprise Voice was set up as a hub and spoke.</span></span> <span data-ttu-id="4d35f-115">C'era una posizione centrale che ha mantenuto il gateway PSTN nell'area geografica che ha fornito la connessione alla rete PSTN per gli utenti VoIP aziendale Skype for Business nel paese.</span><span class="sxs-lookup"><span data-stu-id="4d35f-115">There was a central location that maintained the PSTN gateway in the region that provided the connection to the PSTN for the Skype for Business Enterprise Voice users in country.</span></span> <span data-ttu-id="4d35f-116">Spesso questi uffici satellitari non hanno un proprio indirizzo Internet in uscita.</span><span class="sxs-lookup"><span data-stu-id="4d35f-116">Often these satellite offices did not have their own Internet egress.</span></span> <span data-ttu-id="4d35f-117">I numeri per questi utenti risiedevano nel trunk SIP che si connette a un database SBC esistente.</span><span class="sxs-lookup"><span data-stu-id="4d35f-117">The numbers for these users resided on the SIP trunk connecting to an existing SBC.</span></span> 

<span data-ttu-id="4d35f-118">Per determinare se il controller SBC già distribuito è certificato per l'instradamento diretto e il bypass multimediale, Contoso ha controllato l'elenco dei controller dei confini della sessione [certificati per il routing diretto.](direct-routing-border-controllers.md)</span><span class="sxs-lookup"><span data-stu-id="4d35f-118">To determine if the SBC already deployed is certified for Direct Routing and Media Bypass, Contoso checked the [List of Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>  

<span data-ttu-id="4d35f-119">Le abitudini di composizione dell'utente erano di comporre un utente nel sistema di telefonia legacy utilizzando un'estensione, anche quando l'utente dispone di un client Skype for Business disponibile per l'audio peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="4d35f-119">The user's dialing habits were to dial a user on the legacy telephony system using an extension, even when the user has a Skype for Business client available for peer-to-peer audio.</span></span> 

<span data-ttu-id="4d35f-120">Contoso ha basato la decisione sulle domande seguenti:</span><span class="sxs-lookup"><span data-stu-id="4d35f-120">Contoso based their decision on the following questions:</span></span>

- <span data-ttu-id="4d35f-121">D.</span><span class="sxs-lookup"><span data-stu-id="4d35f-121">Q.</span></span> <span data-ttu-id="4d35f-122">È necessario mantenere le funzionalità fornite dalla distribuzione locale?</span><span class="sxs-lookup"><span data-stu-id="4d35f-122">Do we need to retain functionality provided by our on-premises deployment?</span></span><br>
  <span data-ttu-id="4d35f-123">A.</span><span class="sxs-lookup"><span data-stu-id="4d35f-123">A.</span></span> <span data-ttu-id="4d35f-124">No</span><span class="sxs-lookup"><span data-stu-id="4d35f-124">No</span></span> 

- <span data-ttu-id="4d35f-125">D.</span><span class="sxs-lookup"><span data-stu-id="4d35f-125">Q.</span></span> <span data-ttu-id="4d35f-126">È necessario interoperabilità con sistemi PBX di terze parti e altri dispositivi di telefonia?</span><span class="sxs-lookup"><span data-stu-id="4d35f-126">Do we need to interoperate with third-party PBX systems and other telephony equipment?</span></span><br>
  <span data-ttu-id="4d35f-127">A.</span><span class="sxs-lookup"><span data-stu-id="4d35f-127">A.</span></span> <span data-ttu-id="4d35f-128">No</span><span class="sxs-lookup"><span data-stu-id="4d35f-128">No</span></span> 

- <span data-ttu-id="4d35f-129">D.</span><span class="sxs-lookup"><span data-stu-id="4d35f-129">Q.</span></span> <span data-ttu-id="4d35f-130">È necessario conservare l'attuale gestore di terze parti?</span><span class="sxs-lookup"><span data-stu-id="4d35f-130">Do we need to retain our current third-party carrier?</span></span><br> <span data-ttu-id="4d35f-131">A. Sì (paesi regolamentati) e No</span><span class="sxs-lookup"><span data-stu-id="4d35f-131">A. Yes (regulated countries) and No</span></span> 

- <span data-ttu-id="4d35f-132">D.</span><span class="sxs-lookup"><span data-stu-id="4d35f-132">Q.</span></span> <span data-ttu-id="4d35f-133">È necessario distribuire il ROI nei PC SB?</span><span class="sxs-lookup"><span data-stu-id="4d35f-133">Do we need to get the ROI on SBCs deployed?</span></span><br> <span data-ttu-id="4d35f-134">A. Sì e no</span><span class="sxs-lookup"><span data-stu-id="4d35f-134">A. Yes and No</span></span>  

- <span data-ttu-id="4d35f-135">D.</span><span class="sxs-lookup"><span data-stu-id="4d35f-135">Q.</span></span> <span data-ttu-id="4d35f-136">I Piani per chiamate PSTN Microsoft sono disponibili in questa area geografica?</span><span class="sxs-lookup"><span data-stu-id="4d35f-136">Is Microsoft PSTN Calling Plans available in this region?</span></span><br> <span data-ttu-id="4d35f-137">A. Sì e no</span><span class="sxs-lookup"><span data-stu-id="4d35f-137">A. Yes and No</span></span> 

<span data-ttu-id="4d35f-138">In base alle risposte alle loro domande, Contoso ha deciso di:</span><span class="sxs-lookup"><span data-stu-id="4d35f-138">Based on the answers to their questions, Contoso decided to:</span></span>

- <span data-ttu-id="4d35f-139">Spostare gli utenti che si trovano in un'area in cui i piani per le chiamate PSTN sono disponibili nel Sistema telefonico con Piani per chiamate.</span><span class="sxs-lookup"><span data-stu-id="4d35f-139">Move the users that are located in a region where PSTN calling plans is available to Phone System with Calling Plans.</span></span> 

- <span data-ttu-id="4d35f-140">Spostare gli utenti che non si trovano in un'area geografica in cui sono disponibili i piani di chiamata PSTN, gli utenti che si trovano in un sito in cui il ROI dei PC non sono ancora stati soddisfatti e gli utenti che risiedono in un paese che ha normative di telefonia al Sistema telefonico con instradamento diretto.</span><span class="sxs-lookup"><span data-stu-id="4d35f-140">Move the users that are not located in a region where PSTN calling plans is available, users located in a site where the ROI on the SBCs have yet to be met, and users that resided in a country that has telephony regulations to Phone System with Direct Routing.</span></span> 

<span data-ttu-id="4d35f-141">Il diagramma seguente mostra la distribuzione iniziale di Skype for Business VoIP aziendale distribuzione e come è stata eseguita la migrazione di questa distribuzione ai Piani per chiamate Microsoft e all'instradamento diretto:</span><span class="sxs-lookup"><span data-stu-id="4d35f-141">The following diagram shows the initial Skype for Business Enterprise Voice deployment and how this deployment was migrated to both Microsoft Calling Plans and Direct Routing:</span></span>

![Diagramma che mostra gli stati prima e dopo](media/voice-case-study-1.png)

## <a name="site-type-b-traditional-legacy-telephony-systems"></a><span data-ttu-id="4d35f-143">Tipo di sito B: sistemi di telefonia legacy tradizionali</span><span class="sxs-lookup"><span data-stu-id="4d35f-143">Site Type B: Traditional legacy telephony systems</span></span>

<span data-ttu-id="4d35f-144">Contoso ha molti uffici che sfruttano i sistemi di telefonia legacy.</span><span class="sxs-lookup"><span data-stu-id="4d35f-144">Contoso had many offices that leveraged legacy telephony systems.</span></span> <span data-ttu-id="4d35f-145">C'era un sottoinsieme di utenti che avevano un numero di telefono E1.64, mentre altri avevano solo un interno.</span><span class="sxs-lookup"><span data-stu-id="4d35f-145">There were a subset of users that had an E1.64 phone number while others only had an extension.</span></span> <span data-ttu-id="4d35f-146">Questi numeri risiedevano nel trunk TDM al gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="4d35f-146">These numbers resided on the TDM trunk to the PSTN gateway.</span></span> <span data-ttu-id="4d35f-147">La composizione tra siti è stata configurata sfruttando un codice di sito davanti all'interno per determinare dove instradare la chiamata.</span><span class="sxs-lookup"><span data-stu-id="4d35f-147">Intra-site dialing was configured by leveraging a site code in front of the extension to determine where to route the call.</span></span> <span data-ttu-id="4d35f-148">Le abitudini di composizione degli utenti erano di chiamata per interno.</span><span class="sxs-lookup"><span data-stu-id="4d35f-148">The users' dialing habits were to dial by extension.</span></span>   

<span data-ttu-id="4d35f-149">Contoso ha basato la decisione sulle domande seguenti:</span><span class="sxs-lookup"><span data-stu-id="4d35f-149">Contoso based their decision on the following questions:</span></span>

- <span data-ttu-id="4d35f-150">D.</span><span class="sxs-lookup"><span data-stu-id="4d35f-150">Q.</span></span> <span data-ttu-id="4d35f-151">È necessario mantenere le funzionalità fornite dalla distribuzione locale?</span><span class="sxs-lookup"><span data-stu-id="4d35f-151">Do we need to retain functionality provided by our on-premises deployment?</span></span><br>
  <span data-ttu-id="4d35f-152">A.</span><span class="sxs-lookup"><span data-stu-id="4d35f-152">A.</span></span> <span data-ttu-id="4d35f-153">No</span><span class="sxs-lookup"><span data-stu-id="4d35f-153">No</span></span> 

- <span data-ttu-id="4d35f-154">D.</span><span class="sxs-lookup"><span data-stu-id="4d35f-154">Q.</span></span> <span data-ttu-id="4d35f-155">È necessario interoperabilità con sistemi PBX di terze parti e altri dispositivi di telefonia?</span><span class="sxs-lookup"><span data-stu-id="4d35f-155">Do we need to interoperate with third-party PBX systems and other telephony equipment?</span></span><br> <span data-ttu-id="4d35f-156">A. Sì</span><span class="sxs-lookup"><span data-stu-id="4d35f-156">A. Yes</span></span>

- <span data-ttu-id="4d35f-157">D.</span><span class="sxs-lookup"><span data-stu-id="4d35f-157">Q.</span></span> <span data-ttu-id="4d35f-158">È necessario conservare l'attuale gestore di terze parti?</span><span class="sxs-lookup"><span data-stu-id="4d35f-158">Do we need to retain our current third-party carrier?</span></span><br> <span data-ttu-id="4d35f-159">A. No</span><span class="sxs-lookup"><span data-stu-id="4d35f-159">A. No</span></span> 

- <span data-ttu-id="4d35f-160">D.</span><span class="sxs-lookup"><span data-stu-id="4d35f-160">Q.</span></span> <span data-ttu-id="4d35f-161">Il piano per le chiamate DI Microsoft PSTN è disponibile nella nostra area geografica?</span><span class="sxs-lookup"><span data-stu-id="4d35f-161">Is Microsoft PSTN's Calling Plan available in our region?</span></span><br> <span data-ttu-id="4d35f-162">A. Sì e no</span><span class="sxs-lookup"><span data-stu-id="4d35f-162">A. Yes and No</span></span> 

<span data-ttu-id="4d35f-163">In base alle risposte alle loro domande, Contoso ha deciso di:</span><span class="sxs-lookup"><span data-stu-id="4d35f-163">Based on the answers to their questions, Contoso decided to:</span></span> 

- <span data-ttu-id="4d35f-164">Spostare gli utenti che si trovano in un'area in cui i piani per le chiamate PSTN sono disponibili nel Sistema telefonico con Piani per chiamate.</span><span class="sxs-lookup"><span data-stu-id="4d35f-164">Move the users that are located in a region where PSTN calling plans is available to Phone System with Calling Plans.</span></span> 

- <span data-ttu-id="4d35f-165">Spostare gli utenti che non si trovano in un'area geografica in cui i piani per le chiamate PSTN sono disponibili nel Sistema telefonico con instradamento diretto.</span><span class="sxs-lookup"><span data-stu-id="4d35f-165">Move the users that are not located in a region where PSTN calling plans is available to Phone System with Direct Routing.</span></span> 

- <span data-ttu-id="4d35f-166">Mantenere una connessione PSTN a dispositivi analogici di importanza fondamentale per l'azienda.</span><span class="sxs-lookup"><span data-stu-id="4d35f-166">Maintain a PSTN connection to business critical analog devices.</span></span>

<span data-ttu-id="4d35f-167">I diagrammi seguenti mostrano la distribuzione di sistema legacy originale con i siti remoti e la migrazione a una distribuzione di routing diretto con l'ottimizzazione dei supporti locali:</span><span class="sxs-lookup"><span data-stu-id="4d35f-167">The following diagrams show the original legacy system deployment with remote sites and the migration to a Direct Routing deployment with Local Media Optimization:</span></span>

<span data-ttu-id="4d35f-168">**Distribuzione legacy originale**  
 ![ Diagramma che mostra gli stati prima e dopo](media/voice-case-study-2.png)</span><span class="sxs-lookup"><span data-stu-id="4d35f-168">**Original legacy deployment** 
![Diagram showing before and after states](media/voice-case-study-2.png)</span></span>


<span data-ttu-id="4d35f-169">**Distribuzione con routing diretto**</span><span class="sxs-lookup"><span data-stu-id="4d35f-169">**Deployment with Direct Routing**</span></span>

![Diagramma che mostra gli stati prima e dopo](media/voice-case-study-3.png)
 
## <a name="site-type-c-combination-of-skype-for-business-enterprise-voice-and-traditional-legacy-telephony-systems"></a><span data-ttu-id="4d35f-171">Tipo di sito C: Combinazione dei sistemi di telefonia legacy VoIP aziendale Skype for Business e tradizionali</span><span class="sxs-lookup"><span data-stu-id="4d35f-171">Site Type C: Combination of Skype for Business Enterprise Voice and traditional legacy telephony systems</span></span>

<span data-ttu-id="4d35f-172">Contoso Skype for Business VoIP aziendale i numeri degli utenti risiedono nel trunk SIP al sistema SBC dal gestore.</span><span class="sxs-lookup"><span data-stu-id="4d35f-172">Contoso Skype for Business Enterprise Voice users' numbers reside on the SIP trunk to the SBC from the carrier.</span></span> <span data-ttu-id="4d35f-173">I numeri dei sistemi di telefonia tradizionali risiedevano nel trunk TDM al gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="4d35f-173">The numbers for the traditional telephony systems resided on the TDM trunk to the PSTN gateway.</span></span>   

<span data-ttu-id="4d35f-174">Contoso ha basato la decisione sulle domande seguenti:</span><span class="sxs-lookup"><span data-stu-id="4d35f-174">Contoso based their decision on the following questions:</span></span>

- <span data-ttu-id="4d35f-175">D.</span><span class="sxs-lookup"><span data-stu-id="4d35f-175">Q.</span></span> <span data-ttu-id="4d35f-176">È necessario mantenere le funzionalità fornite dalla distribuzione locale?</span><span class="sxs-lookup"><span data-stu-id="4d35f-176">Do we need to retain functionality provided by our on-premises deployment?</span></span><br>
  <span data-ttu-id="4d35f-177">A.</span><span class="sxs-lookup"><span data-stu-id="4d35f-177">A.</span></span> <span data-ttu-id="4d35f-178">No</span><span class="sxs-lookup"><span data-stu-id="4d35f-178">No</span></span> 

- <span data-ttu-id="4d35f-179">D.</span><span class="sxs-lookup"><span data-stu-id="4d35f-179">Q.</span></span> <span data-ttu-id="4d35f-180">È necessario interoperabilità con sistemi PBX di terze parti e altri dispositivi di telefonia?</span><span class="sxs-lookup"><span data-stu-id="4d35f-180">Do we need to interoperate with third-party PBX systems and other telephony equipment?</span></span><br> <span data-ttu-id="4d35f-181">A. No</span><span class="sxs-lookup"><span data-stu-id="4d35f-181">A. No</span></span> 

- <span data-ttu-id="4d35f-182">D.</span><span class="sxs-lookup"><span data-stu-id="4d35f-182">Q.</span></span> <span data-ttu-id="4d35f-183">È necessario conservare l'attuale gestore di terze parti?</span><span class="sxs-lookup"><span data-stu-id="4d35f-183">Do we need to retain our current third-party carrier?</span></span><br> <span data-ttu-id="4d35f-184">A. No</span><span class="sxs-lookup"><span data-stu-id="4d35f-184">A. No</span></span> 

- <span data-ttu-id="4d35f-185">D.</span><span class="sxs-lookup"><span data-stu-id="4d35f-185">Q.</span></span> <span data-ttu-id="4d35f-186">È necessario distribuire il ROI nei PC SB?</span><span class="sxs-lookup"><span data-stu-id="4d35f-186">Do we need to get the ROI on SBCs deployed?</span></span><br> <span data-ttu-id="4d35f-187">A. Sì e no</span><span class="sxs-lookup"><span data-stu-id="4d35f-187">A. Yes and No</span></span>  

- <span data-ttu-id="4d35f-188">D.</span><span class="sxs-lookup"><span data-stu-id="4d35f-188">Q.</span></span> <span data-ttu-id="4d35f-189">Il piano chiamate PSTN di Microsoft è disponibile in questa area geografica?</span><span class="sxs-lookup"><span data-stu-id="4d35f-189">Is Microsoft's PSTN Calling Plan available in this region?</span></span><br> <span data-ttu-id="4d35f-190">A. No</span><span class="sxs-lookup"><span data-stu-id="4d35f-190">A. No</span></span> 

<span data-ttu-id="4d35f-191">In base alle risposte alle loro domande, Contoso ha deciso quanto segue:</span><span class="sxs-lookup"><span data-stu-id="4d35f-191">Based on the answers to their questions, Contoso decided on the following:</span></span> 

- <span data-ttu-id="4d35f-192">Per gli utenti della telefonia legacy che saranno abilitati per il routing diretto, Contoso ha portato i numeri dal trunk TDM al trunk SIP per SBC, poiché SBC è certificato per l'instradamento diretto.</span><span class="sxs-lookup"><span data-stu-id="4d35f-192">For the legacy telephony users that will be enabled for Direct Routing, Contoso ported the numbers from the TDM trunk to the SIP Trunk for the SBC, since the SBC is certified for Direct Routing.</span></span> 

- <span data-ttu-id="4d35f-193">Per supportare un sottoinsieme di utenti che passano al Sistema telefonico e per consentire il routing continuo attraverso il sistema legacy, il sistema di telefonia legacy è stato configurato come hop successivo al sistema SBC.</span><span class="sxs-lookup"><span data-stu-id="4d35f-193">To support a subset of users moving to Phone System and to allow continued routing through the legacy system, the legacy telephony system was set up as the next hop to the SBC.</span></span>   

- <span data-ttu-id="4d35f-194">Inoltre, per incoraggiare il cambiamento del comportamento dell'utente e rimuovere la dipendenza dalla composizione delle estensioni interso e interne al sito, Contoso ha fornito indicazioni per usare Teams per tutte le chiamate interne.</span><span class="sxs-lookup"><span data-stu-id="4d35f-194">In addition, to encourage user behavior change and remove the dependency on inter- and intra-site extension dialing, Contoso provided guidance to use Teams for all internal calls.</span></span>  

<span data-ttu-id="4d35f-195">I seguenti diagrammi mostrano la distribuzione originale di Skype for Business VoIP aziendale sistema di telefonia legacy e la migrazione a una distribuzione mista con routing diretto:</span><span class="sxs-lookup"><span data-stu-id="4d35f-195">The following diagrams show the original Skype for Business Enterprise Voice and legacy telephony system deployment and the migration to a mixed deployment using Direct Routing:</span></span>

<span data-ttu-id="4d35f-196">**Distribuzione mista originale** 
 ![ Diagramma che mostra lo stato precedente](media/voice-case-study-4.png)</span><span class="sxs-lookup"><span data-stu-id="4d35f-196">**Original mixed deployment**
![Diagram showing before state](media/voice-case-study-4.png)</span></span>

<span data-ttu-id="4d35f-197">**Distribuzione mista con routing diretto** 
 ![ Diagramma che mostra lo stato precedente](media/voice-case-study-4a.png)</span><span class="sxs-lookup"><span data-stu-id="4d35f-197">**Mixed deployment with Direct Routing**
![Diagram showing before state](media/voice-case-study-4a.png)</span></span>


## <a name="calling-plans"></a><span data-ttu-id="4d35f-198">Piani di chiamata</span><span class="sxs-lookup"><span data-stu-id="4d35f-198">Calling Plans</span></span>

<span data-ttu-id="4d35f-199">Per determinare i requisiti di configurazione per i Piani per chiamate, Contoso ha esaminato le decisioni di distribuzione di base [del Piano per chiamate.](calling-plan-landing-page.md#core-deployment-decisions)</span><span class="sxs-lookup"><span data-stu-id="4d35f-199">To determine the configuration requirements for Calling Plans, Contoso reviewed the [Calling Plan core deployment decisions](calling-plan-landing-page.md#core-deployment-decisions).</span></span> <span data-ttu-id="4d35f-200">Sono state prese le decisioni risultanti:</span><span class="sxs-lookup"><span data-stu-id="4d35f-200">The resulting decisions were made:</span></span> 

- <span data-ttu-id="4d35f-201">D.</span><span class="sxs-lookup"><span data-stu-id="4d35f-201">Q.</span></span> <span data-ttu-id="4d35f-202">Gli utenti devono effettuare chiamate internazionali?</span><span class="sxs-lookup"><span data-stu-id="4d35f-202">Do my users need international calling?</span></span><br> <span data-ttu-id="4d35f-203">A. Sì</span><span class="sxs-lookup"><span data-stu-id="4d35f-203">A. Yes</span></span> 

- <span data-ttu-id="4d35f-204">D.</span><span class="sxs-lookup"><span data-stu-id="4d35f-204">Q.</span></span> <span data-ttu-id="4d35f-205">Gli utenti hanno ciascuno un numero di telefono DID diretto verso l'interno?</span><span class="sxs-lookup"><span data-stu-id="4d35f-205">Do my users each have a direct inward DID phone number?</span></span><br> <span data-ttu-id="4d35f-206">A. Non oggi.</span><span class="sxs-lookup"><span data-stu-id="4d35f-206">A. Not today.</span></span> <span data-ttu-id="4d35f-207">Tutti gli utenti abilitati riceveranno un DID.</span><span class="sxs-lookup"><span data-stu-id="4d35f-207">All users enabled will receive a DID.</span></span> 

- <span data-ttu-id="4d35f-208">D.</span><span class="sxs-lookup"><span data-stu-id="4d35f-208">Q.</span></span> <span data-ttu-id="4d35f-209">Si vuole mascherare o disabilitare l'ID chiamante?</span><span class="sxs-lookup"><span data-stu-id="4d35f-209">Do I want to mask or disable caller ID?</span></span><br> <span data-ttu-id="4d35f-210">A. L'ID chiamante di un utente verrà mascherato al numero locale di Contoso.</span><span class="sxs-lookup"><span data-stu-id="4d35f-210">A. The caller ID for a user will be masked to the local number for Contoso.</span></span> 


## <a name="direct-routing"></a><span data-ttu-id="4d35f-211">Routing diretto</span><span class="sxs-lookup"><span data-stu-id="4d35f-211">Direct Routing</span></span>

<span data-ttu-id="4d35f-212">Contoso ha partecipato a Ignite per restare al corrente sulle funzionalità di Office 365, incluse quelle disponibili con Sistema telefonico e Routing diretto.</span><span class="sxs-lookup"><span data-stu-id="4d35f-212">Contoso attended Ignite to stay current on Office 365 features including those available with Phone system and Direct Routing.</span></span> <span data-ttu-id="4d35f-213">I dirigenti tecnici e architetti hanno usato le indicazioni fornite durante la Ignite 2019 per determinare la direzione.</span><span class="sxs-lookup"><span data-stu-id="4d35f-213">Technical leadership and architects used the guidance provided during the Ignite 2019 to determine their direction.</span></span>  <span data-ttu-id="4d35f-214">Sessioni chiave usate:</span><span class="sxs-lookup"><span data-stu-id="4d35f-214">Key sessions that were used:</span></span> 

- [<span data-ttu-id="4d35f-215">Pianificare il successo con l'instradamento diretto di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4d35f-215">Plan for success with Microsoft Teams Direct Routing</span></span>](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)

- [<span data-ttu-id="4d35f-216">Aggiornamenti per il routing diretto</span><span class="sxs-lookup"><span data-stu-id="4d35f-216">Updates for Direct Routing</span></span>](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)


## <a name="configuration"></a><span data-ttu-id="4d35f-217">Configurazione</span><span class="sxs-lookup"><span data-stu-id="4d35f-217">Configuration</span></span>

### <a name="calling-plans-sites"></a><span data-ttu-id="4d35f-218">Siti piani per chiamate</span><span class="sxs-lookup"><span data-stu-id="4d35f-218">Calling Plans sites</span></span>

<span data-ttu-id="4d35f-219">Per ottenere licenze e assegnare numeri di telefono agli utenti, Contoso ha seguito la procedura descritta in [Configurare i piani per chiamate.](set-up-calling-plans.md)</span><span class="sxs-lookup"><span data-stu-id="4d35f-219">To obtain licenses and assign phone numbers to users, Contoso followed the steps in [Set up Calling Plans](set-up-calling-plans.md).</span></span> 

<span data-ttu-id="4d35f-220">Dato il numero di utenti a cui assegnare numeri di telefono, Contoso ha deciso di usare PowerShell per assegnare i numeri di telefono.</span><span class="sxs-lookup"><span data-stu-id="4d35f-220">Due to the number of users that needed to be assigned phone numbers, Contoso decided to use PowerShell to assign the phone numbers.</span></span> <span data-ttu-id="4d35f-221">Per informazioni su come assegnare numeri usando PowerShell, oltre ad &mdash; altre &mdash; impostazioni, Contoso ha usato la panoramica [di Teams su PowerShell.](teams-powershell-overview.md)</span><span class="sxs-lookup"><span data-stu-id="4d35f-221">To learn how to assign numbers by using PowerShell&mdash;in addition to other settings&mdash;Contoso used the [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>  

### <a name="direct-routing-sites"></a><span data-ttu-id="4d35f-222">Siti di routing diretto</span><span class="sxs-lookup"><span data-stu-id="4d35f-222">Direct Routing sites</span></span>

<span data-ttu-id="4d35f-223">Per connettere l'infrastruttura di telefonia locale di Contoso a Microsoft Teams, l'amministratore di Contoso ha seguito la procedura [descritta](direct-routing-configure.md) in Configurare l'instradamento diretto ed esaminato il video Routing diretto in [Microsoft Teams](https://www.youtube.com/watch?v=1ASftX_Msb8&index=10&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl) per indicazioni.</span><span class="sxs-lookup"><span data-stu-id="4d35f-223">To connect Contoso's on-premises telephony infrastructure to Microsoft Teams, Contoso's administrator followed the steps in [Configure Direct Routing](direct-routing-configure.md) and reviewed the video [Direct Routing in Microsoft Teams](https://www.youtube.com/watch?v=1ASftX_Msb8&index=10&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl) for guidance.</span></span>  <span data-ttu-id="4d35f-224">Contoso ha anche fatto riferimento alla documentazione relativa alla distribuzione del routing diretto da parte del fornitore di SBC certificato.</span><span class="sxs-lookup"><span data-stu-id="4d35f-224">Contoso also referred to the Direct routing deployment documentation by the certified SBC vendor.</span></span> 

<span data-ttu-id="4d35f-225">Dopo la configurazione dell'instradamento diretto tra SBC e Sistema telefonico Microsoft, è necessario che Contoso testi la configurazione.</span><span class="sxs-lookup"><span data-stu-id="4d35f-225">Once Direct Routing was configured between the SBC and Microsoft Phone System, it was necessary for Contoso to test the configuration.</span></span> <span data-ttu-id="4d35f-226">A questo scopo, gli amministratori di Contoso hanno usato il client Tester SIP discusso nella sessione Aggiornamenti per il routing diretto [di Ignite 2019.](https://myignite.techcommunity.microsoft.com/sessions/83178?source=sessions)</span><span class="sxs-lookup"><span data-stu-id="4d35f-226">To do this, Contoso administrators used the SIP Tester client that was discussed in the [Updates for Direct Routing session at Ignite 2019](https://myignite.techcommunity.microsoft.com/sessions/83178?source=sessions).</span></span> <span data-ttu-id="4d35f-227">La documentazione e lo script client tester SIP sono stati scaricati dallo script di PowerShell per testare le connessioni al controller dei confini della sessione di routing diretto.</span><span class="sxs-lookup"><span data-stu-id="4d35f-227">The SIP Tester client script and documentation was downloaded from the PowerShell script to test Direct Routing Session Border Controller connections.</span></span>   


### <a name="local-media-optimization"></a><span data-ttu-id="4d35f-228">Ottimizzazione degli elementi multimediali locali</span><span class="sxs-lookup"><span data-stu-id="4d35f-228">Local Media Optimization</span></span>

<span data-ttu-id="4d35f-229">Contoso ha visto l'opportunità di sfruttare l'ottimizzazione multimediale locale nelle diverse aree geografiche del mondo.</span><span class="sxs-lookup"><span data-stu-id="4d35f-229">Contoso saw the opportunity to leverage Local Media Optimization in the different regions across the globe.</span></span> <span data-ttu-id="4d35f-230">Gli scenari supportati per Contoso sono descritti in Ottimizzazione supporto locale [per il routing diretto.](direct-routing-media-optimization.md)</span><span class="sxs-lookup"><span data-stu-id="4d35f-230">The supported scenarios for Contoso are described in [Local Media Optimization for Direct Routing](direct-routing-media-optimization.md).</span></span> <span data-ttu-id="4d35f-231">La configurazione dell'ottimizzazione degli elementi multimediali locali è stata completata seguendo le indicazioni del fornitore di SBC e di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4d35f-231">The configuration of the local media optimization was completed by following guidance from both the SBC vendor and Microsoft.</span></span> <span data-ttu-id="4d35f-232">I passaggi di configurazione per l'ottimizzazione del supporto locale includono:</span><span class="sxs-lookup"><span data-stu-id="4d35f-232">The configuration steps for Local Media Optimization include:</span></span> 

- <span data-ttu-id="4d35f-233">Configurare l'utente e i siti SBC</span><span class="sxs-lookup"><span data-stu-id="4d35f-233">Configure the user and SBC sites</span></span> 

- <span data-ttu-id="4d35f-234">Configurare SBC in base alle specifiche del fornitore di SBC,</span><span class="sxs-lookup"><span data-stu-id="4d35f-234">Configure the SBC  according to the SBC vendor specification,</span></span> 

- <span data-ttu-id="4d35f-235">Aggiungere indirizzi IP attendibili esterni a ogni sito usato per l'ottimizzazione del supporto locale</span><span class="sxs-lookup"><span data-stu-id="4d35f-235">Add external trusted IP addresses to each site used for Local Media Optimization</span></span>    

- <span data-ttu-id="4d35f-236">Definire la topologia della rete</span><span class="sxs-lookup"><span data-stu-id="4d35f-236">Define the network topology</span></span> 

- <span data-ttu-id="4d35f-237">Definire la topologia della rete virtuale</span><span class="sxs-lookup"><span data-stu-id="4d35f-237">Define the virtual network topology</span></span> 

- <span data-ttu-id="4d35f-238">Determinare la modalità: Ignora sempre o Solo per gli utenti locali</span><span class="sxs-lookup"><span data-stu-id="4d35f-238">Determine the mode: Always Bypass or Only for local users</span></span> 

## <a name="networking-considerations"></a><span data-ttu-id="4d35f-239">Considerazioni sulla rete</span><span class="sxs-lookup"><span data-stu-id="4d35f-239">Networking considerations</span></span>

<span data-ttu-id="4d35f-240">Contoso aveva diversi utenti che dovevano lavorare in remoto per un lungo periodo di tempo dopo l'a attivazione del Sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="4d35f-240">Contoso had a number of users who needed to work remotely for an extended period of time after they were enabled for Phone System.</span></span> <span data-ttu-id="4d35f-241">Gli utenti usava la rete VPN per accedere a determinate applicazioni Line of Business.</span><span class="sxs-lookup"><span data-stu-id="4d35f-241">The users used VPN to access certain Line of Business applications.</span></span> <span data-ttu-id="4d35f-242">Mentre si è connessi alla rete VPN, gli utenti del Sistema telefonico hanno riscontrato una riduzione della qualità delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="4d35f-242">While on VPN, the Phone System users experienced a degradation of call quality.</span></span> 

<span data-ttu-id="4d35f-243">Per risolvere il problema della qualità, Contoso ha implementato lo split tunneling VPN, che consentiva al traffico di Office 365 di attraversare Internet mentre la connessione alle app interne rimaneva nella VPN.</span><span class="sxs-lookup"><span data-stu-id="4d35f-243">To resolve the quality issue, Contoso implemented VPN split tunneling, which allowed their Office 365 traffic to traverse the Internet while the connection to the internal apps remained on the VPN.</span></span> <span data-ttu-id="4d35f-244">Per implementare lo split tunneling VPN, Contoso ha seguito le istruzioni per implementare [lo split tunneling VPN per Office 365.](https://docs.microsoft.com/office365/enterprise/office-365-vpn-implement-split-tunnel)</span><span class="sxs-lookup"><span data-stu-id="4d35f-244">To implement VPN split tunneling, Contoso followed the guidance in [Implementing VPN split tunneling for Office 365](https://docs.microsoft.com/office365/enterprise/office-365-vpn-implement-split-tunnel).</span></span>  

 





