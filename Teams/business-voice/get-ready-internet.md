---
title: Controllare la connessione Internet per Business Voice
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
localization_priority: Priority
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: ''
appliesto:
- Microsoft Teams
ms.openlocfilehash: 37bd749e44c2020d35a927491553662c74bff01f
ms.sourcegitcommit: fa567451f8f7af6d915e33809d88f26b415db54c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "44610975"
---
# <a name="check-your-internet-connection-for-business-voice"></a><span data-ttu-id="26183-102">Controllare la connessione Internet per Business Voice</span><span class="sxs-lookup"><span data-stu-id="26183-102">Check your Internet connection for Business Voice</span></span>

<span data-ttu-id="26183-103">VoIP aziendale si trova nel cloud con Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="26183-103">Business Voice is located in the cloud with Microsoft 365.</span></span> <span data-ttu-id="26183-104">Ogni dispositivo che usa Microsoft Teams e Business Voice richiede una connessione a Internet.</span><span class="sxs-lookup"><span data-stu-id="26183-104">Every device that uses Microsoft Teams and Business Voice needs a connection to the Internet.</span></span>

<span data-ttu-id="26183-105">Per un'esperienza ottimale di Business Voice, è necessaria una connessione Internet a banda larga in grado di supportare il numero massimo di chiamate telefoniche che verranno effettuate dall'organizzazione in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="26183-105">To get the best Business Voice experience, you need a broadband Internet connection that can support the maximum number of phone calls that your organization might make at any one time.</span></span> <span data-ttu-id="26183-106">È anche necessario assicurarsi che i computer della rete possano accedere ai server Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="26183-106">You also need to make sure that the computers on your network can reach Microsoft 365 servers.</span></span>

<span data-ttu-id="26183-107">Per eseguire questa procedura, è necessario avere un tenant con uno degli abbonamenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="26183-107">To follow these steps, you need to have a tenant with one of the following subscriptions:</span></span>

* <span data-ttu-id="26183-108">Microsoft 365 Business Basic</span><span class="sxs-lookup"><span data-stu-id="26183-108">Microsoft 365 Business Basic</span></span>
* <span data-ttu-id="26183-109">Microsoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="26183-109">Microsoft 365 Business Standard</span></span>
* <span data-ttu-id="26183-110">Office 365 E1</span><span class="sxs-lookup"><span data-stu-id="26183-110">Office 365 E1</span></span>
* <span data-ttu-id="26183-111">Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="26183-111">Office 365 E3</span></span>
* <span data-ttu-id="26183-112">Office 365 F1</span><span class="sxs-lookup"><span data-stu-id="26183-112">Office 365 F1</span></span>
* <span data-ttu-id="26183-113">Microsoft 365 A1</span><span class="sxs-lookup"><span data-stu-id="26183-113">Microsoft 365 A1</span></span>
* <span data-ttu-id="26183-114">Microsoft 365 A3</span><span class="sxs-lookup"><span data-stu-id="26183-114">Microsoft 365 A3</span></span>
* <span data-ttu-id="26183-115">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="26183-115">Microsoft 365 E3</span></span>
* <span data-ttu-id="26183-116">Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="26183-116">Microsoft 365 Business</span></span>

<span data-ttu-id="26183-117">Non è necessaria una licenza VoIP aziendale per eseguire questa procedura.</span><span class="sxs-lookup"><span data-stu-id="26183-117">You don't need a Business Voice license to follow these steps.</span></span>

## <a name="check-your-internet-connection-speed"></a><span data-ttu-id="26183-118">Controllare la velocità della connessione Internet</span><span class="sxs-lookup"><span data-stu-id="26183-118">Check your Internet connection speed</span></span>

<span data-ttu-id="26183-119">Questo articolo illustra come determinare se la connessione Internet è abbastanza veloce per il numero di persone che devono effettuare chiamate telefoniche e organizzare videoconferenze.</span><span class="sxs-lookup"><span data-stu-id="26183-119">This article helps determine whether your Internet connection is fast enough for the number of people who need to make phone calls and host video conferences.</span></span> <span data-ttu-id="26183-120">Fornendo alcune informazioni sull'organizzazione è possibile ottenere un report con la quantità di connessione Internet che verrà usata da Teams e da Business Voice.</span><span class="sxs-lookup"><span data-stu-id="26183-120">You'll provide information about your organization and get back a report that shows how much of your Internet connection will be used by Teams and Business Voice.</span></span>

### <a name="gather-information-about-your-internet-connection-and-users"></a><span data-ttu-id="26183-121">Raccogliere informazioni sulla connessione Internet e sugli utenti</span><span class="sxs-lookup"><span data-stu-id="26183-121">Gather information about your Internet connection and users</span></span>

<span data-ttu-id="26183-122">Prima di iniziare, è necessario disporre delle informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="26183-122">Before you start, you need the following information:</span></span>

* <span data-ttu-id="26183-123">La velocità della connessione Internet</span><span class="sxs-lookup"><span data-stu-id="26183-123">The speed of your Internet connection</span></span>
* <span data-ttu-id="26183-124">Quante persone useranno Business Voice principalmente dall'ufficio</span><span class="sxs-lookup"><span data-stu-id="26183-124">How many people will use Business Voice mainly from your office</span></span>
* <span data-ttu-id="26183-125">Quante persone useranno Business Voice principalmente da una posizione remota, come un ufficio a casa</span><span class="sxs-lookup"><span data-stu-id="26183-125">How many people will use Business Voice mainly from a remote location, such as a home office</span></span>

### <a name="enter-your-information-into-the-network-planner"></a><span data-ttu-id="26183-126">Immettere le informazioni in Network Planner</span><span class="sxs-lookup"><span data-stu-id="26183-126">Enter your information into the network planner</span></span>

<span data-ttu-id="26183-127">Eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="26183-127">Follow these steps:</span></span>

1. <span data-ttu-id="26183-128">Aprire un browser e passare a https://admin.teams.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="26183-128">In a browser, go to https://admin.teams.microsoft.com.</span></span> <span data-ttu-id="26183-129">Accedere con un account dotato di autorizzazioni di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="26183-129">Sign in by using an account that has Global Administrator permissions.</span></span> <span data-ttu-id="26183-130">L'account usato per iscriversi a Microsoft 365 o Office 365 dispone di queste autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="26183-130">The account that you used to sign up for Microsoft 365 or Office 365 has these permissions.</span></span>
2. <span data-ttu-id="26183-131">Aprire **Pianificazione** e selezionare **Network Planner**.</span><span class="sxs-lookup"><span data-stu-id="26183-131">Open **Planning** and select **Network planner**.</span></span>
3. <span data-ttu-id="26183-132">In **Piani di rete** selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="26183-132">Under **Network plans**, select **Add**.</span></span> <span data-ttu-id="26183-133">Immettere un nome per il piano e quindi selezionare **Applica**.</span><span class="sxs-lookup"><span data-stu-id="26183-133">Enter a name for your plan, and then select **Apply**.</span></span> <span data-ttu-id="26183-134">Il piano di rete dovrebbe essere simile a questo:</span><span class="sxs-lookup"><span data-stu-id="26183-134">Your network plan should look like this:</span></span>

    ![Schermata principale di Network Planner](../media/network-planner-main.png)
1. <span data-ttu-id="26183-136">Selezionare il nome del piano di rete.</span><span class="sxs-lookup"><span data-stu-id="26183-136">Select the name of your network plan.</span></span> <span data-ttu-id="26183-137">Si tratta di **Ufficio principale** nell'immagine precedente.</span><span class="sxs-lookup"><span data-stu-id="26183-137">(It's **Main office** in the preceding picture.)</span></span>
2. <span data-ttu-id="26183-138">Nella pagina successiva selezionare **Aggiungi un sito di rete** nella scheda **Siti di rete**.</span><span class="sxs-lookup"><span data-stu-id="26183-138">On the next page, select **Add a network site** on the **Network sites** tab.</span></span>
3. <span data-ttu-id="26183-139">Compilare solo i campi indicati nella schermata seguente e quindi selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="26183-139">Fill in only the fields that are indicated in the following screenshot, and then select **Save**.</span></span> <span data-ttu-id="26183-140">Lasciare vuoti gli altri campi della schermata e non selezionare le opzioni **ExpressRoute** o **Connesso a WAN**.</span><span class="sxs-lookup"><span data-stu-id="26183-140">Leave the other fields on this screen blank, and don't select the **ExpressRoute** or **Connected to WAN** options.</span></span>

    ![Informazioni sul sito di Network Planner](../media/network-planner-site-info.png)
1. <span data-ttu-id="26183-142">Nella scheda **Report** selezionare **Avviare un report**.</span><span class="sxs-lookup"><span data-stu-id="26183-142">On the **Report** tab, select **Start a report**.</span></span>
1. <span data-ttu-id="26183-143">Immettere le informazioni seguenti e quindi selezionare **Genera rapporto** per creare un report con i requisiti di larghezza di banda per Teams.</span><span class="sxs-lookup"><span data-stu-id="26183-143">Enter the following information, and then select **Generate report** to create a report that shows the bandwidth requirements for Teams.</span></span> <span data-ttu-id="26183-144">Mostreremo come leggere il report nella sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="26183-144">We show you how to read the report in the next section.</span></span>

    ![Informazioni sul report di Network Planner](../media/network-planner-report-info.png)

### <a name="find-your-minimum-internet-connection-speed"></a><span data-ttu-id="26183-146">Trovare la velocità minima della connessione Internet</span><span class="sxs-lookup"><span data-stu-id="26183-146">Find your minimum Internet connection speed</span></span>

<span data-ttu-id="26183-147">Dopo aver selezionato **Genera report**, Microsoft 365 o Office 365 crea un report simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="26183-147">When you select **Generate report**, Microsoft 365 or Office 365 creates a report that looks like this:</span></span>

![Dettagli sul report di Network Planner](../media/network-planner-report.png)

<span data-ttu-id="26183-149">Il numero evidenziato indica la quantità di connessione Internet che Teams e VoIP aziendale useranno.</span><span class="sxs-lookup"><span data-stu-id="26183-149">The highlighted number shows how much of your Internet connection Teams and Business Voice will use.</span></span> <span data-ttu-id="26183-150">Si consiglia di non superare il 30% della velocità totale della connessione Internet.</span><span class="sxs-lookup"><span data-stu-id="26183-150">We recommend that this number is no more than 30 percent of your total Internet connection speed.</span></span> <span data-ttu-id="26183-151">Ad esempio, se la connessione Internet è di 60 Mbps, Teams e Business Voice non devono usare più di 18 Mbps.</span><span class="sxs-lookup"><span data-stu-id="26183-151">For example, if your Internet connection is 60 Mbps, Teams and Business Voice should use no more than 18 Mbps.</span></span>

<span data-ttu-id="26183-152">Usare questa equazione per determinare la velocità della connessione Internet minima: *\<highlighted number> / 0,3*.</span><span class="sxs-lookup"><span data-stu-id="26183-152">Use this equation to determine your minimum Internet connection speed: *\<highlighted number> / 0.3*.</span></span> <span data-ttu-id="26183-153">Con il numero evidenziato nell'immagine precedente, il calcolo è il seguente: *4,6875 / 0,3 = 15,6*.</span><span class="sxs-lookup"><span data-stu-id="26183-153">With the number that's highlighted in the preceding image, the calculation is *4.6875 / 0.3 = 15.6*.</span></span> <span data-ttu-id="26183-154">In questo caso, la velocità della connessione Internet deve essere di almeno 15,6 Mbps.</span><span class="sxs-lookup"><span data-stu-id="26183-154">In this case, the Internet connection speed should be at least 15.6 Mbps.</span></span>

<span data-ttu-id="26183-155">Se Teams e Business Voice usano più del 30% della velocità totale della connessione Internet, il numero evidenziato verrà visualizzato in rosso.</span><span class="sxs-lookup"><span data-stu-id="26183-155">If Teams and Business Voice will use more than 30 percent of your total Internet connection speed, the highlighted number will appear red.</span></span> <span data-ttu-id="26183-156">In questo caso, potrebbe essere necessario eseguire l'aggiornamento della connessione Internet.</span><span class="sxs-lookup"><span data-stu-id="26183-156">In that case, you may need to upgrade your Internet connection.</span></span>

![Avviso velocità della connessione](../media/network-planner-report-speed-warning.png)

## <a name="make-sure-the-computers-and-devices-on-your-network-can-reach-microsoft-365"></a><span data-ttu-id="26183-158">Assicurarsi che i computer e i dispositivi della rete possano raggiungere Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="26183-158">Make sure the computers and devices on your network can reach Microsoft 365</span></span>

<span data-ttu-id="26183-159">I computer e i dispositivi che usano Business Voice devono essere porte di rete specifiche per comunicare con i server di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="26183-159">Computers and devices that use Business Voice must use specific network ports to communicate with Microsoft 365 servers.</span></span> <span data-ttu-id="26183-160">In poche parole, si tratta di porte che consentono ai dispositivi di comunicare tra di loro tramite una rete o Internet.</span><span class="sxs-lookup"><span data-stu-id="26183-160">These ports are essentially doors through which devices talk to each other over a network or the Internet.</span></span> <span data-ttu-id="26183-161">Il firewall deve consentire ai dispositivi della rete di raggiungere Microsoft 365 usando le porte di rete *in uscita* seguenti:</span><span class="sxs-lookup"><span data-stu-id="26183-161">Your firewall needs to allow devices on your network to reach Microsoft 365 through the following *outbound* network ports:</span></span>

* <span data-ttu-id="26183-162">**porte TCP** 80 e 443</span><span class="sxs-lookup"><span data-stu-id="26183-162">**TCP ports** 80 and 443</span></span>
* <span data-ttu-id="26183-163">**Porte UDP** 3478, 3479, 3480 e 3481</span><span class="sxs-lookup"><span data-stu-id="26183-163">**UDP ports** 3478, 3479, 3480, and 3481</span></span>

<span data-ttu-id="26183-164">Il modo più semplice per verificare se il firewall consente la comunicazione tra queste porte di rete è quello di effettuare una chiamata di prova con Teams:</span><span class="sxs-lookup"><span data-stu-id="26183-164">The easiest way to check whether your firewall allows communication on these network ports is to make a test call in Teams:</span></span>

1. <span data-ttu-id="26183-165">Passare a https://aka.ms/getteams in un computer della rete e installare Teams.</span><span class="sxs-lookup"><span data-stu-id="26183-165">Go to https://aka.ms/getteams on a computer on your network and install Teams.</span></span> <span data-ttu-id="26183-166">Assicurarsi che il computer abbia un microfono e degli altoparlanti.</span><span class="sxs-lookup"><span data-stu-id="26183-166">Make sure that the computer has speakers and a microphone.</span></span>
2. <span data-ttu-id="26183-167">Aprire Teams ed eseguire l'accesso con un account Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="26183-167">Open Teams and sign in by using a Microsoft 365 account.</span></span>
3. <span data-ttu-id="26183-168">In Teams selezionare l'immagine del profilo, quindi passare a **Impostazioni** > **Dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="26183-168">In Teams, select your profile picture, and then go to **Settings** > **Devices**.</span></span>
4. <span data-ttu-id="26183-169">In **Dispositivi audio**, selezionare **Effettua una chiamata di prova**.</span><span class="sxs-lookup"><span data-stu-id="26183-169">Under **Audio devices**, select **Make a test call**.</span></span>
5. <span data-ttu-id="26183-170">Seguire la procedura visualizzata per inviare un messaggio e riascoltarlo.</span><span class="sxs-lookup"><span data-stu-id="26183-170">Follow the steps to leave a message and have it played back to you.</span></span>

   * <span data-ttu-id="26183-171">Se la chiamata si connette e si sente il messaggio, il firewall è configurato correttamente.</span><span class="sxs-lookup"><span data-stu-id="26183-171">If the call connects and you hear your message, your firewall is set up correctly.</span></span>
   * <span data-ttu-id="26183-172">Se la chiamata si connette, ma non si sentono le istruzioni o il messaggio, verificare che gli altoparlanti e il microfono siano configurati correttamente e riprovare.</span><span class="sxs-lookup"><span data-stu-id="26183-172">If the call connects, but you can't hear the instructions or your message, make sure that your speakers and microphone are set up correctly, and then try again.</span></span>
   * <span data-ttu-id="26183-173">Se la chiamata non si connette o se si connette ma non si sente il messaggio, potrebbe essere necessario aggiornare il firewall per autorizzare le porte di rete richieste.</span><span class="sxs-lookup"><span data-stu-id="26183-173">If the call doesn't connect or it connects but you can't hear your message, you might need to update your firewall to allow access to the required network ports.</span></span> <span data-ttu-id="26183-174">Consultare la documentazione del firewall o rivolgersi a un esperto IT per ricevere assistenza.</span><span class="sxs-lookup"><span data-stu-id="26183-174">Check your firewall's documentation, or contact an IT specialist for help.</span></span>

 <span data-ttu-id="26183-175">Se si è un professionista IT e si vogliono ottenere altre informazioni su come preparare reti più grandi o complesse per supportare VoIP aziendale, vedere [Valutare l'ambiente](../3-envision-evaluate-my-environment.md).</span><span class="sxs-lookup"><span data-stu-id="26183-175">If you're an IT professional and want more information about how to prepare larger or more complex networks to support Business Voice, see [Evaluate my environment](../3-envision-evaluate-my-environment.md).</span></span> <span data-ttu-id="26183-176">Questo articolo fornisce informazioni sui requisiti di larghezza di banda, proxy e firewall e su come usare lo [Strumento di valutazione della rete](../3-envision-evaluate-my-environment.md#test-the-network) per testare la rete.</span><span class="sxs-lookup"><span data-stu-id="26183-176">This article provides information about bandwidth, proxy and firewall requirements, and how to use the [Network Assessment Tool](../3-envision-evaluate-my-environment.md#test-the-network) to test your network.</span></span>

