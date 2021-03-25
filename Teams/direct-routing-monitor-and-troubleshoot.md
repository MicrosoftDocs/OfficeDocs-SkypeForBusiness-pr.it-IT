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
description: Informazioni su come monitorare e risolvere i problemi di configurazione del routing diretto, inclusi i controller dei bordi delle sessioni, i componenti di routing diretto e i trunk di Telecom.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 74a67493fa2f9647e6cd0364bb4c9d6a3c05e48a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121404"
---
# <a name="monitor-and-troubleshoot-direct-routing"></a><span data-ttu-id="38479-103">Monitorare e risolvere i problemi di Instradamento diretto</span><span class="sxs-lookup"><span data-stu-id="38479-103">Monitor and troubleshoot Direct Routing</span></span>

<span data-ttu-id="38479-104">Questo articolo descrive come monitorare e risolvere i problemi relativi alla configurazione del routing diretto.</span><span class="sxs-lookup"><span data-stu-id="38479-104">This article describes how to monitor and troubleshoot your Direct Routing configuration.</span></span> 

<span data-ttu-id="38479-105">La possibilità di effettuare e ricevere chiamate tramite Routing diretto implica i componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="38479-105">The ability to make and receive calls by using Direct Routing involves the following components:</span></span> 

- <span data-ttu-id="38479-106">Session Border Controller (SBC)</span><span class="sxs-lookup"><span data-stu-id="38479-106">Session Border Controllers (SBCs)</span></span> 
- <span data-ttu-id="38479-107">Componenti di Routing diretto in Microsoft Cloud</span><span class="sxs-lookup"><span data-stu-id="38479-107">Direct Routing components in the Microsoft Cloud</span></span> 
- <span data-ttu-id="38479-108">Tronchi di telecomunicazione</span><span class="sxs-lookup"><span data-stu-id="38479-108">Telecom trunks</span></span> 

<span data-ttu-id="38479-109">In caso di problemi di risoluzione dei problemi, è possibile aprire un caso di supporto con il fornitore SBC o Microsoft.</span><span class="sxs-lookup"><span data-stu-id="38479-109">If you have difficulties troubleshooting issues, you can open a support case with your SBC vendor or Microsoft.</span></span> 

<span data-ttu-id="38479-110">Microsoft sta lavorando alla fornitura di altri strumenti per la risoluzione dei problemi e il monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="38479-110">Microsoft is working on providing more tools for troubleshooting and monitoring.</span></span> <span data-ttu-id="38479-111">Controllare periodicamente la documentazione per gli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="38479-111">Please check the documentation periodically for updates.</span></span> 

## <a name="monitoring-availability-of-session-border-controllers-using-session-initiation-protocol-sip-options-messages"></a><span data-ttu-id="38479-112">Monitoraggio della disponibilità dei session border controller tramite i messaggi di opzioni SIP (Session Initiation Protocol)</span><span class="sxs-lookup"><span data-stu-id="38479-112">Monitoring availability of Session Border Controllers using Session Initiation Protocol (SIP) options messages</span></span>

<span data-ttu-id="38479-113">Il routing diretto usa le opzioni SIP inviate dai session border controller per monitorare l'integrità di SBC.</span><span class="sxs-lookup"><span data-stu-id="38479-113">Direct Routing uses SIP options sent by the Session Border Controllers to monitor SBC health.</span></span> <span data-ttu-id="38479-114">Non sono necessarie azioni da parte dell'amministratore tenant per abilitare il monitoraggio delle opzioni SIP.</span><span class="sxs-lookup"><span data-stu-id="38479-114">There are no actions required from the tenant administrator to enable the SIP options monitoring.</span></span> <span data-ttu-id="38479-115">Le informazioni raccolte vengono prese in considerazione quando si prendono decisioni relative al routing.</span><span class="sxs-lookup"><span data-stu-id="38479-115">The collected information is taken into consideration when routing decisions are made.</span></span> 

<span data-ttu-id="38479-116">Ad esempio, se per un utente specifico sono disponibili diversi SBC per instradare una chiamata, Direct Routing considera le informazioni sulle opzioni SIP ricevute da ogni SBC per determinare il routing.</span><span class="sxs-lookup"><span data-stu-id="38479-116">For example, if, for a specific user, there are several SBCs available to route a call, Direct Routing considers the SIP options information received from each SBC to determine routing.</span></span> 

<span data-ttu-id="38479-117">Il diagramma seguente mostra un esempio della configurazione:</span><span class="sxs-lookup"><span data-stu-id="38479-117">The following diagram shows an example of the configuration:</span></span> 

![Esempio di configurazione delle opzioni SIP](media/sip-options-config-example.png)

<span data-ttu-id="38479-119">Quando un utente effettua una chiamata al numero +1 425, \<any seven digits> Direct Routing valuta il percorso.</span><span class="sxs-lookup"><span data-stu-id="38479-119">When a user makes a call to number +1 425 \<any seven digits>, Direct Routing evaluates the route.</span></span> <span data-ttu-id="38479-120">Ci sono due SBC nel percorso: sbc1.contoso.com e sbc2.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="38479-120">There are two SBCs in the route: sbc1.contoso.com and sbc2.contoso.com.</span></span> <span data-ttu-id="38479-121">Entrambi i SBC hanno la stessa priorità nel percorso.</span><span class="sxs-lookup"><span data-stu-id="38479-121">Both SBCs have equal priority in the route.</span></span> <span data-ttu-id="38479-122">Prima di scegliere un SBC, il meccanismo di routing valuta l'integrità degli SBC in base all'ultima volta in cui il SBC ha inviato le opzioni SIP.</span><span class="sxs-lookup"><span data-stu-id="38479-122">Before picking an SBC, the routing mechanism evaluates the health of the SBCs based on when the SBC sent the SIP options last time.</span></span> 

<span data-ttu-id="38479-123">Un SBC è considerato integro se le statistiche al momento dell'invio della chiamata mostrano che SBC invia opzioni ogni minuto.</span><span class="sxs-lookup"><span data-stu-id="38479-123">An SBC is considered healthy if statistics at the moment of sending the call shows that the SBC sends options every minute.</span></span>  

<span data-ttu-id="38479-124">Quando viene effettuata una chiamata, si applica la logica seguente:</span><span class="sxs-lookup"><span data-stu-id="38479-124">When a call is made, the following logic applies:</span></span>

- <span data-ttu-id="38479-125">Il valore SBC è stato associato alle 11:00.</span><span class="sxs-lookup"><span data-stu-id="38479-125">The SBC was paired at 11:00 AM.</span></span>  
- <span data-ttu-id="38479-126">L'SBC invia le opzioni alle 11:01, alle 11:02 e così via.</span><span class="sxs-lookup"><span data-stu-id="38479-126">The SBC sends options at 11:01 AM, 11:02 AM, and so on.</span></span>  
- <span data-ttu-id="38479-127">Alle 11:15, un utente effettua una chiamata e il meccanismo di routing seleziona questo SBC.</span><span class="sxs-lookup"><span data-stu-id="38479-127">At 11:15, a user makes a call and the routing mechanism selects this SBC.</span></span> 

<span data-ttu-id="38479-128">Routing diretto accetta le opzioni di intervallo normale tre volte (l'intervallo normale è di un minuto).</span><span class="sxs-lookup"><span data-stu-id="38479-128">Direct Routing takes the regular interval options three times (the regular interval is one minute).</span></span> <span data-ttu-id="38479-129">Se le opzioni sono state inviate negli ultimi tre minuti, il valore SBC è considerato integro.</span><span class="sxs-lookup"><span data-stu-id="38479-129">If options were send during the last three minutes, the SBC is considered healthy.</span></span>

<span data-ttu-id="38479-130">Se l'SBC nell'esempio ha inviato opzioni in qualsiasi periodo compreso tra le 11:12 e le 11:15 (ora in cui è stata effettuata la chiamata), viene considerato integro.</span><span class="sxs-lookup"><span data-stu-id="38479-130">If the SBC in the example sent options at any period between 11:12 AM and 11:15 AM (the time the call was made), it is considered healthy.</span></span> <span data-ttu-id="38479-131">In caso contrario, il valore SBC verrà abbassato di livello dal percorso.</span><span class="sxs-lookup"><span data-stu-id="38479-131">If not, the SBC will be demoted from the route.</span></span> 

<span data-ttu-id="38479-132">L'abbassamento di livello indica che il valore SBC non verrà provato prima.</span><span class="sxs-lookup"><span data-stu-id="38479-132">Demotion means that the SBC will not be tried first.</span></span> <span data-ttu-id="38479-133">Ad esempio, abbiamo sbc1.contoso.com e sbc2.contoso.com con la stessa priorità.</span><span class="sxs-lookup"><span data-stu-id="38479-133">For example, we have sbc1.contoso.com and sbc2.contoso.com with equal priority.</span></span>  

<span data-ttu-id="38479-134">Se sbc1.contoso.com le opzioni SIP non vengono inviate a intervalli regolari come descritto in precedenza, viene abbassata di livello.</span><span class="sxs-lookup"><span data-stu-id="38479-134">If sbc1.contoso.com does not send SIP options on a regular interval as previously described, it is demoted.</span></span> <span data-ttu-id="38479-135">Quindi, sbc2.contoso.com la chiamata.</span><span class="sxs-lookup"><span data-stu-id="38479-135">Next, sbc2.contoso.com tries for the call.</span></span> <span data-ttu-id="38479-136">Se sbc2.contoso.con non riesce a recapitare la chiamata, il sbc1.contoso.com (abbassato di livello) viene riprovato prima che venga generato un errore.</span><span class="sxs-lookup"><span data-stu-id="38479-136">If sbc2.contoso.con cannot deliver the call, the sbc1.contoso.com (demoted) is tried again before a failure is generated.</span></span> 

<span data-ttu-id="38479-137">Se due (o più) SBC in un percorso sono considerati integri e uguali, viene applicata una Fisher-Yates casuale per distribuire le chiamate tra gli SBC.</span><span class="sxs-lookup"><span data-stu-id="38479-137">If two (or more) SBCs in one route are considered healthy and equal, Fisher-Yates shuffle is applied to distribute the calls between the SBCs.</span></span>

## <a name="monitor-call-quality-analytics-dashboard-and-sbc-logs"></a><span data-ttu-id="38479-138">Monitorare il dashboard di Call Quality Analytics e i log SBC</span><span class="sxs-lookup"><span data-stu-id="38479-138">Monitor Call Quality Analytics dashboard and SBC logs</span></span> 
 
<span data-ttu-id="38479-139">In alcuni casi, in particolare durante l'associazione iniziale, potrebbero verificarsi problemi relativi alla configurazione errata dei cluster SBC o del servizio di routing diretto.</span><span class="sxs-lookup"><span data-stu-id="38479-139">In some cases, especially during the initial pairing, there might be issues related to misconfiguration of the SBCs or the Direct Routing service.</span></span> 

<span data-ttu-id="38479-140">Per monitorare la configurazione, è possibile usare gli strumenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="38479-140">You can use the following tools to monitor your configuration:</span></span>  
 
- <span data-ttu-id="38479-141">Dashboard qualità delle chiamate</span><span class="sxs-lookup"><span data-stu-id="38479-141">Call Quality Dashboard</span></span> 
- <span data-ttu-id="38479-142">Log SBC</span><span class="sxs-lookup"><span data-stu-id="38479-142">SBC logs</span></span> 

<span data-ttu-id="38479-143">Il servizio Di routing diretto ha codici di errore molto descrittivi riportati nei log di Call Analytics o SBC.</span><span class="sxs-lookup"><span data-stu-id="38479-143">The Direct Routing service has very descriptive error codes reported to either Call Analytics or the SBC logs.</span></span> 

<span data-ttu-id="38479-144">Il dashboard qualità chiamata fornisce informazioni sulla qualità e l'affidabilità delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="38479-144">The Call Quality Dashboard provides information about call quality and reliability.</span></span> <span data-ttu-id="38479-145">Per altre informazioni su come risolvere i problemi relativi all'uso di Call Analytics, vedere Attivare e usare call quality dashboard per Microsoft Teams e [Skype for Business online](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard) e Usare Call Analytics per risolvere i problemi di scarsa qualità delle [chiamate.](/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality)</span><span class="sxs-lookup"><span data-stu-id="38479-145">To learn more about how to troubleshoot issues using Call Analytics, see [Turning on and using Call Quality Dashboard for Microsoft Teams and Skype for Business Online](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard) and [Use Call Analytics to troubleshoot poor call quality](/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality).</span></span> 

<span data-ttu-id="38479-146">In caso di errori di chiamata, Call Analytics fornisce codici SIP standard per facilitare la risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="38479-146">In case of call failures, Call Analytics provides standard SIP codes to help you with troubleshooting.</span></span> 

![Codice SIP di esempio per l'errore di chiamata](media/failed-response-code.png)

<span data-ttu-id="38479-148">Tuttavia, Call Analytics può essere utile solo quando le chiamate raggiungono i componenti interni di Direct Routing e non riescono.</span><span class="sxs-lookup"><span data-stu-id="38479-148">However, Call Analytics can only help when calls reach the internal components of Direct Routing and fail.</span></span> <span data-ttu-id="38479-149">In caso di problemi con l'associazione SBC o problemi in cui "Invito" SIP è stato rifiutato (ad esempio, il nome dell'FQDN del trunk non è configurato correttamente), Call Analytics non sarà di aiuto.</span><span class="sxs-lookup"><span data-stu-id="38479-149">In case of issues with SBC pairing or issues where SIP "Invite" was rejected (for example, the name of the trunk FQDN is misconfigured), Call Analytics will not help.</span></span> <span data-ttu-id="38479-150">In questo caso, fare riferimento ai log SBC.</span><span class="sxs-lookup"><span data-stu-id="38479-150">In this case, refer to the SBC logs.</span></span> <span data-ttu-id="38479-151">Il routing diretto invia una descrizione dettagliata dei problemi agli SBC; questi problemi possono essere letti dai log SBC.</span><span class="sxs-lookup"><span data-stu-id="38479-151">Direct Routing sends a detailed description of issues to the SBCs; these issues can be read from the SBC logs.</span></span>