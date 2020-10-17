---
title: 'Lync Server 2013: configurazione dei criteri di qualità del servizio per i client in esecuzione in Windows 7 o Windows 8'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Quality of Service policies for clients running on Windows 7 or Windows 8
ms:assetid: efff2b98-b3fb-4183-a4f0-329a9105ce2c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205371(v=OCS.15)
ms:contentKeyID: 48185785
ms.date: 03/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2cd058e2903160f1c9f4ea06e30959b63953ab01
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534973"
---
# <a name="configuring-quality-of-service-policies-in-lync-server-2013-for-clients-running-on-windows-7-or-windows-8"></a><span data-ttu-id="c28be-102">Configurazione dei criteri di qualità del servizio in Lync Server 2013 per i client in esecuzione in Windows 7 o Windows 8</span><span class="sxs-lookup"><span data-stu-id="c28be-102">Configuring Quality of Service policies in Lync Server 2013 for clients running on Windows 7 or Windows 8</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c28be-103">_**Ultimo argomento modificato:** 2016-03-29_</span><span class="sxs-lookup"><span data-stu-id="c28be-103">_**Topic Last Modified:** 2016-03-29_</span></span>

<span data-ttu-id="c28be-104">Oltre a specificare gli intervalli di porte per l'utilizzo da parte dei client di Lync, è inoltre necessario creare criteri di qualità del servizio distinti che verranno applicati ai computer client.</span><span class="sxs-lookup"><span data-stu-id="c28be-104">In addition to specifying port ranges for use by your Lync clients you must also create separate Quality of Service policies that will be applied to client computers.</span></span> <span data-ttu-id="c28be-105">I criteri di qualità dei servizi creati per le conferenze, l'applicazione e i Mediation Server non devono essere applicati ai computer client. Queste informazioni si applicano solo ai computer che eseguono il client Lync 2013 e Windows 7 o Windows 8.</span><span class="sxs-lookup"><span data-stu-id="c28be-105">(The Quality of Service policies created for Conferencing, Application, and Mediation servers should not be applied to client computers.) This information applies only to computers running the Lync 2013 client and either Windows 7 or Windows 8.</span></span>

<span data-ttu-id="c28be-106">Nell'esempio seguente viene utilizzato questo set di intervalli di porte per creare un criterio audio e un criterio video:</span><span class="sxs-lookup"><span data-stu-id="c28be-106">The following example uses this set of port ranges to create an audio policy and a video policy:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c28be-107">Tipo di traffico client</span><span class="sxs-lookup"><span data-stu-id="c28be-107">Client Traffic Type</span></span></th>
<th><span data-ttu-id="c28be-108">Inizio intervallo porte</span><span class="sxs-lookup"><span data-stu-id="c28be-108">Port Start</span></span></th>
<th><span data-ttu-id="c28be-109">Intervallo porte</span><span class="sxs-lookup"><span data-stu-id="c28be-109">Port Range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c28be-110">Audio</span><span class="sxs-lookup"><span data-stu-id="c28be-110">Audio</span></span></p></td>
<td><p><span data-ttu-id="c28be-111">50020</span><span class="sxs-lookup"><span data-stu-id="c28be-111">50020</span></span></p></td>
<td><p><span data-ttu-id="c28be-112">20</span><span class="sxs-lookup"><span data-stu-id="c28be-112">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c28be-113">Video</span><span class="sxs-lookup"><span data-stu-id="c28be-113">Video</span></span></p></td>
<td><p><span data-ttu-id="c28be-114">58000</span><span class="sxs-lookup"><span data-stu-id="c28be-114">58000</span></span></p></td>
<td><p><span data-ttu-id="c28be-115">20</span><span class="sxs-lookup"><span data-stu-id="c28be-115">20</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c28be-116">Condivisione applicazioni</span><span class="sxs-lookup"><span data-stu-id="c28be-116">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="c28be-117">42000</span><span class="sxs-lookup"><span data-stu-id="c28be-117">42000</span></span></p></td>
<td><p><span data-ttu-id="c28be-118">20</span><span class="sxs-lookup"><span data-stu-id="c28be-118">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c28be-119">Trasferimento di file</span><span class="sxs-lookup"><span data-stu-id="c28be-119">File transfer</span></span></p></td>
<td><p><span data-ttu-id="c28be-120">42020</span><span class="sxs-lookup"><span data-stu-id="c28be-120">42020</span></span></p></td>
<td><p><span data-ttu-id="c28be-121">20</span><span class="sxs-lookup"><span data-stu-id="c28be-121">20</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c28be-122">Per creare un criterio audio di qualità del servizio per i computer Windows 7 o Windows 8, accedere innanzitutto a un computer in cui è stata installata la gestione criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="c28be-122">To create a Quality of Service audio policy for Windows 7 or Windows 8 computers, first log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="c28be-123">Aprire Gestione Criteri di gruppo (fare clic su **Start**, scegliere **Strumenti di amministrazione** e fare clic su **Gestione Criteri di gruppo**) e quindi eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="c28be-123">Open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**) and then complete the following procedure:</span></span>

1.  <span data-ttu-id="c28be-p103">In Gestione Criteri di gruppo individuare il contenitore in cui creare il nuovo criterio. Se ad esempio tutti i computer client appartengono a un'unità organizzativa denominata Client, il nuovo criterio dovrà essere creato in tale unità organizzativa Client.</span><span class="sxs-lookup"><span data-stu-id="c28be-p103">In Group Policy Management, locate the container where the new policy should be created. For example, if all your client computers are located in an OU named Clients then the new policy should be created in the Client OU.</span></span>

2.  <span data-ttu-id="c28be-126">Fare clic con il pulsante destro del mouse sul contenitore appropriato e scegliere **Crea un oggetto Criteri di gruppo in questo dominio e crea qui un collegamento**.</span><span class="sxs-lookup"><span data-stu-id="c28be-126">Right-click the appropriate container and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="c28be-127">Nella finestra di dialogo **Nuovo oggetto Criteri di gruppo** digitare il nome da assegnare al nuovo oggetto Criteri di gruppo nella casella **Nome** (ad esempio, **Lync Audio**) e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="c28be-127">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box (for example, **Lync Audio**) and then click **OK**.</span></span>

4.  <span data-ttu-id="c28be-128">Fare clic con il pulsante destro del mouse sul nuovo criterio e quindi su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="c28be-128">Right-click the newly-created policy and then click **Edit**.</span></span>

5.  <span data-ttu-id="c28be-129">In Editor Gestione Criteri di gruppo espandere **Configurazione computer**, **Criteri** e **Impostazioni di Windows**, fare clic con il pulsante destro del mouse su **QoS basata su criteri** e quindi scegliere **Crea nuovo criterio**.</span><span class="sxs-lookup"><span data-stu-id="c28be-129">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Policies**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

6.  <span data-ttu-id="c28be-p104">Nella finestra di dialogo **QoS basata su criteri** della pagina di apertura digitare un nome per il nuovo criterio (ad esempio, **Lync Audio**) nella casella **Nome**. Selezionare **Specifica valore DSCP** e impostare il valore su **46**. Lasciare **Specifica velocità in uscita** non selezionato e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="c28be-p104">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy (e.g., **Lync Audio**) in the **Name** box. Select **Specify DSCP Value** and set the value to **46**. Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

7. <span data-ttu-id="c28be-133">Nella pagina successiva selezionare solo le **applicazioni con il nome del file eseguibile** e immettere il nome **Lync.exe**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="c28be-133">On the next page, select **Only applications with this executable name** and enter the name **Lync.exe**, and then click **Next**.</span></span> <span data-ttu-id="c28be-134">Questa impostazione indica al criterio di assegnare una priorità solo al traffico corrispondente proveniente dal client Lync.</span><span class="sxs-lookup"><span data-stu-id="c28be-134">This setting instructs the policy to only prioritize matching traffic from the Lync client.</span></span>

8.  <span data-ttu-id="c28be-p106">Nella terza pagina verificare che **Qualsiasi indirizzo IP di origine** e **Qualsiasi indirizzo IP di destinazione** siano entrambi selezionati e quindi fare clic su **Avanti**. Queste due impostazioni assicurano che i pacchetti vengano gestiti indipendentemente dal computer (indirizzo IP) che li invia e dal computer (indirizzo IP) che li riceve.</span><span class="sxs-lookup"><span data-stu-id="c28be-p106">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected and then click **Next**. These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

9.  <span data-ttu-id="c28be-137">Nella quarta pagina selezionare **TCP e UDP** dall'elenco a discesa **Seleziona il protocollo a cui si applica questo criterio QoS**.</span><span class="sxs-lookup"><span data-stu-id="c28be-137">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="c28be-138">TCP (Transmission Control Protocol) e UDP (User Datagram Protocol) sono i due protocolli di rete più comunemente utilizzati da Lync Server e dalle sue applicazioni client.</span><span class="sxs-lookup"><span data-stu-id="c28be-138">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Lync Server and its client applications.</span></span>

10. <span data-ttu-id="c28be-p108">Sotto l'intestazione **Specifica il numero della porta di origine** selezionare **Da questo numero di porta o intervallo di porte di origine**. Nella casella di testo abbinata digitare l'intervallo di porte riservato alle trasmissioni audio. Se ad esempio è stato riservato al traffico audio l'intervallo di porte compreso tra la 50020 e la 50039, immettere l'intervallo di porte utilizzando questo formato: **50020:50039**. Fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="c28be-p108">Under the heading **Specify the source port number**, select **From this source port or range**. In the accompanying text box, type the port range reserved for audio transmissions. For example, if you reserved ports 50020 through ports 50039 for audio traffic enter the port range using this format: **50020:50039**. Click **Finish**.</span></span>

<span data-ttu-id="c28be-p109">Dopo aver creato il criterio QoS per l'audio, è necessario creare un secondo criterio per il video. Per creare un criterio per il video, seguire la stessa procedura base osservata per creare il criterio audio, apportandovi le modifiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="c28be-p109">After you have created the QoS policy for audio you should then create a second policy for video. To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="c28be-145">Utilizzare un nome criterio diverso e univoco (ad esempio, **Lync Video**).</span><span class="sxs-lookup"><span data-stu-id="c28be-145">Use a different (and unique) policy name (for example, **Lync Video**).</span></span>

  - <span data-ttu-id="c28be-p110">Impostare il valore DSCP su **34** anziché su 46. Come accennato, non è necessario utilizzare il valore DSCP 34, bensì è sufficiente utilizzare un valore diverso da quello specificato per l'audio.</span><span class="sxs-lookup"><span data-stu-id="c28be-p110">Set the DSCP value to **34** instead of 46. (As noted previously, you do not have to use the DSCP value 34; you simply must assign a different DSCP value than the one used for audio.)</span></span>

  - <span data-ttu-id="c28be-p111">Utilizzare l'intervallo di porte precedentemente configurato per il traffico video. Se ad esempio al video sono state riservate le porte da 58000 a 58019, impostare l'intervallo di porte in questo modo: **58000:58019**.</span><span class="sxs-lookup"><span data-stu-id="c28be-p111">Use the previously-configured port range for video traffic. For example, if you have reserved ports 58000 through 58019 for video, then set the port range to this: **58000:58019**.</span></span>

<span data-ttu-id="c28be-150">Se si decide di creare un criterio per la gestione del traffico della condivisione applicazioni, effettuare queste sostituzioni:</span><span class="sxs-lookup"><span data-stu-id="c28be-150">If you decide to create a policy for managing application sharing traffic make these substitutions:</span></span>

  - <span data-ttu-id="c28be-151">Utilizzare un nome criterio diverso e univoco (ad esempio, **Condivisione applicazioni Lync Server**).</span><span class="sxs-lookup"><span data-stu-id="c28be-151">Use a different (and unique) policy name (for example, **Lync Server Application Sharing**).</span></span>

  - <span data-ttu-id="c28be-p112">Impostare il valore DSCP su **24** anziché su 46. Di nuovo, non è rilevante che questo valore sia 24, bensì è sufficiente che sia diverso dai valori utilizzati per l'audio e per il video.</span><span class="sxs-lookup"><span data-stu-id="c28be-p112">Set the DSCP value to **24** instead of 46. (Again, this value does not have to be 24; it simply must be different than the DSCP values used for audio and for video.)</span></span>

  - <span data-ttu-id="c28be-p113">Utilizzare l'intervallo di porte precedentemente configurato per il traffico video. Se ad esempio alla condivisione delle applicazioni sono state riservate le porte da 42000 a 42019, impostare l'intervallo di porte in questo modo: **42000:42019**.</span><span class="sxs-lookup"><span data-stu-id="c28be-p113">Use the previously-configured port range for video traffic. For example, if you have reserved ports 42000 through 42019 for application sharing, then set the port range to this: **42000:42019**.</span></span>

<span data-ttu-id="c28be-156">Per un criterio di trasferimento file:</span><span class="sxs-lookup"><span data-stu-id="c28be-156">For a file transfer policy:</span></span>

  - <span data-ttu-id="c28be-157">Utilizzare un nome criterio diverso e univoco (ad esempio, **Trasferimenti file di Lync Server**).</span><span class="sxs-lookup"><span data-stu-id="c28be-157">Use a different (and unique) policy name (for example, **Lync Server File Transfers**).</span></span>

  - <span data-ttu-id="c28be-p114">Impostare il valore DSCP su **14**. Di nuovo, non è rilevante che questo valore sia 14, bensì è sufficiente che sia un codice DSCP univoco.</span><span class="sxs-lookup"><span data-stu-id="c28be-p114">Set the DSCP value to **14**. (Again, this value does not have to be 14; it simply must be a unique DSCP code.)</span></span>

  - <span data-ttu-id="c28be-160">Utilizzare l'intervallo di porte configurata in precedenza per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c28be-160">Use the previously-configured port range for application.</span></span> <span data-ttu-id="c28be-161">Se ad esempio alla condivisione delle applicazioni sono state riservate le porte da 42020 a 42039, impostare l'intervallo di porte in questo modo: **42020:42039**.</span><span class="sxs-lookup"><span data-stu-id="c28be-161">For example, if you have reserved ports 42020 through 42039 for application sharing, then set the port range to this: **42020:42039**.</span></span>

<span data-ttu-id="c28be-p116">I nuovi criteri creati non saranno effettivi finché Criteri di gruppo non verrà aggiornato nei computer client. Benché Criteri di gruppo venga aggiornato automaticamente a intervalli regolari, è possibile effettuare un aggiornamento immediato eseguendo il comando seguente in ogni computer in cui è necessario aggiornare Criteri di gruppo:</span><span class="sxs-lookup"><span data-stu-id="c28be-p116">The new policies you have created will not take effect until Group Policy has been refreshed on your client computers. Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpudate.exe /force

<span data-ttu-id="c28be-p117">Questo comando può essere eseguito da qualsiasi finestra dei comandi eseguita con credenziali di amministratore. Per eseguire una finestra dei comandi con credenziali di amministratore, fare clic sul pulsante **Start**, fare clic con il pulsante destro del mouse su **Prompt dei comandi** e quindi scegliere **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="c28be-p117">This command can be run from any command window that is running under administrator credentials. To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

<span data-ttu-id="c28be-166">Tenere presente che questi criteri devono essere indirizzati verso i computer client.</span><span class="sxs-lookup"><span data-stu-id="c28be-166">Keep in mind that these policies should be targeted towards your client computers.</span></span> <span data-ttu-id="c28be-167">Non devono essere applicati ai server che eseguono Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c28be-167">They should not be applied to servers running Lync Server.</span></span>

<span data-ttu-id="c28be-168">Per assicurare che i pacchetti di rete siano contrassegnati con il valore DSCP appropriato, è consigliabile creare una nuova voce del Registro di sistema su ogni computer completando la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="c28be-168">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="c28be-169">Fare clic sul pulsante **Start**, quindi scegliere **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="c28be-169">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="c28be-170">Nella finestra di dialogo **Esegui** digitare **regedit** e quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="c28be-170">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="c28be-171">Nell'editor del registro di sistema **espandere \_ HKEY \_ computer locale**, espandere **System**, espandere **CurrentControlSet**, espandere **Servizi**e quindi espandere **Tcpip**.</span><span class="sxs-lookup"><span data-stu-id="c28be-171">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="c28be-p119">Fare clic con il pulsante destro **Tcpip**, scegliere **Nuovo** e quindi fare clic su **Chiave**. Dopo aver creato la nuova chiave del Registro di sistema, digitare **QoS** e quindi premere INVIO per rinominare la chiave.</span><span class="sxs-lookup"><span data-stu-id="c28be-p119">Right-click **Tcpip**, point to **New**, and then click **Key**. After the new registry key is created, type **QoS** and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="c28be-p120">Fare clic con il pulsante destro del mouse su **QoS**, scegliere **Nuovo** e quindi **Valore stringa**. Dopo aver creato il nuovo valore del Registro di sistema, digitare **Do not use NLA** e quindi premere INVIO per rinominare il valore.</span><span class="sxs-lookup"><span data-stu-id="c28be-p120">Right-click **QoS**, point to **New**, and then click **String Value**. After the new registry value is created, type **Do not use NLA** and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="c28be-p121">Fare doppio clic su **Do not use NLA**. Nella finestra di dialogo **Modifica stringa** digitare **1** nella casella **Dati valore** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="c28be-p121">Double-click **Do not use NLA**. In the **Edit String** dialog box, type **1** in the **Value data** box and then click **OK**.</span></span>

7.  <span data-ttu-id="c28be-178">Chiudere l'editor del Registro di sistema e quindi riavviare il computer.</span><span class="sxs-lookup"><span data-stu-id="c28be-178">Close the Registry Editor and then reboot your computer.</span></span>

<div>

## <a name="configuring-quality-of-service-on-computers-with-multiple-network-adapters"></a><span data-ttu-id="c28be-179">Configurazione della qualità del servizio in computer con più schede di rete</span><span class="sxs-lookup"><span data-stu-id="c28be-179">Configuring Quality of Service on Computers with Multiple Network Adapters</span></span>

<span data-ttu-id="c28be-p122">Se si dispone di un computer dotato di più schede di rete può verificarsi talvolta un problema per il quale i DSCP risultano avere valore 0x00 anziché il valore configurato. Questo solitamente si verifica nei computer in cui una o più schede di rete non sono in grado di accedere al dominio di Active Directory, come avviene ad esempio nel caso delle schede utilizzate per una rete privata. In questi casi i valori DSCP verranno assegnati alle schede che possono accedere al dominio, ma non alle altre.</span><span class="sxs-lookup"><span data-stu-id="c28be-p122">If you have a computer that has multiple network adapters you might occasionally run into issues where DSCP values are shown as 0x00 rather than the configured value. This will typically occur on computers where one or more of the network adapters are not able to access your Active Directory domain (for example, if these adapters are used for a private network). In cases like that, DSCP values will be tagged for the adapters that can access the domain, but will not be tagged for adapters that cannot access the domain.</span></span>

<span data-ttu-id="c28be-p123">Se si desidera che i valori DSCP vengano assegnati a tutte le schede di rete di un computer, comprese quelle che non hanno accesso al dominio, sarà necessario aggiungere un valore al Registro di sistema e configurarlo. A tale scopo, è possibile eseguire la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="c28be-p123">If you would like to tag DSCP values for all the network adapters in a computer, including adapters that do not have access to your domain, then you will need to add and configure a value to the registry. That can be done by completing the following procedure:</span></span>

1.  <span data-ttu-id="c28be-185">Fare clic sul pulsante **Start** e quindi scegliere **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="c28be-185">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="c28be-186">Nella finestra di dialogo **Esegui** digitare **regedit** e quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="c28be-186">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="c28be-187">Nell'editor del registro di sistema **espandere \_ HKEY \_ computer locale**, espandere **System**, espandere **CurrentControlSet**, espandere **Servizi**e quindi espandere **Tcpip**.</span><span class="sxs-lookup"><span data-stu-id="c28be-187">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="c28be-p124">Se non è presente una chiave del Registro di sistema denominata **QoS**, fare clic con il pulsante destro del mouse su **Tcpip**, scegliere **Nuovo** e quindi fare clic su **Chiave**. Dopo aver creato la nuova chiave, digitare **QoS** e quindi premere INVIO per rinominare la chiave.</span><span class="sxs-lookup"><span data-stu-id="c28be-p124">If you do not see a registry key labeled **QoS** then right-click **Tcpip**, point to **New**, and then click **Key**. After the new key is created, type **QoS** and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="c28be-p125">Fare clic con il pulsante destro del mouse su **QoS**, scegliere **Nuovo** e quindi **Valore stringa**. Dopo aver creato il nuovo valore del Registro di sistema, digitare **Do not use NLA** e quindi premere INVIO per rinominare il valore.</span><span class="sxs-lookup"><span data-stu-id="c28be-p125">Right-click **QoS**, point to **New**, and then click **String Value**. After the new registry value is created, type **Do not use NLA** and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="c28be-p126">Fare doppio clic su **Do not use NLA**. Nella finestra di dialogo **Modifica stringa** digitare **1** nella casella **Dati valore** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="c28be-p126">Double-click **Do not use NLA**. In the **Edit String** dialog box, type **1** in the **Value data** box and then click **OK**.</span></span>

<span data-ttu-id="c28be-194">Dopo aver creato e configurato il nuovo valore del Registro di sistema, sarà necessario riavviare il computer per rendere effettive le modifiche.</span><span class="sxs-lookup"><span data-stu-id="c28be-194">After creating and configuring the new registry value you will need to reboot your computer in order for the changes to take effect.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

