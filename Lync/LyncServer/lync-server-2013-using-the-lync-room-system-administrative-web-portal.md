---
title: 'Lync Server 2013: utilizzo del portale Web amministrativo di Lync room System'
description: 'Lync Server 2013: utilizzo del portale Web amministrativo di Lync room System.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Lync Room System Administrative Web Portal
ms:assetid: c387b2a3-3e42-4642-af72-88126ed2820f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743660(v=OCS.15)
ms:contentKeyID: 62268951
ms.date: 11/13/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 28c29677080bf081eae0fa4227e4cb56ccac697b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579652"
---
# <a name="using-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a><span data-ttu-id="00d01-103">Utilizzo del portale Web amministrativo di Lync room System in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="00d01-103">Using the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="00d01-104">_**Ultimo argomento modificato:** 2014-11-10_</span><span class="sxs-lookup"><span data-stu-id="00d01-104">_**Topic Last Modified:** 2014-11-10_</span></span>

<span data-ttu-id="00d01-105">Dopo la distribuzione di LRS nel server, è possibile controllare lo stato di tutte le sale di LRS accedendo al portale di amministrazione di LRS da un browser.</span><span class="sxs-lookup"><span data-stu-id="00d01-105">After you deploy LRS on the server, you can check the status of all LRS rooms by signing into the LRS Administrative Web Portal from a browser.</span></span>

<div>

## <a name="sign-in"></a><span data-ttu-id="00d01-106">Accesso</span><span class="sxs-lookup"><span data-stu-id="00d01-106">Sign in</span></span>

1.  <span data-ttu-id="00d01-107">Passare all'URL seguente:</span><span class="sxs-lookup"><span data-stu-id="00d01-107">Browse to the following URL:</span></span>
    
    <span data-ttu-id="00d01-108">https:// \<fe-server\> /LRS</span><span class="sxs-lookup"><span data-stu-id="00d01-108">https://\<fe-server\>/lrs</span></span>

2.  <span data-ttu-id="00d01-109">Immettere le credenziali per l'account di LRSSupport o un account che è stato aggiunto al gruppo di sicurezza di LRSSupportAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="00d01-109">Enter the credentials for the LRSSupport account or an account that has been added to the LRSSupportAdminGroup security group.</span></span>

<span data-ttu-id="00d01-110">![Schermata di accesso al portale di amministrazione di Lync room System](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Schermata di accesso al portale di amministrazione di Lync room System")</span><span class="sxs-lookup"><span data-stu-id="00d01-110">![Lync Room System Admin Portal Sign In screen](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Lync Room System Admin Portal Sign In screen")</span></span>

</div>

<div>

## <a name="lrs-administrative-web-portal-summary-page"></a><span data-ttu-id="00d01-111">Pagina di riepilogo del portale Web amministrativo di LRS</span><span class="sxs-lookup"><span data-stu-id="00d01-111">LRS Administrative Web Portal Summary Page</span></span>

<span data-ttu-id="00d01-112">Nella pagina Riepilogo sono disponibili le informazioni seguenti per tutte le sale di LRS distribuite nel server:</span><span class="sxs-lookup"><span data-stu-id="00d01-112">The summary page provides the following information for all of the LRS rooms deployed on the server:</span></span>

  - <span data-ttu-id="00d01-113">**Tag**     Nome personalizzato che viene fornito dall'amministratore per la sala.</span><span class="sxs-lookup"><span data-stu-id="00d01-113">**Tag**   The custom name that the administrator gives to the room.</span></span> <span data-ttu-id="00d01-114">Il tag può essere impostato nel portale facendo clic sul nome della sala.</span><span class="sxs-lookup"><span data-stu-id="00d01-114">The Tag can be set in the portal by clicking on the room name.</span></span>

  - <span data-ttu-id="00d01-115">**Integrità**     Lo stato di integrità della sala, che deriva dallo stato di integrità di aggregazione della sala, visualizzata nella sezione integrità della pagina impostazioni sala.</span><span class="sxs-lookup"><span data-stu-id="00d01-115">**Health**   The health status of the room, which is derived from the Aggregate Health status of the room, which is shown under the Health section of the Room Settings page.</span></span>

  - <span data-ttu-id="00d01-116">**Prossima riunione**     Data e ora in cui viene pianificata la riunione successiva.</span><span class="sxs-lookup"><span data-stu-id="00d01-116">**Next Meeting**   The date and time the next meeting is scheduled.</span></span>

  - <span data-ttu-id="00d01-117">**Versione di LRS, produttore, modello**     Questi valori sono preimpostati in LRS.</span><span class="sxs-lookup"><span data-stu-id="00d01-117">**LRS Version, Manufacturer, Model**   These values are preset in LRS.</span></span> <span data-ttu-id="00d01-118">A seconda del produttore, questi campi potrebbero essere lasciati vuoti.</span><span class="sxs-lookup"><span data-stu-id="00d01-118">Depending on the manufacturer, these fields might be left blank.</span></span>

  - <span data-ttu-id="00d01-119">**Ultimo aggiornamento**     Visualizza l'ultima volta che la pagina Web è stata aggiornata.</span><span class="sxs-lookup"><span data-stu-id="00d01-119">**Last Refresh**   Displays the last time the webpage was refreshed.</span></span>

<span data-ttu-id="00d01-120">![Visualizzazione di riepilogo del portale di amministrazione di Lync room System](images/Dn743660.f829ce90-dd95-4725-bd94-6870c5dcf046(OCS.15).png "Visualizzazione di riepilogo del portale di amministrazione di Lync room System")</span><span class="sxs-lookup"><span data-stu-id="00d01-120">![Lync Room System Admin Portal Summary View](images/Dn743660.f829ce90-dd95-4725-bd94-6870c5dcf046(OCS.15).png "Lync Room System Admin Portal Summary View")</span></span>

</div>

<div>

## <a name="lrs-room-information"></a><span data-ttu-id="00d01-121">Informazioni sulla sala LRS</span><span class="sxs-lookup"><span data-stu-id="00d01-121">LRS Room Information</span></span>

<span data-ttu-id="00d01-122">La sezione informazioni sala del portale consente di visualizzare e configurare le singole sale di LRS.</span><span class="sxs-lookup"><span data-stu-id="00d01-122">The Room Info section of the portal allows you to view and configure individual LRS rooms.</span></span> <span data-ttu-id="00d01-123">Contiene quattro sezioni: impostazioni, dettagli, risoluzione dei problemi e integrità.</span><span class="sxs-lookup"><span data-stu-id="00d01-123">It contains four sections: Settings, Details, Troubleshooting, and Health.</span></span>

<div>

## <a name="settings"></a><span data-ttu-id="00d01-124">Impostazioni</span><span class="sxs-lookup"><span data-stu-id="00d01-124">Settings</span></span>

<span data-ttu-id="00d01-125">Nella sezione impostazioni è possibile impostare la password, il tag sala e i livelli di volume predefiniti per la sala.</span><span class="sxs-lookup"><span data-stu-id="00d01-125">In the Settings section, you can set the password, room tag, and default volume levels for the room.</span></span> <span data-ttu-id="00d01-126">Se si configurano queste impostazioni, le modifiche vengono replicate solo dopo aver riavviato la console di LRS.</span><span class="sxs-lookup"><span data-stu-id="00d01-126">If you configure these settings, the changes are replicated only after you restart the LRS console.</span></span> <span data-ttu-id="00d01-127">Verranno visualizzate solo le impostazioni degli aggiornamenti di sistema per i sistemi sala Lync che sono la versione 15,12 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="00d01-127">You will only see System Updates settings for Lync Room Systems that are version 15.12 and later.</span></span>

<span data-ttu-id="00d01-128">![Impostazioni delle sale del portale di amministrazione di Lync room System](images/Dn743660.ab162e19-41ac-4991-9b2a-92575aa53eda(OCS.15).png "Impostazioni delle sale del portale di amministrazione di Lync room System")</span><span class="sxs-lookup"><span data-stu-id="00d01-128">![Lync Room System Admin Portal Room Settings](images/Dn743660.ab162e19-41ac-4991-9b2a-92575aa53eda(OCS.15).png "Lync Room System Admin Portal Room Settings")</span></span>

</div>

<div>

## <a name="details"></a><span data-ttu-id="00d01-129">Dettagli</span><span class="sxs-lookup"><span data-stu-id="00d01-129">Details</span></span>

<span data-ttu-id="00d01-130">Nella sezione dettagli viene fornito un riepilogo di sola lettura delle impostazioni della sala LRS, tra cui: l'ora dell'ultimo aggiornamento. prossima riunione; ultimi aggiornamenti, manutenzione e calibrazione; impostazioni predefinite per altoparlanti, MIC e suonerie; versione URI SIP; numero di schermate e dettagli relativi a ogni schermata; stato e attività.</span><span class="sxs-lookup"><span data-stu-id="00d01-130">The Details section provides a read-only summary of the LRS room’s settings, including: the time of last refresh; next meeting; last updates, maintenance and calibration; default speaker, mic, and ringer settings; version; SIP URI; number of screens and details about each screen; status, and activity.</span></span>

<span data-ttu-id="00d01-131">![Visualizzazione dettagli del portale di amministrazione di Lync room System](images/Dn743660.2958bbba-db74-4670-a920-87fdfb2fc22d(OCS.15).png "Visualizzazione dettagli del portale di amministrazione di Lync room System")</span><span class="sxs-lookup"><span data-stu-id="00d01-131">![Lync Room System Admin Portal Detail View](images/Dn743660.2958bbba-db74-4670-a920-87fdfb2fc22d(OCS.15).png "Lync Room System Admin Portal Detail View")</span></span>

</div>

<div>

## <a name="troubleshooting"></a><span data-ttu-id="00d01-132">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="00d01-132">Troubleshooting</span></span>

<span data-ttu-id="00d01-133">La sezione risoluzione dei problemi può essere utilizzata per raccogliere i log in remoto e salvarli in una posizione specificata.</span><span class="sxs-lookup"><span data-stu-id="00d01-133">The Troubleshooting section can be used to remotely collect logs and save them to a specified location.</span></span> <span data-ttu-id="00d01-134">È inoltre possibile riavviare la console di LRS (interfaccia utente di LRS) o riavviare l'intero sistema.</span><span class="sxs-lookup"><span data-stu-id="00d01-134">You can also restart the LRS console (LRS user interface) or restart the entire system.</span></span> <span data-ttu-id="00d01-135">Per raccogliere i registri, specificare un percorso di cartella nel formato specificato e verificare che la cartella disponga delle autorizzazioni di scrittura concesse all'account del computer LRS.</span><span class="sxs-lookup"><span data-stu-id="00d01-135">To collect logs, provide a folder path in the specified format and make sure that the folder has write permissions given to the LRS machine account.</span></span> <span data-ttu-id="00d01-136">Se la dimensione del registro è troppo grande, è possibile richiedere fino a 5 minuti per completare la raccolta dei registri.</span><span class="sxs-lookup"><span data-stu-id="00d01-136">If the log size is too big, it can take up to 5 minutes to finish collecting logs.</span></span> <span data-ttu-id="00d01-137">L'aggiornamento della pagina consente di ottenere lo stato più recente.</span><span class="sxs-lookup"><span data-stu-id="00d01-137">Refreshing the page will give you the latest status.</span></span>

<span data-ttu-id="00d01-138">![Registrazione sala del portale di amministrazione di Lync room System](images/Dn743660.749aee71-deaa-4ace-a146-fe2b349f0f42(OCS.15).png "Registrazione sala del portale di amministrazione di Lync room System")</span><span class="sxs-lookup"><span data-stu-id="00d01-138">![Lync Room System Admin Portal Room Logging](images/Dn743660.749aee71-deaa-4ace-a146-fe2b349f0f42(OCS.15).png "Lync Room System Admin Portal Room Logging")</span></span>

</div>

<div>

## <a name="health"></a><span data-ttu-id="00d01-139">Sanità</span><span class="sxs-lookup"><span data-stu-id="00d01-139">Health</span></span>

<span data-ttu-id="00d01-140">La sezione Health fornisce un'indicazione visiva dell'integrità della connessione di Lync Server, del dispositivo audio, del dispositivo video, dello stato di resilienza e del dispositivo schermo.</span><span class="sxs-lookup"><span data-stu-id="00d01-140">The Health section gives a visual indication of the health of the Lync Server connection, audio device, video device, resiliency state, and screen device.</span></span>

<span data-ttu-id="00d01-141">![Integrità della sala del portale di amministrazione di Lync room System](images/Dn743660.8cc644f8-8e3e-42d5-9079-045d8fe9daa7(OCS.15).png "Integrità della sala del portale di amministrazione di Lync room System")</span><span class="sxs-lookup"><span data-stu-id="00d01-141">![Lync Room System Admin Portal Room Health](images/Dn743660.8cc644f8-8e3e-42d5-9079-045d8fe9daa7(OCS.15).png "Lync Room System Admin Portal Room Health")</span></span>

</div>

</div>

<div>

## <a name="additional-notes-about-the-administrative-web-portal"></a><span data-ttu-id="00d01-142">Note aggiuntive sul portale Web amministrativo</span><span class="sxs-lookup"><span data-stu-id="00d01-142">Additional Notes about the Administrative Web Portal</span></span>

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P><span data-ttu-id="00d01-143">Le modifiche apportate alle impostazioni vengono applicate solo dopo il riavvio del sistema LRS.</span><span class="sxs-lookup"><span data-stu-id="00d01-143">Setting changes are applied only after the LRS system is restarted.</span></span></P>
> <LI>
> <P><span data-ttu-id="00d01-144">Se la password dell'account LRSApp scade, l'utente non sarà in grado di visualizzare lo stato delle chat room.</span><span class="sxs-lookup"><span data-stu-id="00d01-144">If the LRSApp account password expires, you will not be able to see the status of the rooms.</span></span> <span data-ttu-id="00d01-145">Configurare la password dell'account LRSAppuser in modo che non scada mai o accertarsi di aggiornare la password al termine della scadenza.</span><span class="sxs-lookup"><span data-stu-id="00d01-145">Configure the LRSAppuser account password so that it never expires, or be sure to update the password when it’s near expiration.</span></span></P>
> <LI>
> <P><span data-ttu-id="00d01-146">Il portale Web amministrativo di LRS è supportato solo per le distribuzioni locali.</span><span class="sxs-lookup"><span data-stu-id="00d01-146">The LRS administrative web portal is supported for on-premises deployments only.</span></span></P></LI></UL>



</div>

</div>

<div>

## <a name="frequently-asked-questions"></a><span data-ttu-id="00d01-147">Domande frequenti</span><span class="sxs-lookup"><span data-stu-id="00d01-147">Frequently Asked Questions</span></span>

<div>

## <a name="why-cant-i-sign-in-to-the-administrative-web-portal"></a><span data-ttu-id="00d01-148">Perché non è possibile accedere al portale Web amministrativo?</span><span class="sxs-lookup"><span data-stu-id="00d01-148">Why can’t I sign in to the administrative web portal?</span></span>

  - <span data-ttu-id="00d01-149">Quando si apre https://localhost/lrs , si sarà in grado di visualizzare la pagina di accesso, ma quando si digita le credenziali, non è possibile accedere.</span><span class="sxs-lookup"><span data-stu-id="00d01-149">When you open https://localhost/lrs, you will be able to see the sign in page, but when you type in your credentials, you cannot sign in.</span></span> <span data-ttu-id="00d01-150">In questo caso, è necessario aprire https://FQDNofFEserver/lrs per accedere al portale Web amministrativo.</span><span class="sxs-lookup"><span data-stu-id="00d01-150">In this case, you must open https://FQDNofFEserver/lrs to sign in to the administrative web portal.</span></span>

  - <span data-ttu-id="00d01-151">Se il computer da cui si sta accedendo al portale Web amministrativo è in un gruppo di lavoro, "http://" non funzionerà.</span><span class="sxs-lookup"><span data-stu-id="00d01-151">If the machine from which you are accessing the administrative web portal is in a workgroup, "http://" will not work.</span></span> <span data-ttu-id="00d01-152">Utilizzare invece "https".</span><span class="sxs-lookup"><span data-stu-id="00d01-152">Use "https" instead.</span></span>

</div>

<div>

## <a name="why-cant-i-see-lrs-in-the-administrative-web-portal"></a><span data-ttu-id="00d01-153">Perché non è possibile visualizzare LRS nel portale Web amministrativo?</span><span class="sxs-lookup"><span data-stu-id="00d01-153">Why can’t I see LRS in the administrative web portal?</span></span>

  - <span data-ttu-id="00d01-154">Verificare di disporre degli account di LRS nella distribuzione e che vengano creati in base ai suggerimenti relativi alla distribuzione del portale Web amministrativo di LRS.</span><span class="sxs-lookup"><span data-stu-id="00d01-154">Make sure you have LRS accounts in your deployment and that they are created according to the LRS Administrative Web Portal deployment recommendations.</span></span> <span data-ttu-id="00d01-155">Verificare che gli account di LRS siano sottoposto a provisioning mediante Enable-CsMeetingRoom, not Enable-CsUser, sul server Lync.</span><span class="sxs-lookup"><span data-stu-id="00d01-155">Make sure the LRS accounts are provisioned using Enable-CsMeetingRoom, not Enable-CsUser, on the Lync server.</span></span>

  - <span data-ttu-id="00d01-156">Se sono stati creati account di LRS e non è possibile visualizzare gli account nel portale Web amministrativo, raccogliere i registri del server utilizzando lo strumento di registrazione di Lync Server con il componente **MeetingPortal** selezionato e quindi inviarli al contatto di supporto di LRS.</span><span class="sxs-lookup"><span data-stu-id="00d01-156">If you have created LRS accounts and cannot see the accounts in administrative web portal, collect the server logs by using the Lync Server Logging tool with the **MeetingPortal** component selected, and then send them to your LRS support contact.</span></span>

</div>

<div>

## <a name="why-cant-i-see-the-status-of-lrs-in-the-administrative-web-portal"></a><span data-ttu-id="00d01-157">Perché non è possibile visualizzare lo stato di LRS nel portale Web di amministrazione?</span><span class="sxs-lookup"><span data-stu-id="00d01-157">Why can’t I see the status of LRS in the administrative web portal?</span></span>

  - <span data-ttu-id="00d01-158">Verificare che l'account utente di LRSApp sia abilitato per SIP.</span><span class="sxs-lookup"><span data-stu-id="00d01-158">Make sure that the LRSApp user account is SIP-enabled.</span></span>

  - <span data-ttu-id="00d01-159">Se si verificano ancora problemi, raccogliere il file **Trace. log** nel sistema LRS da D: \\ Tracing \\ LRSAdminLogs \\ e quindi inviarlo al contatto di supporto di LRS.</span><span class="sxs-lookup"><span data-stu-id="00d01-159">If you are still having issues, collect the **Trace.log** file in the LRS system from D:\\Tracing\\LRSAdminLogs\\, and then send it to your LRS support contact.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

