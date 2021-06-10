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
ms.openlocfilehash: 995b4ddf9c07dea57c8d4de9940776d5137c2d02
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101032"
---
# <a name="contoso-case-study-phone-system"></a><span data-ttu-id="fe82f-103">Case study contoso: Sistema telefonico</span><span class="sxs-lookup"><span data-stu-id="fe82f-103">Contoso case study: Phone System</span></span>

<span data-ttu-id="fe82f-104">A seconda della posizione geografica e di altri fattori, Contoso aveva uffici che usavano le soluzioni di telefonia seguenti:</span><span class="sxs-lookup"><span data-stu-id="fe82f-104">Depending on geographic location and other factors, Contoso had offices using the following telephony solutions:</span></span>

- <span data-ttu-id="fe82f-105">Tipo di sito A: Skype for Business VoIP aziendale</span><span class="sxs-lookup"><span data-stu-id="fe82f-105">Site Type A: Skype for Business Enterprise Voice</span></span>

- <span data-ttu-id="fe82f-106">Tipo di sito B: Sistemi di telefonia legacy tradizionali</span><span class="sxs-lookup"><span data-stu-id="fe82f-106">Site Type B: Traditional legacy telephony systems</span></span>

- <span data-ttu-id="fe82f-107">Tipo di sito C: Combinazione di Skype for Business VoIP aziendale tradizionali e sistemi di telefonia legacy</span><span class="sxs-lookup"><span data-stu-id="fe82f-107">Site Type C: A combination of Skype for Business Enterprise Voice and traditional legacy telephony systems</span></span>


<span data-ttu-id="fe82f-108">Per implementare una soluzione Telefono Microsoft System per l'intera organizzazione, Contoso ha dovuto determinare per ogni tipo di sito quali delle opzioni seguenti verrebbero usate con Sistema telefonico per connettersi alla rete &mdash; &mdash; PSTN (Public Switched Telephone Network):</span><span class="sxs-lookup"><span data-stu-id="fe82f-108">To implement a Microsoft Phone System solution for their entire organization, Contoso had to determine&mdash;for each site type&mdash;which of the following options would be used with Phone System to connect to the Public Switched Telephone Network (PSTN):</span></span>

- <span data-ttu-id="fe82f-109">Sistema telefonico piano chiamate</span><span class="sxs-lookup"><span data-stu-id="fe82f-109">Phone System with Calling Plan</span></span> 

- <span data-ttu-id="fe82f-110">Sistema telefonico gestore PSTN tramite routing diretto</span><span class="sxs-lookup"><span data-stu-id="fe82f-110">Phone System with own PSTN carrier through Direct Routing</span></span> 

- <span data-ttu-id="fe82f-111">Combinazione di Sistema telefonico piano per chiamate e Sistema telefonico con il proprio gestore PSTN tramite routing diretto</span><span class="sxs-lookup"><span data-stu-id="fe82f-111">Combination of Phone System with Calling Plan and Phone System with own PSTN carrier through Direct Routing</span></span>
 
<span data-ttu-id="fe82f-112">Per determinare la soluzione giusta per l'organizzazione, Contoso ha usato le soluzioni di telefonia [Microsoft](/SkypeForBusiness/hybrid/msft-telephony-solutions) e la sessione Ignite 2019 [Calling in Microsoft Teams](https://myignite.techcommunity.microsoft.com/sessions/83170?source=sessions).</span><span class="sxs-lookup"><span data-stu-id="fe82f-112">To determine the right solution for their organization, Contoso used [Microsoft telephony solutions](/SkypeForBusiness/hybrid/msft-telephony-solutions) and the Ignite 2019 session [Calling in Microsoft Teams](https://myignite.techcommunity.microsoft.com/sessions/83170?source=sessions).</span></span>  

## <a name="site-type-a-skype-for-business-enterprise-voice"></a><span data-ttu-id="fe82f-113">Tipo di sito A: Skype for Business VoIP aziendale</span><span class="sxs-lookup"><span data-stu-id="fe82f-113">Site Type A: Skype for Business Enterprise Voice</span></span> 

<span data-ttu-id="fe82f-114">Contoso Skype for Business VoIP aziendale è stato configurato come hub e ha parlato.</span><span class="sxs-lookup"><span data-stu-id="fe82f-114">Contoso Skype for Business Enterprise Voice was set up as a hub and spoke.</span></span> <span data-ttu-id="fe82f-115">C'era una posizione centrale che ha mantenuto il gateway PSTN nell'area geografica che ha fornito la connessione alla rete PSTN per gli utenti Skype for Business VoIP aziendale nel paese.</span><span class="sxs-lookup"><span data-stu-id="fe82f-115">There was a central location that maintained the PSTN gateway in the region that provided the connection to the PSTN for the Skype for Business Enterprise Voice users in country.</span></span> <span data-ttu-id="fe82f-116">Spesso questi uffici satellitari non hanno una propria uscita Internet.</span><span class="sxs-lookup"><span data-stu-id="fe82f-116">Often these satellite offices did not have their own Internet egress.</span></span> <span data-ttu-id="fe82f-117">I numeri di questi utenti risiedevano nel trunk SIP che si connetteva a un SBC esistente.</span><span class="sxs-lookup"><span data-stu-id="fe82f-117">The numbers for these users resided on the SIP trunk connecting to an existing SBC.</span></span> 

<span data-ttu-id="fe82f-118">Per determinare se la SBC già distribuita è certificata per il routing diretto e il bypass multimediale, Contoso ha controllato l'elenco dei controller di confine di sessione [certificati per il routing diretto.](direct-routing-border-controllers.md)</span><span class="sxs-lookup"><span data-stu-id="fe82f-118">To determine if the SBC already deployed is certified for Direct Routing and Media Bypass, Contoso checked the [List of Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>  

<span data-ttu-id="fe82f-119">Le abitudini di composizione dell'utente erano di comporre un utente nel sistema di telefonia legacy usando un'estensione, anche quando l'utente ha un client Skype for Business disponibile per l'audio peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="fe82f-119">The user's dialing habits were to dial a user on the legacy telephony system using an extension, even when the user has a Skype for Business client available for peer-to-peer audio.</span></span> 

<span data-ttu-id="fe82f-120">Contoso ha basato la propria decisione sulle domande seguenti:</span><span class="sxs-lookup"><span data-stu-id="fe82f-120">Contoso based their decision on the following questions:</span></span>

- <span data-ttu-id="fe82f-121">D.</span><span class="sxs-lookup"><span data-stu-id="fe82f-121">Q.</span></span> <span data-ttu-id="fe82f-122">È necessario mantenere le funzionalità fornite dalla distribuzione locale?</span><span class="sxs-lookup"><span data-stu-id="fe82f-122">Do we need to retain functionality provided by our on-premises deployment?</span></span><br>
  <span data-ttu-id="fe82f-123">A.</span><span class="sxs-lookup"><span data-stu-id="fe82f-123">A.</span></span> <span data-ttu-id="fe82f-124">No</span><span class="sxs-lookup"><span data-stu-id="fe82f-124">No</span></span> 

- <span data-ttu-id="fe82f-125">D.</span><span class="sxs-lookup"><span data-stu-id="fe82f-125">Q.</span></span> <span data-ttu-id="fe82f-126">È necessario interagire con sistemi PBX di terze parti e altre apparecchiature di telefonia?</span><span class="sxs-lookup"><span data-stu-id="fe82f-126">Do we need to interoperate with third-party PBX systems and other telephony equipment?</span></span><br>
  <span data-ttu-id="fe82f-127">A.</span><span class="sxs-lookup"><span data-stu-id="fe82f-127">A.</span></span> <span data-ttu-id="fe82f-128">No</span><span class="sxs-lookup"><span data-stu-id="fe82f-128">No</span></span> 

- <span data-ttu-id="fe82f-129">D.</span><span class="sxs-lookup"><span data-stu-id="fe82f-129">Q.</span></span> <span data-ttu-id="fe82f-130">È necessario conservare l'attuale gestore di terze parti?</span><span class="sxs-lookup"><span data-stu-id="fe82f-130">Do we need to retain our current third-party carrier?</span></span><br> <span data-ttu-id="fe82f-131">A. Sì (paesi regolamentati) e No</span><span class="sxs-lookup"><span data-stu-id="fe82f-131">A. Yes (regulated countries) and No</span></span> 

- <span data-ttu-id="fe82f-132">D.</span><span class="sxs-lookup"><span data-stu-id="fe82f-132">Q.</span></span> <span data-ttu-id="fe82f-133">È necessario distribuire il ROI sugli SBC?</span><span class="sxs-lookup"><span data-stu-id="fe82f-133">Do we need to get the ROI on SBCs deployed?</span></span><br> <span data-ttu-id="fe82f-134">A. Sì e no</span><span class="sxs-lookup"><span data-stu-id="fe82f-134">A. Yes and No</span></span>  

- <span data-ttu-id="fe82f-135">D.</span><span class="sxs-lookup"><span data-stu-id="fe82f-135">Q.</span></span> <span data-ttu-id="fe82f-136">I piani per chiamate PSTN Microsoft sono disponibili in questa area geografica?</span><span class="sxs-lookup"><span data-stu-id="fe82f-136">Is Microsoft PSTN Calling Plans available in this region?</span></span><br> <span data-ttu-id="fe82f-137">A. Sì e no</span><span class="sxs-lookup"><span data-stu-id="fe82f-137">A. Yes and No</span></span> 

<span data-ttu-id="fe82f-138">In base alle risposte alle loro domande, Contoso ha deciso di:</span><span class="sxs-lookup"><span data-stu-id="fe82f-138">Based on the answers to their questions, Contoso decided to:</span></span>

- <span data-ttu-id="fe82f-139">Spostare gli utenti che si trovano in un'area geografica in cui i piani per le chiamate PSTN sono disponibili Sistema telefonico piani per chiamate.</span><span class="sxs-lookup"><span data-stu-id="fe82f-139">Move the users that are located in a region where PSTN calling plans is available to Phone System with Calling Plans.</span></span> 

- <span data-ttu-id="fe82f-140">Spostare gli utenti che non si trovano in un'area geografica in cui sono disponibili piani per le chiamate PSTN, gli utenti che si trovano in un sito in cui il ROI degli SBC deve ancora essere soddisfatto e gli utenti che risiedono in un paese che ha normative di telefonia da Sistema telefonico con routing diretto.</span><span class="sxs-lookup"><span data-stu-id="fe82f-140">Move the users that are not located in a region where PSTN calling plans is available, users located in a site where the ROI on the SBCs have yet to be met, and users that resided in a country that has telephony regulations to Phone System with Direct Routing.</span></span> 

<span data-ttu-id="fe82f-141">Il diagramma seguente mostra la distribuzione Skype for Business VoIP aziendale distribuzione iniziale e come è stata eseguita la migrazione di questa distribuzione ai piani per chiamate Microsoft e al routing diretto:</span><span class="sxs-lookup"><span data-stu-id="fe82f-141">The following diagram shows the initial Skype for Business Enterprise Voice deployment and how this deployment was migrated to both Microsoft Calling Plans and Direct Routing:</span></span>

![Diagramma che mostra gli stati prima e dopo](media/voice-case-study-1.png)

## <a name="site-type-b-traditional-legacy-telephony-systems"></a><span data-ttu-id="fe82f-143">Tipo di sito B: Sistemi di telefonia legacy tradizionali</span><span class="sxs-lookup"><span data-stu-id="fe82f-143">Site Type B: Traditional legacy telephony systems</span></span>

<span data-ttu-id="fe82f-144">Contoso aveva molti uffici che sfruttavano sistemi di telefonia legacy.</span><span class="sxs-lookup"><span data-stu-id="fe82f-144">Contoso had many offices that leveraged legacy telephony systems.</span></span> <span data-ttu-id="fe82f-145">C'era un sottoinsieme di utenti con un numero di telefono E1.64, mentre altri avevano solo un interno.</span><span class="sxs-lookup"><span data-stu-id="fe82f-145">There were a subset of users that had an E1.64 phone number while others only had an extension.</span></span> <span data-ttu-id="fe82f-146">Questi numeri si trovavano nel trunk TDM al gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="fe82f-146">These numbers resided on the TDM trunk to the PSTN gateway.</span></span> <span data-ttu-id="fe82f-147">La composizione all'interno del sito è stata configurata usando un codice del sito davanti all'interno per determinare dove instradare la chiamata.</span><span class="sxs-lookup"><span data-stu-id="fe82f-147">Intra-site dialing was configured by leveraging a site code in front of the extension to determine where to route the call.</span></span> <span data-ttu-id="fe82f-148">Le abitudini di composizione degli utenti erano di comporre per interno.</span><span class="sxs-lookup"><span data-stu-id="fe82f-148">The users' dialing habits were to dial by extension.</span></span>   

<span data-ttu-id="fe82f-149">Contoso ha basato la propria decisione sulle domande seguenti:</span><span class="sxs-lookup"><span data-stu-id="fe82f-149">Contoso based their decision on the following questions:</span></span>

- <span data-ttu-id="fe82f-150">D.</span><span class="sxs-lookup"><span data-stu-id="fe82f-150">Q.</span></span> <span data-ttu-id="fe82f-151">È necessario mantenere le funzionalità fornite dalla distribuzione locale?</span><span class="sxs-lookup"><span data-stu-id="fe82f-151">Do we need to retain functionality provided by our on-premises deployment?</span></span><br>
  <span data-ttu-id="fe82f-152">A.</span><span class="sxs-lookup"><span data-stu-id="fe82f-152">A.</span></span> <span data-ttu-id="fe82f-153">No</span><span class="sxs-lookup"><span data-stu-id="fe82f-153">No</span></span> 

- <span data-ttu-id="fe82f-154">D.</span><span class="sxs-lookup"><span data-stu-id="fe82f-154">Q.</span></span> <span data-ttu-id="fe82f-155">È necessario interagire con sistemi PBX di terze parti e altre apparecchiature di telefonia?</span><span class="sxs-lookup"><span data-stu-id="fe82f-155">Do we need to interoperate with third-party PBX systems and other telephony equipment?</span></span><br> <span data-ttu-id="fe82f-156">A. Sì</span><span class="sxs-lookup"><span data-stu-id="fe82f-156">A. Yes</span></span>

- <span data-ttu-id="fe82f-157">D.</span><span class="sxs-lookup"><span data-stu-id="fe82f-157">Q.</span></span> <span data-ttu-id="fe82f-158">È necessario conservare l'attuale gestore di terze parti?</span><span class="sxs-lookup"><span data-stu-id="fe82f-158">Do we need to retain our current third-party carrier?</span></span><br> <span data-ttu-id="fe82f-159">A. No</span><span class="sxs-lookup"><span data-stu-id="fe82f-159">A. No</span></span> 

- <span data-ttu-id="fe82f-160">D.</span><span class="sxs-lookup"><span data-stu-id="fe82f-160">Q.</span></span> <span data-ttu-id="fe82f-161">Il piano per le chiamate PSTN di Microsoft è disponibile nella nostra area geografica?</span><span class="sxs-lookup"><span data-stu-id="fe82f-161">Is Microsoft PSTN's Calling Plan available in our region?</span></span><br> <span data-ttu-id="fe82f-162">A. Sì e no</span><span class="sxs-lookup"><span data-stu-id="fe82f-162">A. Yes and No</span></span> 

<span data-ttu-id="fe82f-163">In base alle risposte alle loro domande, Contoso ha deciso di:</span><span class="sxs-lookup"><span data-stu-id="fe82f-163">Based on the answers to their questions, Contoso decided to:</span></span> 

- <span data-ttu-id="fe82f-164">Spostare gli utenti che si trovano in un'area geografica in cui i piani per le chiamate PSTN sono disponibili Sistema telefonico piani per chiamate.</span><span class="sxs-lookup"><span data-stu-id="fe82f-164">Move the users that are located in a region where PSTN calling plans is available to Phone System with Calling Plans.</span></span> 

- <span data-ttu-id="fe82f-165">Spostare gli utenti che non si trovano in un'area geografica in cui i piani per le chiamate PSTN sono disponibili Sistema telefonico routing diretto.</span><span class="sxs-lookup"><span data-stu-id="fe82f-165">Move the users that are not located in a region where PSTN calling plans is available to Phone System with Direct Routing.</span></span> 

- <span data-ttu-id="fe82f-166">Mantenere una connessione PSTN a dispositivi analogici aziendali critici.</span><span class="sxs-lookup"><span data-stu-id="fe82f-166">Maintain a PSTN connection to business critical analog devices.</span></span>

<span data-ttu-id="fe82f-167">I diagrammi seguenti mostrano la distribuzione del sistema legacy originale con siti remoti e la migrazione a una distribuzione di Routing diretto con l'ottimizzazione del supporto locale:</span><span class="sxs-lookup"><span data-stu-id="fe82f-167">The following diagrams show the original legacy system deployment with remote sites and the migration to a Direct Routing deployment with Local Media Optimization:</span></span>

<span data-ttu-id="fe82f-168">**Distribuzione legacy originale**  
 ![ Diagramma che mostra gli stati prima e dopo](media/voice-case-study-2.png)</span><span class="sxs-lookup"><span data-stu-id="fe82f-168">**Original legacy deployment** 
![Diagram showing before and after states](media/voice-case-study-2.png)</span></span>


<span data-ttu-id="fe82f-169">**Distribuzione con routing diretto**</span><span class="sxs-lookup"><span data-stu-id="fe82f-169">**Deployment with Direct Routing**</span></span>

![Diagramma che mostra gli stati prima e dopo](media/voice-case-study-3.png)
 
## <a name="site-type-c-combination-of-skype-for-business-enterprise-voice-and-traditional-legacy-telephony-systems"></a><span data-ttu-id="fe82f-171">Tipo di sito C: Combinazione di Skype for Business VoIP aziendale tradizionali sistemi di telefonia legacy</span><span class="sxs-lookup"><span data-stu-id="fe82f-171">Site Type C: Combination of Skype for Business Enterprise Voice and traditional legacy telephony systems</span></span>

<span data-ttu-id="fe82f-172">Contoso Skype for Business VoIP aziendale i numeri degli utenti risiedono nel trunk SIP alla SBC dal gestore.</span><span class="sxs-lookup"><span data-stu-id="fe82f-172">Contoso Skype for Business Enterprise Voice users' numbers reside on the SIP trunk to the SBC from the carrier.</span></span> <span data-ttu-id="fe82f-173">I numeri dei sistemi di telefonia tradizionali si trovavano nel trunk TDM al gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="fe82f-173">The numbers for the traditional telephony systems resided on the TDM trunk to the PSTN gateway.</span></span>   

<span data-ttu-id="fe82f-174">Contoso ha basato la propria decisione sulle domande seguenti:</span><span class="sxs-lookup"><span data-stu-id="fe82f-174">Contoso based their decision on the following questions:</span></span>

- <span data-ttu-id="fe82f-175">D.</span><span class="sxs-lookup"><span data-stu-id="fe82f-175">Q.</span></span> <span data-ttu-id="fe82f-176">È necessario mantenere le funzionalità fornite dalla distribuzione locale?</span><span class="sxs-lookup"><span data-stu-id="fe82f-176">Do we need to retain functionality provided by our on-premises deployment?</span></span><br>
  <span data-ttu-id="fe82f-177">A.</span><span class="sxs-lookup"><span data-stu-id="fe82f-177">A.</span></span> <span data-ttu-id="fe82f-178">No</span><span class="sxs-lookup"><span data-stu-id="fe82f-178">No</span></span> 

- <span data-ttu-id="fe82f-179">D.</span><span class="sxs-lookup"><span data-stu-id="fe82f-179">Q.</span></span> <span data-ttu-id="fe82f-180">È necessario interagire con sistemi PBX di terze parti e altre apparecchiature di telefonia?</span><span class="sxs-lookup"><span data-stu-id="fe82f-180">Do we need to interoperate with third-party PBX systems and other telephony equipment?</span></span><br> <span data-ttu-id="fe82f-181">A. No</span><span class="sxs-lookup"><span data-stu-id="fe82f-181">A. No</span></span> 

- <span data-ttu-id="fe82f-182">D.</span><span class="sxs-lookup"><span data-stu-id="fe82f-182">Q.</span></span> <span data-ttu-id="fe82f-183">È necessario conservare l'attuale gestore di terze parti?</span><span class="sxs-lookup"><span data-stu-id="fe82f-183">Do we need to retain our current third-party carrier?</span></span><br> <span data-ttu-id="fe82f-184">A. No</span><span class="sxs-lookup"><span data-stu-id="fe82f-184">A. No</span></span> 

- <span data-ttu-id="fe82f-185">D.</span><span class="sxs-lookup"><span data-stu-id="fe82f-185">Q.</span></span> <span data-ttu-id="fe82f-186">È necessario distribuire il ROI sugli SBC?</span><span class="sxs-lookup"><span data-stu-id="fe82f-186">Do we need to get the ROI on SBCs deployed?</span></span><br> <span data-ttu-id="fe82f-187">A. Sì e no</span><span class="sxs-lookup"><span data-stu-id="fe82f-187">A. Yes and No</span></span>  

- <span data-ttu-id="fe82f-188">D.</span><span class="sxs-lookup"><span data-stu-id="fe82f-188">Q.</span></span> <span data-ttu-id="fe82f-189">Il piano chiamate PSTN di Microsoft è disponibile in questa area geografica?</span><span class="sxs-lookup"><span data-stu-id="fe82f-189">Is Microsoft's PSTN Calling Plan available in this region?</span></span><br> <span data-ttu-id="fe82f-190">A. No</span><span class="sxs-lookup"><span data-stu-id="fe82f-190">A. No</span></span> 

<span data-ttu-id="fe82f-191">In base alle risposte alle loro domande, Contoso ha deciso quanto segue:</span><span class="sxs-lookup"><span data-stu-id="fe82f-191">Based on the answers to their questions, Contoso decided on the following:</span></span> 

- <span data-ttu-id="fe82f-192">Per gli utenti di telefonia legacy che verranno abilitati per il routing diretto, Contoso ha portato i numeri dal trunk TDM al trunk SIP per SBC, perché SBC è certificato per il routing diretto.</span><span class="sxs-lookup"><span data-stu-id="fe82f-192">For the legacy telephony users that will be enabled for Direct Routing, Contoso ported the numbers from the TDM trunk to the SIP Trunk for the SBC, since the SBC is certified for Direct Routing.</span></span> 

- <span data-ttu-id="fe82f-193">Per supportare un sottoinsieme di utenti che si spostano in Sistema telefonico e per consentire il routing continuo attraverso il sistema legacy, il sistema di telefonia legacy è stato configurato come hop successivo al sistema SBC.</span><span class="sxs-lookup"><span data-stu-id="fe82f-193">To support a subset of users moving to Phone System and to allow continued routing through the legacy system, the legacy telephony system was set up as the next hop to the SBC.</span></span>   

- <span data-ttu-id="fe82f-194">Inoltre, per incoraggiare il cambiamento del comportamento degli utenti e rimuovere la dipendenza dalla composizione interna e interna al sito, Contoso ha fornito indicazioni per usare Teams per tutte le chiamate interne.</span><span class="sxs-lookup"><span data-stu-id="fe82f-194">In addition, to encourage user behavior change and remove the dependency on inter- and intra-site extension dialing, Contoso provided guidance to use Teams for all internal calls.</span></span>  

<span data-ttu-id="fe82f-195">I diagrammi seguenti mostrano la distribuzione originale Skype for Business VoIP aziendale sistema di telefonia legacy e la migrazione a una distribuzione mista con Routing diretto:</span><span class="sxs-lookup"><span data-stu-id="fe82f-195">The following diagrams show the original Skype for Business Enterprise Voice and legacy telephony system deployment and the migration to a mixed deployment using Direct Routing:</span></span>

<span data-ttu-id="fe82f-196">**Distribuzione mista originale** 
 ![ Diagramma che mostra prima dello stato](media/voice-case-study-4.png)</span><span class="sxs-lookup"><span data-stu-id="fe82f-196">**Original mixed deployment**
![Diagram showing before state](media/voice-case-study-4.png)</span></span>

<span data-ttu-id="fe82f-197">**Distribuzione mista con routing diretto** 
 ![ Diagramma che mostra prima dello stato](media/voice-case-study-4a.png)</span><span class="sxs-lookup"><span data-stu-id="fe82f-197">**Mixed deployment with Direct Routing**
![Diagram showing before state](media/voice-case-study-4a.png)</span></span>


## <a name="calling-plans"></a><span data-ttu-id="fe82f-198">Piani di chiamata</span><span class="sxs-lookup"><span data-stu-id="fe82f-198">Calling Plans</span></span>

<span data-ttu-id="fe82f-199">Per determinare i requisiti di configurazione per i piani per chiamate, Contoso ha esaminato le decisioni di distribuzione principali del piano [di chiamata.](calling-plan-landing-page.md#core-deployment-decisions)</span><span class="sxs-lookup"><span data-stu-id="fe82f-199">To determine the configuration requirements for Calling Plans, Contoso reviewed the [Calling Plan core deployment decisions](calling-plan-landing-page.md#core-deployment-decisions).</span></span> <span data-ttu-id="fe82f-200">Le decisioni risultanti sono state prese:</span><span class="sxs-lookup"><span data-stu-id="fe82f-200">The resulting decisions were made:</span></span> 

- <span data-ttu-id="fe82f-201">D.</span><span class="sxs-lookup"><span data-stu-id="fe82f-201">Q.</span></span> <span data-ttu-id="fe82f-202">Gli utenti hanno bisogno di chiamate internazionali?</span><span class="sxs-lookup"><span data-stu-id="fe82f-202">Do my users need international calling?</span></span><br> <span data-ttu-id="fe82f-203">A. Sì</span><span class="sxs-lookup"><span data-stu-id="fe82f-203">A. Yes</span></span> 

- <span data-ttu-id="fe82f-204">D.</span><span class="sxs-lookup"><span data-stu-id="fe82f-204">Q.</span></span> <span data-ttu-id="fe82f-205">Gli utenti hanno un numero di telefono DID diretto verso l'interno?</span><span class="sxs-lookup"><span data-stu-id="fe82f-205">Do my users each have a direct inward DID phone number?</span></span><br> <span data-ttu-id="fe82f-206">A. Non oggi.</span><span class="sxs-lookup"><span data-stu-id="fe82f-206">A. Not today.</span></span> <span data-ttu-id="fe82f-207">Tutti gli utenti abilitati riceveranno un DID.</span><span class="sxs-lookup"><span data-stu-id="fe82f-207">All users enabled will receive a DID.</span></span> 

- <span data-ttu-id="fe82f-208">D.</span><span class="sxs-lookup"><span data-stu-id="fe82f-208">Q.</span></span> <span data-ttu-id="fe82f-209">Si vuole mascherare o disabilitare l'ID chiamante?</span><span class="sxs-lookup"><span data-stu-id="fe82f-209">Do I want to mask or disable caller ID?</span></span><br> <span data-ttu-id="fe82f-210">A. L'ID chiamante di un utente verrà mascherato al numero locale di Contoso.</span><span class="sxs-lookup"><span data-stu-id="fe82f-210">A. The caller ID for a user will be masked to the local number for Contoso.</span></span> 


## <a name="direct-routing"></a><span data-ttu-id="fe82f-211">Routing diretto</span><span class="sxs-lookup"><span data-stu-id="fe82f-211">Direct Routing</span></span>

<span data-ttu-id="fe82f-212">Contoso ha partecipato a Ignite per rimanere al corrente delle Office 365, incluse quelle disponibili con Telefono sistema e Routing diretto.</span><span class="sxs-lookup"><span data-stu-id="fe82f-212">Contoso attended Ignite to stay current on Office 365 features including those available with Phone system and Direct Routing.</span></span> <span data-ttu-id="fe82f-213">I dirigenti tecnici e gli architetti hanno usato le indicazioni fornite durante Ignite 2019 per determinarne la direzione.</span><span class="sxs-lookup"><span data-stu-id="fe82f-213">Technical leadership and architects used the guidance provided during the Ignite 2019 to determine their direction.</span></span>  <span data-ttu-id="fe82f-214">Sessioni chiave usate:</span><span class="sxs-lookup"><span data-stu-id="fe82f-214">Key sessions that were used:</span></span> 

- [<span data-ttu-id="fe82f-215">Pianificare il successo con Microsoft Teams Direct Routing</span><span class="sxs-lookup"><span data-stu-id="fe82f-215">Plan for success with Microsoft Teams Direct Routing</span></span>](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)

- [<span data-ttu-id="fe82f-216">Aggiornamenti per il routing diretto</span><span class="sxs-lookup"><span data-stu-id="fe82f-216">Updates for Direct Routing</span></span>](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)


## <a name="configuration"></a><span data-ttu-id="fe82f-217">Configurazione</span><span class="sxs-lookup"><span data-stu-id="fe82f-217">Configuration</span></span>

### <a name="calling-plans-sites"></a><span data-ttu-id="fe82f-218">Siti dei piani di chiamata</span><span class="sxs-lookup"><span data-stu-id="fe82f-218">Calling Plans sites</span></span>

<span data-ttu-id="fe82f-219">Per ottenere licenze e assegnare numeri di telefono agli utenti, Contoso ha seguito la procedura descritta in [Configurare i piani per chiamate.](set-up-calling-plans.md)</span><span class="sxs-lookup"><span data-stu-id="fe82f-219">To obtain licenses and assign phone numbers to users, Contoso followed the steps in [Set up Calling Plans](set-up-calling-plans.md).</span></span> 

<span data-ttu-id="fe82f-220">A causa del numero di utenti a cui era necessario assegnare i numeri di telefono, Contoso ha deciso di usare PowerShell per assegnare i numeri di telefono.</span><span class="sxs-lookup"><span data-stu-id="fe82f-220">Due to the number of users that needed to be assigned phone numbers, Contoso decided to use PowerShell to assign the phone numbers.</span></span> <span data-ttu-id="fe82f-221">Per informazioni su come assegnare numeri usando PowerShell oltre ad altre impostazioni, Contoso ha usato la &mdash; &mdash; Teams panoramica di [PowerShell.](teams-powershell-overview.md)</span><span class="sxs-lookup"><span data-stu-id="fe82f-221">To learn how to assign numbers by using PowerShell&mdash;in addition to other settings&mdash;Contoso used the [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>  

### <a name="direct-routing-sites"></a><span data-ttu-id="fe82f-222">Siti di routing diretto</span><span class="sxs-lookup"><span data-stu-id="fe82f-222">Direct Routing sites</span></span>

<span data-ttu-id="fe82f-223">Per connettere l'infrastruttura di telefonia locale di Contoso a Microsoft Teams, l'amministratore di Contoso ha seguito i passaggi descritti in [Configurare](direct-routing-configure.md) il routing diretto e ha esaminato il video Routing diretto [in Microsoft Teams](https://www.youtube.com/watch?v=1ASftX_Msb8&index=10&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl) per istruzioni.</span><span class="sxs-lookup"><span data-stu-id="fe82f-223">To connect Contoso's on-premises telephony infrastructure to Microsoft Teams, Contoso's administrator followed the steps in [Configure Direct Routing](direct-routing-configure.md) and reviewed the video [Direct Routing in Microsoft Teams](https://www.youtube.com/watch?v=1ASftX_Msb8&index=10&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl) for guidance.</span></span>  <span data-ttu-id="fe82f-224">Contoso ha anche fatto riferimento alla documentazione relativa alla distribuzione del routing diretto da parte del fornitore SBC certificato.</span><span class="sxs-lookup"><span data-stu-id="fe82f-224">Contoso also referred to the Direct routing deployment documentation by the certified SBC vendor.</span></span> 

<span data-ttu-id="fe82f-225">Dopo aver configurato il routing diretto tra il sistema SBC e Telefono Microsoft, è stato necessario che Contoso testare la configurazione.</span><span class="sxs-lookup"><span data-stu-id="fe82f-225">Once Direct Routing was configured between the SBC and Microsoft Phone System, it was necessary for Contoso to test the configuration.</span></span> <span data-ttu-id="fe82f-226">A questo scopo, gli amministratori di Contoso hanno usato il client TESTER SIP discusso nella sessione Aggiornamenti per il routing diretto in [Ignite 2019.](https://myignite.techcommunity.microsoft.com/sessions/83178?source=sessions)</span><span class="sxs-lookup"><span data-stu-id="fe82f-226">To do this, Contoso administrators used the SIP Tester client that was discussed in the [Updates for Direct Routing session at Ignite 2019](https://myignite.techcommunity.microsoft.com/sessions/83178?source=sessions).</span></span> <span data-ttu-id="fe82f-227">Lo script client e la documentazione del tester SIP sono stati scaricati dallo script di PowerShell per testare le connessioni di Direct Routing Session Border Controller.</span><span class="sxs-lookup"><span data-stu-id="fe82f-227">The SIP Tester client script and documentation was downloaded from the PowerShell script to test Direct Routing Session Border Controller connections.</span></span>   


### <a name="local-media-optimization"></a><span data-ttu-id="fe82f-228">Ottimizzazione del supporto locale</span><span class="sxs-lookup"><span data-stu-id="fe82f-228">Local Media Optimization</span></span>

<span data-ttu-id="fe82f-229">Contoso ha avuto l'opportunità di sfruttare l'Ottimizzazione multimediale locale nelle diverse aree geografiche del globo.</span><span class="sxs-lookup"><span data-stu-id="fe82f-229">Contoso saw the opportunity to leverage Local Media Optimization in the different regions across the globe.</span></span> <span data-ttu-id="fe82f-230">Gli scenari supportati per Contoso sono descritti in [Ottimizzazione multimediale locale per il routing diretto.](direct-routing-media-optimization.md)</span><span class="sxs-lookup"><span data-stu-id="fe82f-230">The supported scenarios for Contoso are described in [Local Media Optimization for Direct Routing](direct-routing-media-optimization.md).</span></span> <span data-ttu-id="fe82f-231">La configurazione dell'ottimizzazione dei supporti multimediali locali è stata completata seguendo le indicazioni del fornitore SBC e di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fe82f-231">The configuration of the local media optimization was completed by following guidance from both the SBC vendor and Microsoft.</span></span> <span data-ttu-id="fe82f-232">I passaggi di configurazione per Ottimizzazione file multimediali locali includono:</span><span class="sxs-lookup"><span data-stu-id="fe82f-232">The configuration steps for Local Media Optimization include:</span></span> 

- <span data-ttu-id="fe82f-233">Configurare l'utente e i siti SBC</span><span class="sxs-lookup"><span data-stu-id="fe82f-233">Configure the user and SBC sites</span></span> 

- <span data-ttu-id="fe82f-234">Configurare SBC in base alla specifica del fornitore SBC,</span><span class="sxs-lookup"><span data-stu-id="fe82f-234">Configure the SBC  according to the SBC vendor specification,</span></span> 

- <span data-ttu-id="fe82f-235">Aggiungere indirizzi IP attendibili esterni a ogni sito usato per l'ottimizzazione dei supporti locali</span><span class="sxs-lookup"><span data-stu-id="fe82f-235">Add external trusted IP addresses to each site used for Local Media Optimization</span></span>    

- <span data-ttu-id="fe82f-236">Definire la topologia di rete</span><span class="sxs-lookup"><span data-stu-id="fe82f-236">Define the network topology</span></span> 

- <span data-ttu-id="fe82f-237">Definire la topologia della rete virtuale</span><span class="sxs-lookup"><span data-stu-id="fe82f-237">Define the virtual network topology</span></span> 

- <span data-ttu-id="fe82f-238">Determinare la modalità: Ignora sempre o Solo per gli utenti locali</span><span class="sxs-lookup"><span data-stu-id="fe82f-238">Determine the mode: Always Bypass or Only for local users</span></span> 

## <a name="networking-considerations"></a><span data-ttu-id="fe82f-239">Considerazioni sulla rete</span><span class="sxs-lookup"><span data-stu-id="fe82f-239">Networking considerations</span></span>

<span data-ttu-id="fe82f-240">Contoso aveva un certo numero di utenti che dovevano lavorare in remoto per un lungo periodo di tempo dopo essere stati abilitati per Sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="fe82f-240">Contoso had a number of users who needed to work remotely for an extended period of time after they were enabled for Phone System.</span></span> <span data-ttu-id="fe82f-241">Gli utenti hanno usato vpn per accedere a determinate applicazioni Line of Business.</span><span class="sxs-lookup"><span data-stu-id="fe82f-241">The users used VPN to access certain Line of Business applications.</span></span> <span data-ttu-id="fe82f-242">Mentre si è connessi a una rete VPN, Sistema telefonico utenti hanno riscontrato una riduzione della qualità delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="fe82f-242">While on VPN, the Phone System users experienced a degradation of call quality.</span></span> 

<span data-ttu-id="fe82f-243">Per risolvere il problema della qualità, Contoso ha implementato il split tunneling VPN, che ha consentito al traffico Office 365 di attraversare Internet mentre la connessione alle app interne rimaneva nella VPN.</span><span class="sxs-lookup"><span data-stu-id="fe82f-243">To resolve the quality issue, Contoso implemented VPN split tunneling, which allowed their Office 365 traffic to traverse the Internet while the connection to the internal apps remained on the VPN.</span></span> <span data-ttu-id="fe82f-244">Per implementare il split tunneling VPN, Contoso ha seguito le indicazioni in Implementazione del [split tunneling VPN per Office 365](/office365/enterprise/office-365-vpn-implement-split-tunnel).</span><span class="sxs-lookup"><span data-stu-id="fe82f-244">To implement VPN split tunneling, Contoso followed the guidance in [Implementing VPN split tunneling for Office 365](/office365/enterprise/office-365-vpn-implement-split-tunnel).</span></span>  

