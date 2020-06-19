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
ms.openlocfilehash: 7431515d40550a3f731c34f97ed8c10586424901
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786024"
---
# <a name="contoso-case-study-phone-system"></a><span data-ttu-id="ab4f0-103">Case Study di Contoso: sistema telefonico</span><span class="sxs-lookup"><span data-stu-id="ab4f0-103">Contoso case study: Phone System</span></span>

<span data-ttu-id="ab4f0-104">A seconda della posizione geografica e di altri fattori, Contoso ha avuto uffici usando le soluzioni di telefonia seguenti:</span><span class="sxs-lookup"><span data-stu-id="ab4f0-104">Depending on geographic location and other factors, Contoso had offices using the following telephony solutions:</span></span>

- <span data-ttu-id="ab4f0-105">Tipo di sito A: Skype for Business Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="ab4f0-105">Site Type A: Skype for Business Enterprise Voice</span></span>

- <span data-ttu-id="ab4f0-106">Tipo di sito B: sistemi di telefonia legacy tradizionali</span><span class="sxs-lookup"><span data-stu-id="ab4f0-106">Site Type B: Traditional legacy telephony systems</span></span>

- <span data-ttu-id="ab4f0-107">Tipo di sito C: una combinazione di Skype for Business Enterprise Voice e sistemi di telefonia legacy tradizionali</span><span class="sxs-lookup"><span data-stu-id="ab4f0-107">Site Type C: A combination of Skype for Business Enterprise Voice and traditional legacy telephony systems</span></span>


<span data-ttu-id="ab4f0-108">Per implementare una soluzione di sistema telefonico Microsoft per l'intera organizzazione, Contoso ha dovuto determinare &mdash; per ogni tipo di sito &mdash; quale delle opzioni seguenti verrebbero usate con il sistema telefonico per connettersi alla rete PSTN (Public Switched Telephone Network):</span><span class="sxs-lookup"><span data-stu-id="ab4f0-108">To implement a Microsoft Phone System solution for their entire organization, Contoso had to determine&mdash;for each site type&mdash;which of the following options would be used with Phone System to connect to the Public Switched Telephone Network (PSTN):</span></span>

- <span data-ttu-id="ab4f0-109">Sistema telefonico con un piano per le chiamate</span><span class="sxs-lookup"><span data-stu-id="ab4f0-109">Phone System with Calling Plan</span></span> 

- <span data-ttu-id="ab4f0-110">Sistema telefonico con il proprio gestore PSTN tramite routing diretto</span><span class="sxs-lookup"><span data-stu-id="ab4f0-110">Phone System with own PSTN carrier through Direct Routing</span></span> 

- <span data-ttu-id="ab4f0-111">Combinazione di sistema telefonico con piano per chiamate e sistema telefonico con il proprio gestore PSTN tramite routing diretto</span><span class="sxs-lookup"><span data-stu-id="ab4f0-111">Combination of Phone System with Calling Plan and Phone System with own PSTN carrier through Direct Routing</span></span>
 
<span data-ttu-id="ab4f0-112">Per determinare la soluzione appropriata per la propria organizzazione, Contoso ha usato le [soluzioni di telefonia Microsoft](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions) e le [chiamate di sessione Ignite 2019 in Microsoft teams](https://myignite.techcommunity.microsoft.com/sessions/83170?source=sessions).</span><span class="sxs-lookup"><span data-stu-id="ab4f0-112">To determine the right solution for their organization, Contoso used [Microsoft telephony solutions](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions) and the Ignite 2019 session [Calling in Microsoft Teams](https://myignite.techcommunity.microsoft.com/sessions/83170?source=sessions).</span></span>  

## <a name="site-type-a-skype-for-business-enterprise-voice"></a><span data-ttu-id="ab4f0-113">Tipo di sito A: Skype for Business Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="ab4f0-113">Site Type A: Skype for Business Enterprise Voice</span></span> 

<span data-ttu-id="ab4f0-114">Contoso Skype for Business Enterprise Voice è stato configurato come hub e spoke.</span><span class="sxs-lookup"><span data-stu-id="ab4f0-114">Contoso Skype for Business Enterprise Voice was set up as a hub and spoke.</span></span> <span data-ttu-id="ab4f0-115">Esiste una posizione centrale che ha mantenuto il gateway PSTN nell'area che ha fornito la connessione alla rete PSTN per gli utenti di Skype for Business VoIP Enterprise nel paese.</span><span class="sxs-lookup"><span data-stu-id="ab4f0-115">There was a central location that maintained the PSTN gateway in the region that provided the connection to the PSTN for the Skype for Business Enterprise Voice users in country.</span></span> <span data-ttu-id="ab4f0-116">Spesso questi uffici satellitari non avevano una propria uscita Internet.</span><span class="sxs-lookup"><span data-stu-id="ab4f0-116">Often these satellite offices did not have their own Internet egress.</span></span> <span data-ttu-id="ab4f0-117">I numeri per questi utenti risiedevano nel trunk SIP che si connette a un SBC esistente.</span><span class="sxs-lookup"><span data-stu-id="ab4f0-117">The numbers for these users resided on the SIP trunk connecting to an existing SBC.</span></span> 

<span data-ttu-id="ab4f0-118">Per determinare se il SBC già distribuito è certificato per il routing diretto e il bypass multimediale, Contoso ha controllato l' [elenco dei controller di bordo della sessione certificati per il routing diretto](direct-routing-border-controllers.md).</span><span class="sxs-lookup"><span data-stu-id="ab4f0-118">To determine if the SBC already deployed is certified for Direct Routing and Media Bypass, Contoso checked the [List of Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>  

<span data-ttu-id="ab4f0-119">Le abitudini di chiamata dell'utente erano di chiamare un utente nel sistema di telefonia legacy usando un'estensione, anche quando l'utente ha un client Skype for business disponibile per l'audio peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="ab4f0-119">The user's dialing habits were to dial a user on the legacy telephony system using an extension, even when the user has a Skype for Business client available for peer-to-peer audio.</span></span> 

<span data-ttu-id="ab4f0-120">Contoso ha basato la propria decisione sulle seguenti domande:</span><span class="sxs-lookup"><span data-stu-id="ab4f0-120">Contoso based their decision on the following questions:</span></span>

- <span data-ttu-id="ab4f0-121">Q.</span><span class="sxs-lookup"><span data-stu-id="ab4f0-121">Q.</span></span> <span data-ttu-id="ab4f0-122">È necessario mantenere le funzionalità fornite dalla distribuzione locale?</span><span class="sxs-lookup"><span data-stu-id="ab4f0-122">Do we need to retain functionality provided by our on-premises deployment?</span></span><br>
  <span data-ttu-id="ab4f0-123">Un.</span><span class="sxs-lookup"><span data-stu-id="ab4f0-123">A.</span></span> <span data-ttu-id="ab4f0-124">No</span><span class="sxs-lookup"><span data-stu-id="ab4f0-124">No</span></span> 

- <span data-ttu-id="ab4f0-125">Q.</span><span class="sxs-lookup"><span data-stu-id="ab4f0-125">Q.</span></span> <span data-ttu-id="ab4f0-126">È necessario interagire con sistemi PBX di terze parti e altre apparecchiature per la telefonia?</span><span class="sxs-lookup"><span data-stu-id="ab4f0-126">Do we need to interoperate with third-party PBX systems and other telephony equipment?</span></span><br>
  <span data-ttu-id="ab4f0-127">Un.</span><span class="sxs-lookup"><span data-stu-id="ab4f0-127">A.</span></span> <span data-ttu-id="ab4f0-128">No</span><span class="sxs-lookup"><span data-stu-id="ab4f0-128">No</span></span> 

- <span data-ttu-id="ab4f0-129">Q.</span><span class="sxs-lookup"><span data-stu-id="ab4f0-129">Q.</span></span> <span data-ttu-id="ab4f0-130">È necessario mantenere l'attuale vettore di terze parti?</span><span class="sxs-lookup"><span data-stu-id="ab4f0-130">Do we need to retain our current third-party carrier?</span></span><br> <span data-ttu-id="ab4f0-131">A. Sì (paesi regolamentati) e no</span><span class="sxs-lookup"><span data-stu-id="ab4f0-131">A. Yes (regulated countries) and No</span></span> 

- <span data-ttu-id="ab4f0-132">Q.</span><span class="sxs-lookup"><span data-stu-id="ab4f0-132">Q.</span></span> <span data-ttu-id="ab4f0-133">È necessario ottenere il ROI su SBCs distribuito?</span><span class="sxs-lookup"><span data-stu-id="ab4f0-133">Do we need to get the ROI on SBCs deployed?</span></span><br> <span data-ttu-id="ab4f0-134">A. Sì e no</span><span class="sxs-lookup"><span data-stu-id="ab4f0-134">A. Yes and No</span></span>  

- <span data-ttu-id="ab4f0-135">Q.</span><span class="sxs-lookup"><span data-stu-id="ab4f0-135">Q.</span></span> <span data-ttu-id="ab4f0-136">I piani per le chiamate PSTN Microsoft sono disponibili nell'area geografica?</span><span class="sxs-lookup"><span data-stu-id="ab4f0-136">Is Microsoft PSTN Calling Plans available in this region?</span></span><br> <span data-ttu-id="ab4f0-137">A. Sì e no</span><span class="sxs-lookup"><span data-stu-id="ab4f0-137">A. Yes and No</span></span> 

<span data-ttu-id="ab4f0-138">In base alle risposte alle proprie domande, Contoso ha deciso di:</span><span class="sxs-lookup"><span data-stu-id="ab4f0-138">Based on the answers to their questions, Contoso decided to:</span></span>

- <span data-ttu-id="ab4f0-139">Consente di trasferire gli utenti che si trovano in un'area geografica in cui i piani per chiamate PSTN sono disponibili per il sistema telefonico con piani di chiamata.</span><span class="sxs-lookup"><span data-stu-id="ab4f0-139">Move the users that are located in a region where PSTN calling plans is available to Phone System with Calling Plans.</span></span> 

- <span data-ttu-id="ab4f0-140">Consente di trasferire gli utenti che non si trovano in un'area geografica in cui sono disponibili piani per chiamate PSTN, gli utenti che si trovano in un sito in cui il ROI del SBCs deve ancora essere soddisfatto e gli utenti che hanno risieduto in un paese con regole di telefonia per il sistema telefonico con routing diretto.</span><span class="sxs-lookup"><span data-stu-id="ab4f0-140">Move the users that are not located in a region where PSTN calling plans is available, users located in a site where the ROI on the SBCs have yet to be met, and users that resided in a country that has telephony regulations to Phone System with Direct Routing.</span></span> 

<span data-ttu-id="ab4f0-141">Il diagramma seguente mostra la distribuzione vocale iniziale di Skype for business e il modo in cui questa distribuzione è stata migrata sia in piani di chiamate Microsoft che in routing diretto:</span><span class="sxs-lookup"><span data-stu-id="ab4f0-141">The following diagram shows the initial Skype for Business Enterprise Voice deployment and how this deployment was migrated to both Microsoft Calling Plans and Direct Routing:</span></span>

![Diagramma che Mostra gli stati prima e dopo](media/voice-case-study-1.png)

## <a name="site-type-b-traditional-legacy-telephony-systems"></a><span data-ttu-id="ab4f0-143">Tipo di sito B: sistemi di telefonia legacy tradizionali</span><span class="sxs-lookup"><span data-stu-id="ab4f0-143">Site Type B: Traditional legacy telephony systems</span></span>

<span data-ttu-id="ab4f0-144">Contoso ha molti uffici che sfruttano sistemi di telefonia legacy.</span><span class="sxs-lookup"><span data-stu-id="ab4f0-144">Contoso had many offices that leveraged legacy telephony systems.</span></span> <span data-ttu-id="ab4f0-145">C'è stato un sottoinsieme di utenti che avevano un numero di telefono E 1.64, mentre altri avevano solo un'estensione.</span><span class="sxs-lookup"><span data-stu-id="ab4f0-145">There were a subset of users that had an E1.64 phone number while others only had an extension.</span></span> <span data-ttu-id="ab4f0-146">Questi numeri risiedevano nel trunk TDM per il gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="ab4f0-146">These numbers resided on the TDM trunk to the PSTN gateway.</span></span> <span data-ttu-id="ab4f0-147">La configurazione intra-sito è stata configurata sfruttando un codice del sito davanti all'estensione per determinare dove instradare la chiamata.</span><span class="sxs-lookup"><span data-stu-id="ab4f0-147">Intra-site dialing was configured by leveraging a site code in front of the extension to determine where to route the call.</span></span> <span data-ttu-id="ab4f0-148">Le abitudini di chiamata degli utenti dovevano effettuare la chiamata tramite estensione.</span><span class="sxs-lookup"><span data-stu-id="ab4f0-148">The users' dialing habits were to dial by extension.</span></span>   

<span data-ttu-id="ab4f0-149">Contoso ha basato la propria decisione sulle seguenti domande:</span><span class="sxs-lookup"><span data-stu-id="ab4f0-149">Contoso based their decision on the following questions:</span></span>

- <span data-ttu-id="ab4f0-150">Q.</span><span class="sxs-lookup"><span data-stu-id="ab4f0-150">Q.</span></span> <span data-ttu-id="ab4f0-151">È necessario mantenere le funzionalità fornite dalla distribuzione locale?</span><span class="sxs-lookup"><span data-stu-id="ab4f0-151">Do we need to retain functionality provided by our on-premises deployment?</span></span><br>
  <span data-ttu-id="ab4f0-152">Un.</span><span class="sxs-lookup"><span data-stu-id="ab4f0-152">A.</span></span> <span data-ttu-id="ab4f0-153">No</span><span class="sxs-lookup"><span data-stu-id="ab4f0-153">No</span></span> 

- <span data-ttu-id="ab4f0-154">Q.</span><span class="sxs-lookup"><span data-stu-id="ab4f0-154">Q.</span></span> <span data-ttu-id="ab4f0-155">È necessario interagire con sistemi PBX di terze parti e altre apparecchiature per la telefonia?</span><span class="sxs-lookup"><span data-stu-id="ab4f0-155">Do we need to interoperate with third-party PBX systems and other telephony equipment?</span></span><br> <span data-ttu-id="ab4f0-156">A. Sì</span><span class="sxs-lookup"><span data-stu-id="ab4f0-156">A. Yes</span></span>

- <span data-ttu-id="ab4f0-157">Q.</span><span class="sxs-lookup"><span data-stu-id="ab4f0-157">Q.</span></span> <span data-ttu-id="ab4f0-158">È necessario mantenere l'attuale vettore di terze parti?</span><span class="sxs-lookup"><span data-stu-id="ab4f0-158">Do we need to retain our current third-party carrier?</span></span><br> <span data-ttu-id="ab4f0-159">A. No</span><span class="sxs-lookup"><span data-stu-id="ab4f0-159">A. No</span></span> 

- <span data-ttu-id="ab4f0-160">Q.</span><span class="sxs-lookup"><span data-stu-id="ab4f0-160">Q.</span></span> <span data-ttu-id="ab4f0-161">Il piano per le chiamate di Microsoft PSTN è disponibile nell'area geografica?</span><span class="sxs-lookup"><span data-stu-id="ab4f0-161">Is Microsoft PSTN's Calling Plan available in our region?</span></span><br> <span data-ttu-id="ab4f0-162">A. Sì e no</span><span class="sxs-lookup"><span data-stu-id="ab4f0-162">A. Yes and No</span></span> 

<span data-ttu-id="ab4f0-163">In base alle risposte alle proprie domande, Contoso ha deciso di:</span><span class="sxs-lookup"><span data-stu-id="ab4f0-163">Based on the answers to their questions, Contoso decided to:</span></span> 

- <span data-ttu-id="ab4f0-164">Consente di trasferire gli utenti che si trovano in un'area geografica in cui i piani per chiamate PSTN sono disponibili per il sistema telefonico con piani di chiamata.</span><span class="sxs-lookup"><span data-stu-id="ab4f0-164">Move the users that are located in a region where PSTN calling plans is available to Phone System with Calling Plans.</span></span> 

- <span data-ttu-id="ab4f0-165">Consente di trasferire gli utenti che non si trovano in un'area geografica in cui i piani per chiamate PSTN sono disponibili per il sistema telefonico con routing diretto.</span><span class="sxs-lookup"><span data-stu-id="ab4f0-165">Move the users that are not located in a region where PSTN calling plans is available to Phone System with Direct Routing.</span></span> 

- <span data-ttu-id="ab4f0-166">Gestire una connessione PSTN a dispositivi analogici business critical.</span><span class="sxs-lookup"><span data-stu-id="ab4f0-166">Maintain a PSTN connection to business critical analog devices.</span></span>

<span data-ttu-id="ab4f0-167">I diagrammi seguenti mostrano la distribuzione originale del sistema legacy con i siti remoti e la migrazione a una distribuzione di routing diretto con l'ottimizzazione media locale:</span><span class="sxs-lookup"><span data-stu-id="ab4f0-167">The following diagrams show the original legacy system deployment with remote sites and the migration to a Direct Routing deployment with Local Media Optimization:</span></span>

<span data-ttu-id="ab4f0-168">**Original legacy deployment**  
 Distribuzione ![ legacy originale Diagramma che Mostra gli stati prima e dopo](media/voice-case-study-2.png)</span><span class="sxs-lookup"><span data-stu-id="ab4f0-168">**Original legacy deployment** 
![Diagram showing before and after states](media/voice-case-study-2.png)</span></span>


<span data-ttu-id="ab4f0-169">**Distribuzione con routing diretto**</span><span class="sxs-lookup"><span data-stu-id="ab4f0-169">**Deployment with Direct Routing**</span></span>

![Diagramma che Mostra gli stati prima e dopo](media/voice-case-study-3.png)
 
## <a name="site-type-c-combination-of-skype-for-business-enterprise-voice-and-traditional-legacy-telephony-systems"></a><span data-ttu-id="ab4f0-171">Tipo di sito C: combinazione di Skype for Business Enterprise Voice e sistemi di telefonia legacy tradizionali</span><span class="sxs-lookup"><span data-stu-id="ab4f0-171">Site Type C: Combination of Skype for Business Enterprise Voice and traditional legacy telephony systems</span></span>

<span data-ttu-id="ab4f0-172">I numeri di utenti di VoIP Skype for Business Enterprise di Contoso si trovano nel trunk SIP verso il SBC dal vettore.</span><span class="sxs-lookup"><span data-stu-id="ab4f0-172">Contoso Skype for Business Enterprise Voice users' numbers reside on the SIP trunk to the SBC from the carrier.</span></span> <span data-ttu-id="ab4f0-173">I numeri per i sistemi di telefonia tradizionali risiedevano nel trunk TDM per il gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="ab4f0-173">The numbers for the traditional telephony systems resided on the TDM trunk to the PSTN gateway.</span></span>   

<span data-ttu-id="ab4f0-174">Contoso ha basato la propria decisione sulle seguenti domande:</span><span class="sxs-lookup"><span data-stu-id="ab4f0-174">Contoso based their decision on the following questions:</span></span>

- <span data-ttu-id="ab4f0-175">Q.</span><span class="sxs-lookup"><span data-stu-id="ab4f0-175">Q.</span></span> <span data-ttu-id="ab4f0-176">È necessario mantenere le funzionalità fornite dalla distribuzione locale?</span><span class="sxs-lookup"><span data-stu-id="ab4f0-176">Do we need to retain functionality provided by our on-premises deployment?</span></span><br>
  <span data-ttu-id="ab4f0-177">Un.</span><span class="sxs-lookup"><span data-stu-id="ab4f0-177">A.</span></span> <span data-ttu-id="ab4f0-178">No</span><span class="sxs-lookup"><span data-stu-id="ab4f0-178">No</span></span> 

- <span data-ttu-id="ab4f0-179">Q.</span><span class="sxs-lookup"><span data-stu-id="ab4f0-179">Q.</span></span> <span data-ttu-id="ab4f0-180">È necessario interagire con sistemi PBX di terze parti e altre apparecchiature per la telefonia?</span><span class="sxs-lookup"><span data-stu-id="ab4f0-180">Do we need to interoperate with third-party PBX systems and other telephony equipment?</span></span><br> <span data-ttu-id="ab4f0-181">A. No</span><span class="sxs-lookup"><span data-stu-id="ab4f0-181">A. No</span></span> 

- <span data-ttu-id="ab4f0-182">Q.</span><span class="sxs-lookup"><span data-stu-id="ab4f0-182">Q.</span></span> <span data-ttu-id="ab4f0-183">È necessario mantenere l'attuale vettore di terze parti?</span><span class="sxs-lookup"><span data-stu-id="ab4f0-183">Do we need to retain our current third-party carrier?</span></span><br> <span data-ttu-id="ab4f0-184">A. No</span><span class="sxs-lookup"><span data-stu-id="ab4f0-184">A. No</span></span> 

- <span data-ttu-id="ab4f0-185">Q.</span><span class="sxs-lookup"><span data-stu-id="ab4f0-185">Q.</span></span> <span data-ttu-id="ab4f0-186">È necessario ottenere il ROI su SBCs distribuito?</span><span class="sxs-lookup"><span data-stu-id="ab4f0-186">Do we need to get the ROI on SBCs deployed?</span></span><br> <span data-ttu-id="ab4f0-187">A. Sì e no</span><span class="sxs-lookup"><span data-stu-id="ab4f0-187">A. Yes and No</span></span>  

- <span data-ttu-id="ab4f0-188">Q.</span><span class="sxs-lookup"><span data-stu-id="ab4f0-188">Q.</span></span> <span data-ttu-id="ab4f0-189">Il piano per le chiamate PSTN di Microsoft è disponibile nell'area geografica?</span><span class="sxs-lookup"><span data-stu-id="ab4f0-189">Is Microsoft's PSTN Calling Plan available in this region?</span></span><br> <span data-ttu-id="ab4f0-190">A. No</span><span class="sxs-lookup"><span data-stu-id="ab4f0-190">A. No</span></span> 

<span data-ttu-id="ab4f0-191">In base alle risposte alle proprie domande, Contoso ha deciso di eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ab4f0-191">Based on the answers to their questions, Contoso decided on the following:</span></span> 

- <span data-ttu-id="ab4f0-192">Per gli utenti di telefonia legacy che verranno abilitati per il routing diretto, Contoso ha convertito i numeri dal trunk TDM al trunk SIP per il SBC, poiché il SBC è certificato per il routing diretto.</span><span class="sxs-lookup"><span data-stu-id="ab4f0-192">For the legacy telephony users that will be enabled for Direct Routing, Contoso ported the numbers from the TDM trunk to the SIP Trunk for the SBC, since the SBC is certified for Direct Routing.</span></span> 

- <span data-ttu-id="ab4f0-193">Per supportare un sottoinsieme di utenti che si spostano nel sistema telefonico e per consentire il routing continuo attraverso il sistema legacy, il sistema di telefonia legacy è stato configurato come hop successivo per il SBC.</span><span class="sxs-lookup"><span data-stu-id="ab4f0-193">To support a subset of users moving to Phone System and to allow continued routing through the legacy system, the legacy telephony system was set up as the next hop to the SBC.</span></span>   

- <span data-ttu-id="ab4f0-194">Inoltre, per incoraggiare il comportamento degli utenti a modificare e rimuovere la dipendenza dalla chiamata alle estensioni Inter-e intra-sito, Contoso ha fornito indicazioni per l'uso di team per tutte le chiamate interne.</span><span class="sxs-lookup"><span data-stu-id="ab4f0-194">In addition, to encourage user behavior change and remove the dependency on inter- and intra-site extension dialing, Contoso provided guidance to use Teams for all internal calls.</span></span>  

<span data-ttu-id="ab4f0-195">I diagrammi seguenti illustrano la distribuzione originale di Skype for Business Enterprise Voice e legacy sistema di telefonia e la migrazione a una distribuzione mista tramite routing diretto:</span><span class="sxs-lookup"><span data-stu-id="ab4f0-195">The following diagrams show the original Skype for Business Enterprise Voice and legacy telephony system deployment and the migration to a mixed deployment using Direct Routing:</span></span>

<span data-ttu-id="ab4f0-196">**Original mixed deployment** 
 Distribuzione ![ mista originale Diagramma che mostra prima dello stato](media/voice-case-study-4.png)</span><span class="sxs-lookup"><span data-stu-id="ab4f0-196">**Original mixed deployment**
![Diagram showing before state](media/voice-case-study-4.png)</span></span>

<span data-ttu-id="ab4f0-197">**Distribuzione mista con routing diretto** 
 ![ Diagramma che mostra prima dello stato](media/voice-case-study-4a.png)</span><span class="sxs-lookup"><span data-stu-id="ab4f0-197">**Mixed deployment with Direct Routing**
![Diagram showing before state](media/voice-case-study-4a.png)</span></span>


## <a name="calling-plans"></a><span data-ttu-id="ab4f0-198">Piani di chiamata</span><span class="sxs-lookup"><span data-stu-id="ab4f0-198">Calling Plans</span></span>

<span data-ttu-id="ab4f0-199">Per determinare i requisiti di configurazione per i piani di chiamata, Contoso ha esaminato le [decisioni di distribuzione di base del piano chiamante](calling-plan-landing-page.md#core-deployment-decisions).</span><span class="sxs-lookup"><span data-stu-id="ab4f0-199">To determine the configuration requirements for Calling Plans, Contoso reviewed the [Calling Plan core deployment decisions](calling-plan-landing-page.md#core-deployment-decisions).</span></span> <span data-ttu-id="ab4f0-200">Le decisioni risultanti sono state apportate:</span><span class="sxs-lookup"><span data-stu-id="ab4f0-200">The resulting decisions were made:</span></span> 

- <span data-ttu-id="ab4f0-201">Q.</span><span class="sxs-lookup"><span data-stu-id="ab4f0-201">Q.</span></span> <span data-ttu-id="ab4f0-202">I miei utenti hanno bisogno di chiamate internazionali?</span><span class="sxs-lookup"><span data-stu-id="ab4f0-202">Do my users need international calling?</span></span><br> <span data-ttu-id="ab4f0-203">A. Sì</span><span class="sxs-lookup"><span data-stu-id="ab4f0-203">A. Yes</span></span> 

- <span data-ttu-id="ab4f0-204">Q.</span><span class="sxs-lookup"><span data-stu-id="ab4f0-204">Q.</span></span> <span data-ttu-id="ab4f0-205">I miei utenti hanno ciascuno un numero di telefono diretto verso l'interno?</span><span class="sxs-lookup"><span data-stu-id="ab4f0-205">Do my users each have a direct inward DID phone number?</span></span><br> <span data-ttu-id="ab4f0-206">A. non oggi.</span><span class="sxs-lookup"><span data-stu-id="ab4f0-206">A. Not today.</span></span> <span data-ttu-id="ab4f0-207">Tutti gli utenti abilitati riceveranno un DID.</span><span class="sxs-lookup"><span data-stu-id="ab4f0-207">All users enabled will receive a DID.</span></span> 

- <span data-ttu-id="ab4f0-208">Q.</span><span class="sxs-lookup"><span data-stu-id="ab4f0-208">Q.</span></span> <span data-ttu-id="ab4f0-209">Si vuole mascherare o disabilitare l'ID chiamante?</span><span class="sxs-lookup"><span data-stu-id="ab4f0-209">Do I want to mask or disable caller ID?</span></span><br> <span data-ttu-id="ab4f0-210">A. l'ID chiamante per un utente verrà mascherato al numero locale per contoso.</span><span class="sxs-lookup"><span data-stu-id="ab4f0-210">A. The caller ID for a user will be masked to the local number for Contoso.</span></span> 


## <a name="direct-routing"></a><span data-ttu-id="ab4f0-211">Routing diretto</span><span class="sxs-lookup"><span data-stu-id="ab4f0-211">Direct Routing</span></span>

<span data-ttu-id="ab4f0-212">Contoso ha partecipato a Ignite per mantenersi aggiornati sulle caratteristiche di Office 365, incluse quelle disponibili con il sistema telefonico e il routing diretto.</span><span class="sxs-lookup"><span data-stu-id="ab4f0-212">Contoso attended Ignite to stay current on Office 365 features including those available with Phone system and Direct Routing.</span></span> <span data-ttu-id="ab4f0-213">La leadership tecnica e gli architetti hanno usato le indicazioni fornite durante l'accensione 2019 per determinarne la direzione.</span><span class="sxs-lookup"><span data-stu-id="ab4f0-213">Technical leadership and architects used the guidance provided during the Ignite 2019 to determine their direction.</span></span>  <span data-ttu-id="ab4f0-214">Sessioni chiave usate:</span><span class="sxs-lookup"><span data-stu-id="ab4f0-214">Key sessions that were used:</span></span> 

- [<span data-ttu-id="ab4f0-215">Pianificare il successo con il routing diretto di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ab4f0-215">Plan for success with Microsoft Teams Direct Routing</span></span>](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)

- [<span data-ttu-id="ab4f0-216">Aggiornamenti per il routing diretto</span><span class="sxs-lookup"><span data-stu-id="ab4f0-216">Updates for Direct Routing</span></span>](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)


## <a name="configuration"></a><span data-ttu-id="ab4f0-217">Configurazione</span><span class="sxs-lookup"><span data-stu-id="ab4f0-217">Configuration</span></span>

### <a name="calling-plans-sites"></a><span data-ttu-id="ab4f0-218">Siti di piani di chiamata</span><span class="sxs-lookup"><span data-stu-id="ab4f0-218">Calling Plans sites</span></span>

<span data-ttu-id="ab4f0-219">Per ottenere licenze e assegnare numeri di telefono agli utenti, Contoso ha seguito la procedura descritta in [configurare i piani](set-up-calling-plans.md)per le chiamate.</span><span class="sxs-lookup"><span data-stu-id="ab4f0-219">To obtain licenses and assign phone numbers to users, Contoso followed the steps in [Set up Calling Plans](set-up-calling-plans.md).</span></span> 

<span data-ttu-id="ab4f0-220">A causa del numero di utenti a cui devono essere assegnati i numeri di telefono, Contoso ha deciso di usare PowerShell per assegnare i numeri di telefono.</span><span class="sxs-lookup"><span data-stu-id="ab4f0-220">Due to the number of users that needed to be assigned phone numbers, Contoso decided to use PowerShell to assign the phone numbers.</span></span> <span data-ttu-id="ab4f0-221">Per informazioni su come assegnare numeri usando PowerShell &mdash; oltre ad altre impostazioni, &mdash; Contoso ha usato la [Panoramica di PowerShell per Teams](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="ab4f0-221">To learn how to assign numbers by using PowerShell&mdash;in addition to other settings&mdash;Contoso used the [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>  

### <a name="direct-routing-sites"></a><span data-ttu-id="ab4f0-222">Siti di routing diretto</span><span class="sxs-lookup"><span data-stu-id="ab4f0-222">Direct Routing sites</span></span>

<span data-ttu-id="ab4f0-223">Per connettere l'infrastruttura di telefonia locale di Contoso a Microsoft teams, l'amministratore di Contoso ha seguito la procedura descritta in [configurare il routing diretto](direct-routing-configure.md) e ha esaminato il video [Direct routing in Microsoft teams](https://www.youtube.com/watch?v=1ASftX_Msb8&index=10&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl) per le indicazioni.</span><span class="sxs-lookup"><span data-stu-id="ab4f0-223">To connect Contoso's on-premises telephony infrastructure to Microsoft Teams, Contoso's administrator followed the steps in [Configure Direct Routing](direct-routing-configure.md) and reviewed the video [Direct Routing in Microsoft Teams](https://www.youtube.com/watch?v=1ASftX_Msb8&index=10&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl) for guidance.</span></span>  <span data-ttu-id="ab4f0-224">Contoso ha inoltre fatto riferimento alla documentazione relativa alla distribuzione diretta del routing da parte del fornitore SBC certificato.</span><span class="sxs-lookup"><span data-stu-id="ab4f0-224">Contoso also referred to the Direct routing deployment documentation by the certified SBC vendor.</span></span> 

<span data-ttu-id="ab4f0-225">Una volta configurato il routing diretto tra SBC e il sistema telefonico Microsoft, era necessario che contoso provasse la configurazione.</span><span class="sxs-lookup"><span data-stu-id="ab4f0-225">Once Direct Routing was configured between the SBC and Microsoft Phone System, it was necessary for Contoso to test the configuration.</span></span> <span data-ttu-id="ab4f0-226">A questo scopo, gli amministratori di Contoso hanno usato il client tester SIP discusso nella [sessione aggiornamenti per il routing diretto in ignite 2019](https://myignite.techcommunity.microsoft.com/sessions/83178?source=sessions).</span><span class="sxs-lookup"><span data-stu-id="ab4f0-226">To do this, Contoso administrators used the SIP Tester client that was discussed in the [Updates for Direct Routing session at Ignite 2019](https://myignite.techcommunity.microsoft.com/sessions/83178?source=sessions).</span></span> <span data-ttu-id="ab4f0-227">Lo script client del tester SIP e la documentazione sono stati scaricati dallo script di PowerShell per testare le connessioni del controller di bordo della sessione di routing diretto.</span><span class="sxs-lookup"><span data-stu-id="ab4f0-227">The SIP Tester client script and documentation was downloaded from the PowerShell script to test Direct Routing Session Border Controller connections.</span></span>   


### <a name="local-media-optimization"></a><span data-ttu-id="ab4f0-228">Ottimizzazione media locale</span><span class="sxs-lookup"><span data-stu-id="ab4f0-228">Local Media Optimization</span></span>

<span data-ttu-id="ab4f0-229">Contoso ha visto l'opportunità di sfruttare l'ottimizzazione dei contenuti multimediali locali nelle diverse aree geografiche in tutto il mondo.</span><span class="sxs-lookup"><span data-stu-id="ab4f0-229">Contoso saw the opportunity to leverage Local Media Optimization in the different regions across the globe.</span></span> <span data-ttu-id="ab4f0-230">Gli scenari supportati per Contoso sono descritti nell' [ottimizzazione di elementi multimediali locali per il routing diretto](direct-routing-media-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="ab4f0-230">The supported scenarios for Contoso are described in [Local Media Optimization for Direct Routing](direct-routing-media-optimization.md).</span></span> <span data-ttu-id="ab4f0-231">La configurazione dell'Ottimizzazione multimediale locale è stata completata seguendo le indicazioni del fornitore SBC e Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ab4f0-231">The configuration of the local media optimization was completed by following guidance from both the SBC vendor and Microsoft.</span></span> <span data-ttu-id="ab4f0-232">I passaggi di configurazione per l'ottimizzazione di elementi multimediali locali includono:</span><span class="sxs-lookup"><span data-stu-id="ab4f0-232">The configuration steps for Local Media Optimization include:</span></span> 

- <span data-ttu-id="ab4f0-233">Configurare i siti utente e SBC</span><span class="sxs-lookup"><span data-stu-id="ab4f0-233">Configure the user and SBC sites</span></span> 

- <span data-ttu-id="ab4f0-234">Configurare SBC in base alla specifica del fornitore SBC,</span><span class="sxs-lookup"><span data-stu-id="ab4f0-234">Configure the SBC  according to the SBC vendor specification,</span></span> 

- <span data-ttu-id="ab4f0-235">Aggiungere indirizzi IP attendibili esterni a ogni sito usato per l'ottimizzazione media locale</span><span class="sxs-lookup"><span data-stu-id="ab4f0-235">Add external trusted IP addresses to each site used for Local Media Optimization</span></span>    

- <span data-ttu-id="ab4f0-236">Definire la topologia di rete</span><span class="sxs-lookup"><span data-stu-id="ab4f0-236">Define the network topology</span></span> 

- <span data-ttu-id="ab4f0-237">Definire la topologia di rete virtuale</span><span class="sxs-lookup"><span data-stu-id="ab4f0-237">Define the virtual network topology</span></span> 

- <span data-ttu-id="ab4f0-238">Determinare la modalità: aggirare sempre o solo per gli utenti locali</span><span class="sxs-lookup"><span data-stu-id="ab4f0-238">Determine the mode: Always Bypass or Only for local users</span></span> 

## <a name="networking-considerations"></a><span data-ttu-id="ab4f0-239">Considerazioni sulla rete</span><span class="sxs-lookup"><span data-stu-id="ab4f0-239">Networking considerations</span></span>

<span data-ttu-id="ab4f0-240">Contoso ha avuto un numero di utenti che avevano bisogno di lavorare in remoto per un periodo di tempo prolungato dopo l'abilitazione per il sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="ab4f0-240">Contoso had a number of users who needed to work remotely for an extended period of time after they were enabled for Phone System.</span></span> <span data-ttu-id="ab4f0-241">Gli utenti hanno usato la VPN per accedere ad alcune applicazioni della linea di business.</span><span class="sxs-lookup"><span data-stu-id="ab4f0-241">The users used VPN to access certain Line of Business applications.</span></span> <span data-ttu-id="ab4f0-242">Mentre si è in VPN, gli utenti del sistema telefonico hanno sperimentato una degradazione della qualità delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="ab4f0-242">While on VPN, the Phone System users experienced a degradation of call quality.</span></span> 

<span data-ttu-id="ab4f0-243">Per risolvere il problema di qualità, Contoso ha implementato il tunneling Split VPN, che ha consentito al traffico di Office 365 di attraversare Internet mentre la connessione alle app interne rimaneva nella VPN.</span><span class="sxs-lookup"><span data-stu-id="ab4f0-243">To resolve the quality issue, Contoso implemented VPN split tunneling, which allowed their Office 365 traffic to traverse the Internet while the connection to the internal apps remained on the VPN.</span></span> <span data-ttu-id="ab4f0-244">Per implementare il tunneling Split VPN, Contoso ha seguito le indicazioni per l' [implementazione del tunneling Split VPN per Office 365](https://docs.microsoft.com/office365/enterprise/office-365-vpn-implement-split-tunnel).</span><span class="sxs-lookup"><span data-stu-id="ab4f0-244">To implement VPN split tunneling, Contoso followed the guidance in [Implementing VPN split tunneling for Office 365](https://docs.microsoft.com/office365/enterprise/office-365-vpn-implement-split-tunnel).</span></span>  

 





