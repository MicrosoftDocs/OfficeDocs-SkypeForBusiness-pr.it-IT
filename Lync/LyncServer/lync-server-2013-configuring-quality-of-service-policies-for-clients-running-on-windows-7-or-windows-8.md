---
title: 'Lync Server 2013: configurare i criteri di qualità dei servizi per i client in uso in Windows 7 o Windows 8'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Quality of Service policies for clients running on Windows 7 or Windows 8
ms:assetid: efff2b98-b3fb-4183-a4f0-329a9105ce2c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205371(v=OCS.15)
ms:contentKeyID: 48185785
ms.date: 03/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 365ce7a48a3c30a9e810d44edc1b7130ceb2643b
ms.sourcegitcommit: f7ec026accb0bb91ce62a9d5f24ac4b70a514c4e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/25/2019
ms.locfileid: "40982249"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-quality-of-service-policies-in-lync-server-2013-for-clients-running-on-windows-7-or-windows-8"></a><span data-ttu-id="a123a-102">Configurazione di criteri di qualità dei servizi in Lync Server 2013 per i client in uso in Windows 7 o Windows 8</span><span class="sxs-lookup"><span data-stu-id="a123a-102">Configuring Quality of Service policies in Lync Server 2013 for clients running on Windows 7 or Windows 8</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a123a-103">_**Argomento Ultima modifica:** 2016-03-29_</span><span class="sxs-lookup"><span data-stu-id="a123a-103">_**Topic Last Modified:** 2016-03-29_</span></span>

<span data-ttu-id="a123a-104">Oltre a specificare gli intervalli di porte per l'uso da parte dei client Lync, devi anche creare criteri di qualità distinti per i servizi che verranno applicati ai computer client.</span><span class="sxs-lookup"><span data-stu-id="a123a-104">In addition to specifying port ranges for use by your Lync clients you must also create separate Quality of Service policies that will be applied to client computers.</span></span> <span data-ttu-id="a123a-105">I criteri di qualità dei servizi creati per le conferenze, le applicazioni e i server di mediazione non devono essere applicati ai computer client. Queste informazioni si applicano solo ai computer che eseguono il client Lync 2013 e Windows 7 o Windows 8.</span><span class="sxs-lookup"><span data-stu-id="a123a-105">(The Quality of Service policies created for Conferencing, Application, and Mediation servers should not be applied to client computers.) This information applies only to computers running the Lync 2013 client and either Windows 7 or Windows 8.</span></span>

<span data-ttu-id="a123a-106">Nell'esempio seguente viene usato questo set di intervalli di porte per creare un criterio audio e un criterio video:</span><span class="sxs-lookup"><span data-stu-id="a123a-106">The following example uses this set of port ranges to create an audio policy and a video policy:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a123a-107">Tipo di traffico client</span><span class="sxs-lookup"><span data-stu-id="a123a-107">Client Traffic Type</span></span></th>
<th><span data-ttu-id="a123a-108">Inizio porta</span><span class="sxs-lookup"><span data-stu-id="a123a-108">Port Start</span></span></th>
<th><span data-ttu-id="a123a-109">Intervallo di porte</span><span class="sxs-lookup"><span data-stu-id="a123a-109">Port Range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a123a-110">Audio</span><span class="sxs-lookup"><span data-stu-id="a123a-110">Audio</span></span></p></td>
<td><p><span data-ttu-id="a123a-111">50020</span><span class="sxs-lookup"><span data-stu-id="a123a-111">50020</span></span></p></td>
<td><p><span data-ttu-id="a123a-112">20</span><span class="sxs-lookup"><span data-stu-id="a123a-112">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a123a-113">Video</span><span class="sxs-lookup"><span data-stu-id="a123a-113">Video</span></span></p></td>
<td><p><span data-ttu-id="a123a-114">58000</span><span class="sxs-lookup"><span data-stu-id="a123a-114">58000</span></span></p></td>
<td><p><span data-ttu-id="a123a-115">20</span><span class="sxs-lookup"><span data-stu-id="a123a-115">20</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a123a-116">Condivisione applicazioni</span><span class="sxs-lookup"><span data-stu-id="a123a-116">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="a123a-117">42000</span><span class="sxs-lookup"><span data-stu-id="a123a-117">42000</span></span></p></td>
<td><p><span data-ttu-id="a123a-118">20</span><span class="sxs-lookup"><span data-stu-id="a123a-118">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a123a-119">Trasferimento di file</span><span class="sxs-lookup"><span data-stu-id="a123a-119">File transfer</span></span></p></td>
<td><p><span data-ttu-id="a123a-120">42020</span><span class="sxs-lookup"><span data-stu-id="a123a-120">42020</span></span></p></td>
<td><p><span data-ttu-id="a123a-121">20</span><span class="sxs-lookup"><span data-stu-id="a123a-121">20</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a123a-122">Per creare un criterio di qualità dei servizi audio per i computer Windows 7 o Windows 8, prima di tutto accedere a un computer in cui è stata installata la gestione di criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="a123a-122">To create a Quality of Service audio policy for Windows 7 or Windows 8 computers, first log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="a123a-123">Aprire Gestione criteri di gruppo (fare clic sul pulsante **Start**, scegliere **strumenti di amministrazione**e quindi fare clic su **Gestione criteri di gruppo**) e quindi completare la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="a123a-123">Open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**) and then complete the following procedure:</span></span>

1.  <span data-ttu-id="a123a-124">In Gestione criteri di gruppo individuare il contenitore in cui deve essere creato il nuovo criterio.</span><span class="sxs-lookup"><span data-stu-id="a123a-124">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="a123a-125">Ad esempio, se tutti i computer client si trovano in un'unità organizzativa denominata clients, il nuovo criterio deve essere creato nell'unità organizzativa client.</span><span class="sxs-lookup"><span data-stu-id="a123a-125">For example, if all your client computers are located in an OU named Clients then the new policy should be created in the Client OU.</span></span>

2.  <span data-ttu-id="a123a-126">Fare clic con il pulsante destro del mouse sul contenitore appropriato e quindi scegliere **Crea un GPO in questo dominio e collegarlo qui**.</span><span class="sxs-lookup"><span data-stu-id="a123a-126">Right-click the appropriate container and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="a123a-127">Nella finestra di dialogo **nuovo GPO** Digitare un nome per il nuovo oggetto Criteri di gruppo nella casella **nome** , ad esempio **audio Lync**, e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="a123a-127">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box (for example, **Lync Audio**) and then click **OK**.</span></span>

4.  <span data-ttu-id="a123a-128">Fare clic con il pulsante destro del mouse sul criterio appena creato e quindi scegliere **modifica**.</span><span class="sxs-lookup"><span data-stu-id="a123a-128">Right-click the newly-created policy and then click **Edit**.</span></span>

5.  <span data-ttu-id="a123a-129">In Editor gestione criteri di gruppo espandere **Configurazione computer**, espandere **criteri**, espandere **impostazioni di Windows**, fare clic con il pulsante destro del mouse su **QoS basata su criteri**e quindi scegliere **Crea nuovo criterio**.</span><span class="sxs-lookup"><span data-stu-id="a123a-129">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Policies**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

6.  <span data-ttu-id="a123a-130">Nella pagina di apertura della finestra di dialogo **QoS basata sui criteri** Digitare un nome per il nuovo criterio, ad esempio **audio Lync**, nella casella **nome** .</span><span class="sxs-lookup"><span data-stu-id="a123a-130">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy (e.g., **Lync Audio**) in the **Name** box.</span></span> <span data-ttu-id="a123a-131">Selezionare **Specifica valore DSCP** e impostare il valore su **46**.</span><span class="sxs-lookup"><span data-stu-id="a123a-131">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="a123a-132">Lascia **specificare la frequenza di accelerazione in uscita** deselezionata e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a123a-132">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

7. <span data-ttu-id="a123a-133">Nella pagina successiva selezionare **solo le applicazioni con il nome eseguibile** e immettere il nome **Lync. exe**e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a123a-133">On the next page, select **Only applications with this executable name** and enter the name **Lync.exe**, and then click **Next**.</span></span> <span data-ttu-id="a123a-134">Questa impostazione indica al criterio di assegnare la priorità solo al traffico corrispondente dal client Lync.</span><span class="sxs-lookup"><span data-stu-id="a123a-134">This setting instructs the policy to only prioritize matching traffic from the Lync client.</span></span>

8.  <span data-ttu-id="a123a-135">Nella terza pagina verificare che sia selezionato l'indirizzo IP di **origine** e **qualsiasi indirizzo IP di destinazione** e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a123a-135">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected and then click **Next**.</span></span> <span data-ttu-id="a123a-136">Queste due impostazioni assicurano che i pacchetti vengano gestiti indipendentemente da quale computer (indirizzo IP) ha inviato i pacchetti e quale computer (indirizzo IP) riceverà tali pacchetti.</span><span class="sxs-lookup"><span data-stu-id="a123a-136">These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

9.  <span data-ttu-id="a123a-137">Nella pagina quattro selezionare **TCP e UDP** dal pulsante **Seleziona il protocollo questo criterio di QoS si applica all'elenco a** discesa.</span><span class="sxs-lookup"><span data-stu-id="a123a-137">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="a123a-138">TCP (Transmission Control Protocol) e UDP (User Datagram Protocol) sono i due protocolli di rete usati più comunemente da Lync Server e dalle sue applicazioni client.</span><span class="sxs-lookup"><span data-stu-id="a123a-138">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Lync Server and its client applications.</span></span>

10. <span data-ttu-id="a123a-139">Sotto l'intestazione **specificare il numero della porta di origine**, selezionare **dalla porta o dall'intervallo di origine**.</span><span class="sxs-lookup"><span data-stu-id="a123a-139">Under the heading **Specify the source port number**, select **From this source port or range**.</span></span> <span data-ttu-id="a123a-140">Nella casella di testo associata digitare l'intervallo di porte riservato per le trasmissioni audio.</span><span class="sxs-lookup"><span data-stu-id="a123a-140">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="a123a-141">Ad esempio, se hai riservato le porte 50020 tramite le porte 50039 per il traffico audio, immetti l'intervallo di porte usando questo formato: **50020:50039**.</span><span class="sxs-lookup"><span data-stu-id="a123a-141">For example, if you reserved ports 50020 through ports 50039 for audio traffic enter the port range using this format: **50020:50039**.</span></span> <span data-ttu-id="a123a-142">Fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="a123a-142">Click **Finish**.</span></span>

<span data-ttu-id="a123a-143">Dopo aver creato i criteri QoS per l'audio, è necessario creare un secondo criterio per il video.</span><span class="sxs-lookup"><span data-stu-id="a123a-143">After you have created the QoS policy for audio you should then create a second policy for video.</span></span> <span data-ttu-id="a123a-144">Per creare un criterio per il video, seguire la stessa procedura di base seguita durante la creazione dei criteri audio, eseguendo queste sostituzioni:</span><span class="sxs-lookup"><span data-stu-id="a123a-144">To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="a123a-145">Usare un nome di criterio diverso (e univoco), ad esempio **Lync video**.</span><span class="sxs-lookup"><span data-stu-id="a123a-145">Use a different (and unique) policy name (for example, **Lync Video**).</span></span>

  - <span data-ttu-id="a123a-146">Impostare il valore DSCP su **34** anziché su 46.</span><span class="sxs-lookup"><span data-stu-id="a123a-146">Set the DSCP value to **34** instead of 46.</span></span> <span data-ttu-id="a123a-147">Come indicato in precedenza, non è necessario usare il valore DSCP 34; devi semplicemente assegnare un valore DSCP diverso rispetto a quello usato per l'audio.</span><span class="sxs-lookup"><span data-stu-id="a123a-147">(As noted previously, you do not have to use the DSCP value 34; you simply must assign a different DSCP value than the one used for audio.)</span></span>

  - <span data-ttu-id="a123a-148">Usa l'intervallo di porte configurato in precedenza per il traffico video.</span><span class="sxs-lookup"><span data-stu-id="a123a-148">Use the previously-configured port range for video traffic.</span></span> <span data-ttu-id="a123a-149">Ad esempio, se sono state riservate le porte da 58000 a 58019 per il video, impostare l'intervallo di porte su questo: **58000:58019**.</span><span class="sxs-lookup"><span data-stu-id="a123a-149">For example, if you have reserved ports 58000 through 58019 for video, then set the port range to this: **58000:58019**.</span></span>

<span data-ttu-id="a123a-150">Se si decide di creare un criterio per la gestione del traffico di condivisione delle applicazioni, eseguire queste sostituzioni:</span><span class="sxs-lookup"><span data-stu-id="a123a-150">If you decide to create a policy for managing application sharing traffic make these substitutions:</span></span>

  - <span data-ttu-id="a123a-151">Usare un nome di criterio diverso (e univoco), ad esempio la **condivisione delle applicazioni di Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="a123a-151">Use a different (and unique) policy name (for example, **Lync Server Application Sharing**).</span></span>

  - <span data-ttu-id="a123a-152">Impostare il valore DSCP su **24** anziché su 46.</span><span class="sxs-lookup"><span data-stu-id="a123a-152">Set the DSCP value to **24** instead of 46.</span></span> <span data-ttu-id="a123a-153">(Anche in questo caso, il valore non deve essere 24; è semplicemente diverso dai valori DSCP usati per l'audio e per il video.)</span><span class="sxs-lookup"><span data-stu-id="a123a-153">(Again, this value does not have to be 24; it simply must be different than the DSCP values used for audio and for video.)</span></span>

  - <span data-ttu-id="a123a-154">Usa l'intervallo di porte configurato in precedenza per il traffico video.</span><span class="sxs-lookup"><span data-stu-id="a123a-154">Use the previously-configured port range for video traffic.</span></span> <span data-ttu-id="a123a-155">Ad esempio, se si hanno le porte riservate da 42000 a 42019 per la condivisione delle applicazioni, impostare l'intervallo di porte su questo: **42000:42019**.</span><span class="sxs-lookup"><span data-stu-id="a123a-155">For example, if you have reserved ports 42000 through 42019 for application sharing, then set the port range to this: **42000:42019**.</span></span>

<span data-ttu-id="a123a-156">Per un criterio di trasferimento file:</span><span class="sxs-lookup"><span data-stu-id="a123a-156">For a file transfer policy:</span></span>

  - <span data-ttu-id="a123a-157">Usare un nome di criterio diverso (e univoco), ad esempio i **trasferimenti di file di Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="a123a-157">Use a different (and unique) policy name (for example, **Lync Server File Transfers**).</span></span>

  - <span data-ttu-id="a123a-158">Imposta il valore DSCP su **14**.</span><span class="sxs-lookup"><span data-stu-id="a123a-158">Set the DSCP value to **14**.</span></span> <span data-ttu-id="a123a-159">(Anche in questo caso, il valore non deve essere 14, ma è semplicemente un codice DSCP univoco).</span><span class="sxs-lookup"><span data-stu-id="a123a-159">(Again, this value does not have to be 14; it simply must be a unique DSCP code.)</span></span>

  - <span data-ttu-id="a123a-160">Usa l'intervallo di porte configurato in precedenza per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a123a-160">Use the previously-configured port range for application.</span></span> <span data-ttu-id="a123a-161">Ad esempio, se si hanno le porte riservate da 42020 a 42039 per la condivisione delle applicazioni, impostare l'intervallo di porte su questo: **42020:42039**.</span><span class="sxs-lookup"><span data-stu-id="a123a-161">For example, if you have reserved ports 42020 through 42039 for application sharing, then set the port range to this: **42020:42039**.</span></span>

<span data-ttu-id="a123a-162">I nuovi criteri creati non avranno effetto finché i criteri di gruppo non saranno stati aggiornati nei computer client.</span><span class="sxs-lookup"><span data-stu-id="a123a-162">The new policies you have created will not take effect until Group Policy has been refreshed on your client computers.</span></span> <span data-ttu-id="a123a-163">Anche se i criteri di gruppo vengono periodicamente aggiornati autonomamente, è possibile forzare l'aggiornamento immediato eseguendo il comando seguente in ogni computer in cui è necessario aggiornare i criteri di gruppo:</span><span class="sxs-lookup"><span data-stu-id="a123a-163">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpudate.exe /force

<span data-ttu-id="a123a-164">Questo comando può essere eseguito da qualsiasi finestra di comando in esecuzione in credenziali di amministratore.</span><span class="sxs-lookup"><span data-stu-id="a123a-164">This command can be run from any command window that is running under administrator credentials.</span></span> <span data-ttu-id="a123a-165">Per eseguire una finestra di comando in credenziali di amministratore, fare clic su **Start**, fare clic con il pulsante destro del mouse su **prompt dei comandi**e quindi scegliere **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="a123a-165">To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

<span data-ttu-id="a123a-166">Tieni presente che questi criteri devono essere mirati verso i computer client.</span><span class="sxs-lookup"><span data-stu-id="a123a-166">Keep in mind that these policies should be targeted towards your client computers.</span></span> <span data-ttu-id="a123a-167">Non devono essere applicati ai server che eseguono Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a123a-167">They should not be applied to servers running Lync Server.</span></span>

<span data-ttu-id="a123a-168">Per assicurarti che i pacchetti di rete siano contrassegnati con il valore DSCP appropriato, devi anche creare una nuova voce del registro di sistema in ogni computer completando la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="a123a-168">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="a123a-169">Fare clic sul pulsante **Start** e quindi su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="a123a-169">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="a123a-170">Nella finestra di dialogo **Esegui** Digitare **Regedit** e quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="a123a-170">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="a123a-171">Nell'editor del registro di sistema **espandere\_HKEY\_computer locale**, espandere **System**, espandere **CurrentControlSet**, espandere **Servizi**e quindi espandere **Tcpip**.</span><span class="sxs-lookup"><span data-stu-id="a123a-171">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="a123a-172">Fare clic con il pulsante destro del mouse su **Tcpip**, scegliere **nuovo**e quindi fare clic su **chiave**.</span><span class="sxs-lookup"><span data-stu-id="a123a-172">Right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="a123a-173">Dopo la creazione della nuova chiave del registro di sistema, digitare **QoS** e quindi premere INVIO per rinominare la chiave.</span><span class="sxs-lookup"><span data-stu-id="a123a-173">After the new registry key is created, type **QoS** and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="a123a-174">Fare clic con il pulsante destro del mouse su **QoS**, scegliere **nuovo**e quindi fare clic su **valore stringa**.</span><span class="sxs-lookup"><span data-stu-id="a123a-174">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="a123a-175">Dopo la creazione del nuovo valore del registro di sistema, digitare non **usare NLA** e quindi premere INVIO per rinominare il valore.</span><span class="sxs-lookup"><span data-stu-id="a123a-175">After the new registry value is created, type **Do not use NLA** and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="a123a-176">Fare doppio clic su non **usare NLA**.</span><span class="sxs-lookup"><span data-stu-id="a123a-176">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="a123a-177">Nella finestra di dialogo **Modifica stringa** Digitare **1** nella casella **dati valore** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="a123a-177">In the **Edit String** dialog box, type **1** in the **Value data** box and then click **OK**.</span></span>

7.  <span data-ttu-id="a123a-178">Chiudere l'editor del registro di sistema e riavviare il computer.</span><span class="sxs-lookup"><span data-stu-id="a123a-178">Close the Registry Editor and then reboot your computer.</span></span>

<div>

## <a name="configuring-quality-of-service-on-computers-with-multiple-network-adapters"></a><span data-ttu-id="a123a-179">Configurazione della qualità del servizio nei computer con più schede di rete</span><span class="sxs-lookup"><span data-stu-id="a123a-179">Configuring Quality of Service on Computers with Multiple Network Adapters</span></span>

<span data-ttu-id="a123a-180">Se si dispone di un computer in cui sono presenti più schede di rete, è possibile che si verifichino occasionalmente problemi in cui i valori DSCP sono visualizzati come 0x00 invece del valore configurato.</span><span class="sxs-lookup"><span data-stu-id="a123a-180">If you have a computer that has multiple network adapters you might occasionally run into issues where DSCP values are shown as 0x00 rather than the configured value.</span></span> <span data-ttu-id="a123a-181">Ciò si verifica in genere nei computer in cui una o più schede di rete non sono in grado di accedere al dominio Active Directory, ad esempio se questi adapter vengono usati per una rete privata.</span><span class="sxs-lookup"><span data-stu-id="a123a-181">This will typically occur on computers where one or more of the network adapters are not able to access your Active Directory domain (for example, if these adapters are used for a private network).</span></span> <span data-ttu-id="a123a-182">In casi come questo, i valori DSCP verranno contrassegnati per gli adapter che possono accedere al dominio, ma non verranno contrassegnati per gli adapter che non possono accedere al dominio.</span><span class="sxs-lookup"><span data-stu-id="a123a-182">In cases like that, DSCP values will be tagged for the adapters that can access the domain, but will not be tagged for adapters that cannot access the domain.</span></span>

<span data-ttu-id="a123a-183">Se si vuole contrassegnare i valori DSCP per tutte le schede di rete in un computer, inclusi gli adapter che non hanno accesso al dominio, è necessario aggiungere e configurare un valore per il registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="a123a-183">If you would like to tag DSCP values for all the network adapters in a computer, including adapters that do not have access to your domain, then you will need to add and configure a value to the registry.</span></span> <span data-ttu-id="a123a-184">Questa operazione può essere eseguita completando la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="a123a-184">That can be done by completing the following procedure:</span></span>

1.  <span data-ttu-id="a123a-185">Fare clic sul pulsante **Start** e quindi su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="a123a-185">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="a123a-186">Nella finestra di dialogo **Esegui** Digitare **Regedit** e quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="a123a-186">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="a123a-187">Nell'editor del registro di sistema **espandere\_HKEY\_computer locale**, espandere **System**, espandere **CurrentControlSet**, espandere **Servizi**e quindi espandere **Tcpip**.</span><span class="sxs-lookup"><span data-stu-id="a123a-187">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="a123a-188">Se non viene visualizzata una chiave del registro di sistema con l'etichetta **QoS** , fare clic con il pulsante destro del mouse su **Tcpip**, scegliere **nuovo**e quindi fare clic su **chiave**.</span><span class="sxs-lookup"><span data-stu-id="a123a-188">If you do not see a registry key labeled **QoS** then right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="a123a-189">Dopo aver creato la nuova chiave, digitare **QoS** e quindi premere INVIO per rinominare la chiave.</span><span class="sxs-lookup"><span data-stu-id="a123a-189">After the new key is created, type **QoS** and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="a123a-190">Fare clic con il pulsante destro del mouse su **QoS**, scegliere **nuovo**e quindi fare clic su **valore stringa**.</span><span class="sxs-lookup"><span data-stu-id="a123a-190">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="a123a-191">Dopo la creazione del nuovo valore del registro di sistema, digitare non **usare NLA** e quindi premere INVIO per rinominare il valore.</span><span class="sxs-lookup"><span data-stu-id="a123a-191">After the new registry value is created, type **Do not use NLA** and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="a123a-192">Fare doppio clic su non **usare NLA**.</span><span class="sxs-lookup"><span data-stu-id="a123a-192">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="a123a-193">Nella finestra di dialogo **Modifica stringa** Digitare **1** nella casella **dati valore** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="a123a-193">In the **Edit String** dialog box, type **1** in the **Value data** box and then click **OK**.</span></span>

<span data-ttu-id="a123a-194">Dopo aver creato e configurato il nuovo valore del registro di sistema, sarà necessario riavviare il computer in modo che le modifiche abbiano effetto.</span><span class="sxs-lookup"><span data-stu-id="a123a-194">After creating and configuring the new registry value you will need to reboot your computer in order for the changes to take effect.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

