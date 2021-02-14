---
title: Implementare la qualità del servizio (QoS) nei client di Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: Serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies
audience: admin
description: Informazioni su come usare la qualità del servizio (QoS, Quality of Service) per ottimizzare il traffico di rete per il client desktop di Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: bc352303cf63ea966927aece0aef36854a0ace1b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526403"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams-clients"></a><span data-ttu-id="bcb20-103">Implementare la qualità del servizio (QoS) nei client di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bcb20-103">Implement Quality of Service (QoS) in Microsoft Teams clients</span></span>

<span data-ttu-id="bcb20-104">È possibile usare la qualità del servizio (QoS) basata su criteri all'interno di Criteri di gruppo per impostare l'intervallo delle porte di origine per il valore DSCP predefinito nel client di Teams.</span><span class="sxs-lookup"><span data-stu-id="bcb20-104">You can use policy-based Quality of Service (QoS) within Group Policy to set the source port range for the predefined DSCP value in the Teams client.</span></span> <span data-ttu-id="bcb20-105">Gli intervalli di porta specificati nella tabella seguente sono un punto di partenza per creare criteri per ogni carico di lavoro.</span><span class="sxs-lookup"><span data-stu-id="bcb20-105">The port ranges specified in the following table are a starting point to create a policy for each workload.</span></span>

<span data-ttu-id="bcb20-106">*Tabella 1. Intervalli di porta iniziali consigliati*</span><span class="sxs-lookup"><span data-stu-id="bcb20-106">*Table 1. Recommended initial port ranges*</span></span>

|<span data-ttu-id="bcb20-107">Tipo di traffico multimediale</span><span class="sxs-lookup"><span data-stu-id="bcb20-107">Media traffic type</span></span>| <span data-ttu-id="bcb20-108">Intervallo di porte di origine client </span><span class="sxs-lookup"><span data-stu-id="bcb20-108">Client source port range</span></span> |<span data-ttu-id="bcb20-109">Protocollo</span><span class="sxs-lookup"><span data-stu-id="bcb20-109">Protocol</span></span>|<span data-ttu-id="bcb20-110">Valore DSCP</span><span class="sxs-lookup"><span data-stu-id="bcb20-110">DSCP value</span></span>|<span data-ttu-id="bcb20-111">Classe DSCP</span><span class="sxs-lookup"><span data-stu-id="bcb20-111">DSCP class</span></span>|
|:--- |:--- |:--- |:--- |:--- |
|<span data-ttu-id="bcb20-112">Audio</span><span class="sxs-lookup"><span data-stu-id="bcb20-112">Audio</span></span>| <span data-ttu-id="bcb20-113">50.000–50.019</span><span class="sxs-lookup"><span data-stu-id="bcb20-113">50,000–50,019</span></span>|<span data-ttu-id="bcb20-114">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="bcb20-114">TCP/UDP</span></span>|<span data-ttu-id="bcb20-115">46</span><span class="sxs-lookup"><span data-stu-id="bcb20-115">46</span></span>|<span data-ttu-id="bcb20-116">Expedited Forwarding (EF)</span><span class="sxs-lookup"><span data-stu-id="bcb20-116">Expedited Forwarding (EF)</span></span>|
|<span data-ttu-id="bcb20-117">Video</span><span class="sxs-lookup"><span data-stu-id="bcb20-117">Video</span></span>| <span data-ttu-id="bcb20-118">50.020–50.039</span><span class="sxs-lookup"><span data-stu-id="bcb20-118">50,020–50,039</span></span>|<span data-ttu-id="bcb20-119">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="bcb20-119">TCP/UDP</span></span>|<span data-ttu-id="bcb20-120">34</span><span class="sxs-lookup"><span data-stu-id="bcb20-120">34</span></span>|<span data-ttu-id="bcb20-121">Assured Forwarding (AF41)</span><span class="sxs-lookup"><span data-stu-id="bcb20-121">Assured Forwarding (AF41)</span></span>|
|<span data-ttu-id="bcb20-122">Condivisione di applicazioni/schermi</span><span class="sxs-lookup"><span data-stu-id="bcb20-122">Application/Screen Sharing</span></span>| <span data-ttu-id="bcb20-123">50.040–50.059</span><span class="sxs-lookup"><span data-stu-id="bcb20-123">50,040–50,059</span></span>|<span data-ttu-id="bcb20-124">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="bcb20-124">TCP/UDP</span></span>|<span data-ttu-id="bcb20-125">18</span><span class="sxs-lookup"><span data-stu-id="bcb20-125">18</span></span>|<span data-ttu-id="bcb20-126">Assured Forwarding (AF21)</span><span class="sxs-lookup"><span data-stu-id="bcb20-126">Assured Forwarding (AF21)</span></span>|
| | | | | |

<span data-ttu-id="bcb20-127">Ove possibile, configurare le impostazioni QoS basate su criteri all'interno di un oggetto Criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="bcb20-127">Wherever possible, configure policy-based QoS settings within a Group Policy object.</span></span> <span data-ttu-id="bcb20-128">I passaggi seguenti sono molto simili alla configurazione degli intervalli di porte e ai criteri di qualità del servizio per i client in  [Skype for Business Server,](https://docs.microsoft.com/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10)che contiene alcuni dettagli aggiuntivi che potrebbero non essere necessari.</span><span class="sxs-lookup"><span data-stu-id="bcb20-128">The following steps are very similar to  [Configuring port ranges and a Quality of Service policy for your clients on Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10), which has some additional details that may not be necessary.</span></span>

<span data-ttu-id="bcb20-129">Per creare criteri audio QoS per computer Windows 10 aggiunti a un dominio, accedere prima di tutto a un computer in cui è stato installato Gestione Criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="bcb20-129">To create a QoS audio policy for domain-joined Windows 10 computers, first log on to a computer on which Group Policy Management has been installed.</span></span> <span data-ttu-id="bcb20-130">Aprire Gestione Criteri di gruppo (fare clic su Start, scegliere Strumenti di amministrazione e quindi fare clic su Gestione Criteri di gruppo) e quindi completare la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="bcb20-130">Open Group Policy Management (click Start, point to Administrative Tools, and then click Group Policy Management), and then complete the following steps:</span></span>

1. <span data-ttu-id="bcb20-131">In Gestione Criteri di gruppo individuare il contenitore in cui deve essere creato il nuovo criterio.</span><span class="sxs-lookup"><span data-stu-id="bcb20-131">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="bcb20-132">Ad esempio, se tutti i computer client si trovano in un'unità organizzativa **Clients,** il nuovo criterio deve essere creato nell'unità organizzativa Clients.</span><span class="sxs-lookup"><span data-stu-id="bcb20-132">For example, if all your client computers are located in an OU named **Clients**, the new policy should be created in the Clients OU.</span></span>

1. <span data-ttu-id="bcb20-133">Fai clic con il pulsante destro del mouse sul contenitore appropriato, quindi fai clic su Crea un oggetto Criteri di gruppo in questo **dominio e collegalo qui.**</span><span class="sxs-lookup"><span data-stu-id="bcb20-133">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

1. <span data-ttu-id="bcb20-134">Nella finestra **di dialogo Nuovo oggetto** Criteri di gruppo digitare  un nome per il nuovo oggetto Criteri di gruppo nella casella Nome e quindi fare clic su **OK.**</span><span class="sxs-lookup"><span data-stu-id="bcb20-134">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box, and then click **OK**.</span></span>

1. <span data-ttu-id="bcb20-135">Fare clic con il pulsante destro del mouse sul criterio appena creato e quindi scegliere **Modifica.**</span><span class="sxs-lookup"><span data-stu-id="bcb20-135">Right-click the newly created policy, and then click **Edit**.</span></span>

1. <span data-ttu-id="bcb20-136">In Editor Gestione Criteri di gruppo espandere **Configurazione computer,** Espandere Impostazioni di **Windows,** fare clic con il pulsante destro del mouse su **QoS** basato su criteri e quindi scegliere Crea **nuovo criterio.**</span><span class="sxs-lookup"><span data-stu-id="bcb20-136">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

1. <span data-ttu-id="bcb20-137">Nella pagina di apertura della finestra di dialogo **QoS** basata su criteri digitare un nome per il nuovo criterio nella **casella** Nome.</span><span class="sxs-lookup"><span data-stu-id="bcb20-137">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy in the **Name** box.</span></span> <span data-ttu-id="bcb20-138">Selezionare **Specifica valore DSCP** e impostare il valore su **46.**</span><span class="sxs-lookup"><span data-stu-id="bcb20-138">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="bcb20-139">Lasciare **l'opzione Specifica velocità di limitazione in** uscita deselezionata e quindi fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="bcb20-139">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

1. <span data-ttu-id="bcb20-140">Nella pagina successiva selezionare Solo le applicazioni **con** questo nome eseguibile e immettere il nome **Teams.exe** e quindi fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="bcb20-140">On the next page, select **Only applications with this executable name** and enter the name **Teams.exe**, and then click **Next**.</span></span> <span data-ttu-id="bcb20-141">Questa impostazione indica al criterio di assegnare priorità solo al traffico corrispondente dal client Teams.</span><span class="sxs-lookup"><span data-stu-id="bcb20-141">This setting instructs the policy to only prioritize matching traffic from the Teams client.</span></span>

1. <span data-ttu-id="bcb20-142">Nella terza pagina verificare che siano selezionati sia Qualsiasi indirizzo **IP** di origine che Qualsiasi **indirizzo IP** di destinazione e quindi fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="bcb20-142">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="bcb20-143">Queste due impostazioni assicurano che i pacchetti verranno gestiti indipendentemente dal computer (indirizzo IP) che ha inviato i pacchetti e dal computer (indirizzo IP) che riceverà i pacchetti.</span><span class="sxs-lookup"><span data-stu-id="bcb20-143">These two settings ensure that packets will be managed regardless of which computer (IP address) sent the packets and which computer (IP address) will receive the packets.</span></span>

1. <span data-ttu-id="bcb20-144">Nella pagina 4 selezionare **TCP e UDP** dall'elenco a discesa Select the protocol this **QoS policy applies to.**</span><span class="sxs-lookup"><span data-stu-id="bcb20-144">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** drop-down list.</span></span> <span data-ttu-id="bcb20-145">TCP (Transmission Control Protocol) e UDP (User Datagram Protocol) sono i due protocolli di rete più comunemente usati.</span><span class="sxs-lookup"><span data-stu-id="bcb20-145">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most commonly used.</span></span>

1. <span data-ttu-id="bcb20-146">Nell'intestazione **Specificare il numero di porta di origine** selezionare Da questa porta o intervallo di **origine.**</span><span class="sxs-lookup"><span data-stu-id="bcb20-146">Under the heading **Specify the source port number**, select **From this source port or range**.</span></span> <span data-ttu-id="bcb20-147">Nella casella di testo di accompagnamento digitare l'intervallo di porte riservato per le trasmissioni audio.</span><span class="sxs-lookup"><span data-stu-id="bcb20-147">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="bcb20-148">Ad esempio, se le porte da 50000 a 50019 sono riservate per il traffico audio, immettere l'intervallo di porte nel formato **50000:50019.**</span><span class="sxs-lookup"><span data-stu-id="bcb20-148">For example, if you reserved ports 50000 through ports 50019 for audio traffic, enter the port range using this format: **50000:50019**.</span></span> <span data-ttu-id="bcb20-149">Fare clic **su Fine.**</span><span class="sxs-lookup"><span data-stu-id="bcb20-149">Click **Finish**.</span></span>

1. <span data-ttu-id="bcb20-150">Ripetere i passaggi da 5 a 10 per creare criteri per condivisione video e applicazioni/desktop sostituendo i valori appropriati nei passaggi 6 e 10.</span><span class="sxs-lookup"><span data-stu-id="bcb20-150">Repeat steps 5-10 to create policies for Video and Application/Desktop Sharing, substituting the appropriate values in steps 6 and 10.</span></span>

<span data-ttu-id="bcb20-151">I nuovi criteri creati saranno applicati solo dopo l'aggiornamento di Criteri di gruppo nei computer client.</span><span class="sxs-lookup"><span data-stu-id="bcb20-151">The new policies you've created won't take effect until Group Policy has been refreshed on your client computers.</span></span> <span data-ttu-id="bcb20-152">Anche se Criteri di gruppo vengono aggiornati periodicamente, è possibile forzare un aggiornamento immediato seguendo questa procedura:</span><span class="sxs-lookup"><span data-stu-id="bcb20-152">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by following these steps:</span></span>

1. <span data-ttu-id="bcb20-153">In ogni computer per cui si vogliono aggiornare i Criteri di gruppo aprire un prompt dei comandi come amministratore *(Esegui come amministratore).*</span><span class="sxs-lookup"><span data-stu-id="bcb20-153">On each computer for which you want to refresh Group Policy, open a Command Prompt as administrator (*Run as administrator*).</span></span>

1. <span data-ttu-id="bcb20-154">Al prompt dei comandi immetti</span><span class="sxs-lookup"><span data-stu-id="bcb20-154">At the command prompt, enter</span></span>

   ```console
   gpupdate /force
   ```

## <a name="verify-dscp-markings-in-the-group-policy-object"></a><span data-ttu-id="bcb20-155">Verificare i contrassegni DSCP nell'oggetto Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="bcb20-155">Verify DSCP markings in the Group Policy object</span></span>

<span data-ttu-id="bcb20-156">Per verificare che i valori dell'oggetto Criteri di gruppo siano stati impostati, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="bcb20-156">To verify that the values from the Group Policy object have been set, perform the following steps:</span></span>

1. <span data-ttu-id="bcb20-157">Aprire un prompt dei comandi come amministratore (*Esegui come amministratore*).</span><span class="sxs-lookup"><span data-stu-id="bcb20-157">Open a Command Prompt as administrator (*Run as administrator*).</span></span>

1. <span data-ttu-id="bcb20-158">Al prompt dei comandi immetti</span><span class="sxs-lookup"><span data-stu-id="bcb20-158">At the command prompt, enter</span></span>

   ```console
   gpresult /R > gp.txt
   ```

   <span data-ttu-id="bcb20-159">Verrà generato un report degli oggetti Criteri di gruppo applicati e inviato a un file di testo *gp.txt.*</span><span class="sxs-lookup"><span data-stu-id="bcb20-159">This will generate a report of applied GPOs and send it to a text file named *gp.txt*.</span></span>

   <span data-ttu-id="bcb20-160">Per un report HTML più leggibile denominato *gp.html,* immettere il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="bcb20-160">For a more readable HTML report named *gp.html*, enter the following command:</span></span>

   ```console
   gpresult /H gp.html
   ```

1. <span data-ttu-id="bcb20-161">Nel file generato cercare l'intestazione Oggetti Criteri di gruppo applicati e verificare che i nomi degli oggetti Criteri di gruppo creati in precedenza siano presenti nell'elenco dei criteri applicati. </span><span class="sxs-lookup"><span data-stu-id="bcb20-161">In the generated file, look for the heading **Applied Group Policy Objects** and verify that the names of the Group Policy objects created earlier are in the list of applied policies.</span></span>

1. <span data-ttu-id="bcb20-162">Apri l'Editor del Registro di sistema e vai a</span><span class="sxs-lookup"><span data-stu-id="bcb20-162">Open the Registry Editor, and go to</span></span>

   <span data-ttu-id="bcb20-163">HKEY \_ LOCAL \_ MACHINE \\ Software \\ Policies \\ Microsoft \\ Windows \\ QoS</span><span class="sxs-lookup"><span data-stu-id="bcb20-163">HKEY\_LOCAL\_MACHINE\\Software\\Policies\\Microsoft\\Windows\\QoS</span></span>

   <span data-ttu-id="bcb20-164">Verificare i valori per le voci del Registro di sistema elencate nella tabella 2.</span><span class="sxs-lookup"><span data-stu-id="bcb20-164">Verify the values for the registry entries listed in Table 2.</span></span>

   <span data-ttu-id="bcb20-165">*Tabella 2. Valori per le voci del Registro di sistema di Windows per QoS*</span><span class="sxs-lookup"><span data-stu-id="bcb20-165">*Table 2. Values for Windows registry entries for QoS*</span></span>

   |          <span data-ttu-id="bcb20-166">Nome</span><span class="sxs-lookup"><span data-stu-id="bcb20-166">Name</span></span>          |  <span data-ttu-id="bcb20-167">Tipo</span><span class="sxs-lookup"><span data-stu-id="bcb20-167">Type</span></span>  |    <span data-ttu-id="bcb20-168">Dati</span><span class="sxs-lookup"><span data-stu-id="bcb20-168">Data</span></span>     |
   |         :---:          | :---:  |    :---:    |
   |    <span data-ttu-id="bcb20-169">Nome applicazione</span><span class="sxs-lookup"><span data-stu-id="bcb20-169">Application Name</span></span>    | <span data-ttu-id="bcb20-170">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="bcb20-170">REG_SZ</span></span> |  <span data-ttu-id="bcb20-171">Teams.exe</span><span class="sxs-lookup"><span data-stu-id="bcb20-171">Teams.exe</span></span>  |
   |       <span data-ttu-id="bcb20-172">Valore DSCP</span><span class="sxs-lookup"><span data-stu-id="bcb20-172">DSCP Value</span></span>       | <span data-ttu-id="bcb20-173">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="bcb20-173">REG_SZ</span></span> |     <span data-ttu-id="bcb20-174">46</span><span class="sxs-lookup"><span data-stu-id="bcb20-174">46</span></span>      |
   |        <span data-ttu-id="bcb20-175">IP locale</span><span class="sxs-lookup"><span data-stu-id="bcb20-175">Local IP</span></span>        | <span data-ttu-id="bcb20-176">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="bcb20-176">REG_SZ</span></span> |     \*      |
   | <span data-ttu-id="bcb20-177">Lunghezza prefisso IP locale</span><span class="sxs-lookup"><span data-stu-id="bcb20-177">Local IP Prefix Length</span></span> | <span data-ttu-id="bcb20-178">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="bcb20-178">REG_SZ</span></span> |     \*      |
   |       <span data-ttu-id="bcb20-179">Porta locale</span><span class="sxs-lookup"><span data-stu-id="bcb20-179">Local Port</span></span>       | <span data-ttu-id="bcb20-180">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="bcb20-180">REG_SZ</span></span> | <span data-ttu-id="bcb20-181">50000-50019</span><span class="sxs-lookup"><span data-stu-id="bcb20-181">50000-50019</span></span> |
   |        <span data-ttu-id="bcb20-182">Protocollo</span><span class="sxs-lookup"><span data-stu-id="bcb20-182">Protocol</span></span>        | <span data-ttu-id="bcb20-183">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="bcb20-183">REG_SZ</span></span> |     \*      |
   |       <span data-ttu-id="bcb20-184">IP remoto</span><span class="sxs-lookup"><span data-stu-id="bcb20-184">Remote IP</span></span>        | <span data-ttu-id="bcb20-185">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="bcb20-185">REG_SZ</span></span> |     \*      |
   |    <span data-ttu-id="bcb20-186">Prefisso IP remoto</span><span class="sxs-lookup"><span data-stu-id="bcb20-186">Remote IP Prefix</span></span>    | <span data-ttu-id="bcb20-187">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="bcb20-187">REG_SZ</span></span> |     \*      |
   |      <span data-ttu-id="bcb20-188">Porta remota</span><span class="sxs-lookup"><span data-stu-id="bcb20-188">Remote Port</span></span>       | <span data-ttu-id="bcb20-189">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="bcb20-189">REG_SZ</span></span> |     \*      |
   |     <span data-ttu-id="bcb20-190">Velocità di limitazione</span><span class="sxs-lookup"><span data-stu-id="bcb20-190">Throttle Rate</span></span>      | <span data-ttu-id="bcb20-191">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="bcb20-191">REG_SZ</span></span> |     <span data-ttu-id="bcb20-192">-1</span><span class="sxs-lookup"><span data-stu-id="bcb20-192">-1</span></span>      |
   | | | |

1. <span data-ttu-id="bcb20-193">Verificare che il valore per la voce Nome applicazione sia corretto per il client in uso e verificare che le voci Valore DSCP e Porta locale riflettano le impostazioni nell'oggetto Criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="bcb20-193">Verify that the value for the Application Name entry is correct for the client you're using, and verify that both the DSCP Value and Local Port entries reflect the settings in the Group Policy object.</span></span>


## <a name="related-topics"></a><span data-ttu-id="bcb20-194">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="bcb20-194">Related topics</span></span>

[<span data-ttu-id="bcb20-195">Implementare la qualità del servizio (QoS) in Teams</span><span class="sxs-lookup"><span data-stu-id="bcb20-195">Implement Quality of Service (QoS) in Teams</span></span>](QoS-in-Teams.md)