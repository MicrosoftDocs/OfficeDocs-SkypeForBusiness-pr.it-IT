---
title: 'Lync Server 2013: Associare una subnet a un sito di rete'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Associate a subnet with a network site
ms:assetid: aa69e3ac-542a-4ba1-9582-2e6bee29f633
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412804(v=OCS.15)
ms:contentKeyID: 48185043
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f54ba8be2be6ae042633e519c5d7d27bde834162
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722806"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="associate-a-subnet-with-a-network-site-in-lync-server-2013"></a><span data-ttu-id="b67ea-102">Associare una subnet a un sito di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b67ea-102">Associate a subnet with a network site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b67ea-103">_**Argomento Ultima modifica:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="b67ea-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="b67ea-104">Ogni subnet della rete deve essere associata a un sito di rete specifico, poiché le informazioni di subnet vengono usate per determinare il sito di rete in cui si trova un endpoint mentre viene avviata una nuova sessione.</span><span class="sxs-lookup"><span data-stu-id="b67ea-104">Every subnet in your network must be associated with a specific network site, because subnet information is used to determine the network site on which an endpoint is located while a new session is initiated.</span></span> <span data-ttu-id="b67ea-105">Quando si conosce la posizione di ogni parte di una sessione, le funzionalità vocali avanzate di Enterprise possono applicare tali informazioni per determinare come gestire la configurazione o il routing delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="b67ea-105">When the location of each party in a session is known, advanced Enterprise Voice features can apply that information to determine how to handle the call setup or routing.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b67ea-106">Tutti gli indirizzi IP pubblici configurati per i server Edge audio/video nella distribuzione devono essere aggiunti alle impostazioni di configurazione della rete.</span><span class="sxs-lookup"><span data-stu-id="b67ea-106">All configured public IP addresses of the Audio/Video Edge Servers in your deployment must be added to your network configuration settings.</span></span> <span data-ttu-id="b67ea-107">Questi indirizzi IP vengono aggiunti come subnet con una maschera di 32.</span><span class="sxs-lookup"><span data-stu-id="b67ea-107">These IP addresses are added as subnets with a mask of 32.</span></span> <span data-ttu-id="b67ea-108">Il sito di rete associato deve corrispondere al sito di rete configurato appropriato.</span><span class="sxs-lookup"><span data-stu-id="b67ea-108">The associated network site should correspond to the appropriate configured network site.</span></span> <span data-ttu-id="b67ea-109">Ad esempio, l'indirizzo IP pubblico che corrisponde all'a/V Edge Server nel sito centrale di Chicago sarebbe NetworkSiteID Chicago.</span><span class="sxs-lookup"><span data-stu-id="b67ea-109">For example, the public IP address that corresponds to the A/V Edge Server in central site Chicago would be NetworkSiteID Chicago.</span></span> <span data-ttu-id="b67ea-110">Per informazioni dettagliate sugli indirizzi IP pubblici, vedere <A href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">determinare i requisiti per il firewall e la porta a/V esterni per Lync Server 2013</A> nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="b67ea-110">For details about public IP addresses, see <A href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">Determine external A/V firewall and port requirements for Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="b67ea-111">Viene generato un avviso KHI (Key Health Indicator), che specifica un elenco di indirizzi IP presenti nella rete, ma che non sono associati a una subnet oppure che la subnet che include gli indirizzi IP non è associata a un sito di rete.</span><span class="sxs-lookup"><span data-stu-id="b67ea-111">A Key Health Indicator (KHI) alert is raised, specifying a list of IP addresses that are present in your network but are either not associated with a subnet, or the subnet that includes the IP addresses is not associated with a network site.</span></span> <span data-ttu-id="b67ea-112">Questo avviso non verrà generato più di una volta all'interno di un periodo di 8 ore.</span><span class="sxs-lookup"><span data-stu-id="b67ea-112">This alert will not be raised more than once within an 8-hour period.</span></span> <span data-ttu-id="b67ea-113">Di seguito sono riportate le informazioni relative agli avvisi e un esempio:</span><span class="sxs-lookup"><span data-stu-id="b67ea-113">The relevant alert information and an example are as follows:</span></span><BR><span data-ttu-id="b67ea-114"><STRONG>Origine:</STRONG> Servizio di criteri di larghezza di banda CS (Core)</span><span class="sxs-lookup"><span data-stu-id="b67ea-114"><STRONG>Source:</STRONG> CS Bandwidth Policy Service (Core)</span></span><BR><span data-ttu-id="b67ea-115"><STRONG>Numero evento:</STRONG> 36034</span><span class="sxs-lookup"><span data-stu-id="b67ea-115"><STRONG>Event number:</STRONG> 36034</span></span><BR><span data-ttu-id="b67ea-116"><STRONG>Livello:</STRONG> 2</span><span class="sxs-lookup"><span data-stu-id="b67ea-116"><STRONG>Level:</STRONG> 2</span></span><BR><span data-ttu-id="b67ea-117"><STRONG>Descrizione:</STRONG> Le subnet per gli indirizzi IP seguenti: &lt;l'elenco di indirizzi&gt; IP non è configurato o le subnet non sono associate a un sito di rete.</span><span class="sxs-lookup"><span data-stu-id="b67ea-117"><STRONG>Description:</STRONG> The subnets for the following IP addresses: &lt;List of IP Addresses&gt; are either not configured or the subnets are not associated to a Network Site.</span></span><BR><span data-ttu-id="b67ea-118"><STRONG>Causa:</STRONG> Le subnet per gli indirizzi IP corrispondenti sono mancanti nelle impostazioni di configurazione della rete o le subnet non sono associate a un sito di rete.</span><span class="sxs-lookup"><span data-stu-id="b67ea-118"><STRONG>Cause:</STRONG> The subnets for the corresponding IP addresses are missing from the network configuration settings or the subnets are not associated to a network site.</span></span><BR><span data-ttu-id="b67ea-119"><STRONG>Risoluzione:</STRONG> Aggiungere subnet che corrispondono all'elenco di indirizzi IP nelle impostazioni di configurazione della rete e associare ogni subnet a un sito di rete.</span><span class="sxs-lookup"><span data-stu-id="b67ea-119"><STRONG>Resolution:</STRONG> Add subnets corresponding to the list of IP addresses into the network configuration settings and associate every subnet to a network site.</span></span><BR><span data-ttu-id="b67ea-120">Ad esempio, se l'elenco di indirizzi IP nell'avviso specifica 10.121.248.226 e 10.121.249.20, questi indirizzi IP non sono associati a una subnet o la subnet a cui sono associati non appartiene a un sito di rete.</span><span class="sxs-lookup"><span data-stu-id="b67ea-120">For example, if the IP address list in the alert specifies 10.121.248.226 and 10.121.249.20, either these IP addresses are not associated with a subnet or the subnet they are associated with does not belong to a network site.</span></span> <span data-ttu-id="b67ea-121">Se 10.121.248.0/24 e 10.121.249.0/24 sono le subnet corrispondenti per questi indirizzi, è possibile risolvere il problema come segue:</span><span class="sxs-lookup"><span data-stu-id="b67ea-121">If 10.121.248.0/24 and 10.121.249.0/24 are the corresponding subnets for these addresses, you can resolve this issue as follows:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="b67ea-122">Assicurarsi che l'indirizzo IP 10.121.248.226 sia associato alla subnet 10.121.248.0/24 e l'indirizzo IP 10.121.249.20 sia associato alla subnet 10.121.249.0/24.</span><span class="sxs-lookup"><span data-stu-id="b67ea-122">Be sure that IP address 10.121.248.226 is associated with the 10.121.248.0/24 subnet and IP address 10.121.249.20 is associated with the 10.121.249.0/24 subnet.</span></span></P>
> <LI>
> <P><span data-ttu-id="b67ea-123">Assicurarsi che le subnet 10.121.248.0/24 e 10.121.249.0/24 siano associate a un sito di rete.</span><span class="sxs-lookup"><span data-stu-id="b67ea-123">Be sure that the 10.121.248.0/24 and 10.121.249.0/24 subnets are each associated with a network site.</span></span></P></LI></OL>



</div>

<span data-ttu-id="b67ea-124">Per informazioni dettagliate sull'uso delle subnet di rete, vedere la documentazione di Lync Server Management Shell per i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="b67ea-124">For details about working with network subnets, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="b67ea-125">New-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="b67ea-125">New-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)

  - [<span data-ttu-id="b67ea-126">Get-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="b67ea-126">Get-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)

  - [<span data-ttu-id="b67ea-127">Set-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="b67ea-127">Set-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)

  - [<span data-ttu-id="b67ea-128">Remove-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="b67ea-128">Remove-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)

<div>


> [!TIP]  
> <span data-ttu-id="b67ea-129">Se si usa un numero elevato di subnet, è consigliabile usare un file con valori delimitati da virgole (CSV) per associare le subnet ai siti.</span><span class="sxs-lookup"><span data-stu-id="b67ea-129">If you are working with a large number of subnets, we recommend using a comma-separated values (CSV) file to associate the subnets to sites.</span></span> <span data-ttu-id="b67ea-130">Il file CSV deve avere le quattro colonne seguenti: <STRONG>IPAddress</STRONG>, <STRONG>mask</STRONG>, <STRONG>Description</STRONG>, <STRONG>NetworkSiteID</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="b67ea-130">The CSV file must have the following four columns: <STRONG>IPAddress</STRONG>, <STRONG>mask</STRONG>, <STRONG>description</STRONG>, <STRONG>NetworkSiteID</STRONG>.</span></span>



</div>

<div>

## <a name="to-associate-a-subnet-with-a-network-site-by-using-management-shell"></a><span data-ttu-id="b67ea-131">Per associare una subnet a un sito di rete tramite Management Shell</span><span class="sxs-lookup"><span data-stu-id="b67ea-131">To associate a subnet with a network site by using Management Shell</span></span>

1.  <span data-ttu-id="b67ea-132">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="b67ea-132">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="b67ea-133">Eseguire il cmdlet **New-CsNetworkSubnet** per associare una subnet a un sito di rete:</span><span class="sxs-lookup"><span data-stu-id="b67ea-133">Run the **New-CsNetworkSubnet** cmdlet to associate a subnet with a network site:</span></span>
    
        New-CsNetworkSubnet -SubnetID <String> -MaskBits <Int32> -NetworkSiteID <String>
    
    <span data-ttu-id="b67ea-134">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="b67ea-134">For example:</span></span>
    
        New-CsNetworkSubnet -SubnetID 172.11.12.13 - MaskBits 20 -NetworkSiteID Chicago
    
    <span data-ttu-id="b67ea-135">In questo esempio è stata creata un'associazione tra la subnet 172.11.12.13 e il sito di rete "Chicago".</span><span class="sxs-lookup"><span data-stu-id="b67ea-135">In this example, you created an association between the subnet 172.11.12.13 and the network site “Chicago”.</span></span>

3.  <span data-ttu-id="b67ea-136">Ripetere il passaggio 2 per tutte le subnet della topologia.</span><span class="sxs-lookup"><span data-stu-id="b67ea-136">Repeat step 2 for all subnets in your topology.</span></span>

</div>

<div>

## <a name="to-associate-subnets-with-network-sites-by-importing-a-csv-file"></a><span data-ttu-id="b67ea-137">Per associare subnet a siti di rete mediante l'importazione di un file CSV</span><span class="sxs-lookup"><span data-stu-id="b67ea-137">To associate subnets with network sites by importing a CSV file</span></span>

1.  <span data-ttu-id="b67ea-138">Creare un file CSV che includa tutte le subnet che si desidera aggiungere.</span><span class="sxs-lookup"><span data-stu-id="b67ea-138">Create a CSV file that includes all of the subnets you want to add.</span></span> <span data-ttu-id="b67ea-139">Ad esempio, crea un file denominato **subnet. csv** con il contenuto seguente:</span><span class="sxs-lookup"><span data-stu-id="b67ea-139">For example, create a file named **subnet.csv** with the following content:</span></span>
    
    `IPAddress, mask, description, NetworkSiteID`
    
    `172.11.12.0, 24, "NA:Subnet in Portland", Portland`
    
    `172.11.13.0, 24, "NA:Subnet in Reno", Reno`
    
    `172.11.14.0, 25, "EMEA:Subnet in Warsaw", Warsaw`
    
    `172.11.15.0, 31, "EMEA:Subnet in Paris", Paris`

2.  <span data-ttu-id="b67ea-140">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="b67ea-140">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="b67ea-141">Eseguire il cmdlet seguente per importare **subnet. csv**e quindi archiviarne il contenuto in Lync Server Management store:</span><span class="sxs-lookup"><span data-stu-id="b67ea-141">Run the following cmdlet to import **subnet.csv**, and then store its contents in the Lync Server management store:</span></span>
    
        import-csv subnet.csv | foreach {New-CSNCSSubnet  _.IPAddress -MaskBits $_.mask -Description $_.description -NetworkSiteID $_.NetworkSiteID}

</div>

<div>

## <a name="to-associate-a-subnet-with-a-network-site-by-using-lync-server-control-panel"></a><span data-ttu-id="b67ea-142">Per associare una subnet a un sito di rete tramite il pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="b67ea-142">To associate a subnet with a network site by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="b67ea-143">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b67ea-143">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b67ea-144">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b67ea-144">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="b67ea-145">Sulla barra di spostamento sinistra fare clic su **configurazione di rete**.</span><span class="sxs-lookup"><span data-stu-id="b67ea-145">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="b67ea-146">Fare clic sul pulsante di spostamento **subnet** .</span><span class="sxs-lookup"><span data-stu-id="b67ea-146">Click the **Subnet** navigation button.</span></span>

4.  <span data-ttu-id="b67ea-147">Fare clic su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="b67ea-147">Click **New**.</span></span>

5.  <span data-ttu-id="b67ea-148">Nella pagina **nuova subnet** fare clic su **ID Subnet**e quindi digitare il primo indirizzo nell'intervallo di indirizzi IP definito dalla subnet che si vuole associare a un sito di rete.</span><span class="sxs-lookup"><span data-stu-id="b67ea-148">On the **New Subnet** page, click **Subnet ID**, and then type the first address in the IP address range defined by the subnet you want to associate with a network site.</span></span>

6.  <span data-ttu-id="b67ea-149">Fare clic su **maschera**e quindi digitare la maschera di forma da applicare alla subnet.</span><span class="sxs-lookup"><span data-stu-id="b67ea-149">Click **Mask**, and then type the bitmask to apply to the subnet.</span></span>

7.  <span data-ttu-id="b67ea-150">Fare clic su **ID sito di rete**e quindi selezionare l'ID sito del sito a cui si sta aggiungendo la subnet.</span><span class="sxs-lookup"><span data-stu-id="b67ea-150">Click **Network site ID**, and then select the site ID of the site to which you are adding this subnet.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b67ea-151">Se non sono ancora stati creati siti di rete, l'elenco sarà vuoto.</span><span class="sxs-lookup"><span data-stu-id="b67ea-151">If you have not yet created network sites, this list will be empty.</span></span> <span data-ttu-id="b67ea-152">Per informazioni dettagliate sulla procedura, vedere <A href="lync-server-2013-create-or-modify-a-network-site.md">creare o modificare un sito di rete in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="b67ea-152">For details about the procedure, see <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or modify a network site in Lync Server 2013</A>.</span></span> <span data-ttu-id="b67ea-153">È anche possibile recuperare gli ID sito per la distribuzione eseguendo il cmdlet <STRONG>Get-CsNetworkSite</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="b67ea-153">You can also retrieve site IDs for your deployment by running the <STRONG>Get-CsNetworkSite</STRONG> cmdlet.</span></span> <span data-ttu-id="b67ea-154">Per informazioni dettagliate, vedere la documentazione di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="b67ea-154">For details, see the Lync Server Management Shell documentation.</span></span>

    
    </div>

8.  <span data-ttu-id="b67ea-155">Facoltativamente, fare clic su **Descrizione**e quindi digitare altre informazioni per descrivere la subnet.</span><span class="sxs-lookup"><span data-stu-id="b67ea-155">Optionally, click **Description**, and then type additional information to describe this subnet.</span></span>

9.  <span data-ttu-id="b67ea-156">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="b67ea-156">Click **Commit**.</span></span>

<span data-ttu-id="b67ea-157">Ripetere questi passaggi per aggiungere altre subnet a un sito di rete.</span><span class="sxs-lookup"><span data-stu-id="b67ea-157">Repeat these steps to add other subnets to a network site.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

