---
title: Pianificare il parcheggio di chiamata in Skype for business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Pianificazione del parcheggio di chiamata in Skype for Business Server VoIP aziendale, che consente di inserire le chiamate in attesa e di trasferire le chiamate ai reparti. Include la pianificazione della capacità, le chiamate supportate e i client supportati.
ms.openlocfilehash: c324e8d61f6d0e9e67870f05597a9157965a3eb3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825926"
---
# <a name="plan-for-call-park-in-skype-for-business"></a><span data-ttu-id="b52bc-104">Pianificare il parcheggio di chiamata in Skype for business</span><span class="sxs-lookup"><span data-stu-id="b52bc-104">Plan for Call Park in Skype for Business</span></span>
 
<span data-ttu-id="b52bc-105">Pianificazione del parcheggio di chiamata in Skype for Business Server VoIP aziendale, che consente di inserire le chiamate in attesa e di trasferire le chiamate ai reparti.</span><span class="sxs-lookup"><span data-stu-id="b52bc-105">Planning for call park in Skype for Business Server Enterprise Voice, which enables putting calls on hold and transferring calls to departments.</span></span> <span data-ttu-id="b52bc-106">Include la pianificazione della capacità, le chiamate supportate e i client supportati.</span><span class="sxs-lookup"><span data-stu-id="b52bc-106">Includes capacity planning, supported calls, and supported clients.</span></span>
  
<span data-ttu-id="b52bc-107">L'applicazione Parcheggio di chiamata consente agli utenti di VoIP aziendale di eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b52bc-107">The Call Park application enables Enterprise Voice users to do the following:</span></span>
  
- <span data-ttu-id="b52bc-108">Mettere una chiamata in attesa e quindi recuperare la chiamata dallo stesso telefono o da uno diverso.</span><span class="sxs-lookup"><span data-stu-id="b52bc-108">Put a call on hold and then retrieve the call from the same phone or another phone.</span></span>
    
- <span data-ttu-id="b52bc-109">Mettere una chiamata in attesa per trasferirla a un altro reparto o a un'altra area generale, ad esempio a un reparto vendite o un magazzino in cui è presente un telefono di area comune.</span><span class="sxs-lookup"><span data-stu-id="b52bc-109">Put a call on hold to transfer it to a department or general area (for example, to a sales department or a warehouse where there is a common area phone).</span></span>
    
- <span data-ttu-id="b52bc-110">Mettere una chiamata in attesa e mantenere libero per altre chiamate il telefono originale da cui si è risposto alla chiamata.</span><span class="sxs-lookup"><span data-stu-id="b52bc-110">Put a call on hold and keep the original answering phone free for other calls.</span></span>
    
<span data-ttu-id="b52bc-111">Quando un utente effettua una chiamata, Skype for Business Server trasferisce la chiamata a un numero temporaneo, denominato orbita, in cui la chiamata viene mantenuta fino a quando non viene recuperata o non viene rilasciata. Skype for Business Server invia l'orbita all'utente che ha parcheggiato la chiamata.</span><span class="sxs-lookup"><span data-stu-id="b52bc-111">When a user parks a call, Skype for Business Server transfers the call to a temporary number, called an orbit, where the call is held until it is retrieved or it times out. Skype for Business Server sends the orbit to the user who parked the call.</span></span> <span data-ttu-id="b52bc-112">Per recuperare la chiamata parcheggiata, l'utente può comporre il codice orbit o fare clic sul collegamento o il pulsante del codice orbit nella finestra Conversazione.</span><span class="sxs-lookup"><span data-stu-id="b52bc-112">To retrieve the parked call, the user can dial the orbit number or click the orbit link or button in the Conversation window.</span></span> 
  
<span data-ttu-id="b52bc-p104">L'utente che ha eseguito il parcheggio di una chiamata può indicare a qualcun altro di recuperare la chiamata utilizzando un meccanismo esterno, ad esempio un sistema di messaggistica istantanea o di paging, per comunicare il codice orbit a un altro utente. L'utente che ha eseguito il parcheggio della chiamata può lasciare aperta la finestra Conversazione per ricevere una notifica quando la chiamata viene recuperata.</span><span class="sxs-lookup"><span data-stu-id="b52bc-p104">The user who parked a call can notify someone to retrieve the call by using an external mechanism, such as instant messaging (IM) or a paging system, to communicate the orbit number to someone else. The user who parked the call can leave the Conversation window open to receive notification when the call is retrieved.</span></span>
  
<span data-ttu-id="b52bc-115">Poiché gli intervalli di Orbit sono univoci a livello globale, è possibile recuperare le chiamate da qualsiasi sito di Skype for Business Server o telefono PBX se il routing è configurato in modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="b52bc-115">Because orbit ranges are globally unique, it is possible to retrieve calls from any Skype for Business Server site or PBX phone if routing is configured appropriately.</span></span> <span data-ttu-id="b52bc-116">Se nessuno recupera la chiamata entro una quantità di tempo configurabile, la chiamata viene nuovamente indirizzata alla persona che ne ha eseguito il parcheggio.</span><span class="sxs-lookup"><span data-stu-id="b52bc-116">If no one retrieves the call within a configurable amount of time, the call rings back to the person who parked it.</span></span> <span data-ttu-id="b52bc-117">Se tale persona non risponde alla richiamata, la chiamata viene trasferita a una destinazione di fallback, ad esempio a un operatore, se questa impostazione è configurata.</span><span class="sxs-lookup"><span data-stu-id="b52bc-117">If that person does not answer the ringback, the call is transferred to a fallback destination, such as to an operator, if so configured.</span></span> <span data-ttu-id="b52bc-118">È possibile configurare da uno a dieci il numero di volte per cui consentire una richiamata prima che la chiamata venga trasferita.</span><span class="sxs-lookup"><span data-stu-id="b52bc-118">You can configure the number of times the call rings back before being transferred from one to ten times.</span></span> <span data-ttu-id="b52bc-119">Se nessuno risponde a una chiamata trasferita, questa viene disconnessa.</span><span class="sxs-lookup"><span data-stu-id="b52bc-119">If no one answers a transferred call, the call is disconnected.</span></span> <span data-ttu-id="b52bc-120">Il codice orbit viene liberato quando la chiamata viene recuperata o disconnessa.</span><span class="sxs-lookup"><span data-stu-id="b52bc-120">The orbit is freed when the call is retrieved or disconnected.</span></span>
  
<span data-ttu-id="b52bc-121">Quando si distribuisce il parcheggio di chiamata, è necessario riservare intervalli di numeri di interno (codici orbit) per il parcheggio delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="b52bc-121">When you deploy Call Park, you need to reserve ranges of extension numbers for parking calls.</span></span> <span data-ttu-id="b52bc-122">Tali numeri devono essere interni virtuali, ovvero numeri a cui non sono assegnati utenti o telefoni.</span><span class="sxs-lookup"><span data-stu-id="b52bc-122">These extensions need to be virtual extensions: extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="b52bc-123">È quindi necessario configurare la tabella dei codici orbit del parcheggio di chiamata con gli intervalli di interni e specificare il servizio applicazione che ospita l'applicazione Parcheggio di chiamata che gestisce ogni intervallo.</span><span class="sxs-lookup"><span data-stu-id="b52bc-123">You then configure the call park orbit table with the ranges of extension numbers and specify which Application service hosts the Call Park application that handles each range.</span></span> <span data-ttu-id="b52bc-124">Ogni pool Front End include una tabella di parcheggio di chiamata nel server di back-end corrispondente utilizzato per gestire le chiamate parcheggiate nel pool.</span><span class="sxs-lookup"><span data-stu-id="b52bc-124">Each Front End pool has a Call Park table on the corresponding Back End Server that is used to manage calls that are parked on the pool.</span></span> <span data-ttu-id="b52bc-125">L'elenco degli intervalli di Orbit è memorizzato nell'archivio di gestione centrale e viene utilizzato per instradare le orbite al pool di destinazione.</span><span class="sxs-lookup"><span data-stu-id="b52bc-125">The list of orbit ranges is stored in Central Management store and is used to route orbits to the destination pool.</span></span> <span data-ttu-id="b52bc-126">Ogni pool di Skype for Business Server in cui è distribuita e configurata l'applicazione Parcheggio di chiamata può disporre di uno o più intervalli di Orbit.</span><span class="sxs-lookup"><span data-stu-id="b52bc-126">Each Skype for Business Server pool where the Call Park application is deployed and configured can have one or more orbit ranges.</span></span> <span data-ttu-id="b52bc-127">Gli intervalli di Orbit devono essere univoci a livello globale nella distribuzione di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="b52bc-127">Orbit ranges must be globally unique across the Skype for Business Server deployment.</span></span> 
  
<span data-ttu-id="b52bc-p107">È anche possibile configurare altre impostazioni di parcheggio chiamata, ad esempio la destinazione di reindirizzamento delle chiamate in caso di timeout e se usare la musica di attesa durante il parcheggio. È anche possibile specificare il file musicale da riprodurre mentre la chiamata è in attesa.</span><span class="sxs-lookup"><span data-stu-id="b52bc-p107">You also configure other Call Park settings, such as where calls are redirected if they time out and whether the person on the phone hears music while parked. You can also specify the music file to play while the call is on hold.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b52bc-130">I file musicali personalizzati per il parcheggio di chiamata non vengono sottoposti a backup come parte del processo di ripristino di emergenza di Skype for Business Server e andranno persi se i file caricati nel pool sono danneggiati, danneggiati o eliminati.</span><span class="sxs-lookup"><span data-stu-id="b52bc-130">Customized music-on-hold files for Call Park are not backed up as part of the Skype for Business Server disaster recovery process and will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span> <span data-ttu-id="b52bc-131">Mantenere sempre una copia di backup distinta dei file di musica di attesa personalizzati caricati per il parcheggio chiamate.</span><span class="sxs-lookup"><span data-stu-id="b52bc-131">Always keep a separate backup copy of the customized music-on-hold files that you have uploaded for Call Park.</span></span> 
  
<span data-ttu-id="b52bc-p109">L'applicazione Parcheggio di chiamata è un componente di VoIP aziendale. Quando si distribuisce VoIP aziendale, l'applicazione Parcheggio di chiamata viene installata e attivata automaticamente. Prima di poter utilizzare l'applicazione Parcheggio di chiamata, tuttavia, l'amministratore di VoIP aziendale deve configurarla e abilitarla per gli utenti tramite criteri vocali.</span><span class="sxs-lookup"><span data-stu-id="b52bc-p109">The Call Park application is a component of Enterprise Voice. When you deploy Enterprise Voice, the Call Park application is installed and activated automatically. Before you can use Call Park, however, the Enterprise Voice administrator must configure it and enable it for users through voice policy.</span></span>
  
## <a name="deployment-and-requirements"></a><span data-ttu-id="b52bc-135">Distribuzione e requisiti</span><span class="sxs-lookup"><span data-stu-id="b52bc-135">Deployment and requirements</span></span>

<span data-ttu-id="b52bc-136">L'applicazione Parcheggio di chiamata viene automaticamente installata quando si distribuisce VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="b52bc-136">The Call Park application is automatically installed when you deploy Enterprise Voice.</span></span> <span data-ttu-id="b52bc-137">Si Abilita il parcheggio di chiamata configurando il criterio vocale.</span><span class="sxs-lookup"><span data-stu-id="b52bc-137">You enable Call Park by configuring voice policy.</span></span>
  
### <a name="software-requirements"></a><span data-ttu-id="b52bc-138">Requisiti software</span><span class="sxs-lookup"><span data-stu-id="b52bc-138">Software requirements</span></span>

<span data-ttu-id="b52bc-139">Tutti i Front End Server e i server Standard Edition in cui è distribuito il parcheggio di chiamata devono avere installato Windows Media Format Runtime per i server che eseguono Windows Server 2008 R2 o Microsoft Media Foundation per i server che eseguono Windows Server 2012 o Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="b52bc-139">All Front End Servers and Standard Edition servers where Call Park is deployed must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="b52bc-140">Per Windows Server 2008 R2, Windows Media Format Runtime è installato come parte dell'esperienza desktop di Windows.</span><span class="sxs-lookup"><span data-stu-id="b52bc-140">For Windows Server 2008 R2, Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span> <span data-ttu-id="b52bc-141">Windows Media Format Runtime o Microsoft Media Foundation è necessario per i file Windows Media Audio (. WMA) che il parcheggio di chiamata gioca per la musica di attesa.</span><span class="sxs-lookup"><span data-stu-id="b52bc-141">Windows Media Format Runtime or Microsoft Media Foundation is required for Windows Media Audio (.wma) files that Call Park plays for music on hold.</span></span>
  
### <a name="port-requirements"></a><span data-ttu-id="b52bc-142">Requisiti delle porte</span><span class="sxs-lookup"><span data-stu-id="b52bc-142">Port requirements</span></span>

<span data-ttu-id="b52bc-143">L'applicazione Parcheggio di chiamata utilizza la **porta 5075**  per le richieste di attesa SIP.</span><span class="sxs-lookup"><span data-stu-id="b52bc-143">The Call Park application uses **Port 5075**  for SIP listening requests.</span></span>
    
> [!NOTE]
> <span data-ttu-id="b52bc-144">Questa porta è un'impostazione predefinita che può essere modificata usando il cmdlet **Set-CsApplicationServer**.</span><span class="sxs-lookup"><span data-stu-id="b52bc-144">This port is a default setting that you can change by using the **Set-CsApplicationServer** cmdlet.</span></span> <span data-ttu-id="b52bc-145">Per informazioni dettagliate su questo cmdlet, vedere la documentazione di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="b52bc-145">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>
  
### <a name="audio-file-requirements"></a><span data-ttu-id="b52bc-146">Requisiti dei file audio</span><span class="sxs-lookup"><span data-stu-id="b52bc-146">Audio File requirements</span></span>

<span data-ttu-id="b52bc-147">L'applicazione Parcheggio di chiamata supporta solo i file di Windows Media Audio (WMA) per la musica di attesa.</span><span class="sxs-lookup"><span data-stu-id="b52bc-147">The Call Park application supports only Windows Media Audio (.wma) files for music on hold.</span></span> <span data-ttu-id="b52bc-148">Per personalizzare i file per la musica di attesa, è possibile usare Microsoft Expression Encoder 4.</span><span class="sxs-lookup"><span data-stu-id="b52bc-148">You can use the Microsoft Expression Encoder 4 to customize files for music on hold.</span></span> <span data-ttu-id="b52bc-149">Per scaricare Expression Encoder 4, vedere   ["Expression Encoder 4"](https://go.microsoft.com/fwlink/p/?linkId=202843).</span><span class="sxs-lookup"><span data-stu-id="b52bc-149">To download Expression Encoder 4, see   ["Expression Encoder 4"](https://go.microsoft.com/fwlink/p/?linkId=202843).</span></span> <span data-ttu-id="b52bc-150">Utilizzare lo strumento per convertire il file in un formato wma.</span><span class="sxs-lookup"><span data-stu-id="b52bc-150">Use the tool to convert the file to a .wma format.</span></span> <span data-ttu-id="b52bc-151">Il formato consigliato per i file musicali del parcheggio di chiamata è media audio 9, 44 kHz, 16 bit, mono, CBR, 32 kbps.</span><span class="sxs-lookup"><span data-stu-id="b52bc-151">The recommended format for Call Park music-on-hold files is Media Audio 9, 44 kHz, 16 bits, Mono, CBR, 32 kbps.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b52bc-152">Il file convertito viene riprodotto nel telefono solo a 16 kHz, anche se è stato registrato a 44 kHz.</span><span class="sxs-lookup"><span data-stu-id="b52bc-152">The converted file plays over the phone only at 16 kHz, even if it was recorded at 44 kHz.</span></span> 
  
## <a name="supported-clients-and-calls"></a><span data-ttu-id="b52bc-153">Client e chiamate supportate</span><span class="sxs-lookup"><span data-stu-id="b52bc-153">Supported clients and calls</span></span>

<span data-ttu-id="b52bc-154">I client e i tipi di chiamate seguenti sono supportati per il parcheggio di chiamata</span><span class="sxs-lookup"><span data-stu-id="b52bc-154">The following clients and types of calls are supported for Call Park</span></span>
  
### <a name="clients-supported-for-parking-calls"></a><span data-ttu-id="b52bc-155">Client supportati per parcheggiare le chiamate</span><span class="sxs-lookup"><span data-stu-id="b52bc-155">Clients Supported for Parking Calls</span></span>

<span data-ttu-id="b52bc-156">È possibile parcheggiare chiamate da qualsiasi telefono IP, PBX (Private Branch Exchange), PSTN (Public Switched Telephone Network) o cellulare.</span><span class="sxs-lookup"><span data-stu-id="b52bc-156">Calls from any IP, private branch exchange (PBX), public switched telephone network (PSTN), or mobile phone can be parked.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b52bc-p114">Solo le chiamate audio possono essere parcheggiate. Questa funzionalità non è disponibile per messaggi istantanei e conferenze.</span><span class="sxs-lookup"><span data-stu-id="b52bc-p114">Only audio calls can be parked. Instant messages and conferences cannot be parked.</span></span> 
  
<span data-ttu-id="b52bc-159">I client seguenti possono utilizzare il parcheggio di chiamata per parcheggiare le chiamate:</span><span class="sxs-lookup"><span data-stu-id="b52bc-159">The following clients can use Call Park to park calls:</span></span>
  
- <span data-ttu-id="b52bc-160">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="b52bc-160">Skype for Business</span></span>
    
- <span data-ttu-id="b52bc-161">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="b52bc-161">Lync 2013</span></span>
    
- <span data-ttu-id="b52bc-162">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="b52bc-162">Lync 2010</span></span>
    
- <span data-ttu-id="b52bc-163">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="b52bc-163">Lync 2010 Attendant</span></span>
    
- <span data-ttu-id="b52bc-164">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="b52bc-164">Lync Phone Edition</span></span>
    
> [!NOTE]
> <span data-ttu-id="b52bc-165">I telefoni cellulari non possono utilizzare il parcheggio di chiamata per parcheggiare le chiamate.</span><span class="sxs-lookup"><span data-stu-id="b52bc-165">Mobile phones cannot use Call Park to park calls.</span></span> 
  
### <a name="clients-supported-for-retrieving-calls"></a><span data-ttu-id="b52bc-166">Client supportati per il recupero delle chiamate</span><span class="sxs-lookup"><span data-stu-id="b52bc-166">Clients Supported for Retrieving Calls</span></span>

<span data-ttu-id="b52bc-p115">Gli intervalli di codici orbit sono configurati come blocchi di estensioni virtuali, ovvero estensioni a cui non sono assegnati utenti o telefoni. Quando si configurano i codici orbit come estensioni virtuali, i telefoni cellulari e i telefoni PSTN non supportano il recupero delle chiamate parcheggiate.</span><span class="sxs-lookup"><span data-stu-id="b52bc-p115">Orbit ranges are configured as blocks of virtual extensions (extensions without an assigned user or phone). When you configure orbits as virtual extensions, mobile phones and PSTN phones cannot retrieve parked calls.</span></span>
  
<span data-ttu-id="b52bc-169">Gli utenti federati non possono recuperare le chiamate parcheggiate.</span><span class="sxs-lookup"><span data-stu-id="b52bc-169">Federated users cannot retrieve parked calls.</span></span>
  
<span data-ttu-id="b52bc-170">I client seguenti possono recuperare le chiamate parcheggiate su parcheggio di chiamata:</span><span class="sxs-lookup"><span data-stu-id="b52bc-170">The following clients can retrieve calls that are parked on Call Park:</span></span>
  
- <span data-ttu-id="b52bc-171">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="b52bc-171">Skype for Business</span></span>
    
- <span data-ttu-id="b52bc-172">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="b52bc-172">Lync 2013</span></span>
    
- <span data-ttu-id="b52bc-173">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="b52bc-173">Lync 2010</span></span>
    
- <span data-ttu-id="b52bc-174">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="b52bc-174">Lync 2010 Attendant</span></span>
    
- <span data-ttu-id="b52bc-175">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="b52bc-175">Lync Phone Edition</span></span>
    
- <span data-ttu-id="b52bc-176">Telefono IP di area comune</span><span class="sxs-lookup"><span data-stu-id="b52bc-176">IP common area phones</span></span>
    
- <span data-ttu-id="b52bc-177">Telefoni non IP che sono connessi all'infrastruttura di Skype for Business Server, compresi i telefoni delle aree comuni e i telefoni PBX (Private Branch Exchange)</span><span class="sxs-lookup"><span data-stu-id="b52bc-177">Non-IP phones that are connected to the Skype for Business Server infrastructure, including common area phones and private branch exchange (PBX) phones</span></span>
    
## <a name="call-park-capacity-planning"></a><span data-ttu-id="b52bc-178">Pianificazione della capacità del parcheggio di chiamata</span><span class="sxs-lookup"><span data-stu-id="b52bc-178">Call Park capacity planning</span></span>

<span data-ttu-id="b52bc-179">Nella tabella seguente viene descritto il modello utente del parcheggio di chiamata che è possibile utilizzare come base per i requisiti di pianificazione della capacità.</span><span class="sxs-lookup"><span data-stu-id="b52bc-179">The following table describes the Call Park user model that you can use as the basis for capacity planning requirements.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="b52bc-180">Tenere presente che, per la pianificazione della capacità di ripristino di emergenza, ogni pool di un pool associato dovrebbe essere in grado di gestire i carichi di lavoro per i servizi parcheggio di chiamata in entrambi i pool.</span><span class="sxs-lookup"><span data-stu-id="b52bc-180">Keep in mind that, for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for Call Park services in both pools.</span></span> 
  
<span data-ttu-id="b52bc-181">**Modello utente del parcheggio di chiamata**</span><span class="sxs-lookup"><span data-stu-id="b52bc-181">**Call Park User Model**</span></span>

|<span data-ttu-id="b52bc-182">**Metrica**</span><span class="sxs-lookup"><span data-stu-id="b52bc-182">**Metric**</span></span>|<span data-ttu-id="b52bc-183">**Per pool Front End  <br/>  (con 8 Front End Server)**</span><span class="sxs-lookup"><span data-stu-id="b52bc-183">**Per Front End pool  <br/>  (with 8 Front End Servers)**</span></span>|<span data-ttu-id="b52bc-184">**Per server Standard Edition**</span><span class="sxs-lookup"><span data-stu-id="b52bc-184">**Per Standard Edition server**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b52bc-185">Frequenza di parcheggio</span><span class="sxs-lookup"><span data-stu-id="b52bc-185">Park rate</span></span>  <br/> |<span data-ttu-id="b52bc-186">8 al minuto</span><span class="sxs-lookup"><span data-stu-id="b52bc-186">8 per minute</span></span>  <br/> |<span data-ttu-id="b52bc-187">1 al minuto</span><span class="sxs-lookup"><span data-stu-id="b52bc-187">1 per minute</span></span>  <br/> |
|<span data-ttu-id="b52bc-188">Frequenza di recupero delle chiamate parcheggiate</span><span class="sxs-lookup"><span data-stu-id="b52bc-188">Retrieve parked call rate</span></span>  <br/> |<span data-ttu-id="b52bc-189">8 al minuto</span><span class="sxs-lookup"><span data-stu-id="b52bc-189">8 per minute</span></span>  <br/> |<span data-ttu-id="b52bc-190">1 al minuto</span><span class="sxs-lookup"><span data-stu-id="b52bc-190">1 per minute</span></span>  <br/> |
|<span data-ttu-id="b52bc-191">Durata media del parcheggio</span><span class="sxs-lookup"><span data-stu-id="b52bc-191">Average park duration</span></span>  <br/> |<span data-ttu-id="b52bc-192">60 secondi</span><span class="sxs-lookup"><span data-stu-id="b52bc-192">60 seconds</span></span>  <br/> |<span data-ttu-id="b52bc-193">60 secondi</span><span class="sxs-lookup"><span data-stu-id="b52bc-193">60 seconds</span></span>  <br/> |
   

