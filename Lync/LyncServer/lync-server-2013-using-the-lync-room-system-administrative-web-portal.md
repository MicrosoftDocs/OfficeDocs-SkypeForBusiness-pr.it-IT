---
title: 'Lync Server 2013: Uso del portale Web amministrativo di Lync Room System'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using the Lync Room System Administrative Web Portal
ms:assetid: c387b2a3-3e42-4642-af72-88126ed2820f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743660(v=OCS.15)
ms:contentKeyID: 62268951
ms.date: 11/13/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2369cdde9d14275fddf007b5e073c748ce5a8906
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984263"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a><span data-ttu-id="1f23f-102">Uso del portale Web amministrativo di Lync Room System in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1f23f-102">Using the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1f23f-103">_**Argomento Ultima modifica:** 2014-11-10_</span><span class="sxs-lookup"><span data-stu-id="1f23f-103">_**Topic Last Modified:** 2014-11-10_</span></span>

<span data-ttu-id="1f23f-104">Dopo la distribuzione di LRS nel server, è possibile controllare lo stato di tutte le sale di LRS accedendo al portale Web amministrativo di LRS da un browser.</span><span class="sxs-lookup"><span data-stu-id="1f23f-104">After you deploy LRS on the server, you can check the status of all LRS rooms by signing into the LRS Administrative Web Portal from a browser.</span></span>

<div>

## <a name="sign-in"></a><span data-ttu-id="1f23f-105">Accedi</span><span class="sxs-lookup"><span data-stu-id="1f23f-105">Sign in</span></span>

1.  <span data-ttu-id="1f23f-106">Passare all'URL seguente:</span><span class="sxs-lookup"><span data-stu-id="1f23f-106">Browse to the following URL:</span></span>
    
    <span data-ttu-id="1f23f-107">https://\<Fe-server\>/LRS</span><span class="sxs-lookup"><span data-stu-id="1f23f-107">https://\<fe-server\>/lrs</span></span>

2.  <span data-ttu-id="1f23f-108">Immettere le credenziali per l'account di LRSSupport o un account aggiunto al gruppo di sicurezza di LRSSupportAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="1f23f-108">Enter the credentials for the LRSSupport account or an account that has been added to the LRSSupportAdminGroup security group.</span></span>

<span data-ttu-id="1f23f-109">Schermata ![di accesso al portale di amministrazione di Lync room System](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "")</span><span class="sxs-lookup"><span data-stu-id="1f23f-109">![Lync Room System Admin Portal Sign In screen](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Lync Room System Admin Portal Sign In screen")</span></span>

</div>

<div>

## <a name="lrs-administrative-web-portal-summary-page"></a><span data-ttu-id="1f23f-110">Pagina di riepilogo di LRS Administrative Web Portal</span><span class="sxs-lookup"><span data-stu-id="1f23f-110">LRS Administrative Web Portal Summary Page</span></span>

<span data-ttu-id="1f23f-111">Nella pagina di riepilogo sono disponibili le informazioni seguenti per tutte le sale LRS distribuite nel server:</span><span class="sxs-lookup"><span data-stu-id="1f23f-111">The summary page provides the following information for all of the LRS rooms deployed on the server:</span></span>

  - <span data-ttu-id="1f23f-112">**Contrassegnare**   il nome personalizzato che l'amministratore assegna alla chat room.</span><span class="sxs-lookup"><span data-stu-id="1f23f-112">**Tag**   The custom name that the administrator gives to the room.</span></span> <span data-ttu-id="1f23f-113">Il tag può essere impostato nel portale facendo clic sul nome della chat room.</span><span class="sxs-lookup"><span data-stu-id="1f23f-113">The Tag can be set in the portal by clicking on the room name.</span></span>

  - <span data-ttu-id="1f23f-114">**Integrità**   lo stato di integrità della sala, derivato dallo stato di integrità aggregato della sala, visualizzato nella sezione integrità della pagina impostazioni sala.</span><span class="sxs-lookup"><span data-stu-id="1f23f-114">**Health**   The health status of the room, which is derived from the Aggregate Health status of the room, which is shown under the Health section of the Room Settings page.</span></span>

  - <span data-ttu-id="1f23f-115">**Riunione successiva la**   data e l'ora in cui è programmata la riunione successiva.</span><span class="sxs-lookup"><span data-stu-id="1f23f-115">**Next Meeting**   The date and time the next meeting is scheduled.</span></span>

  - <span data-ttu-id="1f23f-116">**LRS versione, produttore, modello**   questi valori sono preimpostati in LRS.</span><span class="sxs-lookup"><span data-stu-id="1f23f-116">**LRS Version, Manufacturer, Model**   These values are preset in LRS.</span></span> <span data-ttu-id="1f23f-117">A seconda del produttore, questi campi potrebbero essere lasciati vuoti.</span><span class="sxs-lookup"><span data-stu-id="1f23f-117">Depending on the manufacturer, these fields might be left blank.</span></span>

  - <span data-ttu-id="1f23f-118">**L'ultimo aggiornamento**   Visualizza l'ultima volta che è stata aggiornata la pagina Web.</span><span class="sxs-lookup"><span data-stu-id="1f23f-118">**Last Refresh**   Displays the last time the webpage was refreshed.</span></span>

<span data-ttu-id="1f23f-119">Interfaccia di ![amministrazione di Lync room System-visualizzazione]Riepilogo del portale di amministrazione di(images/Dn743660.f829ce90-dd95-4725-bd94-6870c5dcf046(OCS.15).png "Lync room System")</span><span class="sxs-lookup"><span data-stu-id="1f23f-119">![Lync Room System Admin Portal Summary View](images/Dn743660.f829ce90-dd95-4725-bd94-6870c5dcf046(OCS.15).png "Lync Room System Admin Portal Summary View")</span></span>

</div>

<div>

## <a name="lrs-room-information"></a><span data-ttu-id="1f23f-120">LRS informazioni sulle camere</span><span class="sxs-lookup"><span data-stu-id="1f23f-120">LRS Room Information</span></span>

<span data-ttu-id="1f23f-121">La sezione informazioni sala del portale consente di visualizzare e configurare singole sale LRS.</span><span class="sxs-lookup"><span data-stu-id="1f23f-121">The Room Info section of the portal allows you to view and configure individual LRS rooms.</span></span> <span data-ttu-id="1f23f-122">Contiene quattro sezioni: impostazioni, dettagli, risoluzione dei problemi e integrità.</span><span class="sxs-lookup"><span data-stu-id="1f23f-122">It contains four sections: Settings, Details, Troubleshooting, and Health.</span></span>

<div>

## <a name="settings"></a><span data-ttu-id="1f23f-123">Impostazioni</span><span class="sxs-lookup"><span data-stu-id="1f23f-123">Settings</span></span>

<span data-ttu-id="1f23f-124">Nella sezione Impostazioni puoi impostare la password, il tag room e i livelli di volume predefiniti per la chat room.</span><span class="sxs-lookup"><span data-stu-id="1f23f-124">In the Settings section, you can set the password, room tag, and default volume levels for the room.</span></span> <span data-ttu-id="1f23f-125">Se si configurano queste impostazioni, le modifiche verranno replicate solo dopo aver riavviato la console LRS.</span><span class="sxs-lookup"><span data-stu-id="1f23f-125">If you configure these settings, the changes are replicated only after you restart the LRS console.</span></span> <span data-ttu-id="1f23f-126">Verranno visualizzate solo le impostazioni di aggiornamenti di sistema per i sistemi room Lync versione 15,12 e successive.</span><span class="sxs-lookup"><span data-stu-id="1f23f-126">You will only see System Updates settings for Lync Room Systems that are version 15.12 and later.</span></span>

<span data-ttu-id="1f23f-127">Impostazioni della sala di ![amministrazione di Lync room System Portal Settings]di(images/Dn743660.ab162e19-41ac-4991-9b2a-92575aa53eda(OCS.15).png "Lync room System")</span><span class="sxs-lookup"><span data-stu-id="1f23f-127">![Lync Room System Admin Portal Room Settings](images/Dn743660.ab162e19-41ac-4991-9b2a-92575aa53eda(OCS.15).png "Lync Room System Admin Portal Room Settings")</span></span>

</div>

<div>

## <a name="details"></a><span data-ttu-id="1f23f-128">Dettagli</span><span class="sxs-lookup"><span data-stu-id="1f23f-128">Details</span></span>

<span data-ttu-id="1f23f-129">La sezione dettagli offre un riepilogo di sola lettura delle impostazioni della sala LRS, tra cui: l'ora dell'ultimo aggiornamento; riunione successiva; ultimi aggiornamenti, manutenzione e calibrazione; impostazioni predefinite altoparlante, microfono e suoneria; versione URI SIP; numero di schermate e dettagli su ogni schermata; stato e attività.</span><span class="sxs-lookup"><span data-stu-id="1f23f-129">The Details section provides a read-only summary of the LRS room’s settings, including: the time of last refresh; next meeting; last updates, maintenance and calibration; default speaker, mic, and ringer settings; version; SIP URI; number of screens and details about each screen; status, and activity.</span></span>

<span data-ttu-id="1f23f-130">![Informazioni dettagliate sul portale di amministrazione di Lync]room System per la visualizzazione dei(images/Dn743660.2958bbba-db74-4670-a920-87fdfb2fc22d(OCS.15).png "Dettagli del portale di amministrazione")</span><span class="sxs-lookup"><span data-stu-id="1f23f-130">![Lync Room System Admin Portal Detail View](images/Dn743660.2958bbba-db74-4670-a920-87fdfb2fc22d(OCS.15).png "Lync Room System Admin Portal Detail View")</span></span>

</div>

<div>

## <a name="troubleshooting"></a><span data-ttu-id="1f23f-131">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="1f23f-131">Troubleshooting</span></span>

<span data-ttu-id="1f23f-132">La sezione risoluzione dei problemi può essere usata per raccogliere i log in remoto e salvarli in una posizione specifica.</span><span class="sxs-lookup"><span data-stu-id="1f23f-132">The Troubleshooting section can be used to remotely collect logs and save them to a specified location.</span></span> <span data-ttu-id="1f23f-133">È anche possibile riavviare la console LRS (interfaccia utente di LRS) o riavviare l'intero sistema.</span><span class="sxs-lookup"><span data-stu-id="1f23f-133">You can also restart the LRS console (LRS user interface) or restart the entire system.</span></span> <span data-ttu-id="1f23f-134">Per raccogliere i log, specificare un percorso di cartella nel formato specificato e verificare che la cartella disponga delle autorizzazioni di scrittura assegnate all'account del computer LRS.</span><span class="sxs-lookup"><span data-stu-id="1f23f-134">To collect logs, provide a folder path in the specified format and make sure that the folder has write permissions given to the LRS machine account.</span></span> <span data-ttu-id="1f23f-135">Se le dimensioni del log sono troppo grandi, possono essere necessarie fino a 5 minuti per completare la raccolta dei log.</span><span class="sxs-lookup"><span data-stu-id="1f23f-135">If the log size is too big, it can take up to 5 minutes to finish collecting logs.</span></span> <span data-ttu-id="1f23f-136">L'aggiornamento della pagina ti darà lo stato più recente.</span><span class="sxs-lookup"><span data-stu-id="1f23f-136">Refreshing the page will give you the latest status.</span></span>

<span data-ttu-id="1f23f-137">Interfaccia di ![amministrazione di Lync room System Portal Login]sala di(images/Dn743660.749aee71-deaa-4ace-a146-fe2b349f0f42(OCS.15).png "amministrazione di Lync room System")</span><span class="sxs-lookup"><span data-stu-id="1f23f-137">![Lync Room System Admin Portal Room Logging](images/Dn743660.749aee71-deaa-4ace-a146-fe2b349f0f42(OCS.15).png "Lync Room System Admin Portal Room Logging")</span></span>

</div>

<div>

## <a name="health"></a><span data-ttu-id="1f23f-138">Integrità</span><span class="sxs-lookup"><span data-stu-id="1f23f-138">Health</span></span>

<span data-ttu-id="1f23f-139">La sezione integrità offre un'indicazione visiva dell'integrità della connessione Lync Server, del dispositivo audio, del dispositivo video, dello stato di resilienza e del dispositivo schermo.</span><span class="sxs-lookup"><span data-stu-id="1f23f-139">The Health section gives a visual indication of the health of the Lync Server connection, audio device, video device, resiliency state, and screen device.</span></span>

<span data-ttu-id="1f23f-140">Interfaccia di ![amministrazione di Lync room System Portal]per l'integrità della sala di(images/Dn743660.8cc644f8-8e3e-42d5-9079-045d8fe9daa7(OCS.15).png "Amministrazione") dell'ambiente</span><span class="sxs-lookup"><span data-stu-id="1f23f-140">![Lync Room System Admin Portal Room Health](images/Dn743660.8cc644f8-8e3e-42d5-9079-045d8fe9daa7(OCS.15).png "Lync Room System Admin Portal Room Health")</span></span>

</div>

</div>

<div>

## <a name="additional-notes-about-the-administrative-web-portal"></a><span data-ttu-id="1f23f-141">Altre note sul portale Web amministrativo</span><span class="sxs-lookup"><span data-stu-id="1f23f-141">Additional Notes about the Administrative Web Portal</span></span>

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P><span data-ttu-id="1f23f-142">L'impostazione delle modifiche viene applicata solo dopo il riavvio del sistema LRS.</span><span class="sxs-lookup"><span data-stu-id="1f23f-142">Setting changes are applied only after the LRS system is restarted.</span></span></P>
> <LI>
> <P><span data-ttu-id="1f23f-143">Se la password dell'account LRSApp scade, non sarà possibile visualizzare lo stato delle chat room.</span><span class="sxs-lookup"><span data-stu-id="1f23f-143">If the LRSApp account password expires, you will not be able to see the status of the rooms.</span></span> <span data-ttu-id="1f23f-144">Configurare la password dell'account di LRSAppuser in modo che non scada mai o assicurarsi di aggiornare la password quando è vicina alla scadenza.</span><span class="sxs-lookup"><span data-stu-id="1f23f-144">Configure the LRSAppuser account password so that it never expires, or be sure to update the password when it’s near expiration.</span></span></P>
> <LI>
> <P><span data-ttu-id="1f23f-145">Il portale Web amministrativo di LRS è supportato solo per le distribuzioni locali.</span><span class="sxs-lookup"><span data-stu-id="1f23f-145">The LRS administrative web portal is supported for on-premises deployments only.</span></span></P></LI></UL>



</div>

</div>

<div>

## <a name="frequently-asked-questions"></a><span data-ttu-id="1f23f-146">Domande frequenti</span><span class="sxs-lookup"><span data-stu-id="1f23f-146">Frequently Asked Questions</span></span>

<div>

## <a name="why-cant-i-sign-in-to-the-administrative-web-portal"></a><span data-ttu-id="1f23f-147">Perché non è possibile accedere al portale Web amministrativo?</span><span class="sxs-lookup"><span data-stu-id="1f23f-147">Why can’t I sign in to the administrative web portal?</span></span>

  - <span data-ttu-id="1f23f-148">Quando si apre https://localhost/lrs, sarà possibile visualizzare la pagina di accesso, ma quando si digita le credenziali non è possibile accedere.</span><span class="sxs-lookup"><span data-stu-id="1f23f-148">When you open https://localhost/lrs, you will be able to see the sign in page, but when you type in your credentials, you cannot sign in.</span></span> <span data-ttu-id="1f23f-149">In questo caso, è necessario aprire https://FQDNofFEserver/lrs per accedere al portale Web amministrativo.</span><span class="sxs-lookup"><span data-stu-id="1f23f-149">In this case, you must open https://FQDNofFEserver/lrs to sign in to the administrative web portal.</span></span>

  - <span data-ttu-id="1f23f-150">Se il computer da cui si accede al portale Web amministrativo è in un gruppo di lavoro, "http://" non funzionerà.</span><span class="sxs-lookup"><span data-stu-id="1f23f-150">If the machine from which you are accessing the administrative web portal is in a workgroup, "http://" will not work.</span></span> <span data-ttu-id="1f23f-151">USA invece "https".</span><span class="sxs-lookup"><span data-stu-id="1f23f-151">Use "https" instead.</span></span>

</div>

<div>

## <a name="why-cant-i-see-lrs-in-the-administrative-web-portal"></a><span data-ttu-id="1f23f-152">Perché non è possibile visualizzare LRS nel portale Web amministrativo?</span><span class="sxs-lookup"><span data-stu-id="1f23f-152">Why can’t I see LRS in the administrative web portal?</span></span>

  - <span data-ttu-id="1f23f-153">Verificare di avere gli account di LRS nella distribuzione e di essere creati in base ai consigli di distribuzione di LRS Administrative Web Portal.</span><span class="sxs-lookup"><span data-stu-id="1f23f-153">Make sure you have LRS accounts in your deployment and that they are created according to the LRS Administrative Web Portal deployment recommendations.</span></span> <span data-ttu-id="1f23f-154">Verificare che gli account di LRS vengano provisionati usando Enable-CsMeetingRoom, non Enable-CsUser, nel server Lync.</span><span class="sxs-lookup"><span data-stu-id="1f23f-154">Make sure the LRS accounts are provisioned using Enable-CsMeetingRoom, not Enable-CsUser, on the Lync server.</span></span>

  - <span data-ttu-id="1f23f-155">Se sono stati creati account di LRS e non è possibile visualizzare gli account nel portale Web amministrativo, raccogliere i log del server usando lo strumento di registrazione di Lync Server con il componente **MeetingPortal** selezionato e quindi inviarli al contatto di supporto di LRS.</span><span class="sxs-lookup"><span data-stu-id="1f23f-155">If you have created LRS accounts and cannot see the accounts in administrative web portal, collect the server logs by using the Lync Server Logging tool with the **MeetingPortal** component selected, and then send them to your LRS support contact.</span></span>

</div>

<div>

## <a name="why-cant-i-see-the-status-of-lrs-in-the-administrative-web-portal"></a><span data-ttu-id="1f23f-156">Perché non è possibile visualizzare lo stato di LRS nel portale Web amministrativo?</span><span class="sxs-lookup"><span data-stu-id="1f23f-156">Why can’t I see the status of LRS in the administrative web portal?</span></span>

  - <span data-ttu-id="1f23f-157">Verificare che l'account utente di LRSApp sia abilitato per SIP.</span><span class="sxs-lookup"><span data-stu-id="1f23f-157">Make sure that the LRSApp user account is SIP-enabled.</span></span>

  - <span data-ttu-id="1f23f-158">Se si verificano ancora problemi, raccogliere il file **Trace. log** nel sistema LRS da D:\\Tracing\\LRSAdminLogs\\e quindi inviarlo al contatto di supporto di LRS.</span><span class="sxs-lookup"><span data-stu-id="1f23f-158">If you are still having issues, collect the **Trace.log** file in the LRS system from D:\\Tracing\\LRSAdminLogs\\, and then send it to your LRS support contact.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

