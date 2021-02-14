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
description: Informazioni su come monitorare e risolvere i problemi di configurazione del routing diretto, inclusi i controller dei confini della sessione, i componenti di routing diretto e i trunk di Telecom.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 52ab594b901606ccf7c3b43fc8484d989c248fcd
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2020
ms.locfileid: "43901911"
---
# <a name="monitor-and-troubleshoot-direct-routing"></a><span data-ttu-id="343df-103">Monitorare e risolvere i problemi di Instradamento diretto</span><span class="sxs-lookup"><span data-stu-id="343df-103">Monitor and troubleshoot Direct Routing</span></span>

<span data-ttu-id="343df-104">Questo articolo descrive come monitorare e risolvere i problemi di configurazione del routing diretto.</span><span class="sxs-lookup"><span data-stu-id="343df-104">This article describes how to monitor and troubleshoot your Direct Routing configuration.</span></span> 

<span data-ttu-id="343df-105">La possibilità di effettuare e ricevere chiamate con l'instradamento diretto implica l'uso dei seguenti componenti:</span><span class="sxs-lookup"><span data-stu-id="343df-105">The ability to make and receive calls by using Direct Routing involves the following components:</span></span> 

- <span data-ttu-id="343df-106">Controller dei confini della sessione (SBC)</span><span class="sxs-lookup"><span data-stu-id="343df-106">Session Border Controllers (SBCs)</span></span> 
- <span data-ttu-id="343df-107">Componenti di routing diretto in Microsoft Cloud</span><span class="sxs-lookup"><span data-stu-id="343df-107">Direct Routing components in the Microsoft Cloud</span></span> 
- <span data-ttu-id="343df-108">Trunks di telecomunicazioni</span><span class="sxs-lookup"><span data-stu-id="343df-108">Telecom trunks</span></span> 

<span data-ttu-id="343df-109">In caso di difficoltà nella risoluzione dei problemi, è possibile aprire un caso di supporto con il fornitore SBC o Microsoft.</span><span class="sxs-lookup"><span data-stu-id="343df-109">If you have difficulties troubleshooting issues, you can open a support case with your SBC vendor or Microsoft.</span></span> 

<span data-ttu-id="343df-110">Microsoft sta lavorando per fornire altri strumenti per la risoluzione dei problemi e il monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="343df-110">Microsoft is working on providing more tools for troubleshooting and monitoring.</span></span> <span data-ttu-id="343df-111">Controlla periodicamente la documentazione per aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="343df-111">Please check the documentation periodically for updates.</span></span> 

## <a name="monitoring-availability-of-session-border-controllers-using-session-initiation-protocol-sip-options-messages"></a><span data-ttu-id="343df-112">Monitoraggio della disponibilità dei controller dei confini della sessione con i messaggi delle opzioni SIP (Session Initiation Protocol)</span><span class="sxs-lookup"><span data-stu-id="343df-112">Monitoring availability of Session Border Controllers using Session Initiation Protocol (SIP) options messages</span></span>

<span data-ttu-id="343df-113">Il routing diretto usa le opzioni SIP inviate dai controller dei confini della sessione per monitorare l'integrità di SBC.</span><span class="sxs-lookup"><span data-stu-id="343df-113">Direct Routing uses SIP options sent by the Session Border Controllers to monitor SBC health.</span></span> <span data-ttu-id="343df-114">Non sono necessarie azioni da parte dell'amministratore del tenant per abilitare il monitoraggio delle opzioni SIP.</span><span class="sxs-lookup"><span data-stu-id="343df-114">There are no actions required from the tenant administrator to enable the SIP options monitoring.</span></span> <span data-ttu-id="343df-115">Le informazioni raccolte vengono prese in considerazione quando vengono prese decisioni di routing.</span><span class="sxs-lookup"><span data-stu-id="343df-115">The collected information is taken into consideration when routing decisions are made.</span></span> 

<span data-ttu-id="343df-116">Ad esempio, se per un utente specifico sono disponibili diversi SBC per instradare una chiamata, l'instradamento diretto considera le informazioni sulle opzioni SIP ricevute da ogni SBC per determinare il routing.</span><span class="sxs-lookup"><span data-stu-id="343df-116">For example, if, for a specific user, there are several SBCs available to route a call, Direct Routing considers the SIP options information received from each SBC to determine routing.</span></span> 

<span data-ttu-id="343df-117">Il diagramma seguente mostra un esempio della configurazione:</span><span class="sxs-lookup"><span data-stu-id="343df-117">The following diagram shows an example of the configuration:</span></span> 

![Esempio di configurazione delle opzioni SIP](media/sip-options-config-example.png)

<span data-ttu-id="343df-119">Quando un utente effettua una chiamata al numero +1 425 qualsiasi sette>, l'instradamento diretto \< valuta il percorso.</span><span class="sxs-lookup"><span data-stu-id="343df-119">When a user makes a call to number +1 425 \<any seven digits>, Direct Routing evaluates the route.</span></span> <span data-ttu-id="343df-120">Nel percorso sono presenti due SBC: sbc1.contoso.com e sbc2.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="343df-120">There are two SBCs in the route: sbc1.contoso.com and sbc2.contoso.com.</span></span> <span data-ttu-id="343df-121">Entrambi gli SBC hanno la stessa priorità nel percorso.</span><span class="sxs-lookup"><span data-stu-id="343df-121">Both SBCs have equal priority in the route.</span></span> <span data-ttu-id="343df-122">Prima di scegliere un valore SBC, il meccanismo di routing valuta l'integrità dei server SBC in base all'ultima volta in cui SBC ha inviato le opzioni SIP.</span><span class="sxs-lookup"><span data-stu-id="343df-122">Before picking an SBC, the routing mechanism evaluates the health of the SBCs based on when the SBC sent the SIP options last time.</span></span> 

<span data-ttu-id="343df-123">Un SBC viene considerato integro se le statistiche al momento dell'invio della chiamata mostrano che SBC invia opzioni ogni minuto.</span><span class="sxs-lookup"><span data-stu-id="343df-123">An SBC is considered healthy if statistics at the moment of sending the call shows that the SBC sends options every minute.</span></span>  

<span data-ttu-id="343df-124">Quando viene effettuata una chiamata, si applica la logica seguente:</span><span class="sxs-lookup"><span data-stu-id="343df-124">When a call is made, the following logic applies:</span></span>

- <span data-ttu-id="343df-125">Il campo SBC è stato abbinato alle 11:00.</span><span class="sxs-lookup"><span data-stu-id="343df-125">The SBC was paired at 11:00 AM.</span></span>  
- <span data-ttu-id="343df-126">L'indirizzo SBC invia le opzioni alle 11:01, alle 11:02 e così via.</span><span class="sxs-lookup"><span data-stu-id="343df-126">The SBC sends options at 11:01 AM, 11:02 AM, and so on.</span></span>  
- <span data-ttu-id="343df-127">Alle 11:15 un utente effettua una chiamata e il meccanismo di routing seleziona questo SBC.</span><span class="sxs-lookup"><span data-stu-id="343df-127">At 11:15, a user makes a call and the routing mechanism selects this SBC.</span></span> 

<span data-ttu-id="343df-128">L'instradamento diretto accetta le opzioni a intervalli regolari tre volte (l'intervallo regolare è di un minuto).</span><span class="sxs-lookup"><span data-stu-id="343df-128">Direct Routing takes the regular interval options three times (the regular interval is one minute).</span></span> <span data-ttu-id="343df-129">Se le opzioni sono state inviate negli ultimi tre minuti, L'SBC è considerato integro.</span><span class="sxs-lookup"><span data-stu-id="343df-129">If options were send during the last three minutes, the SBC is considered healthy.</span></span>

<span data-ttu-id="343df-130">Se il valore SBC nell'esempio ha inviato opzioni in qualsiasi periodo tra le 11:12 e le 11:15 (l'ora in cui è stata effettuata la chiamata), è considerato integro.</span><span class="sxs-lookup"><span data-stu-id="343df-130">If the SBC in the example sent options at any period between 11:12 AM and 11:15 AM (the time the call was made), it is considered healthy.</span></span> <span data-ttu-id="343df-131">In caso contrario, il valore SBC verrà abbassato di livello rispetto al percorso.</span><span class="sxs-lookup"><span data-stu-id="343df-131">If not, the SBC will be demoted from the route.</span></span> 

<span data-ttu-id="343df-132">L'abbassamento di livello indica che il valore SBC non verrà provato prima.</span><span class="sxs-lookup"><span data-stu-id="343df-132">Demotion means that the SBC will not be tried first.</span></span> <span data-ttu-id="343df-133">Ad esempio, abbiamo sbc1.contoso.com e sbc2.contoso.com con la stessa priorità.</span><span class="sxs-lookup"><span data-stu-id="343df-133">For example, we have sbc1.contoso.com and sbc2.contoso.com with equal priority.</span></span>  

<span data-ttu-id="343df-134">Se sbc1.contoso.com opzioni SIP non vengono inviate a intervalli regolari come descritto in precedenza, le opzioni vengono abbassate di livello.</span><span class="sxs-lookup"><span data-stu-id="343df-134">If sbc1.contoso.com does not send SIP options on a regular interval as previously described, it is demoted.</span></span> <span data-ttu-id="343df-135">Quindi, sbc2.contoso.com la chiamata.</span><span class="sxs-lookup"><span data-stu-id="343df-135">Next, sbc2.contoso.com tries for the call.</span></span> <span data-ttu-id="343df-136">Se sbc2.contoso.con non riesce a recapitare la chiamata, il sbc1.contoso.com (abbassato di livello) viene riprovato prima che venga generato un errore.</span><span class="sxs-lookup"><span data-stu-id="343df-136">If sbc2.contoso.con cannot deliver the call, the sbc1.contoso.com (demoted) is tried again before a failure is generated.</span></span> 

<span data-ttu-id="343df-137">Se due (o più) SBC in un percorso sono considerati integri e uguali, viene Fisher-Yates chiamata casuale per distribuire le chiamate tra gli SBC.</span><span class="sxs-lookup"><span data-stu-id="343df-137">If two (or more) SBCs in one route are considered healthy and equal, Fisher-Yates shuffle is applied to distribute the calls between the SBCs.</span></span>

## <a name="monitor-call-quality-analytics-dashboard-and-sbc-logs"></a><span data-ttu-id="343df-138">Monitorare il dashboard Call Quality Analytics e i log SBC</span><span class="sxs-lookup"><span data-stu-id="343df-138">Monitor Call Quality Analytics dashboard and SBC logs</span></span> 
 
<span data-ttu-id="343df-139">In alcuni casi, in particolare durante l'associazione iniziale, potrebbero verificarsi problemi relativi a una configurazione errata del servizio di routing diretto o SBCs.</span><span class="sxs-lookup"><span data-stu-id="343df-139">In some cases, especially during the initial pairing, there might be issues related to misconfiguration of the SBCs or the Direct Routing service.</span></span> 

<span data-ttu-id="343df-140">È possibile usare gli strumenti seguenti per monitorare la configurazione:</span><span class="sxs-lookup"><span data-stu-id="343df-140">You can use the following tools to monitor your configuration:</span></span>  
 
- <span data-ttu-id="343df-141">Dashboard qualità delle chiamate</span><span class="sxs-lookup"><span data-stu-id="343df-141">Call Quality Dashboard</span></span> 
- <span data-ttu-id="343df-142">Log SBC</span><span class="sxs-lookup"><span data-stu-id="343df-142">SBC logs</span></span> 

<span data-ttu-id="343df-143">Il servizio di instradamento diretto ha codici di errore molto descrittivi segnalati ai log di Call Analytics o SBC.</span><span class="sxs-lookup"><span data-stu-id="343df-143">The Direct Routing service has very descriptive error codes reported to either Call Analytics or the SBC logs.</span></span> 

<span data-ttu-id="343df-144">Call Quality Dashboard fornisce informazioni sulla qualità e l'affidabilità delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="343df-144">The Call Quality Dashboard provides information about call quality and reliability.</span></span> <span data-ttu-id="343df-145">Per ulteriori informazioni su come risolvere i problemi con Call Analytics, consulta Attivazione e utilizzo di Call Quality Dashboard per Microsoft Teams e [Skype for Business online](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard) e Uso di Call Analytics per risolvere i problemi di bassa qualità delle [chiamate.](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality)</span><span class="sxs-lookup"><span data-stu-id="343df-145">To learn more about how to troubleshoot issues using Call Analytics, see [Turning on and using Call Quality Dashboard for Microsoft Teams and Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard) and [Use Call Analytics to troubleshoot poor call quality](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality).</span></span> 

<span data-ttu-id="343df-146">In caso di errori di chiamata, Call Analytics fornisce codici SIP standard per facilitare la risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="343df-146">In case of call failures, Call Analytics provides standard SIP codes to help you with troubleshooting.</span></span> 

![Esempio di codice SIP per l'errore di chiamata](media/failed-response-code.png)

<span data-ttu-id="343df-148">Tuttavia, Call Analytics può essere utile solo quando le chiamate raggiungono i componenti interni dell'instradamento diretto e hanno esito negativo.</span><span class="sxs-lookup"><span data-stu-id="343df-148">However, Call Analytics can only help when calls reach the internal components of Direct Routing and fail.</span></span> <span data-ttu-id="343df-149">In caso di problemi con l'associazione SBC o problemi in cui SIP "Invito" è stato rifiutato (ad esempio, il nome dell'FQDN trunk non è configurato correttamente), Call Analytics non sarà di aiuto.</span><span class="sxs-lookup"><span data-stu-id="343df-149">In case of issues with SBC pairing or issues where SIP "Invite" was rejected (for example, the name of the trunk FQDN is misconfigured), Call Analytics will not help.</span></span> <span data-ttu-id="343df-150">In questo caso, fare riferimento ai log SBC.</span><span class="sxs-lookup"><span data-stu-id="343df-150">In this case, refer to the SBC logs.</span></span> <span data-ttu-id="343df-151">Il routing diretto invia una descrizione dettagliata dei problemi agli SBC; questi problemi possono essere letti dai log SBC.</span><span class="sxs-lookup"><span data-stu-id="343df-151">Direct Routing sends a detailed description of issues to the SBCs; these issues can be read from the SBC logs.</span></span> 
