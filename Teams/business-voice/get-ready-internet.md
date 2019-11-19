---
title: Controllare la connessione Internet
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
localization_priority: Priority
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: ''
appliesto:
- Microsoft Teams
ms.openlocfilehash: 19f26c0bd7ab4fe89770909d81d60abc97aaa8b0
ms.sourcegitcommit: 4a4ed872eff22663720296ae29c0e644286857f2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/15/2019
ms.locfileid: "38653552"
---
# <a name="check-your-internet-connection"></a><span data-ttu-id="44b7e-102">Controllare la connessione Internet</span><span class="sxs-lookup"><span data-stu-id="44b7e-102">Check your Internet connection</span></span>

<span data-ttu-id="44b7e-103">VoIP aziendale si trova nel cloud con Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="44b7e-103">Business Voice is located in the cloud with Microsoft 365.</span></span> <span data-ttu-id="44b7e-104">Ogni computer e dispositivo che usa Microsoft Teams e VoIP aziendale richiede una connessione a Internet.</span><span class="sxs-lookup"><span data-stu-id="44b7e-104">Every computer and device that uses Microsoft Teams and Business Voice needs a connection to the Internet.</span></span> <span data-ttu-id="44b7e-105">Per ottenere risultati ottimali con VoIP aziendale, è necessaria una connessione Internet a banda larga in grado di supportare il numero previsto di chiamate telefoniche che verranno eseguite in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="44b7e-105">To get the best experience with Business Voice, you need a broadband Internet connection that can support the expected number of phone calls that will be made at any one time.</span></span> <span data-ttu-id="44b7e-106">È anche necessario assicurarsi che i computer della rete possano accedere ai server Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="44b7e-106">You also need to make sure that computers on your network can reach Microsoft 365 servers.</span></span>

<span data-ttu-id="44b7e-107">Per eseguire questa procedura, è necessario avere un tenant con uno degli abbonamenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="44b7e-107">To follow these steps, you need to have a tenant with one of the following subscriptions:</span></span>

* <span data-ttu-id="44b7e-108">Office 365 Business Essentials</span><span class="sxs-lookup"><span data-stu-id="44b7e-108">Office 365 Business Essentials</span></span>
* <span data-ttu-id="44b7e-109">Office 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="44b7e-109">Office 365 Business Premium</span></span>
* <span data-ttu-id="44b7e-110">Office 365 E1</span><span class="sxs-lookup"><span data-stu-id="44b7e-110">Office 365 E1</span></span>
* <span data-ttu-id="44b7e-111">Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="44b7e-111">Office 365 E3</span></span>
* <span data-ttu-id="44b7e-112">Office 365 F1</span><span class="sxs-lookup"><span data-stu-id="44b7e-112">Office 365 F1</span></span>
* <span data-ttu-id="44b7e-113">Microsoft 365 A1</span><span class="sxs-lookup"><span data-stu-id="44b7e-113">Microsoft 365 A1</span></span>
* <span data-ttu-id="44b7e-114">Microsoft 365 A3</span><span class="sxs-lookup"><span data-stu-id="44b7e-114">Microsoft 365 A3</span></span>
* <span data-ttu-id="44b7e-115">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="44b7e-115">Microsoft 365 E3</span></span>
* <span data-ttu-id="44b7e-116">Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="44b7e-116">Microsoft 365 Business</span></span>

<span data-ttu-id="44b7e-117">Non è necessaria una licenza VoIP aziendale per eseguire questa procedura.</span><span class="sxs-lookup"><span data-stu-id="44b7e-117">You don't need a Business Voice license to follow these steps.</span></span>

## <a name="check-your-internet-connection-speed"></a><span data-ttu-id="44b7e-118">Controllare la velocità della connessione Internet</span><span class="sxs-lookup"><span data-stu-id="44b7e-118">Check your Internet connection speed</span></span>

<span data-ttu-id="44b7e-119">Questo articolo illustra come determinare se la connessione Internet è abbastanza veloce per il numero di persone che devono effettuare chiamate telefoniche, organizzare videoconferenze e così via.</span><span class="sxs-lookup"><span data-stu-id="44b7e-119">This article helps you determine whether your Internet connection is fast enough for the number of people who need to make phone calls, host video conferences, and so on.</span></span> <span data-ttu-id="44b7e-120">Immettendo alcune informazioni sull'organizzazione è possibile ottenere un report con la quantità di connessione Internet che verrà usata da Teams e da VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="44b7e-120">You'll enter some information about your organization and get back a report with how much of your Internet connection will be used by Teams and Business Voice.</span></span>

### <a name="get-information-about-your-internet-connection-and-users"></a><span data-ttu-id="44b7e-121">Ottenere informazioni sulla connessione Internet e sugli utenti</span><span class="sxs-lookup"><span data-stu-id="44b7e-121">Get information about your Internet connection and users</span></span>

<span data-ttu-id="44b7e-122">Prima di iniziare, è necessario disporre delle informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="44b7e-122">Before you start, you need to know the following information:</span></span>

* <span data-ttu-id="44b7e-123">La velocità della connessione Internet.</span><span class="sxs-lookup"><span data-stu-id="44b7e-123">The speed of your Internet connection.</span></span>
* <span data-ttu-id="44b7e-124">Quante persone useranno VoIP aziendale principalmente dall'ufficio.</span><span class="sxs-lookup"><span data-stu-id="44b7e-124">How many people will use Business Voice mainly from your office.</span></span>
* <span data-ttu-id="44b7e-125">Quante persone useranno VoIP aziendale principalmente da una posizione remota, come un ufficio a casa.</span><span class="sxs-lookup"><span data-stu-id="44b7e-125">How many people will use Business Voice mainly from a remote location, such as a home office.</span></span>

### <a name="enter-your-information-into-the-network-planner"></a><span data-ttu-id="44b7e-126">Immettere le informazioni nel Network Planner</span><span class="sxs-lookup"><span data-stu-id="44b7e-126">Enter your information into the network planner</span></span>

<span data-ttu-id="44b7e-127">Ecco cosa fare:</span><span class="sxs-lookup"><span data-stu-id="44b7e-127">Here's what you need to do:</span></span>

1. <span data-ttu-id="44b7e-128">Aprire il browser e passare a https://admin.teams.microsoft.com, quindi accedere con un account dotato di autorizzazioni di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="44b7e-128">Open a browser and go to https://admin.teams.microsoft.com and sign in with an account that has Global Administrator permissions.</span></span> <span data-ttu-id="44b7e-129">L'account usato per iscriversi a Office 365 dispone di queste autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="44b7e-129">The account you used to sign up for Office 365 has these permissions.</span></span>
1. <span data-ttu-id="44b7e-130">Aprire **Pianificazione** e poi selezionare **Network planner**.</span><span class="sxs-lookup"><span data-stu-id="44b7e-130">Open **Org-wide settings** and then select **Network planner**.</span></span>
1. <span data-ttu-id="44b7e-131">In **Piani di rete** selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="44b7e-131">Under **Network plans**, select **Add**.</span></span> <span data-ttu-id="44b7e-132">Assegnare un nome al piano e quindi selezionare **Applica**.</span><span class="sxs-lookup"><span data-stu-id="44b7e-132">Give your plan a name, and then select **Apply**.</span></span> <span data-ttu-id="44b7e-133">Il piano di rete dovrebbe essere simile a questo:</span><span class="sxs-lookup"><span data-stu-id="44b7e-133">Your network plan should look like this:</span></span>

    ![Schermata principale di Network Planner](../media/network-planner-main.png)
1. <span data-ttu-id="44b7e-135">Fare clic sul nome del piano di rete, **Ufficio principale** nell'immagine sopra.</span><span class="sxs-lookup"><span data-stu-id="44b7e-135">Click on your network plan's name (**Main office** in the picture above).</span></span>
1. <span data-ttu-id="44b7e-136">Nella pagina successiva selezionare **Aggiungi un sito di rete** nella scheda **Siti di rete**.</span><span class="sxs-lookup"><span data-stu-id="44b7e-136">On the next page, select **Add a network site** under the **Network sites** tab.</span></span>
1. <span data-ttu-id="44b7e-137">Compilare solo i campi indicati nella schermata seguente e poi selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="44b7e-137">Fill in only the fields indicated in the screenshot below and then select **Save**.</span></span> <span data-ttu-id="44b7e-138">Lasciare vuoti gli altri campi della schermata e non selezionare le opzioni **ExpressRoute** o **Connesso a WAN**.</span><span class="sxs-lookup"><span data-stu-id="44b7e-138">Leave the other fields on this screen blank, and don't select either the **ExpressRoute** or **Connected to WAN** options.</span></span>

    ![Informazioni sul sito di Network Planner](../media/network-planner-site-info.png)
1. <span data-ttu-id="44b7e-140">Nella scheda **Report** selezionare **Avviare un report**.</span><span class="sxs-lookup"><span data-stu-id="44b7e-140">Under the **Report** tab, select **Start a report**.</span></span>
1. <span data-ttu-id="44b7e-141">Compilare le informazioni seguenti e poi selezionare **Genera rapporto** per creare un report con i requisiti di larghezza di banda per Teams.</span><span class="sxs-lookup"><span data-stu-id="44b7e-141">Fill out the following information and then select **Generate report** to create a report showing the bandwidth requirements for Teams.</span></span> <span data-ttu-id="44b7e-142">Mostreremo come leggere il report nella sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="44b7e-142">We'll show you how to read the report in the next section.</span></span>

    ![Informazioni sul report di Network Planner](../media/network-planner-report-info.png)

### <a name="find-your-minimum-internet-connection-speed"></a><span data-ttu-id="44b7e-144">Trovare la velocità minima della connessione Internet</span><span class="sxs-lookup"><span data-stu-id="44b7e-144">Find your minimum Internet connection speed</span></span>

<span data-ttu-id="44b7e-145">Dopo aver selezionato **Genera report**, Office 365 crea un report simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="44b7e-145">When you select **Generate report**, Office 365 creates a report that looks like this:</span></span>

![Dettagli sul report di Network Planner](../media/network-planner-report.png)

<span data-ttu-id="44b7e-147">Il numero evidenziato indica la quantità di connessione Internet che Teams e VoIP aziendale useranno.</span><span class="sxs-lookup"><span data-stu-id="44b7e-147">The highlighted number shows how much of your Internet connection Teams and Business Voice will use.</span></span> <span data-ttu-id="44b7e-148">Si consiglia di non superare il 30% della velocità totale della connessione Internet.</span><span class="sxs-lookup"><span data-stu-id="44b7e-148">We recommend that this number be no more than 30% of your total Internet connection speed.</span></span> <span data-ttu-id="44b7e-149">Ad esempio, se la connessione Internet è di 60 Mbps, Teams e VoIP aziendale non devono usare più di 18 Mbps.</span><span class="sxs-lookup"><span data-stu-id="44b7e-149">For example, if your Internet connection is 60Mbps, Teams and Business Voice should take up no more than 18Mbps.</span></span>

<span data-ttu-id="44b7e-150">Per determinare la velocità minima della connessione Internet, eseguire questo calcolo: `<highlighted number> / .3`.</span><span class="sxs-lookup"><span data-stu-id="44b7e-150">You can find your minimum Internet connection speed by doing this calculation: `<highlighted number> / .3`.</span></span> <span data-ttu-id="44b7e-151">Usando il numero evidenziato nell'immagine sopra, il calcolo sarebbe `4.6875 / .3 = 15.6`.</span><span class="sxs-lookup"><span data-stu-id="44b7e-151">Using the highlighted number in the picture above, the calculation would be `4.6875 / .3 = 15.6`.</span></span> <span data-ttu-id="44b7e-152">Ciò significa che la velocità minima della connessione Internet deve essere di 15,6 Mbps.</span><span class="sxs-lookup"><span data-stu-id="44b7e-152">This means your minimum Internet connection speed needs to be at least 15.6Mbps.</span></span>

<span data-ttu-id="44b7e-153">Se Teams e VoIP aziendale usano più del 30% della velocità totale della connessione Internet, il numero evidenziato verrà visualizzato in rosso.</span><span class="sxs-lookup"><span data-stu-id="44b7e-153">If Teams and Business Voice will use more than 30% of your total Internet connection speed, the highlighted number will show up as red.</span></span> <span data-ttu-id="44b7e-154">In questo caso, potrebbe essere necessario eseguire l'aggiornamento della connessione Internet.</span><span class="sxs-lookup"><span data-stu-id="44b7e-154">If this happens, you might need to upgrade your Internet connection.</span></span>

![Avviso velocità della connessione](../media/network-planner-report-speed-warning.png)

## <a name="make-sure-computers-and-devices-on-your-network-can-reach-microsoft-365"></a><span data-ttu-id="44b7e-156">Assicurarsi che i computer e i dispositivi della rete possano raggiungere Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="44b7e-156">Make sure computers and devices on your network can reach Microsoft 365</span></span>

<span data-ttu-id="44b7e-157">Per funzionare correttamente, i computer e i dispositivi che si vogliono usare con VoIP aziendale devono comunicare con i server di Microsoft 365 usando specifiche porte di rete.</span><span class="sxs-lookup"><span data-stu-id="44b7e-157">To work correctly, computers and devices you want to use with Business Voice need to communicate with Microsoft 365 servers using specific network ports.</span></span> <span data-ttu-id="44b7e-158">Le porte di rete sono, in poche parole, porte che consentono a computer e dispositivi di comunicare tra di loro tramite una rete o Internet.</span><span class="sxs-lookup"><span data-stu-id="44b7e-158">Network ports are essentially doors through which computers and devices can talk to each other over a network or the Internet.</span></span> <span data-ttu-id="44b7e-159">Il firewall deve consentire ai computer e ai dispositivi della rete di raggiungere Microsoft 365 usando le porte di rete in uscita seguenti:</span><span class="sxs-lookup"><span data-stu-id="44b7e-159">Your firewall needs to allow computers and devices on your network to reach Microsoft 365 using the following outbound network ports:</span></span>

* <span data-ttu-id="44b7e-160">**porte TCP** 80 e 443</span><span class="sxs-lookup"><span data-stu-id="44b7e-160">**TCP ports** 80 and 443</span></span>
* <span data-ttu-id="44b7e-161">**Porte UDP** 3478, 3479, 3480 e 3481</span><span class="sxs-lookup"><span data-stu-id="44b7e-161">**UDP ports** 3478, 3479, 3480, and 3481</span></span>

<span data-ttu-id="44b7e-162">Il modo più semplice per verificare se il firewall consente la comunicazione tra queste porte di rete è quello di effettuare una chiamata di prova con Teams.</span><span class="sxs-lookup"><span data-stu-id="44b7e-162">The easiest way to check whether your firewall allows communication on these network ports is to make a test call using Teams.</span></span> <span data-ttu-id="44b7e-163">Per effettuare una chiamata di prova, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="44b7e-163">To make a test call, do the following:</span></span>

1. <span data-ttu-id="44b7e-164">Passare a https://aka.ms/getteams in un computer della rete per installare Teams.</span><span class="sxs-lookup"><span data-stu-id="44b7e-164">Go to https://aka.ms/getteams on a computer on your network to install Teams.</span></span> <span data-ttu-id="44b7e-165">Assicurarsi che gli altoparlanti e il microfono siano connessi al computer.</span><span class="sxs-lookup"><span data-stu-id="44b7e-165">Make sure speakers and a microphone are connected to this computer.</span></span>
2. <span data-ttu-id="44b7e-166">Aprire Teams ed eseguire l'accesso con un account Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="44b7e-166">Open Teams and sign in using a Microsoft 365 account</span></span>
3. <span data-ttu-id="44b7e-167">In Teams selezionare l'immagine del profilo, quindi **Impostazioni** > **Dispositivi**</span><span class="sxs-lookup"><span data-stu-id="44b7e-167">In Teams, select your profile picture, then **Settings** > **Devices**</span></span>
4. <span data-ttu-id="44b7e-168">Scegliere **Effettua una chiamata di prova** in **Dispositivi audio**</span><span class="sxs-lookup"><span data-stu-id="44b7e-168">Choose **Make a test call** under **Audio devices**</span></span>
5. <span data-ttu-id="44b7e-169">Seguire le istruzioni visualizzate per inviare un messaggio e riascoltarlo</span><span class="sxs-lookup"><span data-stu-id="44b7e-169">Follow the prompts to leave a message and have it played back to you</span></span>

* <span data-ttu-id="44b7e-170">Se la chiama si connette ed si sente il messaggio riprodotto, il firewall è configurato correttamente.</span><span class="sxs-lookup"><span data-stu-id="44b7e-170">If the call connects and you can hear your message played back to you, your firewall is set up correctly.</span></span>
* <span data-ttu-id="44b7e-171">Se la chiamata si connette, ma non si sentono le istruzioni o il messaggio riprodotto, verificare che gli altoparlanti e il microfono siano configurati correttamente e che vengano rilevati dal computer.</span><span class="sxs-lookup"><span data-stu-id="44b7e-171">If the call connects but you can't hear the prompts or your message played back to you, make sure your speakers and microphone are set up correctly and detected by the computer.</span></span> <span data-ttu-id="44b7e-172">Riprovare.</span><span class="sxs-lookup"><span data-stu-id="44b7e-172">Try again.</span></span>
* <span data-ttu-id="44b7e-173">Se la chiamata non si connette o se si connette ma non si sente il messaggio riprodotto, potrebbe essere necessario aggiornare il firewall per autorizzare le porte di rete elencate in precedenza.</span><span class="sxs-lookup"><span data-stu-id="44b7e-173">If the call doesn't connect or if it does but you can't hear your message played back to you, you might need to update your firewall to allow the network ports listed above.</span></span> <span data-ttu-id="44b7e-174">Consultare la documentazione del firewall su come consentire alle porte di rete di raggiungere Internet o rivolgersi a un tecnico informatico per assistenza.</span><span class="sxs-lookup"><span data-stu-id="44b7e-174">Check your firewall's documentation on how to allow network ports to reach the Internet, or contact an IT specialist to help you.</span></span>

<span data-ttu-id="44b7e-175">Se si è un professionista informatico e si vogliono ottenere altre informazioni su come preparare reti più grandi o complesse per supportare VoIP aziendale, vedere [Valutare l'ambiente](../3-envision-evaluate-my-environment.md).</span><span class="sxs-lookup"><span data-stu-id="44b7e-175">If you're an IT professional and want more information about how to prepare larger or more complex networks to support Business Voice, take a look at [Evaluate my environment](../3-envision-evaluate-my-environment.md).</span></span> <span data-ttu-id="44b7e-176">L’articolo [Valutare l'ambiente](../3-envision-evaluate-my-environment.md) fornisce informazioni aggiuntive sui requisiti di larghezza di banda, proxy e firewall e anche su come testare la rete con lo [Strumento di valutazione della rete](../3-envision-evaluate-my-environment.md#test-the-network).</span><span class="sxs-lookup"><span data-stu-id="44b7e-176">The [Evaluate my environment](../3-envision-evaluate-my-environment.md) article gives additional information about bandwidth, proxy, and firewall requirements and also how to test your network using the [Network Assessment Tool](../3-envision-evaluate-my-environment.md#test-the-network).</span></span>
