---
title: Monitorare e risolvere i problemi di Instradamento diretto
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: troubleshooting
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Questo articolo descrive come monitorare e risolvere i problemi di configurazione del routing diretto.
ms.openlocfilehash: 5dcae4d734c146c92c0cda4ac988d6010f90cc6f
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836046"
---
# <a name="monitor-and-troubleshoot-direct-routing"></a><span data-ttu-id="30e78-103">Monitorare e risolvere i problemi di Instradamento diretto</span><span class="sxs-lookup"><span data-stu-id="30e78-103">Monitor and troubleshoot Direct Routing</span></span>

<span data-ttu-id="30e78-104">Questo articolo descrive come monitorare e risolvere i problemi di configurazione del routing diretto.</span><span class="sxs-lookup"><span data-stu-id="30e78-104">This article describes how to monitor and troubleshoot your Direct Routing configuration.</span></span> 

<span data-ttu-id="30e78-105">La possibilità di effettuare e ricevere chiamate tramite routing diretto include i componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="30e78-105">The ability to make and receive calls by using Direct Routing involves the following components:</span></span> 

- <span data-ttu-id="30e78-106">Controller bordo sessione (SBCs)</span><span class="sxs-lookup"><span data-stu-id="30e78-106">Session Border Controllers (SBCs)</span></span> 
- <span data-ttu-id="30e78-107">Componenti di routing diretto in Microsoft Cloud</span><span class="sxs-lookup"><span data-stu-id="30e78-107">Direct Routing components in the Microsoft Cloud</span></span> 
- <span data-ttu-id="30e78-108">Trunks Telecom</span><span class="sxs-lookup"><span data-stu-id="30e78-108">Telecom trunks</span></span> 

<span data-ttu-id="30e78-109">In caso di difficoltà di risoluzione dei problemi, è possibile aprire una causa di supporto con il fornitore SBC o Microsoft.</span><span class="sxs-lookup"><span data-stu-id="30e78-109">If you have difficulties troubleshooting issues, you can open a support case with your SBC vendor or Microsoft.</span></span> 

<span data-ttu-id="30e78-110">Microsoft sta lavorando per fornire altri strumenti per la risoluzione dei problemi e il monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="30e78-110">Microsoft is working on providing more tools for troubleshooting and monitoring.</span></span> <span data-ttu-id="30e78-111">Verificare periodicamente la documentazione relativa agli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="30e78-111">Please check the documentation periodically for updates.</span></span> 

## <a name="monitoring-availability-of-session-border-controllers-using-session-initiation-protocol-sip-options-messages"></a><span data-ttu-id="30e78-112">Monitoraggio della disponibilità dei controller di bordo della sessione con i messaggi delle opzioni SIP (Session Initiation Protocol)</span><span class="sxs-lookup"><span data-stu-id="30e78-112">Monitoring availability of Session Border Controllers using Session Initiation Protocol (SIP) options messages</span></span>

<span data-ttu-id="30e78-113">Il routing diretto USA le opzioni SIP inviate dai controller di bordo della sessione per monitorare l'integrità di SBC.</span><span class="sxs-lookup"><span data-stu-id="30e78-113">Direct Routing uses SIP options sent by the Session Border Controllers to monitor SBC health.</span></span> <span data-ttu-id="30e78-114">L'amministratore del tenant non deve eseguire alcuna azione per abilitare il monitoraggio delle opzioni SIP.</span><span class="sxs-lookup"><span data-stu-id="30e78-114">There are no actions required from the tenant administrator to enable the SIP options monitoring.</span></span> <span data-ttu-id="30e78-115">Le informazioni raccolte vengono prese in considerazione quando vengono apportate decisioni di routing.</span><span class="sxs-lookup"><span data-stu-id="30e78-115">The collected information is taken into consideration when routing decisions are made.</span></span> 

<span data-ttu-id="30e78-116">Ad esempio, se per un utente specifico sono disponibili diverse SBCs per instradare una chiamata, il routing diretto considera le informazioni sulle opzioni SIP ricevute da ogni SBC per determinare il routing.</span><span class="sxs-lookup"><span data-stu-id="30e78-116">For example, if, for a specific user, there are several SBCs available to route a call, Direct Routing considers the SIP options information received from each SBC to determine routing.</span></span> 

<span data-ttu-id="30e78-117">Il diagramma seguente mostra un esempio di configurazione:</span><span class="sxs-lookup"><span data-stu-id="30e78-117">The following diagram shows an example of the configuration:</span></span> 

![Esempio di configurazione delle opzioni SIP](media/sip-options-config-example.png)

<span data-ttu-id="30e78-119">Quando un utente effettua una chiamata al numero + 1 425 \<le sette cifre>, il routing diretto valuta la route.</span><span class="sxs-lookup"><span data-stu-id="30e78-119">When a user makes a call to number +1 425 \<any seven digits>, Direct Routing evaluates the route.</span></span> <span data-ttu-id="30e78-120">Nella route sono presenti due SBCs: sbc1.contoso.com e sbc2.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="30e78-120">There are two SBCs in the route: sbc1.contoso.com and sbc2.contoso.com.</span></span> <span data-ttu-id="30e78-121">Entrambe le SBCs hanno la stessa priorità nella route.</span><span class="sxs-lookup"><span data-stu-id="30e78-121">Both SBCs have equal priority in the route.</span></span> <span data-ttu-id="30e78-122">Prima di selezionare un SBC, il meccanismo di routing valuta lo stato di SBCs in base al momento in cui il SBC ha inviato le opzioni SIP l'ultima volta.</span><span class="sxs-lookup"><span data-stu-id="30e78-122">Before picking an SBC, the routing mechanism evaluates the health of the SBCs based on when the SBC sent the SIP options last time.</span></span> 

<span data-ttu-id="30e78-123">Un SBC viene considerato integro se le statistiche al momento dell'invio della chiamata indicano che il SBC Invia le opzioni ogni minuto.</span><span class="sxs-lookup"><span data-stu-id="30e78-123">An SBC is considered healthy if statistics at the moment of sending the call shows that the SBC sends options every minute.</span></span>  

<span data-ttu-id="30e78-124">Quando viene eseguita una chiamata, viene applicata la logica seguente:</span><span class="sxs-lookup"><span data-stu-id="30e78-124">When a call is made, the following logic applies:</span></span>

- <span data-ttu-id="30e78-125">Il SBC è stato associato a 11:00 AM.</span><span class="sxs-lookup"><span data-stu-id="30e78-125">The SBC was paired at 11:00 AM.</span></span>  
- <span data-ttu-id="30e78-126">Il SBC Invia le opzioni in 11:01 AM, 11:02 AM e così via.</span><span class="sxs-lookup"><span data-stu-id="30e78-126">The SBC sends options at 11:01 AM, 11:02 AM, and so on.</span></span>  
- <span data-ttu-id="30e78-127">In 11:15, un utente effettua una chiamata e il meccanismo di routing seleziona questo SBC.</span><span class="sxs-lookup"><span data-stu-id="30e78-127">At 11:15, a user makes a call and the routing mechanism selects this SBC.</span></span> 

<span data-ttu-id="30e78-128">Il routing diretto richiede tre volte le opzioni di intervalli regolari (l'intervallo regolare è di un minuto).</span><span class="sxs-lookup"><span data-stu-id="30e78-128">Direct Routing takes the regular interval options three times (the regular interval is one minute).</span></span> <span data-ttu-id="30e78-129">Se le opzioni sono state inviate durante gli ultimi tre minuti, l'SBC viene considerato integro.</span><span class="sxs-lookup"><span data-stu-id="30e78-129">If options were send during the last three minutes, the SBC is considered healthy.</span></span>

<span data-ttu-id="30e78-130">Se il SBC nell'esempio ha inviato le opzioni in qualsiasi periodo compreso tra 11:12 AM e 11:15 AM (l'ora in cui è stata effettuata la chiamata), viene considerato integro.</span><span class="sxs-lookup"><span data-stu-id="30e78-130">If the SBC in the example sent options at any period between 11:12 AM and 11:15 AM (the time the call was made), it is considered healthy.</span></span> <span data-ttu-id="30e78-131">In caso contrario, l'SBC verrà retrocesso dalla route.</span><span class="sxs-lookup"><span data-stu-id="30e78-131">If not, the SBC will be demoted from the route.</span></span> 

<span data-ttu-id="30e78-132">L'abbassamento indica che l'SBC non verrà provato per primo.</span><span class="sxs-lookup"><span data-stu-id="30e78-132">Demotion means that the SBC will not be tried first.</span></span> <span data-ttu-id="30e78-133">Ad esempio, abbiamo sbc1.contoso.com e sbc2.contoso.com con priorità uguale.</span><span class="sxs-lookup"><span data-stu-id="30e78-133">For example, we have sbc1.contoso.com and sbc2.contoso.com with equal priority.</span></span>  

<span data-ttu-id="30e78-134">Se sbc1.contoso.com non invia le opzioni SIP in un intervallo regolare come descritto in precedenza, viene retrocesso.</span><span class="sxs-lookup"><span data-stu-id="30e78-134">If sbc1.contoso.com does not send SIP options on a regular interval as previously described, it is demoted.</span></span> <span data-ttu-id="30e78-135">Sbc2.contoso.com Cerca quindi la chiamata.</span><span class="sxs-lookup"><span data-stu-id="30e78-135">Next, sbc2.contoso.com tries for the call.</span></span> <span data-ttu-id="30e78-136">Se sbc2. contoso. con non riesce a eseguire la chiamata, il sbc1.contoso.com (retrocesso) viene riprovato prima che venga generato un errore.</span><span class="sxs-lookup"><span data-stu-id="30e78-136">If sbc2.contoso.con cannot deliver the call, the sbc1.contoso.com (demoted) is tried again before a failure is generated.</span></span> 

<span data-ttu-id="30e78-137">Se due (o più) SBCs in una route sono considerati integri e uguali, Fisher-Yates shuffle viene applicato per distribuire le chiamate tra SBCs.</span><span class="sxs-lookup"><span data-stu-id="30e78-137">If two (or more) SBCs in one route are considered healthy and equal, Fisher-Yates shuffle is applied to distribute the calls between the SBCs.</span></span>

## <a name="monitor-call-quality-analytics-dashboard-and-sbc-logs"></a><span data-ttu-id="30e78-138">Monitorare i log di dashboard e SBC di Call Quality Analytics</span><span class="sxs-lookup"><span data-stu-id="30e78-138">Monitor Call Quality Analytics dashboard and SBC logs</span></span> 
 
<span data-ttu-id="30e78-139">In alcuni casi, soprattutto durante l'associazione iniziale, potrebbero esserci problemi relativi alla configurazione errata di SBCs o del servizio di routing diretto.</span><span class="sxs-lookup"><span data-stu-id="30e78-139">In some cases, especially during the initial pairing, there might be issues related to misconfiguration of the SBCs or the Direct Routing service.</span></span> 

<span data-ttu-id="30e78-140">Per monitorare la configurazione, è possibile usare gli strumenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="30e78-140">You can use the following tools to monitor your configuration:</span></span>  
 
- <span data-ttu-id="30e78-141">Dashboard qualità delle chiamate</span><span class="sxs-lookup"><span data-stu-id="30e78-141">Call Quality Dashboard</span></span> 
- <span data-ttu-id="30e78-142">Registri SBC</span><span class="sxs-lookup"><span data-stu-id="30e78-142">SBC logs</span></span> 

<span data-ttu-id="30e78-143">Il servizio di routing diretto contiene codici di errore molto descrittivi segnalati per l'analisi delle chiamate o per i registri SBC.</span><span class="sxs-lookup"><span data-stu-id="30e78-143">The Direct Routing service has very descriptive error codes reported to either Call Analytics or the SBC logs.</span></span> 

<span data-ttu-id="30e78-144">Il dashboard qualità chiamata offre informazioni su qualità e affidabilità delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="30e78-144">The Call Quality Dashboard provides information about call quality and reliability.</span></span> <span data-ttu-id="30e78-145">Per altre informazioni su come risolvere i problemi con l'uso di analisi delle chiamate, vedere [attivazione e utilizzo di Call Quality dashboard per Microsoft teams e Skype for business online](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard) e [usare la chiamata analitica per la risoluzione dei problemi di qualità delle chiamate](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality).</span><span class="sxs-lookup"><span data-stu-id="30e78-145">To learn more about how to troubleshoot issues using Call Analytics, see [Turning on and using Call Quality Dashboard for Microsoft Teams and Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard) and [Use Call Analytics to troubleshoot poor call quality](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality).</span></span> 

<span data-ttu-id="30e78-146">In caso di errori di chiamata, l'analisi delle chiamate fornisce codici SIP standard per facilitare la risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="30e78-146">In case of call failures, Call Analytics provides standard SIP codes to help you with troubleshooting.</span></span> 

![Esempio di codice SIP per l'errore di chiamata](media/failed-response-code.png)

<span data-ttu-id="30e78-148">Tuttavia, l'analisi delle chiamate può aiutare solo quando le chiamate raggiungono i componenti interni del routing diretto e non riescono.</span><span class="sxs-lookup"><span data-stu-id="30e78-148">However, Call Analytics can only help when calls reach the internal components of Direct Routing and fail.</span></span> <span data-ttu-id="30e78-149">In caso di problemi con l'associazione di SBC o i problemi in cui il SIP "invite" è stato rifiutato, ad esempio il nome dell'FQDN del trunk non è configurato correttamente, l'analisi delle chiamate non sarà utile.</span><span class="sxs-lookup"><span data-stu-id="30e78-149">In case of issues with SBC pairing or issues where SIP “Invite” was rejected (for example, the name of the trunk FQDN is misconfigured), Call Analytics will not help.</span></span> <span data-ttu-id="30e78-150">In questo caso, fare riferimento ai registri SBC.</span><span class="sxs-lookup"><span data-stu-id="30e78-150">In this case, refer to the SBC logs.</span></span> <span data-ttu-id="30e78-151">Il routing diretto Invia una descrizione dettagliata dei problemi relativi a SBCs; questi problemi possono essere letti dai log SBC.</span><span class="sxs-lookup"><span data-stu-id="30e78-151">Direct Routing sends a detailed description of issues to the SBCs; these issues can be read from the SBC logs.</span></span> 
