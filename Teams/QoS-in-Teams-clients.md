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
ms.openlocfilehash: 3447f86be825099b7fada63fecd1b106f94cd80a
ms.sourcegitcommit: 2b76e6a9a6ba0eb391e4adba5402eb572d1dc61f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/18/2019
ms.locfileid: "40303868"
---
# <a name="set-qos-on-windows-clients"></a><span data-ttu-id="697e0-103">Configurare QoS nei client di Windows</span><span class="sxs-lookup"><span data-stu-id="697e0-103">Set QoS on Windows clients</span></span>

<span data-ttu-id="697e0-104">È possibile usare il QoS basato su criteri all'interno di criteri di gruppo per impostare l'intervallo della porta di origine per il valore DSCP predefinito nel client teams.</span><span class="sxs-lookup"><span data-stu-id="697e0-104">You can use policy-based QoS within Group Policy to set the source port range for the predefined DSCP value in the Teams client.</span></span> <span data-ttu-id="697e0-105">Gli intervalli di porte specificati nella tabella seguente sono un punto di partenza per creare un criterio per ogni carico di lavoro.</span><span class="sxs-lookup"><span data-stu-id="697e0-105">The port ranges specified in the following table are a starting point to create a policy for each workload.</span></span>

<span data-ttu-id="697e0-106">*Tabella 1. Intervalli di porte iniziali consigliati*</span><span class="sxs-lookup"><span data-stu-id="697e0-106">*Table 1. Recommended initial port ranges*</span></span>

|<span data-ttu-id="697e0-107">Tipo di traffico multimediale</span><span class="sxs-lookup"><span data-stu-id="697e0-107">Media traffic type</span></span>| <span data-ttu-id="697e0-108">Intervallo di porte di origine client</span><span class="sxs-lookup"><span data-stu-id="697e0-108">Client source port range</span></span> |<span data-ttu-id="697e0-109">Protocollo</span><span class="sxs-lookup"><span data-stu-id="697e0-109">Protocol</span></span>|<span data-ttu-id="697e0-110">Valore DSCP</span><span class="sxs-lookup"><span data-stu-id="697e0-110">DSCP value</span></span>|<span data-ttu-id="697e0-111">Classe DSCP</span><span class="sxs-lookup"><span data-stu-id="697e0-111">DSCP class</span></span>|
|:--- |:--- |:--- |:--- |:--- |
|<span data-ttu-id="697e0-112">Audio</span><span class="sxs-lookup"><span data-stu-id="697e0-112">Audio</span></span>| <span data-ttu-id="697e0-113">50000-50019</span><span class="sxs-lookup"><span data-stu-id="697e0-113">50,000–50,019</span></span>|<span data-ttu-id="697e0-114">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="697e0-114">TCP/UDP</span></span>|<span data-ttu-id="697e0-115">46</span><span class="sxs-lookup"><span data-stu-id="697e0-115">46</span></span>|<span data-ttu-id="697e0-116">Inoltro accelerato (EF)</span><span class="sxs-lookup"><span data-stu-id="697e0-116">Expedited Forwarding (EF)</span></span>|
|<span data-ttu-id="697e0-117">Video</span><span class="sxs-lookup"><span data-stu-id="697e0-117">Video</span></span>| <span data-ttu-id="697e0-118">50020-50039</span><span class="sxs-lookup"><span data-stu-id="697e0-118">50,020–50,039</span></span>|<span data-ttu-id="697e0-119">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="697e0-119">TCP/UDP</span></span>|<span data-ttu-id="697e0-120">34</span><span class="sxs-lookup"><span data-stu-id="697e0-120">34</span></span>|<span data-ttu-id="697e0-121">Inoltro assicurato (AF41)</span><span class="sxs-lookup"><span data-stu-id="697e0-121">Assured Forwarding (AF41)</span></span>|
|<span data-ttu-id="697e0-122">Condivisione di applicazioni/schermi</span><span class="sxs-lookup"><span data-stu-id="697e0-122">Application/Screen Sharing</span></span>| <span data-ttu-id="697e0-123">50040-50059</span><span class="sxs-lookup"><span data-stu-id="697e0-123">50,040–50,059</span></span>|<span data-ttu-id="697e0-124">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="697e0-124">TCP/UDP</span></span>|<span data-ttu-id="697e0-125">18</span><span class="sxs-lookup"><span data-stu-id="697e0-125">18</span></span>|<span data-ttu-id="697e0-126">Inoltro assicurato (AF21)</span><span class="sxs-lookup"><span data-stu-id="697e0-126">Assured Forwarding (AF21)</span></span>|
| | | | | |

<span data-ttu-id="697e0-127">Laddove possibile, configurare le impostazioni QoS basate su criteri all'interno di un oggetto Criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="697e0-127">Wherever possible, configure policy-based QoS settings within a Group Policy object.</span></span> <span data-ttu-id="697e0-128">I passaggi seguenti sono molto simili a [configurare gli intervalli di porte e i criteri di qualità dei servizi per i clienti in Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10), che contiene alcuni dettagli aggiuntivi che potrebbero non essere necessari.</span><span class="sxs-lookup"><span data-stu-id="697e0-128">The following steps are very similar to  [Configuring port ranges and a Quality of Service policy for your clients on Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10), which has some additional details that may not be necessary.</span></span>

<span data-ttu-id="697e0-129">Per creare criteri audio QoS per i computer Windows 10 aggiunti al dominio, accedere prima a un computer in cui è stata installata la gestione dei criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="697e0-129">To create a QoS audio policy for domain-joined Windows 10 computers, first log on to a computer on which Group Policy Management has been installed.</span></span> <span data-ttu-id="697e0-130">Aprire Gestione criteri di gruppo (fare clic sul pulsante Start, scegliere Strumenti di amministrazione e quindi Gestione criteri di gruppo) e quindi completare i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="697e0-130">Open Group Policy Management (click Start, point to Administrative Tools, and then click Group Policy Management), and then complete the following steps:</span></span>

1. <span data-ttu-id="697e0-131">In Gestione criteri di gruppo individuare il contenitore in cui deve essere creato il nuovo criterio.</span><span class="sxs-lookup"><span data-stu-id="697e0-131">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="697e0-132">Ad esempio, se tutti i computer client si trovano in un'unità organizzativa denominata **clients**, è necessario creare il nuovo criterio nell'unità organizzativa client.</span><span class="sxs-lookup"><span data-stu-id="697e0-132">For example, if all your client computers are located in an OU named **Clients**, the new policy should be created in the Clients OU.</span></span>

1. <span data-ttu-id="697e0-133">Fare clic con il pulsante destro del mouse sul contenitore appropriato e quindi scegliere **Crea un GPO in questo dominio e collegarlo qui**.</span><span class="sxs-lookup"><span data-stu-id="697e0-133">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

1. <span data-ttu-id="697e0-134">Nella finestra di dialogo **nuovo GPO** Digitare un nome per il nuovo oggetto Criteri di gruppo nella casella **nome** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="697e0-134">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box, and then click **OK**.</span></span>

1. <span data-ttu-id="697e0-135">Fare clic con il pulsante destro del mouse sul criterio appena creato e quindi scegliere **modifica**.</span><span class="sxs-lookup"><span data-stu-id="697e0-135">Right-click the newly created policy, and then click **Edit**.</span></span>

1. <span data-ttu-id="697e0-136">In Editor gestione criteri di gruppo espandere **Configurazione computer**, espandere **impostazioni di Windows**, fare clic con il pulsante destro del mouse su **QoS basata su criteri**e quindi scegliere **Crea nuovo criterio**.</span><span class="sxs-lookup"><span data-stu-id="697e0-136">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

1. <span data-ttu-id="697e0-137">Nella pagina di apertura della finestra di dialogo **QoS basata sui criteri** Digitare un nome per il nuovo criterio nella casella **nome** .</span><span class="sxs-lookup"><span data-stu-id="697e0-137">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy in the **Name** box.</span></span> <span data-ttu-id="697e0-138">Selezionare **Specifica valore DSCP** e impostare il valore su **46**.</span><span class="sxs-lookup"><span data-stu-id="697e0-138">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="697e0-139">Lascia **specificare la frequenza di accelerazione in uscita** deselezionata e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="697e0-139">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

1. <span data-ttu-id="697e0-140">Nella pagina successiva selezionare **solo le applicazioni con il nome del file eseguibile** e immettere il nome **Teams. exe**e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="697e0-140">On the next page, select **Only applications with this executable name** and enter the name **Teams.exe**, and then click **Next**.</span></span> <span data-ttu-id="697e0-141">Questa impostazione indica al criterio di assegnare priorità solo al traffico corrispondente dal client teams.</span><span class="sxs-lookup"><span data-stu-id="697e0-141">This setting instructs the policy to only prioritize matching traffic from the Teams client.</span></span>

1. <span data-ttu-id="697e0-142">Nella terza pagina verificare che sia selezionato l'indirizzo IP di **origine** e **qualsiasi indirizzo IP di destinazione** e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="697e0-142">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="697e0-143">Queste due impostazioni assicurano che i pacchetti vengano gestiti indipendentemente da quale computer (indirizzo IP) ha inviato i pacchetti e quale computer (indirizzo IP) riceverà i pacchetti.</span><span class="sxs-lookup"><span data-stu-id="697e0-143">These two settings ensure that packets will be managed regardless of which computer (IP address) sent the packets and which computer (IP address) will receive the packets.</span></span>

1. <span data-ttu-id="697e0-144">Nella pagina quattro selezionare **TCP e UDP** dall'elenco **a discesa selezionare il protocollo questo criterio QoS** .</span><span class="sxs-lookup"><span data-stu-id="697e0-144">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** drop-down list.</span></span> <span data-ttu-id="697e0-145">TCP (Transmission Control Protocol) e UDP (User Datagram Protocol) sono i due protocolli di rete usati più comunemente.</span><span class="sxs-lookup"><span data-stu-id="697e0-145">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most commonly used.</span></span>

1. <span data-ttu-id="697e0-146">Sotto l'intestazione **specificare il numero della porta di origine**, selezionare **dalla porta o dall'intervallo di origine**.</span><span class="sxs-lookup"><span data-stu-id="697e0-146">Under the heading **Specify the source port number**, select **From this source port or range**.</span></span> <span data-ttu-id="697e0-147">Nella casella di testo associata digitare l'intervallo di porte riservato per le trasmissioni audio.</span><span class="sxs-lookup"><span data-stu-id="697e0-147">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="697e0-148">Ad esempio, se hai riservato le porte 50000 tramite le porte 50019 per il traffico audio, immetti l'intervallo di porte usando questo formato: **50000:50019**.</span><span class="sxs-lookup"><span data-stu-id="697e0-148">For example, if you reserved ports 50000 through ports 50019 for audio traffic, enter the port range using this format: **50000:50019**.</span></span> <span data-ttu-id="697e0-149">Fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="697e0-149">Click **Finish**.</span></span>

1. <span data-ttu-id="697e0-150">Ripetere i passaggi 5-10 per creare criteri per la condivisione di video e applicazioni/desktop, sostituendo i valori appropriati nei passaggi 6 e 10.</span><span class="sxs-lookup"><span data-stu-id="697e0-150">Repeat steps 5-10 to create policies for Video and Application/Desktop Sharing, substituting the appropriate values in steps 6 and 10.</span></span>

<span data-ttu-id="697e0-151">I nuovi criteri creati non avranno effetto finché i criteri di gruppo non vengono aggiornati nei computer client.</span><span class="sxs-lookup"><span data-stu-id="697e0-151">The new policies you’ve created won’t take effect until Group Policy has been refreshed on your client computers.</span></span> <span data-ttu-id="697e0-152">Anche se i criteri di gruppo vengono periodicamente aggiornati autonomamente, è possibile forzare l'aggiornamento immediato eseguendo la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="697e0-152">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by following these steps:</span></span>

1. <span data-ttu-id="697e0-153">In ogni computer per cui si vogliono aggiornare i criteri di gruppo aprire un prompt dei comandi come amministratore (*Esegui come amministratore*).</span><span class="sxs-lookup"><span data-stu-id="697e0-153">On each computer for which you want to refresh Group Policy, open a Command Prompt as administrator (*Run as administrator*).</span></span>

1. <span data-ttu-id="697e0-154">Alla riga di comando, immettere</span><span class="sxs-lookup"><span data-stu-id="697e0-154">At the command prompt, enter</span></span>

   ```console
   gpupdate /force
   ```

## <a name="verify-dscp-markings-in-the-group-policy-object"></a><span data-ttu-id="697e0-155">Verificare le marcature DSCP nell'oggetto Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="697e0-155">Verify DSCP markings in the Group Policy object</span></span>

<span data-ttu-id="697e0-156">Per verificare che i valori dell'oggetto Criteri di gruppo siano stati impostati, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="697e0-156">To verify that the values from the Group Policy object have been set, perform the following steps:</span></span>

1. <span data-ttu-id="697e0-157">Aprire un prompt dei comandi come amministratore (*Esegui come amministratore*).</span><span class="sxs-lookup"><span data-stu-id="697e0-157">Open a Command Prompt as administrator (*Run as administrator*).</span></span>

1. <span data-ttu-id="697e0-158">Alla riga di comando, immettere</span><span class="sxs-lookup"><span data-stu-id="697e0-158">At the command prompt, enter</span></span>

   ```console
   gpresult /R > gp.txt
   ```

   <span data-ttu-id="697e0-159">Questo genererà un report degli oggetti Criteri di stato applicati e lo invierà a un file di testo denominato *GP. txt*.</span><span class="sxs-lookup"><span data-stu-id="697e0-159">This will generate a report of applied GPOs and send it to a text file named *gp.txt*.</span></span>

   <span data-ttu-id="697e0-160">Per un report HTML più leggibile denominato *GP. html*, immettere il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="697e0-160">For a more readable HTML report named *gp.html*, enter the following command:</span></span>

   ```console
   gpresult /H gp.html
   ```

1. <span data-ttu-id="697e0-161">Nel file generato cercare gli **oggetti Criteri di gruppo applicati** all'intestazione e verificare che i nomi degli oggetti Criteri di gruppo creati in precedenza si trovino nell'elenco dei criteri applicati.</span><span class="sxs-lookup"><span data-stu-id="697e0-161">In the generated file, look for the heading **Applied Group Policy Objects** and verify that the names of the Group Policy objects created earlier are in the list of applied policies.</span></span>

1. <span data-ttu-id="697e0-162">Aprire l'editor del registro di sistema e andare a</span><span class="sxs-lookup"><span data-stu-id="697e0-162">Open the Registry Editor, and go to</span></span>

   <span data-ttu-id="697e0-163">Criteri\_\\di\_Microsoft\\\\Windows\\\\QoS di HKEY local machine software</span><span class="sxs-lookup"><span data-stu-id="697e0-163">HKEY\_LOCAL\_MACHINE\\Software\\Policies\\Microsoft\\Windows\\QoS</span></span>

   <span data-ttu-id="697e0-164">Verificare i valori delle voci del registro di sistema elencate nella tabella 2.</span><span class="sxs-lookup"><span data-stu-id="697e0-164">Verify the values for the registry entries listed in Table 2.</span></span>

   <span data-ttu-id="697e0-165">*Tabella 2. Valori per le voci del registro di sistema di Windows per QoS*</span><span class="sxs-lookup"><span data-stu-id="697e0-165">*Table 2. Values for Windows registry entries for QoS*</span></span>

   |          <span data-ttu-id="697e0-166">Nome</span><span class="sxs-lookup"><span data-stu-id="697e0-166">Name</span></span>          |  <span data-ttu-id="697e0-167">Tipo</span><span class="sxs-lookup"><span data-stu-id="697e0-167">Type</span></span>  |    <span data-ttu-id="697e0-168">Dati</span><span class="sxs-lookup"><span data-stu-id="697e0-168">Data</span></span>     |
   |         :---:          | :---:  |    :---:    |
   |    <span data-ttu-id="697e0-169">Nome applicazione</span><span class="sxs-lookup"><span data-stu-id="697e0-169">Application Name</span></span>    | <span data-ttu-id="697e0-170">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="697e0-170">REG_SZ</span></span> |  <span data-ttu-id="697e0-171">Teams. exe</span><span class="sxs-lookup"><span data-stu-id="697e0-171">Teams.exe</span></span>  |
   |       <span data-ttu-id="697e0-172">Valore DSCP</span><span class="sxs-lookup"><span data-stu-id="697e0-172">DSCP Value</span></span>       | <span data-ttu-id="697e0-173">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="697e0-173">REG_SZ</span></span> |     <span data-ttu-id="697e0-174">46</span><span class="sxs-lookup"><span data-stu-id="697e0-174">46</span></span>      |
   |        <span data-ttu-id="697e0-175">IP locale</span><span class="sxs-lookup"><span data-stu-id="697e0-175">Local IP</span></span>        | <span data-ttu-id="697e0-176">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="697e0-176">REG_SZ</span></span> |     \*      |
   | <span data-ttu-id="697e0-177">Lunghezza prefisso IP locale</span><span class="sxs-lookup"><span data-stu-id="697e0-177">Local IP Prefix Length</span></span> | <span data-ttu-id="697e0-178">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="697e0-178">REG_SZ</span></span> |     \*      |
   |       <span data-ttu-id="697e0-179">Porta locale</span><span class="sxs-lookup"><span data-stu-id="697e0-179">Local Port</span></span>       | <span data-ttu-id="697e0-180">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="697e0-180">REG_SZ</span></span> | <span data-ttu-id="697e0-181">50000-50019</span><span class="sxs-lookup"><span data-stu-id="697e0-181">50000-50019</span></span> |
   |        <span data-ttu-id="697e0-182">Protocollo</span><span class="sxs-lookup"><span data-stu-id="697e0-182">Protocol</span></span>        | <span data-ttu-id="697e0-183">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="697e0-183">REG_SZ</span></span> |     \*      |
   |       <span data-ttu-id="697e0-184">IP remoto</span><span class="sxs-lookup"><span data-stu-id="697e0-184">Remote IP</span></span>        | <span data-ttu-id="697e0-185">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="697e0-185">REG_SZ</span></span> |     \*      |
   |    <span data-ttu-id="697e0-186">Prefisso IP remoto</span><span class="sxs-lookup"><span data-stu-id="697e0-186">Remote IP Prefix</span></span>    | <span data-ttu-id="697e0-187">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="697e0-187">REG_SZ</span></span> |     \*      |
   |      <span data-ttu-id="697e0-188">Porta remota</span><span class="sxs-lookup"><span data-stu-id="697e0-188">Remote Port</span></span>       | <span data-ttu-id="697e0-189">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="697e0-189">REG_SZ</span></span> |     \*      |
   |     <span data-ttu-id="697e0-190">Tasso di accelerazione</span><span class="sxs-lookup"><span data-stu-id="697e0-190">Throttle Rate</span></span>      | <span data-ttu-id="697e0-191">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="697e0-191">REG_SZ</span></span> |     <span data-ttu-id="697e0-192">-1</span><span class="sxs-lookup"><span data-stu-id="697e0-192">-1</span></span>      |
   | | | |

1. <span data-ttu-id="697e0-193">Verificare che il valore per la voce nome applicazione sia corretto per il client in uso e verificare che sia il valore DSCP che le voci della porta locale riflettano le impostazioni nell'oggetto Criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="697e0-193">Verify that the value for the Application Name entry is correct for the client you’re using, and verify that both the DSCP Value and Local Port entries reflect the settings in the Group Policy object.</span></span>
