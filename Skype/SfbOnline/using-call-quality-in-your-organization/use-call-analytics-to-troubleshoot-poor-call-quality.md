---
title: Utilizzo delle chiamate Analitica per la risoluzione dei Skype insufficiente per le aziende qualità delle chiamate
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 66945036-ae87-4c08-a0bb-984e50d6b009
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: Utilizzare chiama Analitica dettagli sui dispositivi, reti e connettività per la risoluzione dei problemi degli utenti con Skype per chiamate di lavoro e le riunioni.
ms.openlocfilehash: cb887a1c582c9547616c2133c2f175ac634e2da8
ms.sourcegitcommit: 5a0b3fe49b64f08979c89443f66b15827034e755
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/17/2018
---
# <a name="use-call-analytics-to-troubleshoot-poor-skype-for-business-call-quality"></a><span data-ttu-id="1f12f-103">Utilizzo delle chiamate Analitica per la risoluzione dei Skype insufficiente per le aziende qualità delle chiamate</span><span class="sxs-lookup"><span data-stu-id="1f12f-103">Use Call Analytics to troubleshoot poor Skype for Business call quality</span></span>

<span data-ttu-id="1f12f-104">Analitica chiamata consente di risolvere i problemi di connessione o chiamata con Skype per le aziende.</span><span class="sxs-lookup"><span data-stu-id="1f12f-104">Call Analytics helps you to troubleshoot call or connection problems with Skype for Business.</span></span> <span data-ttu-id="1f12f-105">Chiamata Analitica Visualizza informazioni dettagliate sui dispositivi, reti e connettività per le chiamate e le riunioni di ogni utente nel Skype per conto di Business.</span><span class="sxs-lookup"><span data-stu-id="1f12f-105">Call Analytics shows detailed information about the devices, networks, and connectivity for the calls and meetings of each user in your Skype for Business account.</span></span> <span data-ttu-id="1f12f-106">Se si crea, siti e tenant sono state aggiunte informazioni per chiamare Analitica verranno inoltre visualizzato per ogni chiamata e della sessione.</span><span class="sxs-lookup"><span data-stu-id="1f12f-106">If building, site, and tenant information has been added to Call Analytics, it will also be shown for each call and session.</span></span> <span data-ttu-id="1f12f-107">Informazioni disponibili tramite chiamata Analitica consentono di capire perché un utente è insufficiente o esperienza della riunione.</span><span class="sxs-lookup"><span data-stu-id="1f12f-107">Information available via Call Analytics can help you figure out why a user had a poor call or meeting experience.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="1f12f-p102">Call Analytics è attualmente in fase di anteprima. Il testo e le immagini qui riportati possono non corrispondere alla tua esperienza di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="1f12f-p102">Call Analytics is currently in preview. Text and images described here may not match your experience.</span></span>
  
## <a name="troubleshoot-call-quality-problems-using-call-analytics"></a><span data-ttu-id="1f12f-110">Risoluzione dei problemi di qualità chiamata tramite chiamata Analitica</span><span class="sxs-lookup"><span data-stu-id="1f12f-110">Troubleshoot call quality problems using Call Analytics</span></span>

<span data-ttu-id="1f12f-111">Il livello di autorizzazione assegnato all'utente determina il tipo di informazioni è possibile accedere a chiamare Analitica:</span><span class="sxs-lookup"><span data-stu-id="1f12f-111">The permissions level assigned to you determines what type of information you have access to in Call Analytics:</span></span>
  
- <span data-ttu-id="1f12f-112">**Skype per Business admin**: si ha accesso a tutte le informazioni nel chiamare Analitica in Skype per interfaccia di amministrazione di Business.</span><span class="sxs-lookup"><span data-stu-id="1f12f-112">**Skype for Business admin**: You have access to all the information in Call Analytics and in the Skype for Business Admin center.</span></span>
    
- <span data-ttu-id="1f12f-113">**Agenti help desk con autorizzazioni di livello 1**: viene visualizzato un numero limitato di dati di chiamare Analitica.</span><span class="sxs-lookup"><span data-stu-id="1f12f-113">**Helpdesk agent with Tier 1 permissions**: You see a limited set of data in Call Analytics.</span></span> <span data-ttu-id="1f12f-114">È possibile risolvere le chiamate, ma sarà consegnare problemi con le riunioni per un agente di livello 2.</span><span class="sxs-lookup"><span data-stu-id="1f12f-114">You can troubleshoot calls, but you'll hand off problems with meetings to a Tier 2 agent.</span></span> <span data-ttu-id="1f12f-115">Si dispone dell'accesso per il resto del Skype per interfaccia di amministrazione di Business.</span><span class="sxs-lookup"><span data-stu-id="1f12f-115">You don't have access to the rest of the Skype for Business Admin center.</span></span>
    
- <span data-ttu-id="1f12f-116">**Agenti help desk con autorizzazioni di livello 2**: visualizzazione di tutti i dati disponibili in chiamate Analitica e può semplificare la risoluzione dei problemi con le chiamate e le riunioni.</span><span class="sxs-lookup"><span data-stu-id="1f12f-116">**Helpdesk agent with Tier 2 permissions**: You see all available data in Call Analytics and can help troubleshoot problems with both calls and meetings.</span></span> <span data-ttu-id="1f12f-117">Si dispone dell'accesso per il resto del Skype per interfaccia di amministrazione di Business.</span><span class="sxs-lookup"><span data-stu-id="1f12f-117">You don't have access to the rest of the Skype for Business Admin center.</span></span>
    
<span data-ttu-id="1f12f-118">Se hai bisogno di informazioni con le autorizzazioni, vedere il Skype per Business admin.</span><span class="sxs-lookup"><span data-stu-id="1f12f-118">See your Skype for Business admin if you need help with permissions.</span></span>
  
 <span data-ttu-id="1f12f-119">**Aprire chiamare Analitica come agente help desk livello 1 o livello 2**</span><span class="sxs-lookup"><span data-stu-id="1f12f-119">**Open Call Analytics as a Tier 1 or Tier 2 helpdesk agent**</span></span>
  
1. <span data-ttu-id="1f12f-120">Accedere all'interfaccia di amministrazione di Office 365 e accedere utilizzando l'account di lavoro o della scuola.</span><span class="sxs-lookup"><span data-stu-id="1f12f-120">Go to the Office 365 admin center and sign in using your work or school account.</span></span> <span data-ttu-id="1f12f-121">Nel web browser passare alla *https://adminportal.services.skypeforbusiness.com*.</span><span class="sxs-lookup"><span data-stu-id="1f12f-121">Then in your web browser go to *https://adminportal.services.skypeforbusiness.com*.</span></span>
    
2. <span data-ttu-id="1f12f-122">In **Ricerca utente**, iniziare a digitare il nome o sip l'indirizzo dell'utente le cui chiamate da risolvere i problemi e quindi selezionare l'utente dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="1f12f-122">In **User Search**, start typing either the name or sip address of the user whose calls you want to troubleshoot and then select the user from the list.</span></span>
    
    ![Cattura di schermata della casella di ricerca di utenti della chiamata Analitica in Skype per Business Admin Center.](../images/db52efc5-dac1-4623-ba72-41e42f0a0fb4.png)
  
3. <span data-ttu-id="1f12f-124">Nella **cronologia delle chiamate**, selezionare la chiamata o una riunione che si desidera risolvere i problemi.</span><span class="sxs-lookup"><span data-stu-id="1f12f-124">In **Call history**, select the call or meeting that you want to troubleshoot.</span></span>
    
    ![Schermata che mostra la pagina cronologia delle chiamate per un utente con le informazioni, ad esempio informazioni di contatto dell'utente, un riepilogo delle attività per le riunioni e le chiamate e qualità di 7 giorni e una panoramica delle date e ore, i destinatari e qualità audio,](../images/aef80e09-3b37-46db-8e7b-8cf71712349b.png)
  
4. <span data-ttu-id="1f12f-126">Selezionare la scheda **Impostazioni avanzate** e quindi individuare gli elementi gialli e rossi indicano problemi di connessione o qualità chiamate.</span><span class="sxs-lookup"><span data-stu-id="1f12f-126">Select the **Advanced** tab, and then look for yellow and red items which indicate poor call quality or connection problems.</span></span>
    
    <span data-ttu-id="1f12f-127">Nei dettagli della sessione per ogni chiamata o riunione problemi secondari visualizzato in giallo.</span><span class="sxs-lookup"><span data-stu-id="1f12f-127">In the session details for each call or meeting, minor issues appear in yellow.</span></span> <span data-ttu-id="1f12f-128">(Ad esempio, nella schermata seguente i valori sono di colore giallo per instabilità medio, dall'instabilità massima e frequenza di perdita di pacchetti Media.) Se un elemento è giallo, è all'esterno dell'intervallo normale e può contribuire al problema, ma non viene in genere presentarsi principale del problema.</span><span class="sxs-lookup"><span data-stu-id="1f12f-128">(For example, in the following screenshot, the values are in yellow for Average jitter, Max jitter, and Average packet loss rate.) If something is yellow, it's outside of normal range, and it may be contributing to the problem, but it's unlikely to be the main cause of the problem.</span></span> <span data-ttu-id="1f12f-129">Caso di colore rosso, è un problema importante ed è probabile che le cause principali della qualità delle chiamate per la sessione corrente.</span><span class="sxs-lookup"><span data-stu-id="1f12f-129">If something is red, it's a significant problem, and it's likely the main cause of the poor call quality for this session.</span></span> 
    
    ![Schermata che mostra la scheda Avanzate della cronologia delle chiamate di un utente con la sezione di rete in ingresso espansa per visualizzare i dati di instabilità medio, dall'instabilità massimo e frequenza di perdita di pacchetti medie verranno mostrati in un colore giallo, vale a dire che sono problemi secondari.](../images/13f314ce-97cf-4bd0-a147-14b177d07040.png)
  
<span data-ttu-id="1f12f-131">In casi rari, qualità dei dati di utilizzo non viene ricevuta per le sessioni audio.</span><span class="sxs-lookup"><span data-stu-id="1f12f-131">In rare cases, quality of experience data isn't received for audio sessions.</span></span> <span data-ttu-id="1f12f-132">Spesso ciò è dovuto la chiamata della selezione e la connessione con il client che venga interrotto.</span><span class="sxs-lookup"><span data-stu-id="1f12f-132">Often this is caused by the call dropping and connection with the client terminating.</span></span> <span data-ttu-id="1f12f-133">In questo caso, la valutazione della sessione è "non disponibile".</span><span class="sxs-lookup"><span data-stu-id="1f12f-133">When this occurs, the session rating is "unavailable".</span></span>
  
<span data-ttu-id="1f12f-134">Per le sessioni audio di qualità dei dati QoE (dagli utenti QoE), nella tabella seguente vengono descritti i problemi principali che soddisfano una sessione come "scarso".</span><span class="sxs-lookup"><span data-stu-id="1f12f-134">For audio sessions that do have quality of experience (QoE) data, the following table describes major issues that qualify a session as "poor."</span></span>
  
|<span data-ttu-id="1f12f-135">**Problema**</span><span class="sxs-lookup"><span data-stu-id="1f12f-135">**Issue**</span></span>|<span data-ttu-id="1f12f-136">**Area**</span><span class="sxs-lookup"><span data-stu-id="1f12f-136">**Area**</span></span>|<span data-ttu-id="1f12f-137">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="1f12f-137">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1f12f-138">Impostazione delle chiamate</span><span class="sxs-lookup"><span data-stu-id="1f12f-138">Call setup</span></span>  <br/> |<span data-ttu-id="1f12f-139">Sessione</span><span class="sxs-lookup"><span data-stu-id="1f12f-139">Session</span></span>  <br/> |<span data-ttu-id="1f12f-140">Codice di errore che MS-diagnostica 20-29 indica l'impostazione della chiamata non è riuscita.</span><span class="sxs-lookup"><span data-stu-id="1f12f-140">The error code Ms-diag 20-29 indicates the call setup failed.</span></span> <span data-ttu-id="1f12f-141">L'utente non è stato unirsi alla chiamata o riunione.</span><span class="sxs-lookup"><span data-stu-id="1f12f-141">The user couldn't join the call or meeting.</span></span>  <br/> |
|<span data-ttu-id="1f12f-142">Rete audio classificati chiamate</span><span class="sxs-lookup"><span data-stu-id="1f12f-142">Audio network classified poor call</span></span>  <br/> |<span data-ttu-id="1f12f-143">Sessione</span><span class="sxs-lookup"><span data-stu-id="1f12f-143">Session</span></span>  <br/> |<span data-ttu-id="1f12f-144">Problemi di qualità di rete si sono verificati nelle aree, ad esempio la perdita di pacchetti, dall'instabilità, riduzione prestazioni NMOS, RTT, o nascosti rapporto.</span><span class="sxs-lookup"><span data-stu-id="1f12f-144">Network quality issues were encountered in areas such as packet loss, jitter, NMOS degradation, RTT, or concealed ratio.</span></span> <span data-ttu-id="1f12f-145">Per ulteriori informazioni sulle condizioni utilizzato per classificare le chiamate insufficiente, vedere il [blog di Microsoft post](https://go.microsoft.com/fwlink/p/?linkid=852133).</span><span class="sxs-lookup"><span data-stu-id="1f12f-145">For more information about the conditions used to classify poor calls, see this [Microsoft blog post](https://go.microsoft.com/fwlink/p/?linkid=852133).</span></span>  <br/> |
|<span data-ttu-id="1f12f-146">Dispositivo non funzionante</span><span class="sxs-lookup"><span data-stu-id="1f12f-146">Device not functioning</span></span>  <br/> |<span data-ttu-id="1f12f-147">Dispositivo</span><span class="sxs-lookup"><span data-stu-id="1f12f-147">Device</span></span>  <br/> | <span data-ttu-id="1f12f-148">Un dispositivo non funziona correttamente.</span><span class="sxs-lookup"><span data-stu-id="1f12f-148">A device isn't functioning correctly.</span></span> <span data-ttu-id="1f12f-149">Dispositivo non funziona rapporti è:</span><span class="sxs-lookup"><span data-stu-id="1f12f-149">Device not functioning ratios are :</span></span> <br/>  <span data-ttu-id="1f12f-150">DeviceRenderNotFunctioningEventRatio > = 0,005</span><span class="sxs-lookup"><span data-stu-id="1f12f-150">DeviceRenderNotFunctioningEventRatio >= 0.005</span></span> <br/>  <span data-ttu-id="1f12f-151">DeviceCaptureNotFunctioningEventRatio > = 0,005</span><span class="sxs-lookup"><span data-stu-id="1f12f-151">DeviceCaptureNotFunctioningEventRatio >= 0.005</span></span> <br/> |
   
## <a name="related-topics"></a><span data-ttu-id="1f12f-152">See also</span><span class="sxs-lookup"><span data-stu-id="1f12f-152">Related topics</span></span>
[<span data-ttu-id="1f12f-153">Configurazione di Skype for Business Call Analytics</span><span class="sxs-lookup"><span data-stu-id="1f12f-153">Set up Skype for Business Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="1f12f-154">Chiamata Analitica e Dashboard qualità chiamata</span><span class="sxs-lookup"><span data-stu-id="1f12f-154">Call Analytics and Call Quality Dashboard</span></span>](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 