---
title: Configurazione dei criteri di qualità del servizio per i server A/V Edge
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a Quality of Service policy for your A/V Edge Servers
ms:assetid: 119ee1f5-45b9-40ba-98e5-c694dd2fc5c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204681(v=OCS.15)
ms:contentKeyID: 48183444
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e55947fa80e2772bbc53b47f5c6f906761f1bb3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034216"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-quality-of-service-policy-for-your-av-edge-servers-in-lync-server-2013"></a><span data-ttu-id="42ce6-102">Configurazione dei criteri di qualità del servizio per i server A/V Edge in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="42ce6-102">Configuring a Quality of Service policy for your A/V Edge Servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="42ce6-103">_**Ultimo argomento modificato:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="42ce6-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="42ce6-p101">Oltre alla creazione di criteri QoS per i Conferencing Server, server applicazioni e Mediation Server, è necessario anche creare criteri audio e video per il sito interno degli A/V Edge Server. I criteri utilizzati nei server perimetrali, tuttavia, sono diversi da quelli utilizzati nei Conferencing Server, server applicazioni e Mediation Server. Per i Conferencing Server, server applicazioni e Mediation Server è stato specificato un intervallo di porte di origine, mentre con i server perimetrali è necessario specificare un intervallo di porte di destinazione. Di conseguenza, non è possibile applicare semplicemente criteri QoS dei Conferencing Server, server applicazioni e Mediation Server ai server perimetrali poiché non funzionerebbero. È necessario invece creare nuovi criteri e applicarli solo ai server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="42ce6-p101">In addition to creating QoS policies for your Conferencing, Application, and Mediation servers, you must also create both audio and video policies for the internal side of your A/V Edge servers. However, the policies used on your Edge servers are different from the policies used on your Conferencing, Application, and Mediation servers. For the Conferencing, Application, and Mediation servers you specified a source port range; with Edge servers, you need to specify a destination port range. Because of that you cannot simply apply the Conferencing, Application, and Mediation server QoS policies to your Edge servers: these policies simply won't work. Instead, you must create new policies and apply those policies to your Edge servers only.</span></span>

<span data-ttu-id="42ce6-p102">Nella procedura seguente viene descritto il processo per creare oggetti Criteri di gruppo di Active Directory da utilizzare per gestire la Qualità del Servizio (QoS) sui server perimetrali. È naturalmente possibile che i server perimetrali siano server indipendenti che non dispongono di account di Active Directory. In questo caso, è possibile utilizzare Criteri di gruppo locali invece di Criteri di gruppo di Active Directory. L'unica differenza è che questi criteri locali devono essere creati mediante l'Editor Criteri di gruppo locali ed è necessario creare singolarmente lo stesso set di criteri su ogni server perimetrale. Per avviare l'Editor Criteri di gruppo locali su un server perimetrale, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="42ce6-p102">The following procedure describes the process for creating Active Directory Group Policy objects that can be used to manage Quality of Service on Edge Servers. Of course, it's possible that your Edge servers are stand-alone servers that do not have Active Directory accounts. If that's the case, you can use local Group Policy instead of Active Directory Group Policy: the only difference is that you must create these local policies using the Local Group Policy Editor, and must individually create the same set of policies on each Edge Server. To start the Local Group Policy Editor on an Edge server do the following:</span></span>

1.  <span data-ttu-id="42ce6-113">Fare clic sul pulsante **Start**, quindi scegliere **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="42ce6-113">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="42ce6-114">Nella finestra di dialogo **Esegui** digitare **gpedit.msc**, quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="42ce6-114">In the **Run** dialog box, type **gpedit.msc** and then press ENTER.</span></span>

<span data-ttu-id="42ce6-p103">Se si creano criteri basati su Active Directory, è necessario accedere a un computer in cui sia installato Gestione Criteri di gruppo. In questo caso, aprire Gestione Criteri di gruppo facendo su **Start**, scegliendo **Strumenti di amministrazione** e **Gestione Criteri di gruppo**, quindi eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="42ce6-p103">If you are creating Active Directory-based policies, then you should log on to a computer where Group Policy Management has been installed. In that case, open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**) and then complete the following steps:</span></span>

1.  <span data-ttu-id="42ce6-p104">In Gestione Criteri di gruppo individuare il contenitore in cui creare il nuovo criterio. Ad esempio, se tutti i computer Lync Server si trovano in un'unità organizzativa denominata Lync Server, il nuovo criterio deve essere creato nell'unità organizzativa Lync Server.</span><span class="sxs-lookup"><span data-stu-id="42ce6-p104">In Group Policy Management, locate the container where the new policy should be created. For example, if all your Lync Server computers are located in an OU named Lync Server then the new policy should be created in the Lync Server OU.</span></span>

2.  <span data-ttu-id="42ce6-119">Fare clic con il pulsante destro del mouse sul contenitore appropriato e scegliere **Crea un oggetto Criteri di gruppo in questo dominio e crea qui un collegamento**.</span><span class="sxs-lookup"><span data-stu-id="42ce6-119">Right-click the appropriate container and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="42ce6-120">Nella nuova finestra di dialogo **Nuovo oggetto Criteri di gruppo** digitare un nome per il nuovo oggetto Criteri di gruppo nella casella **Nome** (ad esempio, **Lync Server Audio**) e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="42ce6-120">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box (for example, **Lync Server Audio**) and then click **OK**.</span></span>

4.  <span data-ttu-id="42ce6-121">Fare clic con il pulsante destro del mouse sul criterio appena creato e scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="42ce6-121">Right-click the newly-created policy and then click **Edit**.</span></span>

<span data-ttu-id="42ce6-122">Da questo punto in avanti il processo è identico sia per la creazione di un criterio di Active Directory che per la creazione di un criterio locale:</span><span class="sxs-lookup"><span data-stu-id="42ce6-122">From here the process is identical regardless of whether you are creating an Active Directory policy or a local policy:</span></span>

1.  <span data-ttu-id="42ce6-123">In Editor Gestione Criteri di gruppo o Editor Criteri di gruppo locali espandere **Configurazione computer**, espandere **Criteri**, espandere **Impostazioni di Windows**, fare clic con il pulsante destro del mouse su **QoS basata su criteri** e scegliere **Crea nuovo criterio**.</span><span class="sxs-lookup"><span data-stu-id="42ce6-123">In the Group Policy Management Editor or the Local Group Policy Editor, expand **Computer Configuration**, expand **Policies**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

2.  <span data-ttu-id="42ce6-p105">Nella pagina iniziale della finestra di dialogo **QoS basata su criteri** digitare un nome per il nuovo criterio, ad esempio **Lync Server Audio**, nella casella **Nome**. Selezionare **Specifica valore DSCP** e impostare il valore su **46**. Lasciare deselezionata l'opzione **Specifica velocità in uscita** e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="42ce6-p105">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy (e.g., **Lync Server Audio**) in the **Name** box. Select **Specify DSCP Value** and set the value to **46**. Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

3.  <span data-ttu-id="42ce6-p106">Nella pagina successiva verificare che l'opzione **Tutte le applicazioni** sia selezionata, quindi fare clic su **Avanti**. Questa impostazione indica alla rete di cercare tutti i pacchetti contrassegnati con il valore DSCP 46, non solo i pacchetti creati da un'applicazione specifica.</span><span class="sxs-lookup"><span data-stu-id="42ce6-p106">On the next page, make sure that **All applications** is selected and then click **Next**. This setting instructs the network to look for all packets with a DSCP marking of 46, not just packets created by a specific application.</span></span>

4.  <span data-ttu-id="42ce6-p107">Nella terza pagina verificare che **Qualsiasi indirizzo IP di origine** e **Qualsiasi indirizzo IP di destinazione** siano entrambi selezionati e quindi fare clic su **Avanti**. Queste due impostazioni assicurano che i pacchetti vengano gestiti indipendentemente dal computer (indirizzo IP) che li invia e dal computer (indirizzo IP) che li riceve.</span><span class="sxs-lookup"><span data-stu-id="42ce6-p107">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected and then click **Next**. These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

5.  <span data-ttu-id="42ce6-131">Nella quarta pagina selezionare **TCP e UDP** dall'elenco a discesa **Seleziona il protocollo a cui si applica questo criterio QoS**.</span><span class="sxs-lookup"><span data-stu-id="42ce6-131">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="42ce6-132">TCP (Transmission Control Protocol) e UDP (User Datagram Protocol) sono i due protocolli di rete più comunemente utilizzati da Lync Server e dalle sue applicazioni client.</span><span class="sxs-lookup"><span data-stu-id="42ce6-132">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Lync Server and its client applications.</span></span>

6.  <span data-ttu-id="42ce6-p109">In **Specifica il numero della porta di destinazione** selezionare **Verso questo numero di porta o intervallo di porte di destinazione**. Nella casella di testo associata, immettere l'intervallo di porte riservato per le trasmissioni audio. Ad esempio, se sono state riservate le porte da 49152 a 57500 per il traffico audio, immettere l'intervallo di porte nel formato: **49152:57500**. Fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="42ce6-p109">Under the heading **Specify the destination port number**, select **From this destination port or range**. In the accompanying text box, type the port range reserved for audio transmissions. For example, if you reserved ports 49152 through ports 57500 for audio traffic then enter the port range using this format: **49152:57500**. Click **Finish**.</span></span>

<span data-ttu-id="42ce6-p110">Dopo avere creato il criterio QoS per il traffico audio, è necessario creare un secondo criterio per il traffico video. Per creare un criterio per il video, seguire la stessa procedura utilizzata per la creazione del criterio audio, con le seguenti sostituzioni:</span><span class="sxs-lookup"><span data-stu-id="42ce6-p110">After you have created the QoS policy for audio traffic you should create a second policy for video traffic. To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="42ce6-139">Utilizzare un nome di criterio diverso e univoco, ad esempio **Lync Server Video**.</span><span class="sxs-lookup"><span data-stu-id="42ce6-139">Use a different (and unique) policy name (for example, **Lync Server Video**).</span></span>

  - <span data-ttu-id="42ce6-p111">Impostare il valore DSCP su **34** anziché su 46. Tenere presente che non è essenziale utilizzare il valore DSCP 34. L'unico requisito è che si utilizzi un valore DSCP diverso per il video e per l'audio.</span><span class="sxs-lookup"><span data-stu-id="42ce6-p111">Set the DSCP value to **34** instead of 46. (Note that you do not have to use a DSCP value of 34. The only requirement is that you use a different DSCP value for video than you used for audio.)</span></span>

  - <span data-ttu-id="42ce6-p112">Utilizzare l'intervallo di porte configurato in precedenza per il traffico video. Ad esempio, se sono state riservate le porte da 57501 a 65535 per il video, impostare l'intervallo di porte su **57501:65535**. Anche in questo caso è necessario configurarlo come intervallo di porte di destinazione.</span><span class="sxs-lookup"><span data-stu-id="42ce6-p112">Use the previously-configured port range for video traffic. For example, if you have reserved ports 57501 through 65535 for video, then set the port range to this: **57501:65535**. Again, this should be configured as the destination port range.</span></span>

<span data-ttu-id="42ce6-146">Se si decide di creare un criterio per la gestione del traffico di condivisione delle applicazioni, è necessario creare un terzo criterio, con le seguenti sostituzioni:</span><span class="sxs-lookup"><span data-stu-id="42ce6-146">If you decide to create a policy for managing application sharing traffic you must create a third policy, making the following substitutions:</span></span>

  - <span data-ttu-id="42ce6-147">Usare un nome diverso (e univoco) per il criterio (ad esempio, **Lync Server Application Sharing**).</span><span class="sxs-lookup"><span data-stu-id="42ce6-147">Use a different (and unique) policy name (for example, **Lync Server Application Sharing**).</span></span>

  - <span data-ttu-id="42ce6-p113">Impostare il valore DSCP su **24** invece di 46. Come indicato prima, non è obbligatorio usare il valore DSCP 24. L'unico requisito consiste nell'usare un valore DSCP diverso da quello usato per l'audio.</span><span class="sxs-lookup"><span data-stu-id="42ce6-p113">Set the DSCP value to **24** instead of 46. (Again, you do not have to use a DSCP value of 24. The only requirement is that you use a different DSCP value for application sharing than you used for audio or for video.)</span></span>

  - <span data-ttu-id="42ce6-p114">Utilizzare l'intervallo di porte configurato in precedenza per il traffico video. Ad esempio, se sono state riservate le porte da 40803 a 49151 per la condivisione di applicazioni, impostare questo intervallo di porte su **40803:49151**.</span><span class="sxs-lookup"><span data-stu-id="42ce6-p114">Use the previously-configured port range for video traffic. For example, if you have reserved ports 40803 through 49151 for application sharing, then set the port range to this: **40803:49151**.</span></span>

<span data-ttu-id="42ce6-p115">I nuovi criteri creati verranno applicati solo dopo l'aggiornamento di Criteri di gruppo sui server perimetrali. L'aggiornamento di Criteri di gruppo viene eseguito periodicamente in modo automatico, ma è possibile forzarne l'esecuzione immediata utilizzando il comando seguente su ogni computer in cui questa operazione è necessaria:</span><span class="sxs-lookup"><span data-stu-id="42ce6-p115">The new policies you have created will not take effect until Group Policy has been refreshed on your Edge servers. Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpudate.exe /force

<span data-ttu-id="42ce6-155">Questo comando può essere eseguito dall'interno del Lync Server o da qualsiasi finestra di comando in esecuzione con le credenziali di amministratore.</span><span class="sxs-lookup"><span data-stu-id="42ce6-155">This command can be run from within the Lync Server or from any command window that is running under administrator credentials.</span></span> <span data-ttu-id="42ce6-156">Per eseguire una finestra di comando con credenziali di amministratore, fare clic su **Start**, fare clic con il pulsante destro del mouse su **Prompt dei comandi** e scegliere **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="42ce6-156">To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span> <span data-ttu-id="42ce6-157">Può essere necessario riavviare il server perimetrale anche dopo avere eseguito Gpudate.exe.</span><span class="sxs-lookup"><span data-stu-id="42ce6-157">Note that you might need to restart the Edge server even after running Gpudate.exe.</span></span>

<span data-ttu-id="42ce6-158">Per assicurarsi che i pacchetti di rete siano contrassegnati con il valore DSCP appropriato, creare anche una nuova voce del Registro di sistema su ogni computer completando la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="42ce6-158">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="42ce6-159">Fare clic sul pulsante **Start**, quindi scegliere **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="42ce6-159">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="42ce6-160">Nella finestra di dialogo **Esegui** digitare **regedit** e quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="42ce6-160">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="42ce6-161">Nell'editor del registro di sistema **espandere\_HKEY\_computer locale**, espandere **System**, espandere **CurrentControlSet**, espandere **Servizi**e quindi espandere **Tcpip**.</span><span class="sxs-lookup"><span data-stu-id="42ce6-161">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="42ce6-p117">Fare clic con il pulsante destro **Tcpip**, scegliere **Nuovo** e quindi fare clic su **Chiave**. Dopo aver creato la nuova chiave del Registro di sistema, digitare **QoS** e quindi premere INVIO per rinominare la chiave.</span><span class="sxs-lookup"><span data-stu-id="42ce6-p117">Right-click **Tcpip**, point to **New**, and then click **Key**. After the new registry key is created, type **QoS** and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="42ce6-p118">Fare clic con il pulsante destro del mouse su **QoS**, scegliere **Nuovo** e quindi **Valore stringa**. Dopo aver creato il nuovo valore del Registro di sistema, digitare **Do not use NLA** e quindi premere INVIO per rinominare il valore.</span><span class="sxs-lookup"><span data-stu-id="42ce6-p118">Right-click **QoS**, point to **New**, and then click **String Value**. After the new registry value is created, type **Do not use NLA** and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="42ce6-p119">Fare doppio clic su **Do no use NLA**. Nella finestra di dialogo **Modifica stringa** digitare **1** nella casella **Dati valore** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="42ce6-p119">Double-click **Do no use NLA**. In the **Edit String** dialog box, type **1** in the **Value data** box and then click **OK**.</span></span>

7.  <span data-ttu-id="42ce6-168">Chiudere l'editor del Registro di sistema e riavviare il computer.</span><span class="sxs-lookup"><span data-stu-id="42ce6-168">Close the Registry Editor and then reboot your computer.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

