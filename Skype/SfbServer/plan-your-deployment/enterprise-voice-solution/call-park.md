---
title: Pianificare il parcheggio delle chiamate in Skype for business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 985dc326-0aef-4308-b98b-c1d0069311e7
description: Pianificazione di Call Park in Skype for Business Server VoIP aziendale, che consente di effettuare chiamate in attesa e di trasferire le chiamate ai reparti. Include la pianificazione della capacità, le chiamate supportate e i client supportati.
ms.openlocfilehash: 3effeab4afef60fb7a5021206d9fc3cd0227ceb1
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803196"
---
# <a name="plan-for-call-park-in-skype-for-business"></a><span data-ttu-id="7ba0f-104">Pianificare il parcheggio delle chiamate in Skype for business</span><span class="sxs-lookup"><span data-stu-id="7ba0f-104">Plan for Call Park in Skype for Business</span></span>
 
<span data-ttu-id="7ba0f-105">Pianificazione di Call Park in Skype for Business Server VoIP aziendale, che consente di effettuare chiamate in attesa e di trasferire le chiamate ai reparti.</span><span class="sxs-lookup"><span data-stu-id="7ba0f-105">Planning for call park in Skype for Business Server Enterprise Voice, which enables putting calls on hold and transferring calls to departments.</span></span> <span data-ttu-id="7ba0f-106">Include la pianificazione della capacità, le chiamate supportate e i client supportati.</span><span class="sxs-lookup"><span data-stu-id="7ba0f-106">Includes capacity planning, supported calls, and supported clients.</span></span>
  
<span data-ttu-id="7ba0f-107">L'applicazione Call Park consente agli utenti di VoIP aziendale di eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7ba0f-107">The Call Park application enables Enterprise Voice users to do the following:</span></span>
  
- <span data-ttu-id="7ba0f-108">Inserire una chiamata in attesa e quindi recuperare la chiamata dallo stesso telefono o da un altro telefono.</span><span class="sxs-lookup"><span data-stu-id="7ba0f-108">Put a call on hold and then retrieve the call from the same phone or another phone.</span></span>
    
- <span data-ttu-id="7ba0f-109">Inserire una chiamata in attesa per trasferirla in un reparto o in un'area generale, ad esempio in un reparto vendite o in un magazzino in cui è presente un telefono con area comune.</span><span class="sxs-lookup"><span data-stu-id="7ba0f-109">Put a call on hold to transfer it to a department or general area (for example, to a sales department or a warehouse where there is a common area phone).</span></span>
    
- <span data-ttu-id="7ba0f-110">Mettere una chiamata in attesa e mantenere il telefono di risposta originale gratuito per altre chiamate.</span><span class="sxs-lookup"><span data-stu-id="7ba0f-110">Put a call on hold and keep the original answering phone free for other calls.</span></span>
    
<span data-ttu-id="7ba0f-111">Quando un utente parcheggia una chiamata, Skype for Business Server trasferisce la chiamata a un numero temporaneo, detto orbita, in cui la chiamata viene mantenuta fino a quando non viene recuperata o il timeout. Skype for Business Server invia l'orbita all'utente che ha parcheggiato la chiamata.</span><span class="sxs-lookup"><span data-stu-id="7ba0f-111">When a user parks a call, Skype for Business Server transfers the call to a temporary number, called an orbit, where the call is held until it is retrieved or it times out. Skype for Business Server sends the orbit to the user who parked the call.</span></span> <span data-ttu-id="7ba0f-112">Per recuperare la chiamata parcheggiata, l'utente può selezionare il numero dell'orbita oppure fare clic sul collegamento orbita o sul pulsante nella finestra di conversazione.</span><span class="sxs-lookup"><span data-stu-id="7ba0f-112">To retrieve the parked call, the user can dial the orbit number or click the orbit link or button in the Conversation window.</span></span> 
  
<span data-ttu-id="7ba0f-113">L'utente che ha parcheggiato una chiamata può segnalare a qualcuno di recuperare la chiamata usando un meccanismo esterno, ad esempio messaggistica istantanea (IM) o un sistema di paging, per comunicare il numero dell'orbita a qualcun altro.</span><span class="sxs-lookup"><span data-stu-id="7ba0f-113">The user who parked a call can notify someone to retrieve the call by using an external mechanism, such as instant messaging (IM) or a paging system, to communicate the orbit number to someone else.</span></span> <span data-ttu-id="7ba0f-114">L'utente che ha parcheggiato la chiamata può uscire dalla finestra di conversazione per ricevere una notifica quando viene recuperata la chiamata.</span><span class="sxs-lookup"><span data-stu-id="7ba0f-114">The user who parked the call can leave the Conversation window open to receive notification when the call is retrieved.</span></span>
  
<span data-ttu-id="7ba0f-115">Poiché gli intervalli di Orbit sono univoci a livello globale, è possibile recuperare le chiamate da qualsiasi sito di Skype for Business Server o telefono PBX se il routing è configurato in modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="7ba0f-115">Because orbit ranges are globally unique, it is possible to retrieve calls from any Skype for Business Server site or PBX phone if routing is configured appropriately.</span></span> <span data-ttu-id="7ba0f-116">Se non si recupera la chiamata entro un periodo di tempo configurabile, la chiamata torna alla persona che l'ha parcheggiata.</span><span class="sxs-lookup"><span data-stu-id="7ba0f-116">If no one retrieves the call within a configurable amount of time, the call rings back to the person who parked it.</span></span> <span data-ttu-id="7ba0f-117">Se la persona non risponde alla risponderia, la chiamata viene trasferita a una destinazione di fallback, ad esempio a un operatore, se configurata.</span><span class="sxs-lookup"><span data-stu-id="7ba0f-117">If that person does not answer the ringback, the call is transferred to a fallback destination, such as to an operator, if so configured.</span></span> <span data-ttu-id="7ba0f-118">È possibile configurare il numero di volte in cui la chiamata squilla prima di essere trasferita da uno a dieci volte.</span><span class="sxs-lookup"><span data-stu-id="7ba0f-118">You can configure the number of times the call rings back before being transferred from one to ten times.</span></span> <span data-ttu-id="7ba0f-119">Se non si risponde a una chiamata trasferita, la chiamata viene disconnessa.</span><span class="sxs-lookup"><span data-stu-id="7ba0f-119">If no one answers a transferred call, the call is disconnected.</span></span> <span data-ttu-id="7ba0f-120">L'orbita viene liberata quando la chiamata viene recuperata o disconnessa.</span><span class="sxs-lookup"><span data-stu-id="7ba0f-120">The orbit is freed when the call is retrieved or disconnected.</span></span>
  
<span data-ttu-id="7ba0f-121">Quando si distribuisce Call Park, è necessario riservare intervalli di numeri di interno per le chiamate di parcheggio.</span><span class="sxs-lookup"><span data-stu-id="7ba0f-121">When you deploy Call Park, you need to reserve ranges of extension numbers for parking calls.</span></span> <span data-ttu-id="7ba0f-122">Queste estensioni devono essere estensioni virtuali: estensioni che non hanno un utente o un telefono assegnato.</span><span class="sxs-lookup"><span data-stu-id="7ba0f-122">These extensions need to be virtual extensions: extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="7ba0f-123">Si configura quindi la tabella Orbit di Call Park con gli intervalli di numeri di interno e si specifica quale servizio applicazione ospita l'applicazione di parcheggio di chiamata che gestisce ogni intervallo.</span><span class="sxs-lookup"><span data-stu-id="7ba0f-123">You then configure the call park orbit table with the ranges of extension numbers and specify which Application service hosts the Call Park application that handles each range.</span></span> <span data-ttu-id="7ba0f-124">Ogni pool Front end include una tabella di parcheggio di chiamata nel server back-end corrispondente usato per gestire le chiamate parcheggiate nel pool.</span><span class="sxs-lookup"><span data-stu-id="7ba0f-124">Each Front End pool has a Call Park table on the corresponding Back End Server that is used to manage calls that are parked on the pool.</span></span> <span data-ttu-id="7ba0f-125">L'elenco di intervalli orbit è archiviato in Central Management store e viene usato per instradare le orbite al pool di destinazione.</span><span class="sxs-lookup"><span data-stu-id="7ba0f-125">The list of orbit ranges is stored in Central Management store and is used to route orbits to the destination pool.</span></span> <span data-ttu-id="7ba0f-126">Ogni pool di Skype for Business Server in cui è distribuita e configurata l'applicazione Parcheggio di chiamata può avere uno o più intervalli di orbita.</span><span class="sxs-lookup"><span data-stu-id="7ba0f-126">Each Skype for Business Server pool where the Call Park application is deployed and configured can have one or more orbit ranges.</span></span> <span data-ttu-id="7ba0f-127">Gli intervalli di Orbit devono essere univoci a livello globale in tutta la distribuzione di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="7ba0f-127">Orbit ranges must be globally unique across the Skype for Business Server deployment.</span></span> 
  
<span data-ttu-id="7ba0f-128">Si configurano anche altre impostazioni di Call Park, ad esempio dove vengono reindirizzate le chiamate se si verificano il timeout e se la persona del telefono sente la musica durante il parcheggio.</span><span class="sxs-lookup"><span data-stu-id="7ba0f-128">You also configure other Call Park settings, such as where calls are redirected if they time out and whether the person on the phone hears music while parked.</span></span> <span data-ttu-id="7ba0f-129">È anche possibile specificare il file musicale da riprodurre mentre la chiamata è in attesa.</span><span class="sxs-lookup"><span data-stu-id="7ba0f-129">You can also specify the music file to play while the call is on hold.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7ba0f-130">I file musicali personalizzati per il parcheggio delle chiamate non vengono sottoposto a backup come parte del processo di ripristino di emergenza di Skype for Business Server e andranno perduti se i file caricati nel pool sono danneggiati, danneggiati o eliminati.</span><span class="sxs-lookup"><span data-stu-id="7ba0f-130">Customized music-on-hold files for Call Park are not backed up as part of the Skype for Business Server disaster recovery process and will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span> <span data-ttu-id="7ba0f-131">Mantieni sempre una copia di backup separata dei file personalizzati di musica in attesa caricati per Call Park.</span><span class="sxs-lookup"><span data-stu-id="7ba0f-131">Always keep a separate backup copy of the customized music-on-hold files that you have uploaded for Call Park.</span></span> 
  
<span data-ttu-id="7ba0f-132">L'applicazione Call Park è un componente di Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="7ba0f-132">The Call Park application is a component of Enterprise Voice.</span></span> <span data-ttu-id="7ba0f-133">Quando si distribuisce VoIP aziendale, l'applicazione Call Park viene installata e attivata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="7ba0f-133">When you deploy Enterprise Voice, the Call Park application is installed and activated automatically.</span></span> <span data-ttu-id="7ba0f-134">Prima di poter usare Call Park, tuttavia, l'amministratore di VoIP aziendale deve configurarlo e abilitarlo per gli utenti tramite il criterio vocale.</span><span class="sxs-lookup"><span data-stu-id="7ba0f-134">Before you can use Call Park, however, the Enterprise Voice administrator must configure it and enable it for users through voice policy.</span></span>
  
## <a name="deployment-and-requirements"></a><span data-ttu-id="7ba0f-135">Distribuzione e requisiti</span><span class="sxs-lookup"><span data-stu-id="7ba0f-135">Deployment and requirements</span></span>

<span data-ttu-id="7ba0f-136">L'applicazione Call Park viene automaticamente installata quando si distribuisce VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="7ba0f-136">The Call Park application is automatically installed when you deploy Enterprise Voice.</span></span> <span data-ttu-id="7ba0f-137">Si Abilita il parcheggio delle chiamate configurando il criterio vocale.</span><span class="sxs-lookup"><span data-stu-id="7ba0f-137">You enable Call Park by configuring voice policy.</span></span>
  
### <a name="software-requirements"></a><span data-ttu-id="7ba0f-138">Requisiti software</span><span class="sxs-lookup"><span data-stu-id="7ba0f-138">Software requirements</span></span>

<span data-ttu-id="7ba0f-139">Tutti i server front-end e i server Standard Edition in cui è distribuito Call Park devono avere installato Windows Media Format Runtime per i server che utilizzano Windows Server 2008 R2 o Microsoft Media Foundation per i server che utilizzano Windows Server 2012 o Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="7ba0f-139">All Front End Servers and Standard Edition servers where Call Park is deployed must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="7ba0f-140">Per Windows Server 2008 R2, Windows Media Format Runtime viene installato come parte dell'esperienza desktop di Windows.</span><span class="sxs-lookup"><span data-stu-id="7ba0f-140">For Windows Server 2008 R2, Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span> <span data-ttu-id="7ba0f-141">Windows Media Format Runtime o Microsoft Media Foundation è necessario per i file di Windows Media Audio (con estensione WMA) che chiamano Play Park per la musica in attesa.</span><span class="sxs-lookup"><span data-stu-id="7ba0f-141">Windows Media Format Runtime or Microsoft Media Foundation is required for Windows Media Audio (.wma) files that Call Park plays for music on hold.</span></span>
  
### <a name="port-requirements"></a><span data-ttu-id="7ba0f-142">Requisiti della porta</span><span class="sxs-lookup"><span data-stu-id="7ba0f-142">Port requirements</span></span>

<span data-ttu-id="7ba0f-143">L'applicazione Call Park USA la **porta 5075** per le richieste di ascolto SIP.</span><span class="sxs-lookup"><span data-stu-id="7ba0f-143">The Call Park application uses **Port 5075**  for SIP listening requests.</span></span>
    
> [!NOTE]
> <span data-ttu-id="7ba0f-144">Questa porta è un'impostazione predefinita che puoi modificare usando il cmdlet **Set-CsApplicationServer** .</span><span class="sxs-lookup"><span data-stu-id="7ba0f-144">This port is a default setting that you can change by using the **Set-CsApplicationServer** cmdlet.</span></span> <span data-ttu-id="7ba0f-145">Per informazioni dettagliate su questo cmdlet, vedere la documentazione di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="7ba0f-145">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>
  
### <a name="audio-file-requirements"></a><span data-ttu-id="7ba0f-146">Requisiti per i file audio</span><span class="sxs-lookup"><span data-stu-id="7ba0f-146">Audio File requirements</span></span>

<span data-ttu-id="7ba0f-147">L'applicazione Call Park supporta solo file con estensione WMA (Windows Media Audio) per la musica in attesa.</span><span class="sxs-lookup"><span data-stu-id="7ba0f-147">The Call Park application supports only Windows Media Audio (.wma) files for music on hold.</span></span> <span data-ttu-id="7ba0f-148">È possibile usare Microsoft Expression Encoder 4 per personalizzare i file per la musica in attesa.</span><span class="sxs-lookup"><span data-stu-id="7ba0f-148">You can use the Microsoft Expression Encoder 4 to customize files for music on hold.</span></span> <span data-ttu-id="7ba0f-149">Per scaricare Expression Encoder 4, vedere ["Expression Encoder 4"](https://go.microsoft.com/fwlink/p/?linkId=202843).</span><span class="sxs-lookup"><span data-stu-id="7ba0f-149">To download Expression Encoder 4, see   ["Expression Encoder 4"](https://go.microsoft.com/fwlink/p/?linkId=202843).</span></span> <span data-ttu-id="7ba0f-150">Usare lo strumento per convertire il file in un formato WMA.</span><span class="sxs-lookup"><span data-stu-id="7ba0f-150">Use the tool to convert the file to a .wma format.</span></span> <span data-ttu-id="7ba0f-151">Il formato consigliato per i file musicali di Call Park-in-blocco è l'audio multimediale 9, 44 kHz, 16 bit, mono, CBR, 32 kbps.</span><span class="sxs-lookup"><span data-stu-id="7ba0f-151">The recommended format for Call Park music-on-hold files is Media Audio 9, 44 kHz, 16 bits, Mono, CBR, 32 kbps.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7ba0f-152">Il file convertito viene riprodotto al telefono solo a 16 kHz, anche se è stato registrato in 44 kHz.</span><span class="sxs-lookup"><span data-stu-id="7ba0f-152">The converted file plays over the phone only at 16 kHz, even if it was recorded at 44 kHz.</span></span> 
  
## <a name="supported-clients-and-calls"></a><span data-ttu-id="7ba0f-153">Client e chiamate supportati</span><span class="sxs-lookup"><span data-stu-id="7ba0f-153">Supported clients and calls</span></span>

<span data-ttu-id="7ba0f-154">I client e i tipi di chiamate seguenti sono supportati per Call Park</span><span class="sxs-lookup"><span data-stu-id="7ba0f-154">The following clients and types of calls are supported for Call Park</span></span>
  
### <a name="clients-supported-for-parking-calls"></a><span data-ttu-id="7ba0f-155">Client supportati per le chiamate di parcheggio</span><span class="sxs-lookup"><span data-stu-id="7ba0f-155">Clients Supported for Parking Calls</span></span>

<span data-ttu-id="7ba0f-156">Le chiamate da qualsiasi IP, PBX (Private Branch Exchange), PSTN (Public Switched Telephone Network) o cellulare possono essere parcheggiate.</span><span class="sxs-lookup"><span data-stu-id="7ba0f-156">Calls from any IP, private branch exchange (PBX), public switched telephone network (PSTN), or mobile phone can be parked.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7ba0f-157">Solo le chiamate audio possono essere parcheggiate.</span><span class="sxs-lookup"><span data-stu-id="7ba0f-157">Only audio calls can be parked.</span></span> <span data-ttu-id="7ba0f-158">I messaggi istantanei e le conferenze non possono essere parcheggiati.</span><span class="sxs-lookup"><span data-stu-id="7ba0f-158">Instant messages and conferences cannot be parked.</span></span> 
  
<span data-ttu-id="7ba0f-159">I client seguenti possono usare Call Park per parcheggiare le chiamate:</span><span class="sxs-lookup"><span data-stu-id="7ba0f-159">The following clients can use Call Park to park calls:</span></span>
  
- <span data-ttu-id="7ba0f-160">Skype for business</span><span class="sxs-lookup"><span data-stu-id="7ba0f-160">Skype for Business</span></span>
    
- <span data-ttu-id="7ba0f-161">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="7ba0f-161">Lync 2013</span></span>
    
- <span data-ttu-id="7ba0f-162">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="7ba0f-162">Lync 2010</span></span>
    
- <span data-ttu-id="7ba0f-163">Assistente di Lync 2010</span><span class="sxs-lookup"><span data-stu-id="7ba0f-163">Lync 2010 Attendant</span></span>
    
- <span data-ttu-id="7ba0f-164">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="7ba0f-164">Lync Phone Edition</span></span>
    
> [!NOTE]
> <span data-ttu-id="7ba0f-165">I telefoni cellulari non possono usare Call Park per parcheggiare le chiamate.</span><span class="sxs-lookup"><span data-stu-id="7ba0f-165">Mobile phones cannot use Call Park to park calls.</span></span> 
  
### <a name="clients-supported-for-retrieving-calls"></a><span data-ttu-id="7ba0f-166">Client supportati per il recupero delle chiamate</span><span class="sxs-lookup"><span data-stu-id="7ba0f-166">Clients Supported for Retrieving Calls</span></span>

<span data-ttu-id="7ba0f-167">Gli intervalli di Orbit sono configurati come blocchi di estensioni virtuali (estensioni senza un utente o un telefono assegnato).</span><span class="sxs-lookup"><span data-stu-id="7ba0f-167">Orbit ranges are configured as blocks of virtual extensions (extensions without an assigned user or phone).</span></span> <span data-ttu-id="7ba0f-168">Quando si configurano le orbite come estensioni virtuali, i telefoni cellulari e i telefoni PSTN non possono recuperare chiamate parcheggiate.</span><span class="sxs-lookup"><span data-stu-id="7ba0f-168">When you configure orbits as virtual extensions, mobile phones and PSTN phones cannot retrieve parked calls.</span></span>
  
<span data-ttu-id="7ba0f-169">Gli utenti federati non possono recuperare chiamate parcheggiate.</span><span class="sxs-lookup"><span data-stu-id="7ba0f-169">Federated users cannot retrieve parked calls.</span></span>
  
<span data-ttu-id="7ba0f-170">I client seguenti possono recuperare le chiamate parcheggiate su Call Park:</span><span class="sxs-lookup"><span data-stu-id="7ba0f-170">The following clients can retrieve calls that are parked on Call Park:</span></span>
  
- <span data-ttu-id="7ba0f-171">Skype for business</span><span class="sxs-lookup"><span data-stu-id="7ba0f-171">Skype for Business</span></span>
    
- <span data-ttu-id="7ba0f-172">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="7ba0f-172">Lync 2013</span></span>
    
- <span data-ttu-id="7ba0f-173">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="7ba0f-173">Lync 2010</span></span>
    
- <span data-ttu-id="7ba0f-174">Assistente di Lync 2010</span><span class="sxs-lookup"><span data-stu-id="7ba0f-174">Lync 2010 Attendant</span></span>
    
- <span data-ttu-id="7ba0f-175">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="7ba0f-175">Lync Phone Edition</span></span>
    
- <span data-ttu-id="7ba0f-176">Telefoni di area comune IP</span><span class="sxs-lookup"><span data-stu-id="7ba0f-176">IP common area phones</span></span>
    
- <span data-ttu-id="7ba0f-177">Telefoni non IP connessi all'infrastruttura di Skype for Business Server, inclusi i telefoni delle aree comuni e i telefoni PBX (Private Branch Exchange)</span><span class="sxs-lookup"><span data-stu-id="7ba0f-177">Non-IP phones that are connected to the Skype for Business Server infrastructure, including common area phones and private branch exchange (PBX) phones</span></span>
    
## <a name="call-park-capacity-planning"></a><span data-ttu-id="7ba0f-178">Pianificazione della capacità di Call Park</span><span class="sxs-lookup"><span data-stu-id="7ba0f-178">Call Park capacity planning</span></span>

<span data-ttu-id="7ba0f-179">La tabella seguente descrive il modello utente di Call Park che puoi usare come base per i requisiti di pianificazione della capacità.</span><span class="sxs-lookup"><span data-stu-id="7ba0f-179">The following table describes the Call Park user model that you can use as the basis for capacity planning requirements.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="7ba0f-180">Tieni presente che, per la pianificazione della capacità di ripristino di emergenza, ogni pool di un pool associato dovrebbe essere in grado di gestire i carichi di lavoro per i servizi di Call Park in entrambi i pool.</span><span class="sxs-lookup"><span data-stu-id="7ba0f-180">Keep in mind that, for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for Call Park services in both pools.</span></span> 
  
<span data-ttu-id="7ba0f-181">**Modello utente di Call Park**</span><span class="sxs-lookup"><span data-stu-id="7ba0f-181">**Call Park User Model**</span></span>

|<span data-ttu-id="7ba0f-182">**Metrica**</span><span class="sxs-lookup"><span data-stu-id="7ba0f-182">**Metric**</span></span>|<span data-ttu-id="7ba0f-183">**Per pool <br/> front-end (con 8 server front-end)**</span><span class="sxs-lookup"><span data-stu-id="7ba0f-183">**Per Front End pool  <br/>  (with 8 Front End Servers)**</span></span>|<span data-ttu-id="7ba0f-184">**Per server Standard Edition**</span><span class="sxs-lookup"><span data-stu-id="7ba0f-184">**Per Standard Edition server**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7ba0f-185">Tasso di parcheggio</span><span class="sxs-lookup"><span data-stu-id="7ba0f-185">Park rate</span></span>  <br/> |<span data-ttu-id="7ba0f-186">8 al minuto</span><span class="sxs-lookup"><span data-stu-id="7ba0f-186">8 per minute</span></span>  <br/> |<span data-ttu-id="7ba0f-187">1 al minuto</span><span class="sxs-lookup"><span data-stu-id="7ba0f-187">1 per minute</span></span>  <br/> |
|<span data-ttu-id="7ba0f-188">Recuperare la frequenza delle chiamate parcheggiate</span><span class="sxs-lookup"><span data-stu-id="7ba0f-188">Retrieve parked call rate</span></span>  <br/> |<span data-ttu-id="7ba0f-189">8 al minuto</span><span class="sxs-lookup"><span data-stu-id="7ba0f-189">8 per minute</span></span>  <br/> |<span data-ttu-id="7ba0f-190">1 al minuto</span><span class="sxs-lookup"><span data-stu-id="7ba0f-190">1 per minute</span></span>  <br/> |
|<span data-ttu-id="7ba0f-191">Durata media del parco</span><span class="sxs-lookup"><span data-stu-id="7ba0f-191">Average park duration</span></span>  <br/> |<span data-ttu-id="7ba0f-192">60 secondi</span><span class="sxs-lookup"><span data-stu-id="7ba0f-192">60 seconds</span></span>  <br/> |<span data-ttu-id="7ba0f-193">60 secondi</span><span class="sxs-lookup"><span data-stu-id="7ba0f-193">60 seconds</span></span>  <br/> |
   

