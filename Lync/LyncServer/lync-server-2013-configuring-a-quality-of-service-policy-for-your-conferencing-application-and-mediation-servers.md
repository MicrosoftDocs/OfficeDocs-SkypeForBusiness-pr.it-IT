---
title: "Lync Server 2013: configurazione dei criteri di qualità del servizio per le conferenze, l'applicazione e i Mediation Server"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a Quality of Service policy for your Conferencing, Application, and Mediation servers
ms:assetid: 8adcbbc5-c9f5-476d-ab7f-72e61859cacf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205076(v=OCS.15)
ms:contentKeyID: 48184769
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4711c618669a8fe47a877b4adeafe7759564855f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154308"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-a-quality-of-service-policy-in-lync-server-2013-for-your-conferencing-application-and-mediation-servers"></a><span data-ttu-id="20959-102">Configurazione dei criteri di qualità del servizio in Lync Server 2013 per i servizi di conferenza, applicazione e Mediation Server</span><span class="sxs-lookup"><span data-stu-id="20959-102">Configuring a Quality of Service policy in Lync Server 2013 for your Conferencing, Application, and Mediation servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="20959-103">_**Ultimo argomento modificato:** 2014-06-23_</span><span class="sxs-lookup"><span data-stu-id="20959-103">_**Topic Last Modified:** 2014-06-23_</span></span>

<span data-ttu-id="20959-p101">La configurazione degli intervalli di porte agevola l'uso di QoS (Quality of Service) assicurando che tutto il traffico di un tipo specificato (ad esempio, tutto il traffico audio) passi attraverso lo stesso set di porte. Ciò semplifica l'identificazione e il contrassegno di un determinato pacchetto da parte del sistema: se la porta 49152 è riservata per il traffico audio, qualsiasi attraversamento di pacchetto tramite la porta 49152 può essere contrassegnato con un codice DSCP indicante che si tratta di pacchetti audio. A sua volta, ciò consente ai router di identificare il pacchetto come pacchetto audio e assegnargli una priorità più elevata rispetto ai pacchetti non contrassegnati (ad esempio i pacchetti usati per copiare un file da un server all'altro).</span><span class="sxs-lookup"><span data-stu-id="20959-p101">Configuring port ranges facilitates the use of Quality of Service by ensuring that all traffic of a specified type (for example, all audio traffic) travels through the same set of ports. This makes it easy for the system to identify and mark a given packet: if port 49152 is reserved for audio traffic, then any packet traveling through port 49152 can be marked with a DSCP code that indicates that this is an audio packet. In turn, this enables routers to identify the packet as an audio packet, and give it higher priority than unmarked packets (such as packets used to copy a file from one server to another).</span></span>

<span data-ttu-id="20959-107">Tuttavia, limitando semplicemente un set di porte a un tipo di traffico specifico non si determina necessariamente l'assegnazione del codice DSCP appropriato ai pacchetti che le attraversano.</span><span class="sxs-lookup"><span data-stu-id="20959-107">However, simply restricting a set of ports to a specific type of traffic does not result in packets traveling through those ports being marked with the appropriate DSCP code.</span></span> <span data-ttu-id="20959-108">Oltre a definire gli intervalli di porte è anche necessario creare criteri QoS (Quality of Service) che specificano il codice DSCP da associare a ogni intervallo di porte.</span><span class="sxs-lookup"><span data-stu-id="20959-108">In addition to defining port ranges you must also create Quality of Service policies that specify the DSCP code to be associated with each port range.</span></span> <span data-ttu-id="20959-109">Per Microsoft Lync Server 2013 che in genere significa creare due criteri: uno per l'audio e uno per il video.</span><span class="sxs-lookup"><span data-stu-id="20959-109">For Microsoft Lync Server 2013 that typically means creating two policies: one for audio and one for video.</span></span>

<span data-ttu-id="20959-110">I criteri di qualità dei servizi vengono creati e gestiti in modo più semplice tramite criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="20959-110">Quality of Service policies are most-easily created, and managed, by using Group Policy.</span></span> <span data-ttu-id="20959-111">Gli stessi criteri possono essere creati anche utilizzando criteri di protezione locali.</span><span class="sxs-lookup"><span data-stu-id="20959-111">(These same policies can also be created by using local security policies.</span></span> <span data-ttu-id="20959-112">Tuttavia, è necessario ripetere la stessa procedura in tutti i computer. Il set iniziale di criteri QoS (uno per l'audio e uno per il video) deve essere applicato solo ai computer Lync Server che eseguono i servizi di conferenza server, server applicazioni e/o Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="20959-112">However, that requires you to repeat the same procedure on each and every computer.) Your initial set of QoS policies (one for audio and one for video) should be applied only to Lync Server computers running the Conferencing server, Application server, and/or Mediation server services.</span></span> <span data-ttu-id="20959-113">Se tutti questi computer si trovano nella stessa unità organizzativa di Active Directory, è sufficiente assegnare il nuovo oggetto Criteri di gruppo a quell'unità organizzativa.</span><span class="sxs-lookup"><span data-stu-id="20959-113">If all of these computers are located in the same Active Directory OU then you can simply assign the new Group Policy object (GPO) to that OU.</span></span> <span data-ttu-id="20959-114">In alternativa, è possibile eseguire altri passaggi per assegnare il nuovo criterio ai computer specificati. ad esempio, è possibile inserire i computer idonei in un gruppo di sicurezza, quindi utilizzare il filtro di sicurezza di criteri di gruppo per applicare l'oggetto Criteri di sistema solo a quel gruppo di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="20959-114">Alternatively, you can take other steps to target the new policy to the specified computers; for example, you can place the appropriate computers in a security group, then use Group Policy security filtering to apply the GPO just to that security group.</span></span>

<span data-ttu-id="20959-115">Per creare un criterio QoS (Quality of Service) per la gestione dell'audio, accedere a un computer in cui è installato Gestione Criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="20959-115">In order to create a Quality of Service policy for managing audio, log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="20959-116">Aprire Gestione Criteri di gruppo (fare clic su **Start**, scegliere **Strumenti di amministrazione** e fare clic su **Gestione Criteri di gruppo**) e quindi eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="20959-116">Open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**) and then complete the following procedure:</span></span>

1.  <span data-ttu-id="20959-p105">In Gestione Criteri di gruppo individuare il contenitore in cui creare il nuovo criterio. Ad esempio, se tutti i computer Lync Server si trovano in un'unità organizzativa denominata Lync Server, il nuovo criterio deve essere creato nell'unità organizzativa Lync Server.</span><span class="sxs-lookup"><span data-stu-id="20959-p105">In Group Policy Management, locate the container where the new policy should be created. For example, if all your Lync Server computers are located in an OU named Lync Server then the new policy should be created in the Lync Server OU.</span></span>

2.  <span data-ttu-id="20959-119">Fare clic con il pulsante destro del mouse sul contenitore appropriato e scegliere **Crea un oggetto Criteri di gruppo in questo dominio e crea qui un collegamento**.</span><span class="sxs-lookup"><span data-stu-id="20959-119">Right-click the appropriate container and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="20959-120">Nella finestra di dialogo **nuovo GPO** Digitare un nome per il nuovo oggetto Criteri di gruppo nella casella **nome** (ad esempio, **Lync Server QoS**) e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="20959-120">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box (for example, **Lync Server QoS**) and then click **OK**.</span></span>

4.  <span data-ttu-id="20959-121">Fare clic con il pulsante destro del mouse sul criterio appena creato e quindi scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="20959-121">Right-click the newly-created policy and then click **Edit**.</span></span>

5.  <span data-ttu-id="20959-122">Nell'Editor Gestione Criteri di gruppo espandere **Configurazione computer**, espandere **Criteri**, espandere **Impostazioni di Windows**, fare clic con il pulsante destro del mouse su **QoS basata su criteri** e quindi scegliere **Crea nuovo criterio**.</span><span class="sxs-lookup"><span data-stu-id="20959-122">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Policies**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

6.  <span data-ttu-id="20959-123">Nella pagina apertura della finestra di dialogo **QoS basata su criteri** Digitare un nome per il nuovo criterio (ad esempio, **Lync Server QoS**) nella casella **nome** .</span><span class="sxs-lookup"><span data-stu-id="20959-123">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy (e.g., **Lync Server QoS**) in the **Name** box.</span></span> <span data-ttu-id="20959-124">Selezionare **Specifica valore DSCP** e impostare il valore su **46**.</span><span class="sxs-lookup"><span data-stu-id="20959-124">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="20959-125">Lasciare non selezionata l'opzione **Specifica velocità in uscita**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="20959-125">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

7.  <span data-ttu-id="20959-p107">Nella pagina successiva, accertarsi che l'opzione **Tutte le applicazioni** sia selezionata e quindi fare clic su **Avanti**. In questo modo ci si assicura che tutte le applicazioni abbineranno i pacchetti dell'intervallo di porte specificato al codice DSCP specificato.</span><span class="sxs-lookup"><span data-stu-id="20959-p107">On the next page, make sure that **All applications** is selected and then click **Next**. This simply ensures that all applications will match packets from the specified port range with the specified DSCP code.</span></span>

8.  <span data-ttu-id="20959-p108">Nella terza pagina accertarsi che entrambe le opzioni **Qualsiasi indirizzo IP di origine e Qualsiasi indirizzo IP di destinazione** siano selezionate e quindi fare clic su **Avanti**. Queste due impostazioni assicurano che i pacchetti vengano gestiti indipendentemente dal computer (indirizzo IP) di provenienza e dal computer (indirizzo IP) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="20959-p108">On the third page, make sure that both **Any source IP address and Any destination IP address** are selected and then click **Next**. These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

9.  <span data-ttu-id="20959-130">Nella quarta pagina selezionare **TCP e UDP** dall'elenco a discesa **Seleziona il protocollo a cui si applica questo criterio QoS**.</span><span class="sxs-lookup"><span data-stu-id="20959-130">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="20959-131">TCP (Transmission Control Protocol) e UDP (User Datagram Protocol) sono i due protocolli di rete più comunemente utilizzati da Lync Server e dalle sue applicazioni client.</span><span class="sxs-lookup"><span data-stu-id="20959-131">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Lync Server and its client applications.</span></span>

10. <span data-ttu-id="20959-p110">Nel gruppo **Specifica il numero della porta di origine** selezionare **Da questa porta o intervallo di origine**. Nella casella di testo associata, digitare l'intervallo di porte riservato per le trasmissioni audio. Se ad esempio sono state riservate le porte da 49152 a 57500 per il traffico audio, immettere l'intervallo in questo formato **49152:57500**. Fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="20959-p110">Under the heading **Specify the source port number**, select **From this source port or range**. In the accompanying text box, type the port range reserved for audio transmissions. For example, if you reserved ports 49152 through ports 57500 for audio traffic enter the port range using this format: **49152:57500**. Click **Finish**.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="20959-p111">Il valore DSCP di 46 è in qualche modo arbitrario: sebbene il valore DSCP 46 sia spesso usato per contrassegnare i pacchetti audio, non è obbligatorio usarlo per le comunicazioni audio. Se si è già implementata la QoS e si usa un codice DSCP diverso per l'audio (ad esempio, DSCP 40) è necessario configurare il criterio Quality of Service per l'uso dello stesso codice (ovvero 40 per l'audio). Se si sta eseguendo una nuova implementazione della Quality of Service, è consigliabile usare il codice DSCP 46 per l'audio in quando si tratta del valore comunemente usato per contrassegnare i pacchetti audio.</span><span class="sxs-lookup"><span data-stu-id="20959-p111">The DSCP value of 46 is somewhat arbitrary: although DSCP 46 is often used for marking audio packets, you do not have to use DSCP 46 for audio communications. If you have already implemented QoS and you are using a different DSCP code for audio (for example, DSCP 40) then you should configure your Quality of Service policy to use that same code (i.e., 40 for audio). If you are just now implementing Quality of Service, then it is recommended that you use DSCP 46 for audio, simply because that value is commonly used to mark audio packets.</span></span>



</div>

<span data-ttu-id="20959-p112">Dopo aver creato il criterio QoS per il traffico audio, è necessario creare un secondo criterio per il traffico video (ed eventualmente un terzo criterio per la gestione del traffico di condivisione delle applicazioni). Per creare un criterio per il traffico video, seguire la stessa procedura di base usata per la creazione del criterio audio, con le distinzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="20959-p112">After you have created the QoS policy for audio traffic you should then create a second policy for video traffic (and, optionally, a third policy for managing application sharing traffic). To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="20959-141">Usare un nome diverso (e univoco) per il criterio (ad esempio, **Lync Server Video**).</span><span class="sxs-lookup"><span data-stu-id="20959-141">Use a different (and unique) policy name (for example, **Lync Server Video**).</span></span>

  - <span data-ttu-id="20959-p113">Impostare il valore DSCP su **34** invece di 46. Si noti che non è obbligatorio usare il valore DSCP 34. L'unico requisito consiste nell'usare un valore DSCP diverso da quello usato per l'audio.</span><span class="sxs-lookup"><span data-stu-id="20959-p113">Set the DSCP value to **34** instead of 46. (Note that you do not have to use a DSCP value of 34. The only requirement is that you use a different DSCP value for video than you used for audio.)</span></span>

  - <span data-ttu-id="20959-p114">Usare l'intervallo di porte configurato in precedenza per il traffico video. Se ad esempio, sono state riservate le porte da 57501 a 65535 per i contenuti video, impostare l'intervallo di porte su: **57501:65535**.</span><span class="sxs-lookup"><span data-stu-id="20959-p114">Use the previously-configured port range for video traffic. For example, if you have reserved ports 57501 through 65535 for video, then set the port range to this: **57501:65535**.</span></span>

<span data-ttu-id="20959-147">Se si decide di creare un criterio per gestire il traffico di condivisione delle applicazioni, è necessario creare un terzo criterio con le distinzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="20959-147">If you decide to create a policy for managing application sharing traffic you must create a third policy, making the following substitutions:</span></span>

  - <span data-ttu-id="20959-148">Usare un nome diverso (e univoco) per il criterio (ad esempio, **Lync Server Application Sharing**).</span><span class="sxs-lookup"><span data-stu-id="20959-148">Use a different (and unique) policy name (for example, **Lync Server Application Sharing**).</span></span>

  - <span data-ttu-id="20959-p115">Impostare il valore DSCP su **24** invece di 46. Come indicato prima, non è obbligatorio usare il valore DSCP 24. L'unico requisito consiste nell'usare un valore DSCP diverso da quello usato per l'audio.</span><span class="sxs-lookup"><span data-stu-id="20959-p115">Set the DSCP value to **24** instead of 46. (Again, you do not have to use a DSCP value of 24. The only requirement is that you use a different DSCP value for application sharing than you used for audio or for video.)</span></span>

  - <span data-ttu-id="20959-p116">Usare l'intervallo di porte configurato in precedenza per il traffico video. Se ad esempio sono state riservate le porte da 40803 a 49151 per il video, impostare l'intervallo di porte su: **40803:49151**.</span><span class="sxs-lookup"><span data-stu-id="20959-p116">Use the previously-configured port range for video traffic. For example, if you have reserved ports 40803 through 49151 for application sharing, then set the port range to this: **40803:49151**.</span></span>

<span data-ttu-id="20959-154">I nuovi criteri creati non avranno effetto finché i criteri di gruppo non sono stati aggiornati nei computer di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="20959-154">The new policies you have created will not take effect until Group Policy has been refreshed on your Lync Server computers.</span></span> <span data-ttu-id="20959-155">Sebbene l'aggiornamento di Criteri di gruppo venga eseguito automaticamente periodicamente, è possibile imporre l'aggiornamento immediato eseguendo il comando seguente su ogni computer in cui è necessario:</span><span class="sxs-lookup"><span data-stu-id="20959-155">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpupdate.exe /force

<span data-ttu-id="20959-156">Questo comando può essere eseguito dall'interno di Lync Server Management Shell o da qualsiasi finestra di comando in esecuzione con le credenziali di amministratore.</span><span class="sxs-lookup"><span data-stu-id="20959-156">This command can be run from within the Lync Server Management Shell or from any command window that is running under administrator credentials.</span></span> <span data-ttu-id="20959-157">Per eseguire una finestra di comando con credenziali di amministratore, fare clic sul pulsante **Start**, fare clic con il pulsante destro del mouse su **Prompt dei comandi** e quindi scegliere **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="20959-157">To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

<span data-ttu-id="20959-158">Per verificare che i criteri QoS siano stati applicati, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="20959-158">To verify that the new QoS policies have been applied, do the following:</span></span>

1.  <span data-ttu-id="20959-159">In un computer Lync Server fare clic sul pulsante **Start** e quindi su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="20959-159">On a Lync Server computer, click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="20959-160">Nella finestra di dialogo **Esegui** digitare **regedit** e quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="20959-160">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="20959-161">In Editor del registro di sistema espandere **computer**, espandere **HKEY\_\_**, espandere **software**, espandere **criteri**, espandere **Microsoft**, espandere **Windows**e quindi fare clic su **QoS**.</span><span class="sxs-lookup"><span data-stu-id="20959-161">In Registry Editor, expand **Computer**, expand **HKEY\_LOCAL\_MACHINE**, expand **SOFTWARE**, expand **Policies**, expand **Microsoft**, expand **Windows**, and then click **QoS**.</span></span> <span data-ttu-id="20959-162">In **QoS** dovrebbero essere presenti le chiavi del Registro di sistema per ognuno dei Criteri QoS creati.</span><span class="sxs-lookup"><span data-stu-id="20959-162">Under **QoS** you should see registry keys for each of the QoS policies you just created.</span></span> <span data-ttu-id="20959-163">Ad esempio, se sono stati creati due nuovi criteri (uno denominato Lync Server audio QoS e un altro QoS denominato Lync Server video), è consigliabile utilizzare le voci del registro di sistema per Lync Server audio QoS e Lync Server video QoS.</span><span class="sxs-lookup"><span data-stu-id="20959-163">For example, if you created two new policies (one named Lync Server Audio QoS and the other named Lync Server Video QoS) you should registry entries for Lync Server Audio QoS and Lync Server Video QoS.</span></span>

<span data-ttu-id="20959-164">Per assicurare che i pacchetti di rete siano contrassegnati con il valore DSCP appropriato, è consigliabile creare una nuova voce del Registro di sistema su ogni computer completando la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="20959-164">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="20959-165">Fare clic sul pulsante **Start**, quindi scegliere **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="20959-165">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="20959-166">Nella finestra di dialogo **Esegui** digitare **regedit**, quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="20959-166">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="20959-167">Nell'editor del registro di sistema **espandere\_HKEY\_computer locale**, espandere **System**, espandere **CurrentControlSet**, espandere **Servizi**e quindi espandere **Tcpip**.</span><span class="sxs-lookup"><span data-stu-id="20959-167">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="20959-p120">Fare clic con il pulsante destro **Tcpip**, scegliere **Nuovo** e quindi fare clic su **Chiave**. Dopo aver creato la nuova chiave del Registro di sistema, digitare **QoS** e quindi premere INVIO per rinominare la chiave.</span><span class="sxs-lookup"><span data-stu-id="20959-p120">Right-click **Tcpip**, point to **New**, and then click **Key**. After the new registry key is created, type **QoS** and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="20959-p121">Fare clic con il pulsante destro del mouse su **QoS**, scegliere **Nuovo** e quindi **Valore stringa**. Dopo aver creato il nuovo valore del Registro di sistema, digitare **Do not use NLA** e quindi premere INVIO per rinominare il valore.</span><span class="sxs-lookup"><span data-stu-id="20959-p121">Right-click **QoS**, point to **New**, and then click **String Value**. After the new registry value is created, type **Do not use NLA** and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="20959-p122">Fare doppio clic su **Do not use NLA**. Nella finestra di dialogo **Modifica stringa** digitare **1** nella casella **Dati valore** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="20959-p122">Double-click **Do not use NLA**. In the **Edit String** dialog box, type **1** in the **Value data** box and then click **OK**.</span></span>

7.  <span data-ttu-id="20959-174">Chiudere l'editor del Registro di sistema e riavviare il computer.</span><span class="sxs-lookup"><span data-stu-id="20959-174">Close the Registry Editor and then reboot your computer.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

