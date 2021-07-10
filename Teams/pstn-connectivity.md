---
title: Opzioni di connettività PSTN
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 07/08/2021
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- M365-voice
- m365initiative-voice
- m365solution-voice
- m365solution-scenario
ms.reviewer: crowe
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.cloudvoice
- seo-marvel-apr2020
- seo-marvel-may2020
search.appverid: MET150
description: Altre informazioni sulle opzioni Teams chiamate (connettività PSTN) e sulle decisioni che verranno prese per l'organizzazione.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5b1b06178b269529b1d0227ff02d529c91ba1480
ms.sourcegitcommit: 5720fa12bdabdfc2988bf835c8cf95e4d64fa54e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2021
ms.locfileid: "53354518"
---
# <a name="pstn-connectivity-options"></a><span data-ttu-id="0722c-103">Opzioni di connettività PSTN</span><span class="sxs-lookup"><span data-stu-id="0722c-103">PSTN connectivity options</span></span>

<span data-ttu-id="0722c-104">Microsoft offre funzionalità COMPLETE Private Branch Exchange (PBX) per l'organizzazione tramite Sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="0722c-104">Microsoft provides complete Private Branch Exchange (PBX) capabilities for your organization through Phone System.</span></span> <span data-ttu-id="0722c-105">Tuttavia, per consentire agli utenti di effettuare chiamate all'esterno dell'organizzazione, è necessario connettersi Sistema telefonico rete PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="0722c-105">However, to enable users to make calls outside your organization, you need to connect Phone System to the Public Switched Telephone Network (PSTN).</span></span>

<span data-ttu-id="0722c-106">Questo articolo è in particolare sulle opzioni di connettività PSTN.</span><span class="sxs-lookup"><span data-stu-id="0722c-106">This article focuses on PSTN connectivity options.</span></span> <span data-ttu-id="0722c-107">Per altre informazioni sulle soluzioni vocali Microsoft, per informazioni dettagliate sulle funzionalità Sistema telefonico, vedere Pianificare la Teams [vocale.](cloud-voice-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="0722c-107">For more information about Microsoft voice solutions, incuding details about Phone System features, see [Plan your Teams voice solution](cloud-voice-landing-page.md).</span></span>

<span data-ttu-id="0722c-108">Per connettersi Sistema telefonico alla rete PSTN, è possibile scegliere tra le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0722c-108">To connect Phone System to the PSTN, you can choose from the following options:</span></span>

- <span data-ttu-id="0722c-109">[**Piano chiamate**](#phone-system-with-calling-plan).</span><span class="sxs-lookup"><span data-stu-id="0722c-109">[**Calling Plan**](#phone-system-with-calling-plan).</span></span> <span data-ttu-id="0722c-110">Una soluzione all-in-the-cloud con Microsoft come gestore PSTN.</span><span class="sxs-lookup"><span data-stu-id="0722c-110">An all-in-the-cloud solution with Microsoft as your PSTN carrier.</span></span>

- <span data-ttu-id="0722c-111">[**Routing diretto**](#phone-system-with-direct-routing), che consente di usare il proprio gestore PSTN collegando i controller di bordo della sessione (SBC) a Sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="0722c-111">[**Direct Routing**](#phone-system-with-direct-routing), which enables you to use your own PSTN carrier by connecting your Session Border Controller(s) (SBC) to Phone System.</span></span>

- <span data-ttu-id="0722c-112">[**Operatore Connessione**](#phone-system-with-operator-connect), attualmente disponibile solo **nell'anteprima pubblica.**</span><span class="sxs-lookup"><span data-stu-id="0722c-112">[**Operator Connect**](#phone-system-with-operator-connect), which is currently available only in **public preview.**</span></span>  <span data-ttu-id="0722c-113">Con Operator Connessione, se il gestore esistente è un partecipante al programma Microsoft Operator Connessione, può gestire le chiamate PSTN e i session border controller (SBC).</span><span class="sxs-lookup"><span data-stu-id="0722c-113">With Operator Connect, if your existing carrier is a participant in the Microsoft Operator Connect program, they can manage PSTN calling and Session Border Controllers (SBCs).</span></span> 

<span data-ttu-id="0722c-114">È anche possibile scegliere una combinazione di opzioni, che consente di progettare una soluzione per un ambiente complesso o di gestire una migrazione in più passaggi.</span><span class="sxs-lookup"><span data-stu-id="0722c-114">You can also choose a combination of options, which enables you to design a solution for a complex environment, or manage a multi-step migration.</span></span>

<span data-ttu-id="0722c-115">Tenere presente che l'opzione o le opzioni selezionate influiscono sulla configurazione di Sistema telefonico caratteristiche.</span><span class="sxs-lookup"><span data-stu-id="0722c-115">Be aware that the option or options you choose affect how some Phone System features are configured.</span></span> <span data-ttu-id="0722c-116">Per altre informazioni, vedere [Considerazioni sulla configurazione](#configuration-considerations) più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="0722c-116">For more information, see [Configuration considerations](#configuration-considerations) later in this article.</span></span>


## <a name="phone-system-with-calling-plan"></a><span data-ttu-id="0722c-117">Sistema telefonico piano chiamate</span><span class="sxs-lookup"><span data-stu-id="0722c-117">Phone System with Calling Plan</span></span> 

<span data-ttu-id="0722c-118">Sistema telefonico piano chiamate è la soluzione vocale all-in-the-cloud di Microsoft per Teams utenti.</span><span class="sxs-lookup"><span data-stu-id="0722c-118">Phone System with Calling Plan is Microsoft's all-in-the-cloud voice solution for Teams users.</span></span> <span data-ttu-id="0722c-119">Questa è l'opzione più semplice che Sistema telefonico alla rete PSTN.</span><span class="sxs-lookup"><span data-stu-id="0722c-119">This is the simplest option that connects Phone System to the PSTN.</span></span> <span data-ttu-id="0722c-120">Con questa opzione, Microsoft funge da gestore PSTN, come illustrato nel diagramma seguente:</span><span class="sxs-lookup"><span data-stu-id="0722c-120">With this option, Microsoft acts as your PSTN carrier, as shown in the following diagram:</span></span>

![Il diagramma 1 mostra Sistema telefonico piano per chiamate](media/voice-solutions-simple.png)

<span data-ttu-id="0722c-122">Se si risponde sì a quanto segue, Sistema telefonico piano per chiamate è la soluzione giusta per te:</span><span class="sxs-lookup"><span data-stu-id="0722c-122">If you answer yes to the following, then Phone System with Calling Plan is the right solution for you:</span></span>

- <span data-ttu-id="0722c-123">Piano chiamate è disponibile nella tua area geografica.</span><span class="sxs-lookup"><span data-stu-id="0722c-123">Calling Plan is available in your region.</span></span>
- <span data-ttu-id="0722c-124">Non è necessario conservare il gestore PSTN corrente.</span><span class="sxs-lookup"><span data-stu-id="0722c-124">You do not need to retain your current PSTN carrier.</span></span>
- <span data-ttu-id="0722c-125">Si vuole usare l'accesso gestito da Microsoft alla rete PSTN.</span><span class="sxs-lookup"><span data-stu-id="0722c-125">You want to use Microsoft-managed access to the PSTN.</span></span>

<span data-ttu-id="0722c-126">Con questa opzione:</span><span class="sxs-lookup"><span data-stu-id="0722c-126">With this option:</span></span> 

- <span data-ttu-id="0722c-127">Si ottiene Telefono Microsoft sistema con l'aggiunta di piani per chiamate nazionali o internazionali che consentono di chiamare verso telefoni di tutto il mondo (a seconda del livello di servizio concesso in licenza).</span><span class="sxs-lookup"><span data-stu-id="0722c-127">You get Microsoft Phone System with added Domestic or International Calling Plans that enable calling to phones around the world (depending on the level of service being licensed).</span></span>

- <span data-ttu-id="0722c-128">Non è necessario eseguire la distribuzione o la manutenzione di una distribuzione locale perché il piano di chiamata funziona &mdash; Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0722c-128">You do not require deployment or maintenance of an on-premises deployment&mdash;because Calling Plan operates out of Microsoft 365.</span></span>

- <span data-ttu-id="0722c-129">Nota: se necessario, è possibile scegliere di connettere un session border controller (SBC) supportato tramite Direct Routing per garantire l'interoperabilità con sistemi IPX di terze parti, dispositivi analogici e altre apparecchiature di telefonia di terze parti supportate da SBC.</span><span class="sxs-lookup"><span data-stu-id="0722c-129">Note: If necessary, you can choose to connect a supported Session Border Controller (SBC) through Direct Routing for interoperability with third-party PBXs, analog devices, and other third-party telephony equipment supported by the SBC.</span></span>

<span data-ttu-id="0722c-130">Questa opzione richiede una connessione ininterrotta Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0722c-130">This option requires uninterrupted connection to Microsoft 365.</span></span>

<span data-ttu-id="0722c-131">Per altre informazioni sul piano chiamate, vedere gli articoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="0722c-131">For more information about Calling Plan, see the following articles:</span></span>

- [<span data-ttu-id="0722c-132">Qual è il piano di chiamata adatto alle proprie esigenze?</span><span class="sxs-lookup"><span data-stu-id="0722c-132">Which Calling Plan is right for you?</span></span>](calling-plan-landing-page.md)
- [<span data-ttu-id="0722c-133">Come acquistare un piano di chiamata</span><span class="sxs-lookup"><span data-stu-id="0722c-133">How to buy a Calling Plan</span></span>](calling-plans-for-office-365.md)
- [<span data-ttu-id="0722c-134">Disponibilità di Piano di chiamata in Paesi e aree geografiche</span><span class="sxs-lookup"><span data-stu-id="0722c-134">Country and region availability for Calling Plan</span></span>](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
- [<span data-ttu-id="0722c-135">Configurare il piano per le chiamate</span><span class="sxs-lookup"><span data-stu-id="0722c-135">Set up Calling Plan</span></span>](set-up-calling-plans.md)


## <a name="phone-system-with-direct-routing"></a><span data-ttu-id="0722c-136">Sistema telefonico con routing diretto</span><span class="sxs-lookup"><span data-stu-id="0722c-136">Phone System with Direct Routing</span></span>

<span data-ttu-id="0722c-137">Questa opzione consente Sistema telefonico alla rete di telefonia tramite Routing diretto, come illustrato nel diagramma seguente:</span><span class="sxs-lookup"><span data-stu-id="0722c-137">This option connects Phone System to your telephony network by using Direct Routing, as shown in the following diagram:</span></span> 

![Il diagramma 5 mostra Sistema telefonico routing diretto](media/voice-solution-with-direct-routing.png)

<span data-ttu-id="0722c-139">Se si risponde sì alle domande seguenti, Sistema telefonico il routing diretto è la soluzione giusta:</span><span class="sxs-lookup"><span data-stu-id="0722c-139">If you answer yes to the following questions, then Phone System with Direct Routing is the right solution for you:</span></span>

- <span data-ttu-id="0722c-140">Si vuole usare le Teams con Sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="0722c-140">You want to use Teams with Phone System.</span></span>
- <span data-ttu-id="0722c-141">È necessario conservare il gestore PSTN corrente.</span><span class="sxs-lookup"><span data-stu-id="0722c-141">You need to retain your current PSTN carrier.</span></span>
- <span data-ttu-id="0722c-142">Vuoi combinare l'instradamento, con alcune chiamate che attraversano il Piano chiamate, altre tramite il tuo gestore.</span><span class="sxs-lookup"><span data-stu-id="0722c-142">You want to mix routing, with some calls going through Calling Plan, some through your carrier.</span></span>
- <span data-ttu-id="0722c-143">È necessario interagire con sistemi PBX e/o apparecchiature di terze parti, ad esempio test di paginazione, dispositivi analogici e così via.</span><span class="sxs-lookup"><span data-stu-id="0722c-143">You need to interoperate with third-party PBXs and/or equipment such us overhead pagers, analog devices, and so on.</span></span>

<span data-ttu-id="0722c-144">Con questa opzione:</span><span class="sxs-lookup"><span data-stu-id="0722c-144">With this option:</span></span>

- <span data-ttu-id="0722c-145">È possibile connettere il proprio session border controller (SBC) supportato a Sistema telefonico senza la necessità di software locale aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="0722c-145">You connect your own supported Session Border Controller (SBC) to Phone System without the need for additional on-premises software.</span></span>

- <span data-ttu-id="0722c-146">È possibile usare praticamente qualsiasi gestore di telefonia con Sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="0722c-146">You can use virtually any telephony carrier with Phone System.</span></span>

- <span data-ttu-id="0722c-147">È possibile scegliere di configurare e gestire questa opzione oppure può essere configurata e gestita dal gestore o dal partner (chiedere se il gestore o il partner fornisce questa opzione).</span><span class="sxs-lookup"><span data-stu-id="0722c-147">You can choose to configure and manage this option, or it can be configured and managed by your carrier or partner (ask if your carrier or partner provides this option).</span></span>

- <span data-ttu-id="0722c-148">È possibile configurare l'interoperabilità tra le apparecchiature di telefonia, ad esempio un PBX di terze parti e dispositivi &mdash; analogici &mdash; e Sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="0722c-148">You can configure interoperability between your telephony equipment&mdash;such as a third-party PBX and analog devices&mdash;and Phone System.</span></span>

<span data-ttu-id="0722c-149">Questa opzione richiede quanto segue:</span><span class="sxs-lookup"><span data-stu-id="0722c-149">This option requires the following:</span></span>

- <span data-ttu-id="0722c-150">Connessione ininterrotta a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0722c-150">Uninterrupted connection to Microsoft 365.</span></span>

- <span data-ttu-id="0722c-151">Distribuzione e gestione di un SBC supportato.</span><span class="sxs-lookup"><span data-stu-id="0722c-151">Deploying and maintaining a supported SBC.</span></span>

- <span data-ttu-id="0722c-152">Contratto con un gestore di terze parti.</span><span class="sxs-lookup"><span data-stu-id="0722c-152">A contract with a third-party carrier.</span></span>
  <span data-ttu-id="0722c-153">(A meno che non venga distribuita come opzione per fornire la connessione a PBX di terze parti, dispositivi analogici o altre apparecchiature di telefonia per gli utenti che Sistema telefonico con piano chiamate.</span><span class="sxs-lookup"><span data-stu-id="0722c-153">(Unless deployed as an option to provide connection to third-party PBX, analog devices, or other telephony equipment for users who are on Phone System with Calling Plan.)</span></span>

<span data-ttu-id="0722c-154">Per altre informazioni sul routing diretto, vedere gli articoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="0722c-154">For more information about Direct Routing, see the following articles:</span></span>

- [<span data-ttu-id="0722c-155">Pianificare Instradamento diretto</span><span class="sxs-lookup"><span data-stu-id="0722c-155">Plan Direct Routing</span></span>](direct-routing-plan.md)
- [<span data-ttu-id="0722c-156">Configurare Instradamento diretto</span><span class="sxs-lookup"><span data-stu-id="0722c-156">Configure Direct Routing</span></span>](direct-routing-configure.md)
- [<span data-ttu-id="0722c-157">Gestire i criteri di routing vocale per l'uso con Routing diretto</span><span class="sxs-lookup"><span data-stu-id="0722c-157">Manage voice routing policies for use with Direct Routing</span></span>](manage-voice-routing-policies.md)
- [<span data-ttu-id="0722c-158">Pianificare l'instradamento basato sulla posizione per Instradamento diretto</span><span class="sxs-lookup"><span data-stu-id="0722c-158">Plan Location-Based Routing for Direct Routing</span></span>](location-based-routing-plan.md)
- [<span data-ttu-id="0722c-159">Elenco di Session Border Controller certificati per Instradamento diretto</span><span class="sxs-lookup"><span data-stu-id="0722c-159">List of Session Border Controllers certified for Direct Routing</span></span>](direct-routing-border-controllers.md)


## <a name="phone-system-with-operator-connect"></a><span data-ttu-id="0722c-160">Sistema telefonico con operatore Connessione</span><span class="sxs-lookup"><span data-stu-id="0722c-160">Phone System with Operator Connect</span></span>

<span data-ttu-id="0722c-161">Con Operator Connessione, attualmente in anteprima pubblica, se il gestore esistente è un partecipante al programma Microsoft Operator Connessione, può gestire il servizio per portare le chiamate PSTN in Teams.</span><span class="sxs-lookup"><span data-stu-id="0722c-161">With Operator Connect, currently in public preview, if your existing carrier is a participant in the Microsoft Operator Connect program, they can manage the service for bringing PSTN calling to Teams.</span></span> <span data-ttu-id="0722c-162">Il gestore gestisce i servizi di chiamata PSTN e i session border controller (SBC), consentendo di risparmiare sull'acquisto e la gestione dell'hardware.</span><span class="sxs-lookup"><span data-stu-id="0722c-162">Your carrier manages the PSTN calling services and Session Border Controllers (SBCs), allowing you to save on hardware purchase and management.</span></span>

<span data-ttu-id="0722c-163">La Connessione operatore potrebbe essere la soluzione giusta per l'organizzazione se:</span><span class="sxs-lookup"><span data-stu-id="0722c-163">Operator Connect might be the right solution for your organization if:</span></span>

- <span data-ttu-id="0722c-164">Microsoft Calling Plan non è disponibile nella tua posizione geografica.</span><span class="sxs-lookup"><span data-stu-id="0722c-164">Microsoft Calling Plan isn't available in your geographic location.</span></span>
- <span data-ttu-id="0722c-165">Il gestore preferito è un partecipante al programma Microsoft Operator Connessione.</span><span class="sxs-lookup"><span data-stu-id="0722c-165">Your preferred carrier is a participant in the Microsoft Operator Connect program.</span></span>
- <span data-ttu-id="0722c-166">Si vuole trovare un nuovo gestore per abilitare le chiamate in Teams.</span><span class="sxs-lookup"><span data-stu-id="0722c-166">You want to find a new carrier to enable calling in Teams.</span></span>

<span data-ttu-id="0722c-167">Per informazioni sui vantaggi e i requisiti dell'operatore Connessione e per un elenco dei corrieri che partecipano a questo programma, vedere Pianificare l'operatore [Connessione](operator-connect-plan.md).</span><span class="sxs-lookup"><span data-stu-id="0722c-167">For information on the benefits and requirements of Operator Connect, and for a list of carriers participating in this program, see [Plan Operator Connect](operator-connect-plan.md).</span></span> <span data-ttu-id="0722c-168">Per informazioni su come configurare l'operatore Connessione, vedere [Configurare le](operator-connect-configure.md)impostazioni Connessione .</span><span class="sxs-lookup"><span data-stu-id="0722c-168">For information on how to configure Operator Connect, see [Configure Operator Connect](operator-connect-configure.md).</span></span>

## <a name="configuration-considerations"></a><span data-ttu-id="0722c-169">Considerazioni sulla configurazione</span><span class="sxs-lookup"><span data-stu-id="0722c-169">Configuration considerations</span></span>

<span data-ttu-id="0722c-170">La Sistema telefonico caratteristiche sono le stesse indipendentemente dall'opzione di connettività PSTN scelta.</span><span class="sxs-lookup"><span data-stu-id="0722c-170">Most Phone System features are the same regardless of the PSTN connectivity option you choose.</span></span> <span data-ttu-id="0722c-171">Ad esempio, le impostazioni di chiamata senza risposta e inoltro, trasferimento di chiamata, musica personalizzata in attesa, parcheggio di chiamata, linea condivisa e app vocali sono tutte disponibili.</span><span class="sxs-lookup"><span data-stu-id="0722c-171">For example, call unanswered and forwarding settings, call transfer, custom music on hold, call park, shared line, and voice apps are all available.</span></span> <span data-ttu-id="0722c-172">Per un elenco completo delle Sistema telefonico, vedere Ecco cosa si ottiene con [Sistema telefonico.](here-s-what-you-get-with-phone-system.md)</span><span class="sxs-lookup"><span data-stu-id="0722c-172">For a complete list of Phone System features, see [Here's what you get with Phone System](here-s-what-you-get-with-phone-system.md).</span></span>

<span data-ttu-id="0722c-173">Esistono tuttavia alcune differenze di funzionalità che influiscono sulla modalità di configurazione di alcune Sistema telefonico funzionalità.</span><span class="sxs-lookup"><span data-stu-id="0722c-173">There are some differences in functionality, however, that affect how you configure certain Phone System features.</span></span> <span data-ttu-id="0722c-174">Ad esempio, Il routing diretto richiede altri passaggi per configurare il routing delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="0722c-174">For example, Direct Routing requires additional steps to configure call routing.</span></span> <span data-ttu-id="0722c-175">Come altro esempio, Il routing diretto fornisce il routing in base alla posizione (LBR, Location-Based-Routing), in modo che sia possibile limitare il bypass a pedaggio in determinate posizioni geografiche in cui non è consentito.</span><span class="sxs-lookup"><span data-stu-id="0722c-175">As another example, Direct Routing provides Location-Based-Routing (LBR)--so that you can restrict toll bypass in certain geographic locations where it is not allowed.</span></span> 


### <a name="phone-number-management"></a><span data-ttu-id="0722c-176">Telefono gestione dei numeri</span><span class="sxs-lookup"><span data-stu-id="0722c-176">Phone number management</span></span>

<span data-ttu-id="0722c-177">Microsoft ha a disposizione due tipi di numeri di telefono: numeri abbonati (utente), che possono essere assegnati agli utenti dell'organizzazione, e numeri di servizio, disponibili come numeri di servizio a numero verde e a numero verde.</span><span class="sxs-lookup"><span data-stu-id="0722c-177">Microsoft has two types of telephone numbers available: subscriber (user) numbers, which can be assigned to users in your organization, and service numbers, available as toll and toll-free service numbers.</span></span> <span data-ttu-id="0722c-178">I numeri di servizio hanno una capacità di chiamata simultanea maggiore rispetto ai numeri degli abbonati e possono essere assegnati a servizi come audioconferenze, operatori automatici o code di chiamata.</span><span class="sxs-lookup"><span data-stu-id="0722c-178">Service numbers have higher concurrent call capacity than subscriber numbers and can be assigned to services such as Audio Conferencing, Auto Attendants, or Call Queues.</span></span>

<span data-ttu-id="0722c-179">Dovrai decidere:</span><span class="sxs-lookup"><span data-stu-id="0722c-179">You will need to decide:</span></span>

- <span data-ttu-id="0722c-180">Quali posizioni degli utenti hanno bisogno di nuovi numeri di telefono da Microsoft?</span><span class="sxs-lookup"><span data-stu-id="0722c-180">Which user locations need new phone numbers from Microsoft?</span></span>
- <span data-ttu-id="0722c-181">Quale tipo di numero di telefono (abbonato o servizio) è necessario?</span><span class="sxs-lookup"><span data-stu-id="0722c-181">Which type of telephone number (subscriber or service) do I need?</span></span>
- <span data-ttu-id="0722c-182">Come faccio a eseguire il port di numeri di telefono esistenti Teams?</span><span class="sxs-lookup"><span data-stu-id="0722c-182">How do I port existing phone numbers to Teams?</span></span>

<span data-ttu-id="0722c-183">La modalità di acquisizione e gestione dei numeri di telefono varia a seconda dell'opzione di connettività PSTN.</span><span class="sxs-lookup"><span data-stu-id="0722c-183">How you acquire and manage phone numbers differs depending on your PSTN connectivity option.</span></span>

- <span data-ttu-id="0722c-184">Per informazioni sulla gestione dei numeri di telefono per il piano chiamate, vedere [Gestire i numeri di telefono per l'organizzazione.](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)</span><span class="sxs-lookup"><span data-stu-id="0722c-184">For information about managing phone numbers for Calling Plan, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).</span></span>

- <span data-ttu-id="0722c-185">Per informazioni sulla gestione dei numeri di telefono per Il routing diretto, vedere Configurare il numero di telefono [e abilitare la segreteria telefonica e la segreteria telefonica aziendale.](direct-routing-enable-users.md#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail-online)</span><span class="sxs-lookup"><span data-stu-id="0722c-185">For information about managing phone numbers for Direct Routing, see [Configure the phone number and enable enterprise voice and voicemail](direct-routing-enable-users.md#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail-online).</span></span>

- <span data-ttu-id="0722c-186">Per informazioni sulla gestione dei numeri di telefono con Operatore Connessione, vedere Configurare i numeri di telefono [con Operatore Connessione](operator-connect-configure.md#set-up-phone-numbers).</span><span class="sxs-lookup"><span data-stu-id="0722c-186">For information about managing phone numbers with Operator Connect, see [Set up phone numbers with Operator Connect](operator-connect-configure.md#set-up-phone-numbers).</span></span>


### <a name="call-routing-and-dial-plans"></a><span data-ttu-id="0722c-187">Routing delle chiamate e dial plan</span><span class="sxs-lookup"><span data-stu-id="0722c-187">Call routing and dial plans</span></span>

<span data-ttu-id="0722c-188">La modalità di configurazione del routing delle chiamate varia a seconda dell'opzione di connettività PSTN.</span><span class="sxs-lookup"><span data-stu-id="0722c-188">How you configure call routing differs depending on your PSTN connectivity option.</span></span>  

- <span data-ttu-id="0722c-189">Per i piani per chiamate, la maggior parte del routing delle chiamate è gestita dall'infrastruttura del piano per chiamate Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0722c-189">For Calling Plans, most of call routing is handled by the Microsoft Calling Plan infrastructure.</span></span> <span data-ttu-id="0722c-190">È possibile configurare i piani di chiamata degli utenti ai fini della traduzione dei numeri per l'autorizzazione delle chiamate e il routing delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="0722c-190">You configure user dial plans for purposes of number translation for call authorization and call routing.</span></span> <span data-ttu-id="0722c-191">Per altre informazioni, vedere [Che cosa sono i dial plan?](what-are-dial-plans.md).</span><span class="sxs-lookup"><span data-stu-id="0722c-191">For more information, see [What are dial plans?](what-are-dial-plans.md).</span></span>

- <span data-ttu-id="0722c-192">Per il routing diretto, è necessario configurare il routing delle chiamate specificando le route vocali e assegnando criteri di routing vocale agli utenti.</span><span class="sxs-lookup"><span data-stu-id="0722c-192">For Direct Routing, you must configure call routing by specifying the voice routes and assigning voice routing policies to users.</span></span> <span data-ttu-id="0722c-193">È possibile configurare i dial plan per la traduzione dei numeri a livello di trunk per garantire l'interoperabilità con i session border controller (SBC).</span><span class="sxs-lookup"><span data-stu-id="0722c-193">You can configure dial plans for number translation at the trunk level to ensure interoperability with Session Border Controllers (SBCs).</span></span> <span data-ttu-id="0722c-194">Per altre informazioni, vedere [Configurare il routing vocale per Routing diretto,](direct-routing-voice-routing.md)Gestire i criteri di routing [vocale](manage-voice-routing-policies.md) e Tradurre i numeri [di telefono.](direct-routing-translate-numbers.md)</span><span class="sxs-lookup"><span data-stu-id="0722c-194">For more information, see [Configure voice routing for Direct Routing](direct-routing-voice-routing.md), [Manage voice routing policies](manage-voice-routing-policies.md) and [Translate phone numbers](direct-routing-translate-numbers.md).</span></span> 

- <span data-ttu-id="0722c-195">Per gli operatori Connessione, la maggior parte del routing delle chiamate è gestita dal gestore.</span><span class="sxs-lookup"><span data-stu-id="0722c-195">For Operator Connect, most of call routing is managed by the carrier.</span></span>  <span data-ttu-id="0722c-196">È possibile configurare i piani di chiamata degli utenti ai fini della traduzione dei numeri per l'autorizzazione delle chiamate e il routing delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="0722c-196">You configure user dial plans for purposes of number translation for call authorization and call routing.</span></span> <span data-ttu-id="0722c-197">Per altre informazioni, vedere [Che cosa sono i dial plan?](what-are-dial-plans.md).</span><span class="sxs-lookup"><span data-stu-id="0722c-197">For more information, see [What are dial plans?](what-are-dial-plans.md).</span></span>


### <a name="location-based-routing-for-direct-routing"></a><span data-ttu-id="0722c-198">Location-Based routing diretto</span><span class="sxs-lookup"><span data-stu-id="0722c-198">Location-Based Routing for Direct Routing</span></span>

<span data-ttu-id="0722c-199">In alcuni paesi e aree geografiche, è illegale aggirare il gestore PSTN per ridurre i costi delle chiamate interurbane.</span><span class="sxs-lookup"><span data-stu-id="0722c-199">In some countries and regions, it's illegal to bypass the PSTN carrier to decrease long-distance calling costs.</span></span> <span data-ttu-id="0722c-200">Location-Based routing (LBR) per il routing diretto consente di limitare il bypass a pedaggio per Teams utenti in base alla loro posizione geografica.</span><span class="sxs-lookup"><span data-stu-id="0722c-200">Location-Based Routing (LBR) for Direct Routing enables you to restrict toll bypass for Teams users based on their geographic location.</span></span> <span data-ttu-id="0722c-201">Per altre informazioni su come pianificare e configurare LBR, vedere gli articoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="0722c-201">For more information about how to plan and configure LBR, see the following articles:</span></span>

- [<span data-ttu-id="0722c-202">Pianificare l'instradamento basato sulla posizione per Instradamento diretto</span><span class="sxs-lookup"><span data-stu-id="0722c-202">Plan Location-Based Routing for Direct Routing</span></span>](location-based-routing-plan.md)
- [<span data-ttu-id="0722c-203">Configurare le impostazioni di rete per l'instradamento basato sulla posizione</span><span class="sxs-lookup"><span data-stu-id="0722c-203">Configure network settings for Location-Based Routing</span></span>](location-based-routing-configure-network-settings.md)
- [<span data-ttu-id="0722c-204">Abilitare l'instradamento basato sulla posizione per Instradamento diretto</span><span class="sxs-lookup"><span data-stu-id="0722c-204">Enable Location-Based Routing for Direct Routing</span></span>](location-based-routing-enable.md)
- [<span data-ttu-id="0722c-205">Case study contoso: Location-Based Routing</span><span class="sxs-lookup"><span data-stu-id="0722c-205">Contoso case study: Location-Based Routing</span></span>](voice-case-study-location-based-routing.md)<br>
  <span data-ttu-id="0722c-206">Descrive in che modo una multinazionale fittizia, Contoso, ha implementato Location-Based routing per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="0722c-206">Describes how a fictional multi-national corporation, Contoso, implemented Location-Based Routing for their organization.</span></span>


### <a name="emergency-calling"></a><span data-ttu-id="0722c-207">Chiamate di emergenza</span><span class="sxs-lookup"><span data-stu-id="0722c-207">Emergency calling</span></span>

<span data-ttu-id="0722c-208">La modalità di configurazione delle chiamate di emergenza varia a seconda dell'opzione di connettività PSTN.</span><span class="sxs-lookup"><span data-stu-id="0722c-208">How you configure emergency calling differs depending on your PSTN connectivity option.</span></span>

- <span data-ttu-id="0722c-209">Per il Piano chiamate, ogni utente è abilitato automaticamente per le chiamate di emergenza ed è necessario avere un indirizzo di emergenza registrato associato al numero di telefono assegnato.</span><span class="sxs-lookup"><span data-stu-id="0722c-209">For Calling Plan, each user is automatically enabled for emergency calling and is required to have a registered emergency address associated with their assigned telephone number.</span></span> <span data-ttu-id="0722c-210">Le chiamate di emergenza dinamiche (in base alla posizione Teams client) sono supportate.</span><span class="sxs-lookup"><span data-stu-id="0722c-210">Dynamic emergency calling (based on the location of the Teams client) is supported.</span></span>  

- <span data-ttu-id="0722c-211">Per il routing diretto, è necessario definire i criteri per le chiamate di emergenza per gli utenti usando un criterio di routing delle chiamate di emergenza Teams (TeamsEmergencyCallRoutingPolicy) per definire i numeri di emergenza e la destinazione di routing associata.</span><span class="sxs-lookup"><span data-stu-id="0722c-211">For Direct Routing, you must define emergency calling policies for users by using a Teams emergency call routing policy (TeamsEmergencyCallRoutingPolicy) to define emergency numbers and their associated routing destination.</span></span> <span data-ttu-id="0722c-212">Le posizioni di emergenza registrate non sono supportate per gli utenti di Routing diretto.</span><span class="sxs-lookup"><span data-stu-id="0722c-212">Registered emergency locations are not supported for Direct Routing users.</span></span> <span data-ttu-id="0722c-213">Per le chiamate di emergenza dinamiche, è necessaria una configurazione aggiuntiva per l'instradamento delle chiamate di emergenza e, eventualmente, per la connettività dei partner.</span><span class="sxs-lookup"><span data-stu-id="0722c-213">For dynamic emergency calling, additional configuration is required for routing emergency calls and possibly for partner connectivity.</span></span>

- <span data-ttu-id="0722c-214">Per l'operatore Connessione, ogni utente è abilitato automaticamente per le chiamate di emergenza ed è necessario avere un indirizzo di emergenza registrato associato al numero di telefono assegnato, ma può essere impostato solo dal partner gestore.</span><span class="sxs-lookup"><span data-stu-id="0722c-214">For Operator Connect, each user is automatically enabled for emergency calling and is required to have a registered emergency address associated with their assigned telephone number but can only be set by the carrier partner.</span></span> <span data-ttu-id="0722c-215">Le chiamate di emergenza dinamiche (in base alla posizione Teams client) sono supportate.</span><span class="sxs-lookup"><span data-stu-id="0722c-215">Dynamic emergency calling (based on the location of the Teams client) is supported.</span></span>

<span data-ttu-id="0722c-216">Per altre informazioni sui concetti e la terminologia delle chiamate di emergenza e su come configurare le chiamate di emergenza e le chiamate di emergenza dinamiche, vedere gli articoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="0722c-216">For more information about emergency calling concepts and terminology, and how to configure emergency calling and dynamic emergency calling, see the following articles:</span></span>

- [<span data-ttu-id="0722c-217">Gestire le chiamate di emergenza</span><span class="sxs-lookup"><span data-stu-id="0722c-217">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="0722c-218">Pianificare e configurare chiamate di emergenza dinamiche</span><span class="sxs-lookup"><span data-stu-id="0722c-218">Plan and configure dynamic emergency calling</span></span>](configure-dynamic-emergency-calling.md)
- [<span data-ttu-id="0722c-219">Gestire i criteri delle chiamate di emergenza</span><span class="sxs-lookup"><span data-stu-id="0722c-219">Manage emergency calling policies</span></span>](manage-emergency-calling-policies.md)
- [<span data-ttu-id="0722c-220">Gestire i criteri di routing delle chiamate di emergenza per il routing diretto</span><span class="sxs-lookup"><span data-stu-id="0722c-220">Manage emergency call routing policies for Direct Routing</span></span>](manage-emergency-call-routing-policies.md)
- [<span data-ttu-id="0722c-221">Caso di studio Contoso: Chiamate di emergenza</span><span class="sxs-lookup"><span data-stu-id="0722c-221">Contoso case study: Emergency calling</span></span>](voice-case-study-emergency-calling.md)<br>
  <span data-ttu-id="0722c-222">Descrive come una multinazionale fittizia, Contoso, ha implementato le chiamate di emergenza per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="0722c-222">Describes how a fictional multi-national corporation, Contoso, implemented emergency calling for their organization.</span></span>


### <a name="network-topology-for-voice-features"></a><span data-ttu-id="0722c-223">Topologia di rete per le funzionalità vocali</span><span class="sxs-lookup"><span data-stu-id="0722c-223">Network topology for voice features</span></span>

<span data-ttu-id="0722c-224">Se si distribuiscono chiamate di emergenza dinamiche o Location-Based routing per il routing diretto, è necessario configurare le impostazioni di rete per l'uso con queste funzionalità in Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="0722c-224">If you are deploying dynamic emergency calling or Location-Based Routing for Direct Routing, you must configure network settings for use with these features in Microsoft Teams.</span></span> <span data-ttu-id="0722c-225">Per informazioni su come configurare le impostazioni di rete per aree di rete, siti di rete, subnet di rete e indirizzi IP attendibili, vedere gli articoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="0722c-225">To learn how to configure network settings for network regions, network sites, network subnets, and trusted IP addresses, see the following articles:</span></span>

- [<span data-ttu-id="0722c-226">Impostazioni di rete per le funzionalità vocali cloud in Microsoft Teams - Concetti e terminologia</span><span class="sxs-lookup"><span data-stu-id="0722c-226">Network settings for cloud voice features in Microsoft Teams - Concepts and terminology</span></span>](cloud-voice-network-settings.md)
- [<span data-ttu-id="0722c-227">Gestire la topologia di rete per le funzionalità vocali cloud in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0722c-227">Manage your network topology for cloud voice features in Microsoft Teams</span></span>](manage-your-network-topology.md)



