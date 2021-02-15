---
title: Configurazione di intervalli di porte e di qualità del servizio per i server perimetrali
ms.reviewer: ''
ms:assetid: 6f0ae442-6624-4e3f-849a-5b9e387fb8cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204996(v=OCS.15)
ms:contentKeyID: 48184469
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: In questo articolo viene descritto come configurare gli intervalli di porte per i server perimetrali e come configurare un criterio qualità del servizio per i server A/V Edge.
ms.openlocfilehash: c88f784fe1956fa16b8464caa4f9f26e5c61005e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832906"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-edge-servers-in-skype-for-business-server"></a><span data-ttu-id="0b799-103">Configurazione degli intervalli di porte e dei criteri di qualità del servizio per i server perimetrali in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="0b799-103">Configuring port ranges and a Quality of Service policy for your Edge Servers in Skype for Business Server</span></span>

<span data-ttu-id="0b799-104">In questo articolo viene descritto come configurare gli intervalli di porte per i server perimetrali e come configurare un criterio qualità del servizio per i server A/V Edge.</span><span class="sxs-lookup"><span data-stu-id="0b799-104">This article describes how to configure port ranges for Edge Servers and how to configure a Quality of Service policy for your A/V Edge Servers.</span></span>

## <a name="configure-port-ranges"></a><span data-ttu-id="0b799-105">Configurare gli intervalli di porte</span><span class="sxs-lookup"><span data-stu-id="0b799-105">Configure port ranges</span></span>

<span data-ttu-id="0b799-106">Con i server perimetrali, non è necessario configurare intervalli di porte separati per la condivisione di audio, video e applicazioni; Analogamente, gli intervalli di porte utilizzati per i server perimetrali non devono corrispondere agli intervalli di porte utilizzati con i server per conferenze, applicazioni e Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="0b799-106">With Edge servers, you do not have to configure separate port ranges for audio, video, and application sharing; likewise, the port ranges used for Edge servers do not have to match the port ranges used with your Conferencing, Application, and Mediation servers.</span></span> <span data-ttu-id="0b799-107">Prima di procedere con l'esempio, è importante sottolineare che, mentre questa opzione esiste, è consigliabile non modificare gli intervalli di porte, in quanto ciò può influire negativamente su alcuni scenari se si esce dall'intervallo di porte 50000.</span><span class="sxs-lookup"><span data-stu-id="0b799-107">Before we proceed with our example, it's important to stress that while this option exists, we recommend you not change the port ranges, as this may adversely affect some scenarios if you move out of the 50000 port range.</span></span>

<span data-ttu-id="0b799-108">Si supponga, ad esempio, di aver configurato i server per conferenze, applicazioni e Mediation Server per l'utilizzo di questi intervalli di porte:</span><span class="sxs-lookup"><span data-stu-id="0b799-108">For example, suppose you have configured your Conferencing, Application, and Mediation servers to use these port ranges:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0b799-109">Tipo di pacchetto</span><span class="sxs-lookup"><span data-stu-id="0b799-109">Packet Type</span></span></th>
<th><span data-ttu-id="0b799-110">Numero di porta iniziale</span><span class="sxs-lookup"><span data-stu-id="0b799-110">Starting Port</span></span></th>
<th><span data-ttu-id="0b799-111">Numero di porte riservate</span><span class="sxs-lookup"><span data-stu-id="0b799-111">Number of Ports Reserved</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0b799-112">Condivisione applicazioni</span><span class="sxs-lookup"><span data-stu-id="0b799-112">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="0b799-113">40803</span><span class="sxs-lookup"><span data-stu-id="0b799-113">40803</span></span></p></td>
<td><p><span data-ttu-id="0b799-114">8348</span><span class="sxs-lookup"><span data-stu-id="0b799-114">8348</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b799-115">Audio</span><span class="sxs-lookup"><span data-stu-id="0b799-115">Audio</span></span></p></td>
<td><p><span data-ttu-id="0b799-116">49152</span><span class="sxs-lookup"><span data-stu-id="0b799-116">49152</span></span></p></td>
<td><p><span data-ttu-id="0b799-117">8348</span><span class="sxs-lookup"><span data-stu-id="0b799-117">8348</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b799-118">Video</span><span class="sxs-lookup"><span data-stu-id="0b799-118">Video</span></span></p></td>
<td><p><span data-ttu-id="0b799-119">57500</span><span class="sxs-lookup"><span data-stu-id="0b799-119">57500</span></span></p></td>
<td><p><span data-ttu-id="0b799-120">8034</span><span class="sxs-lookup"><span data-stu-id="0b799-120">8034</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b799-121"><strong>Totali</strong></span><span class="sxs-lookup"><span data-stu-id="0b799-121"><strong>Totals</strong></span></span></p></td>
<td><p>--</p></td>
<td><p><span data-ttu-id="0b799-122">24730</span><span class="sxs-lookup"><span data-stu-id="0b799-122">24730</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="0b799-123">Come puoi vedere, gli intervalli di porte per la condivisione di audio, video e applicazioni iniziano dalla porta 40803 e comprendono un totale di 24732 porte.</span><span class="sxs-lookup"><span data-stu-id="0b799-123">As you can see, your port ranges for audio, video, and application sharing start at port 40803 and encompass a total of 24732 ports.</span></span> <span data-ttu-id="0b799-124">Se si preferisce, è possibile configurare un determinato server perimetrale per utilizzare questi valori di porta complessivi eseguendo un comando simile al seguente da Skype for Business Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="0b799-124">If you prefer, you can configure a given Edge Server to use these overall port values by running a command similar to this one from within the Skype for Business Server Management Shell:</span></span>

    Set-CsEdgeServer -Identity EdgeServer:atl-edge-001.litwareinc.com -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730

<span data-ttu-id="0b799-125">Alternativamente, è possibile utilizzare il comando seguente per configurare simultaneamente tutti i server perimetrali all'interno dell'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="0b799-125">Or, use the following command to simultaneously configure all the Edge Servers in your organization:</span></span>

    Get-CsService -EdgeServer | ForEach-Object {Set-CsEdgeServer -Identity $_.Identity -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730}

<span data-ttu-id="0b799-126">È possibile verificare le impostazioni correnti delle porte per i server perimetrali utilizzando questo comando di Skype for Business Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="0b799-126">You can verify the current port settings for your Edge Servers by using this Skype for Business Server Management Shell command:</span></span>

    Get-CsService -EdgeServer | Select-Object Identity, MediaCommunicationPortStart, MediaCommunicationPortCount

<span data-ttu-id="0b799-127">Anche in questo caso, mentre queste opzioni sono disponibili, è consigliabile lasciare gli elementi così come sono per la configurazione delle porte.</span><span class="sxs-lookup"><span data-stu-id="0b799-127">Again, while we do provide these options, we strongly recommend you leave things as they are for the port configuration.</span></span>

## <a name="configure-a-qos-policy-for-your-av-edge-servers"></a><span data-ttu-id="0b799-128">Configurare un criterio QoS per I server A/V Edge</span><span class="sxs-lookup"><span data-stu-id="0b799-128">Configure a QoS policy for your A/V Edge Servers</span></span>

<span data-ttu-id="0b799-129">Oltre alla creazione di criteri QoS per i Conferencing Server, server applicazioni e Mediation Server, è necessario anche creare criteri audio e video per il sito interno degli A/V Edge Server.</span><span class="sxs-lookup"><span data-stu-id="0b799-129">In addition to creating QoS policies for your Conferencing, Application, and Mediation servers, you must also create both audio and video policies for the internal side of your A/V Edge servers.</span></span> <span data-ttu-id="0b799-130">I criteri utilizzati nei server perimetrali, tuttavia, sono diversi da quelli utilizzati nei Conferencing Server, server applicazioni e Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="0b799-130">However, the policies used on your Edge servers are different from the policies used on your Conferencing, Application, and Mediation servers.</span></span> <span data-ttu-id="0b799-131">Per i server per conferenze, applicazioni e Mediation Server è stato specificato un intervallo di porte di origine. con i server perimetrali, è necessario specificare un intervallo di porte di destinazione.</span><span class="sxs-lookup"><span data-stu-id="0b799-131">For the Conferencing, Application, and Mediation servers, you specified a source port range; with Edge servers, you need to specify a destination port range.</span></span> <span data-ttu-id="0b799-132">Per questo, non è possibile applicare semplicemente i criteri QoS per conferenze, applicazioni e Mediation Server ai server perimetrali: questi criteri semplicemente non funzionano.</span><span class="sxs-lookup"><span data-stu-id="0b799-132">Because of this, you cannot simply apply the Conferencing, Application, and Mediation server QoS policies to your Edge servers: these policies simply won't work.</span></span> <span data-ttu-id="0b799-133">È necessario invece creare nuovi criteri e applicarli solo ai server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="0b799-133">Instead, you must create new policies and apply those policies to your Edge servers only.</span></span>

<span data-ttu-id="0b799-134">Nella procedura seguente viene descritto il processo di creazione di oggetti Criteri di gruppo di Active Directory che possono essere utilizzati per gestire la qualità del servizio nei server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="0b799-134">The following procedure describes the process for creating Active Directory Group Policy objects that can be used to manage Quality of Service on Edge Servers.</span></span> <span data-ttu-id="0b799-135">Naturalmente, è possibile che i server perimetrali siano server autonomi che non dispongono di account Active Directory.</span><span class="sxs-lookup"><span data-stu-id="0b799-135">Of course, it's possible that your Edge servers are stand-alone servers that do not have Active Directory accounts.</span></span> <span data-ttu-id="0b799-136">In questo caso, è possibile utilizzare Criteri di gruppo locali anziché Criteri di gruppo di Active Directory: l'unica differenza è che è necessario creare questi criteri locali utilizzando l'Editor Criteri di gruppo locali e creare singolarmente lo stesso set di criteri in ogni server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="0b799-136">If that's the case, you can use local Group Policy instead of Active Directory Group Policy: the only difference is that you must create these local policies using the Local Group Policy Editor, and must individually create the same set of policies on each Edge Server.</span></span> <span data-ttu-id="0b799-137">Per avviare l'Editor Criteri di gruppo locali in un server perimetrale, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0b799-137">To start the Local Group Policy Editor on an Edge server, do the following:</span></span>

1.  <span data-ttu-id="0b799-138">Fare clic su **Start** quindi scegliere **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="0b799-138">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="0b799-139">Nella finestra **di** dialogo Esegui digitare **gpedit.msc** e quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="0b799-139">In the **Run** dialog box, type **gpedit.msc**, and then press ENTER.</span></span>

<span data-ttu-id="0b799-140">Se si creano criteri basati su Active Directory, è necessario accedere a un computer in cui sia installato Gestione Criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="0b799-140">If you are creating Active Directory-based policies, then you should log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="0b799-141">In tal caso, aprire Gestione Criteri di gruppo (fare clic sul pulsante **Start,** scegliere Strumenti di amministrazione **e** quindi Gestione Criteri di **gruppo),** quindi eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="0b799-141">In that case, open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**), and then complete the following steps:</span></span>

1.  <span data-ttu-id="0b799-142">In Gestione Criteri di gruppo, individuare il contenitore in cui creare il nuovo criterio.</span><span class="sxs-lookup"><span data-stu-id="0b799-142">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="0b799-143">Ad esempio, se tutti i computer Skype for Business Server si trovano in un'unità organizzativa denominata Skype for Business Server, il nuovo criterio deve essere creato nell'unità organizzativa Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="0b799-143">For example, if all your Skype for Business Server computers are located in an OU named Skype for Business Server, the new policy should be created in the Skype for Business Server OU.</span></span>

2.  <span data-ttu-id="0b799-144">Fai clic con il pulsante destro del mouse sul contenitore appropriato, quindi fai clic su Crea un oggetto Criteri di gruppo in questo dominio **e collegalo qui.**</span><span class="sxs-lookup"><span data-stu-id="0b799-144">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="0b799-145">Nella finestra **di** dialogo Nuovo oggetto Criteri di gruppo digitare  un nome per il nuovo oggetto Criteri di gruppo nella casella Nome (ad esempio, **Skype for Business Server Audio)** e quindi fare clic su **OK.**</span><span class="sxs-lookup"><span data-stu-id="0b799-145">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box (for example, **Skype for Business Server Audio**), and then click **OK**.</span></span>

4.  <span data-ttu-id="0b799-146">Fare clic con il pulsante destro del mouse sul criterio appena creato e quindi scegliere **Modifica.**</span><span class="sxs-lookup"><span data-stu-id="0b799-146">Right-click the newly-created policy, and then click **Edit**.</span></span>

<span data-ttu-id="0b799-147">Da questo punto in avanti il processo è identico sia per la creazione di un criterio di Active Directory che per la creazione di un criterio locale:</span><span class="sxs-lookup"><span data-stu-id="0b799-147">From here the process is identical regardless of whether you are creating an Active Directory policy or a local policy:</span></span>

1.  <span data-ttu-id="0b799-148">In Editor Gestione Criteri di gruppo o Editor Criteri di gruppo locali espandere **Configurazione computer**, espandere **Criteri**, espandere **Impostazioni di Windows**, fare clic con il pulsante destro del mouse su **QoS basata su criteri** e scegliere **Crea nuovo criterio**.</span><span class="sxs-lookup"><span data-stu-id="0b799-148">In the Group Policy Management Editor or the Local Group Policy Editor, expand **Computer Configuration**, expand **Policies**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

2.  <span data-ttu-id="0b799-149">Nella pagina di apertura della finestra di dialogo **QoS** basata su criteri digitare un nome per il nuovo criterio (ad esempio, **Skype for Business Server Audio)** nella casella Nome. </span><span class="sxs-lookup"><span data-stu-id="0b799-149">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy (e.g., **Skype for Business Server Audio**) in the **Name** box.</span></span> <span data-ttu-id="0b799-150">Selezionare **Specifica valore DSCP** e impostare il valore su **46**.</span><span class="sxs-lookup"><span data-stu-id="0b799-150">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="0b799-151">Lasciare non selezionata l'opzione **Specifica velocità in uscita**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="0b799-151">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

3.  <span data-ttu-id="0b799-152">Nella pagina successiva verificare  che sia selezionata l'opzione Tutte le applicazioni e quindi fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="0b799-152">On the next page, make sure that **All applications** is selected, and then click **Next**.</span></span> <span data-ttu-id="0b799-153">Questa impostazione indica alla rete di cercare tutti i pacchetti con DSCP 46, non solo quelli creati da un'applicazione specifica.</span><span class="sxs-lookup"><span data-stu-id="0b799-153">This setting instructs the network to look for all packets with a DSCP marking of 46, not just packets created by a specific application.</span></span>

4.  <span data-ttu-id="0b799-154">Nella terza pagina verificare che siano selezionati sia Qualsiasi indirizzo **IP** di origine che Qualsiasi **indirizzo IP** di destinazione e quindi fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="0b799-154">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="0b799-155">Queste due impostazioni assicurano che i pacchetti vengano gestiti indipendentemente dal computer (indirizzo IP) di provenienza e dal computer (indirizzo IP) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="0b799-155">These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

5.  <span data-ttu-id="0b799-156">Nella quarta pagina selezionare **TCP e UDP** dall'elenco a discesa **Seleziona il protocollo a cui si applica questo criterio QoS**.</span><span class="sxs-lookup"><span data-stu-id="0b799-156">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="0b799-157">TCP (Transmission Control Protocol) e UDP (User Datagram Protocol) sono i due protocolli di rete più comunemente utilizzati da Skype for Business Server e dalle relative applicazioni client.</span><span class="sxs-lookup"><span data-stu-id="0b799-157">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Skype for Business Server and its client applications.</span></span>

6.  <span data-ttu-id="0b799-158">In **Specifica il numero della porta di destinazione** selezionare **Verso questo numero di porta o intervallo di porte di destinazione**.</span><span class="sxs-lookup"><span data-stu-id="0b799-158">Under the heading **Specify the destination port number**, select **From this destination port or range**.</span></span> <span data-ttu-id="0b799-159">Nella casella di testo associata, immettere l'intervallo di porte riservato per le trasmissioni audio.</span><span class="sxs-lookup"><span data-stu-id="0b799-159">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="0b799-160">Ad esempio, se le porte da 49152 a 57500 sono riservate per il traffico audio, immettere l'intervallo di porte utilizzando il formato **49152:57500.**</span><span class="sxs-lookup"><span data-stu-id="0b799-160">For example, if you reserved ports 49152 through ports 57500 for audio traffic, enter the port range using this format: **49152:57500**.</span></span> <span data-ttu-id="0b799-161">Fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="0b799-161">Click **Finish**.</span></span>

<span data-ttu-id="0b799-162">Dopo aver creato i criteri QoS per il traffico audio, è necessario creare un secondo criterio per il traffico video.</span><span class="sxs-lookup"><span data-stu-id="0b799-162">After you have created the QoS policy for audio traffic, you should create a second policy for video traffic.</span></span> <span data-ttu-id="0b799-163">Per creare un criterio per il traffico video, seguire la stessa procedura di base usata per la creazione del criterio audio, con le distinzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0b799-163">To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="0b799-164">Usare un nome di criterio diverso (e univoco), ad esempio **Skype for Business Server Video.**</span><span class="sxs-lookup"><span data-stu-id="0b799-164">Use a different (and unique) policy name (for example, **Skype for Business Server Video**).</span></span>

  - <span data-ttu-id="0b799-p113">Impostare il valore DSCP su **34** invece di 46. Si noti che non è obbligatorio usare il valore DSCP 34. L'unico requisito consiste nell'usare un valore DSCP diverso da quello usato per l'audio.</span><span class="sxs-lookup"><span data-stu-id="0b799-p113">Set the DSCP value to **34** instead of 46. (Note that you do not have to use a DSCP value of 34. The only requirement is that you use a different DSCP value for video than you used for audio.)</span></span>

  - <span data-ttu-id="0b799-168">Usa l'intervallo di porte configurato in precedenza per il traffico video.</span><span class="sxs-lookup"><span data-stu-id="0b799-168">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="0b799-169">Ad esempio, se sono state riservate le porte da 57501 a 65535 per il video, impostare l'intervallo di porte su: **57501:65535**.</span><span class="sxs-lookup"><span data-stu-id="0b799-169">For example, if you have reserved ports 57501 through 65535 for video, set the port range to this: **57501:65535**.</span></span> <span data-ttu-id="0b799-170">Anche in questo caso è necessario configurarlo come intervallo di porte di destinazione.</span><span class="sxs-lookup"><span data-stu-id="0b799-170">Again, this should be configured as the destination port range.</span></span>

<span data-ttu-id="0b799-171">Se si decide di creare un criterio per la gestione del traffico di condivisione applicazioni, è necessario creare un terzo criterio, apportando le sostituzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0b799-171">If you decide to create a policy for managing application sharing traffic, you must create a third policy, making the following substitutions:</span></span>

  - <span data-ttu-id="0b799-172">Utilizzare un nome di criterio diverso (e univoco), ad esempio Condivisione applicazioni di **Skype for Business Server.**</span><span class="sxs-lookup"><span data-stu-id="0b799-172">Use a different (and unique) policy name (for example, **Skype for Business Server Application Sharing**).</span></span>

  - <span data-ttu-id="0b799-p115">Impostare il valore DSCP su **24** invece di 46. Come indicato prima, non è obbligatorio usare il valore DSCP 24. L'unico requisito consiste nell'usare un valore DSCP diverso da quello usato per l'audio.</span><span class="sxs-lookup"><span data-stu-id="0b799-p115">Set the DSCP value to **24** instead of 46. (Again, you do not have to use a DSCP value of 24. The only requirement is that you use a different DSCP value for application sharing than you used for audio or for video.)</span></span>

  - <span data-ttu-id="0b799-176">Usa l'intervallo di porte configurato in precedenza per il traffico video.</span><span class="sxs-lookup"><span data-stu-id="0b799-176">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="0b799-177">Ad esempio, se sono state riservate le porte da 40803 a 49151 per la condivisione delle applicazioni, impostare l'intervallo di porte **su: 40803:49151.**</span><span class="sxs-lookup"><span data-stu-id="0b799-177">For example, if you have reserved ports 40803 through 49151 for application sharing, set the port range to this: **40803:49151**.</span></span>

<span data-ttu-id="0b799-p117">I nuovi criteri creati verranno applicati solo dopo l'aggiornamento di Criteri di gruppo sui server perimetrali. L'aggiornamento di Criteri di gruppo viene eseguito periodicamente in modo automatico, ma è possibile forzarne l'esecuzione immediata utilizzando il comando seguente su ogni computer in cui questa operazione è necessaria:</span><span class="sxs-lookup"><span data-stu-id="0b799-p117">The new policies you have created will not take effect until Group Policy has been refreshed on your Edge servers. Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpudate.exe /force

<span data-ttu-id="0b799-180">Questo comando può essere eseguito da Skype for Business Server o da qualsiasi finestra di comando in esecuzione con credenziali di amministratore.</span><span class="sxs-lookup"><span data-stu-id="0b799-180">This command can be run from within the Skype for Business Server or from any command window that is running under administrator credentials.</span></span> <span data-ttu-id="0b799-181">Per eseguire una finestra di comando con credenziali di amministratore, fare clic su **Start**, fare clic con il pulsante destro del mouse su **Prompt dei comandi** e scegliere **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="0b799-181">To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span> <span data-ttu-id="0b799-182">Può essere necessario riavviare il server perimetrale anche dopo avere eseguito Gpudate.exe.</span><span class="sxs-lookup"><span data-stu-id="0b799-182">Note that you might need to restart the Edge server even after running Gpudate.exe.</span></span>

<span data-ttu-id="0b799-183">Per assicurarsi che i pacchetti di rete siano contrassegnati con il valore DSCP appropriato, creare anche una nuova voce del Registro di sistema su ogni computer completando la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="0b799-183">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="0b799-184">Fare clic su **Start** quindi scegliere **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="0b799-184">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="0b799-185">Nella finestra **di** dialogo Esegui digitare **regedit** e quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="0b799-185">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="0b799-186">Nell'Editor del Registro di sistema espandere **HKEY \_ LOCAL \_ MACHINE,** **SYSTEM,** **CurrentControlSet,** **services** e **quindi Tcpip.**</span><span class="sxs-lookup"><span data-stu-id="0b799-186">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="0b799-187">Fare clic con il pulsante destro **Tcpip**, scegliere **Nuovo** e quindi fare clic su **Chiave**.</span><span class="sxs-lookup"><span data-stu-id="0b799-187">Right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="0b799-188">Dopo aver creato la nuova chiave del Registro di sistema, digitare **QoS** e quindi premere INVIO per rinominare la chiave.</span><span class="sxs-lookup"><span data-stu-id="0b799-188">After the new registry key is created, type **QoS**, and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="0b799-189">Fare clic con il pulsante destro del mouse su **QoS**, scegliere **Nuovo** e quindi **Valore stringa**.</span><span class="sxs-lookup"><span data-stu-id="0b799-189">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="0b799-190">Dopo aver creato il nuovo valore del Registro di sistema, digitare **Do not use NLA** e quindi premere INVIO per rinominare il valore.</span><span class="sxs-lookup"><span data-stu-id="0b799-190">After the new registry value is created, type **Do not use NLA**, and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="0b799-191">Fare doppio clic su **Do no use NLA**.</span><span class="sxs-lookup"><span data-stu-id="0b799-191">Double-click **Do no use NLA**.</span></span> <span data-ttu-id="0b799-192">Nella finestra **di dialogo Modifica** stringa digitare **1** nella **casella** Dati valore e quindi fare clic su **OK.**</span><span class="sxs-lookup"><span data-stu-id="0b799-192">In the **Edit String** dialog box, type **1** in the **Value data** box, and then click **OK**.</span></span>

7.  <span data-ttu-id="0b799-193">Chiudi l'Editor del Registro di sistema e riavvia il computer.</span><span class="sxs-lookup"><span data-stu-id="0b799-193">Close the Registry Editor and reboot your computer.</span></span>
