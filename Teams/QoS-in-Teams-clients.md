---
title: Implementare la qualità del servizio nei client di Microsoft Teams
author: jambirk
ms.author: jambirk
manager: Serdars
ms.date: 2/17/2019
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Implementare la qualità del servizio (QoS) per i client di Microsoft teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 28e6664fa43819493e5b9e02d182bcec44f00905
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2019
ms.locfileid: "37572564"
---
# <a name="set-qos-on-windows-clients"></a><span data-ttu-id="c8033-103">Impostare QoS nei client Windows</span><span class="sxs-lookup"><span data-stu-id="c8033-103">Set QoS on Windows clients</span></span>

<span data-ttu-id="c8033-104">È possibile usare il QoS basato su criteri all'interno di criteri di gruppo per impostare l'intervallo della porta di origine per il valore DSCP predefinito nel client teams.</span><span class="sxs-lookup"><span data-stu-id="c8033-104">You can use policy-based QoS within Group Policy to set the source port range for the predefined DSCP value in the Teams client.</span></span> <span data-ttu-id="c8033-105">Gli intervalli di porte specificati nella tabella seguente sono un punto di partenza per creare un criterio per ogni carico di lavoro.</span><span class="sxs-lookup"><span data-stu-id="c8033-105">The port ranges specified in the following table are a starting point to create a policy for each workload.</span></span>

<span data-ttu-id="c8033-106">_Intervalli di porte iniziali consigliati_</span><span class="sxs-lookup"><span data-stu-id="c8033-106">_Recommended initial port ranges_</span></span>

<span data-ttu-id="c8033-107">Tipo di traffico multimediale</span><span class="sxs-lookup"><span data-stu-id="c8033-107">Media traffic type</span></span>| <span data-ttu-id="c8033-108">Intervallo di porte di origine client</span><span class="sxs-lookup"><span data-stu-id="c8033-108">Client source port range</span></span> |<span data-ttu-id="c8033-109">Protocollo</span><span class="sxs-lookup"><span data-stu-id="c8033-109">Protocol</span></span>|<span data-ttu-id="c8033-110">Valore DSCP</span><span class="sxs-lookup"><span data-stu-id="c8033-110">DSCP value</span></span>|<span data-ttu-id="c8033-111">Classe DSCP</span><span class="sxs-lookup"><span data-stu-id="c8033-111">DSCP class</span></span>|
|:--- |:--- |:--- |:--- |:--- |
|<span data-ttu-id="c8033-112">Audio</span><span class="sxs-lookup"><span data-stu-id="c8033-112">Audio</span></span>| <span data-ttu-id="c8033-113">50000-50019</span><span class="sxs-lookup"><span data-stu-id="c8033-113">50,000–50,019</span></span>|<span data-ttu-id="c8033-114">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="c8033-114">TCP/UDP</span></span>|<span data-ttu-id="c8033-115">46</span><span class="sxs-lookup"><span data-stu-id="c8033-115">46</span></span>|<span data-ttu-id="c8033-116">Inoltro accelerato (EF)</span><span class="sxs-lookup"><span data-stu-id="c8033-116">Expedited Forwarding (EF)</span></span>|
|<span data-ttu-id="c8033-117">Video</span><span class="sxs-lookup"><span data-stu-id="c8033-117">Video</span></span>| <span data-ttu-id="c8033-118">50020-50039</span><span class="sxs-lookup"><span data-stu-id="c8033-118">50,020–50,039</span></span>|<span data-ttu-id="c8033-119">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="c8033-119">TCP/UDP</span></span>|<span data-ttu-id="c8033-120">34</span><span class="sxs-lookup"><span data-stu-id="c8033-120">34</span></span>|<span data-ttu-id="c8033-121">Inoltro assicurato (AF41)</span><span class="sxs-lookup"><span data-stu-id="c8033-121">Assured Forwarding (AF41)</span></span>|
|<span data-ttu-id="c8033-122">Condivisione di applicazioni/schermi</span><span class="sxs-lookup"><span data-stu-id="c8033-122">Application/Screen Sharing</span></span>| <span data-ttu-id="c8033-123">50040-50059</span><span class="sxs-lookup"><span data-stu-id="c8033-123">50,040–50,059</span></span>|<span data-ttu-id="c8033-124">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="c8033-124">TCP/UDP</span></span>|<span data-ttu-id="c8033-125">18</span><span class="sxs-lookup"><span data-stu-id="c8033-125">18</span></span>|<span data-ttu-id="c8033-126">Inoltro assicurato (AF21)</span><span class="sxs-lookup"><span data-stu-id="c8033-126">Assured Forwarding (AF21)</span></span>|
| | | | |

<span data-ttu-id="c8033-127">Laddove possibile, configurare le impostazioni QoS basate su criteri all'interno di un oggetto Criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="c8033-127">Wherever possible, configure policy-based QoS settings within a Group Policy object.</span></span> <span data-ttu-id="c8033-128">I passaggi seguenti sono molto simili a [configurare gli intervalli di porte e i criteri di qualità dei servizi per i clienti in Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10), che contiene alcuni dettagli aggiuntivi che potrebbero non essere necessari.</span><span class="sxs-lookup"><span data-stu-id="c8033-128">The following steps are very similar to  [Configuring port ranges and a Quality of Service policy for your clients on Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10), which has some additional details that may not be necessary.</span></span>

<span data-ttu-id="c8033-129">Per creare criteri audio QoS per i computer Windows 10 aggiunti al dominio, accedere prima a un computer in cui è stata installata la gestione dei criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="c8033-129">To create a QoS audio policy for domain-joined Windows 10 computers, first log on to a computer on which Group Policy Management has been installed.</span></span> <span data-ttu-id="c8033-130">Aprire Gestione criteri di gruppo (fare clic sul pulsante Start, scegliere Strumenti di amministrazione e quindi Gestione criteri di gruppo) e quindi completare i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="c8033-130">Open Group Policy Management (click Start, point to Administrative Tools, and then click Group Policy Management), and then complete the following steps:</span></span>

1. <span data-ttu-id="c8033-131">In Gestione criteri di gruppo individuare il contenitore in cui deve essere creato il nuovo criterio.</span><span class="sxs-lookup"><span data-stu-id="c8033-131">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="c8033-132">Ad esempio, se tutti i computer client si trovano in un'unità organizzativa denominata **clients**, è necessario creare il nuovo criterio nell'unità organizzativa client.</span><span class="sxs-lookup"><span data-stu-id="c8033-132">For example, if all your client computers are located in an OU named **Clients**, the new policy should be created in the Client OU.</span></span>

2. <span data-ttu-id="c8033-133">Fare clic con il pulsante destro del mouse sul contenitore appropriato e quindi scegliere **Crea un GPO in questo dominio e collegarlo qui**.</span><span class="sxs-lookup"><span data-stu-id="c8033-133">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

3. <span data-ttu-id="c8033-134">Nella finestra di dialogo **nuovo GPO** Digitare un nome per il nuovo oggetto Criteri di gruppo nella casella **nome** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="c8033-134">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box, and then click **OK**.</span></span>

4. <span data-ttu-id="c8033-135">Fare clic con il pulsante destro del mouse sul criterio appena creato e quindi scegliere **modifica**.</span><span class="sxs-lookup"><span data-stu-id="c8033-135">Right-click the newly created policy, and then click **Edit**.</span></span>

5. <span data-ttu-id="c8033-136">In Editor gestione criteri di gruppo espandere **Configurazione computer**, espandere **impostazioni di Windows**, fare clic con il pulsante destro del mouse su **QoS basata su criteri**e quindi scegliere **Crea nuovo criterio**.</span><span class="sxs-lookup"><span data-stu-id="c8033-136">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

6. <span data-ttu-id="c8033-137">Nella pagina di apertura della finestra di dialogo **QoS basata sui criteri** Digitare un nome per il nuovo criterio nella casella **nome** .</span><span class="sxs-lookup"><span data-stu-id="c8033-137">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy in the **Name** box.</span></span> <span data-ttu-id="c8033-138">Selezionare **Specifica valore DSCP** e impostare il valore su **46**.</span><span class="sxs-lookup"><span data-stu-id="c8033-138">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="c8033-139">Lascia **specificare la frequenza di accelerazione in uscita** deselezionata e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="c8033-139">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

7. <span data-ttu-id="c8033-140">Nella pagina successiva selezionare **solo le applicazioni con il nome del file eseguibile** e immettere il nome **Teams. exe**e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="c8033-140">On the next page, select **Only applications with this executable name** and enter the name **Teams.exe**, and then click **Next**.</span></span> <span data-ttu-id="c8033-141">Questa impostazione indica al criterio di assegnare priorità solo al traffico corrispondente dal client teams.</span><span class="sxs-lookup"><span data-stu-id="c8033-141">This setting instructs the policy to only prioritize matching traffic from the Teams client.</span></span>

8. <span data-ttu-id="c8033-142">Nella terza pagina verificare che sia selezionato l'indirizzo IP di **origine** e **qualsiasi indirizzo IP di destinazione** e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="c8033-142">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="c8033-143">Queste due impostazioni assicurano che i pacchetti vengano gestiti indipendentemente da quale computer (indirizzo IP) ha inviato i pacchetti e quale computer (indirizzo IP) riceverà i pacchetti.</span><span class="sxs-lookup"><span data-stu-id="c8033-143">These two settings ensure that packets will be managed regardless of which computer (IP address) sent the packets and which computer (IP address) will receive the packets.</span></span>

9. <span data-ttu-id="c8033-144">Nella pagina quattro selezionare **TCP e UDP** dall'elenco **a discesa selezionare il protocollo questo criterio QoS** .</span><span class="sxs-lookup"><span data-stu-id="c8033-144">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** drop-down list.</span></span> <span data-ttu-id="c8033-145">TCP (Transmission Control Protocol) e UDP (User Datagram Protocol) sono i due protocolli di rete usati più comunemente.</span><span class="sxs-lookup"><span data-stu-id="c8033-145">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most commonly used.</span></span>

10. <span data-ttu-id="c8033-146">Sotto l'intestazione **specificare il numero della porta di origine**, selezionare **dalla porta o dall'intervallo di origine**.</span><span class="sxs-lookup"><span data-stu-id="c8033-146">Under the heading **Specify the source port number**, select **From this source port or range**.</span></span> <span data-ttu-id="c8033-147">Nella casella di testo associata digitare l'intervallo di porte riservato per le trasmissioni audio.</span><span class="sxs-lookup"><span data-stu-id="c8033-147">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="c8033-148">Ad esempio, se hai riservato le porte 50000 tramite le porte 50019 per il traffico audio, immetti l'intervallo di porte usando questo formato: **50000:50019**.</span><span class="sxs-lookup"><span data-stu-id="c8033-148">For example, if you reserved ports 50000 through ports 50019 for audio traffic, enter the port range using this format: **50000:50019**.</span></span> <span data-ttu-id="c8033-149">Fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="c8033-149">Click **Finish**.</span></span>

11. <span data-ttu-id="c8033-150">Ripetere i passaggi 5-10 per creare criteri per la condivisione di video e applicazioni/desktop, sostituendo i valori appropriati nei passaggi 6 e 10.</span><span class="sxs-lookup"><span data-stu-id="c8033-150">Repeat steps 5-10 to create policies for Video and Application/Desktop Sharing, substituting the appropriate values in steps 6 and 10.</span></span>

<span data-ttu-id="c8033-151">I nuovi criteri creati non avranno effetto finché i criteri di gruppo non vengono aggiornati nei computer client.</span><span class="sxs-lookup"><span data-stu-id="c8033-151">The new policies you’ve created won’t take effect until Group Policy has been refreshed on your client computers.</span></span> <span data-ttu-id="c8033-152">Anche se i criteri di gruppo vengono periodicamente aggiornati autonomamente, è possibile forzare l'aggiornamento immediato eseguendo la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="c8033-152">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by following these steps:</span></span>

1. <span data-ttu-id="c8033-153">In ogni computer per cui si vogliono aggiornare i criteri di gruppo aprire una console dei comandi.</span><span class="sxs-lookup"><span data-stu-id="c8033-153">On each computer for which you want to refresh Group Policy, open a command console.</span></span> <span data-ttu-id="c8033-154">Verificare che la console dei comandi sia impostata per l'esecuzione come amministratore.</span><span class="sxs-lookup"><span data-stu-id="c8033-154">Ensure that the command console is set to run as administrator.</span></span>

2. <span data-ttu-id="c8033-155">Alla riga di comando, immettere</span><span class="sxs-lookup"><span data-stu-id="c8033-155">At the command prompt, enter</span></span>

   ``` powershell
    gpupdate.exe /force
   ```

## <a name="verify-dscp-markings-in-the-group-policy-object"></a><span data-ttu-id="c8033-156">Verificare le marcature DSCP nell'oggetto Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="c8033-156">Verify DSCP markings in the Group Policy object</span></span>

<span data-ttu-id="c8033-157">Per verificare che i valori dell'oggetto Criteri di gruppo siano stati impostati, eseguire la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="c8033-157">To verify that the values from the Group Policy object have been set, perform the following steps.</span></span>

1. <span data-ttu-id="c8033-158">Aprire una console di comando.</span><span class="sxs-lookup"><span data-stu-id="c8033-158">Open a command console.</span></span> <span data-ttu-id="c8033-159">Verificare che la console dei comandi sia impostata per l'esecuzione come amministratore.</span><span class="sxs-lookup"><span data-stu-id="c8033-159">Ensure that the command console is set to run as administrator.</span></span>

2. <span data-ttu-id="c8033-160">Alla riga di comando, digitare:</span><span class="sxs-lookup"><span data-stu-id="c8033-160">At the command prompt, enter:</span></span>

   ``` powershell
   gpresult /R > gp.txt
   ```

   <span data-ttu-id="c8033-161">Questo genererà un report e lo invierà in un file di testo denominato GP. txt.</span><span class="sxs-lookup"><span data-stu-id="c8033-161">This will generate a report and send it to a text file named gp.txt.</span></span> <span data-ttu-id="c8033-162">In alternativa, è possibile immettere il comando seguente per produrre gli stessi dati in un report HTML più leggibile denominato GP. html:</span><span class="sxs-lookup"><span data-stu-id="c8033-162">Alternatively, you can enter the following command to produce the same data in a more readable HTML report named gp.html:</span></span>

   ``` powershell
   gpresult /H >gp.html
   ```

   <span data-ttu-id="c8033-163">![Screenshot della finestra della console in cui è in uso il comando gpresult.](media/Qos-in-Teams-Image3.png "Screenshot della finestra della console in cui è in uso il comando gpresult.")</span><span class="sxs-lookup"><span data-stu-id="c8033-163">![Screenshot of the console window running the gpresult command.](media/Qos-in-Teams-Image3.png "Screenshot of the console window running the gpresult command.")</span></span>

3. <span data-ttu-id="c8033-164">Nel file generato cercare gli **oggetti Criteri di gruppo applicati** all'intestazione e verificare che i nomi degli oggetti Criteri di gruppo creati in precedenza si trovino nell'elenco dei criteri applicati.</span><span class="sxs-lookup"><span data-stu-id="c8033-164">In the generated file, look for the heading **Applied Group Policy Objects** and verify that the names of the Group Policy objects created earlier are in the list of applied policies.</span></span>

4. <span data-ttu-id="c8033-165">Aprire l'editor del registro di sistema e andare a:</span><span class="sxs-lookup"><span data-stu-id="c8033-165">Open the Registry Editor, and go to:</span></span>

   <span data-ttu-id="c8033-166">HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\QoS</span><span class="sxs-lookup"><span data-stu-id="c8033-166">HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\QoS</span></span>\

   <span data-ttu-id="c8033-167">Verificare i valori delle voci del registro di sistema elencate nella tabella 4.</span><span class="sxs-lookup"><span data-stu-id="c8033-167">Verify the values for the registry entries listed in Table 4.</span></span>

   <span data-ttu-id="c8033-168">_Tabella 4. Valori per le voci del registro di sistema di Windows per QoS_</span><span class="sxs-lookup"><span data-stu-id="c8033-168">_Table 4. Values for Windows registry entries for QoS_</span></span>

   |          <span data-ttu-id="c8033-169">Nome</span><span class="sxs-lookup"><span data-stu-id="c8033-169">Name</span></span>          |  <span data-ttu-id="c8033-170">Tipo</span><span class="sxs-lookup"><span data-stu-id="c8033-170">Type</span></span>  |    <span data-ttu-id="c8033-171">Dati</span><span class="sxs-lookup"><span data-stu-id="c8033-171">Data</span></span>     |
   |         :---:          |:---:   |    :---:    |
   |    <span data-ttu-id="c8033-172">Nome applicazione</span><span class="sxs-lookup"><span data-stu-id="c8033-172">Application Name</span></span>    | <span data-ttu-id="c8033-173">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="c8033-173">REG_SZ</span></span> |  <span data-ttu-id="c8033-174">Teams. exe</span><span class="sxs-lookup"><span data-stu-id="c8033-174">Teams.exe</span></span>  |
   |       <span data-ttu-id="c8033-175">Valore DSCP</span><span class="sxs-lookup"><span data-stu-id="c8033-175">DSCP Value</span></span>       | <span data-ttu-id="c8033-176">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="c8033-176">REG_SZ</span></span> |     <span data-ttu-id="c8033-177">46</span><span class="sxs-lookup"><span data-stu-id="c8033-177">46</span></span>      |
   |        <span data-ttu-id="c8033-178">IP locale</span><span class="sxs-lookup"><span data-stu-id="c8033-178">Local IP</span></span>        | <span data-ttu-id="c8033-179">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="c8033-179">REG_SZ</span></span> |     \*      |
   | <span data-ttu-id="c8033-180">Lunghezza prefisso IP locale</span><span class="sxs-lookup"><span data-stu-id="c8033-180">Local IP Prefix Length</span></span> | <span data-ttu-id="c8033-181">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="c8033-181">REG_SZ</span></span> |     \*      |
   |       <span data-ttu-id="c8033-182">Porta locale</span><span class="sxs-lookup"><span data-stu-id="c8033-182">Local Port</span></span>       | <span data-ttu-id="c8033-183">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="c8033-183">REG_SZ</span></span> | <span data-ttu-id="c8033-184">50000-50019</span><span class="sxs-lookup"><span data-stu-id="c8033-184">50000-50019</span></span> |
   |        <span data-ttu-id="c8033-185">Protocollo</span><span class="sxs-lookup"><span data-stu-id="c8033-185">Protocol</span></span>        | <span data-ttu-id="c8033-186">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="c8033-186">REG_SZ</span></span> |     \*      |
   |       <span data-ttu-id="c8033-187">IP remoto</span><span class="sxs-lookup"><span data-stu-id="c8033-187">Remote IP</span></span>        | <span data-ttu-id="c8033-188">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="c8033-188">REG_SZ</span></span> |     \*      |
   |    <span data-ttu-id="c8033-189">Prefisso IP remoto</span><span class="sxs-lookup"><span data-stu-id="c8033-189">Remote IP Prefix</span></span>    | <span data-ttu-id="c8033-190">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="c8033-190">REG_SZ</span></span> |     \*      |
   |      <span data-ttu-id="c8033-191">Porta remota</span><span class="sxs-lookup"><span data-stu-id="c8033-191">Remote Port</span></span>       | <span data-ttu-id="c8033-192">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="c8033-192">REG_SZ</span></span> |     \*      |
   |     <span data-ttu-id="c8033-193">Tasso di accelerazione</span><span class="sxs-lookup"><span data-stu-id="c8033-193">Throttle Rate</span></span>      | <span data-ttu-id="c8033-194">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="c8033-194">REG_SZ</span></span> |     <span data-ttu-id="c8033-195">-1</span><span class="sxs-lookup"><span data-stu-id="c8033-195">-1</span></span>      |

5. <span data-ttu-id="c8033-196">Verificare che il valore per la voce nome applicazione sia corretto per il client in uso e verificare che sia il valore DSCP che le voci della porta locale riflettano le impostazioni nell'oggetto Criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="c8033-196">Verify that the value for the Application Name entry is correct for the client you’re using, and verify that both the DSCP Value and Local Port entries reflect the settings in the Group Policy object.</span></span>
