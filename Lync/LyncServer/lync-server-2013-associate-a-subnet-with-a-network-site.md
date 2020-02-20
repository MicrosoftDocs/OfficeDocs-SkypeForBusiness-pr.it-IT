---
title: 'Lync Server 2013: associare una subnet a un sito di rete'
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
ms.openlocfilehash: 419c88e32e3a0dd78fdc2503dcc2bb09b2c705ac
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149215"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="associate-a-subnet-with-a-network-site-in-lync-server-2013"></a><span data-ttu-id="15b76-102">Associare una subnet a un sito di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15b76-102">Associate a subnet with a network site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="15b76-103">_**Ultimo argomento modificato:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="15b76-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="15b76-104">Ogni subnet della rete deve essere associata a un sito di rete specifico, perché le informazioni sulla subnet vengono utilizzate per determinare il sito di rete in cui si trova un endpoint durante l'avvio di una nuova sessione.</span><span class="sxs-lookup"><span data-stu-id="15b76-104">Every subnet in your network must be associated with a specific network site, because subnet information is used to determine the network site on which an endpoint is located while a new session is initiated.</span></span> <span data-ttu-id="15b76-105">Quando la posizione di ogni parte di una sessione è nota, le funzionalità di VoIP aziendale avanzate possono applicare queste informazioni per determinare la modalità di gestione dell'installazione o del routing delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="15b76-105">When the location of each party in a session is known, advanced Enterprise Voice features can apply that information to determine how to handle the call setup or routing.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="15b76-106">Tutti gli indirizzi IP pubblici configurati per i server perimetrali audio/video nella distribuzione devono essere aggiunti alle impostazioni di configurazione di rete.</span><span class="sxs-lookup"><span data-stu-id="15b76-106">All configured public IP addresses of the Audio/Video Edge Servers in your deployment must be added to your network configuration settings.</span></span> <span data-ttu-id="15b76-107">Questi indirizzi IP vengono aggiunti come subnet con una maschera di 32.</span><span class="sxs-lookup"><span data-stu-id="15b76-107">These IP addresses are added as subnets with a mask of 32.</span></span> <span data-ttu-id="15b76-108">Il sito di rete associato deve corrispondere al sito di rete configurato appropriato.</span><span class="sxs-lookup"><span data-stu-id="15b76-108">The associated network site should correspond to the appropriate configured network site.</span></span> <span data-ttu-id="15b76-109">Ad esempio, l'indirizzo IP pubblico che corrisponde al server a/V Edge nel sito centrale Chicago sarebbe NetworkSiteID Chicago.</span><span class="sxs-lookup"><span data-stu-id="15b76-109">For example, the public IP address that corresponds to the A/V Edge Server in central site Chicago would be NetworkSiteID Chicago.</span></span> <span data-ttu-id="15b76-110">Per informazioni dettagliate sugli indirizzi IP pubblici, vedere <A href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">Determine External a/V firewall and Port requirements for Lync Server 2013</A> nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="15b76-110">For details about public IP addresses, see <A href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">Determine external A/V firewall and port requirements for Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="15b76-111">Viene generato un avviso Key Health Indicator (KHI) in cui viene specificato un elenco di indirizzi IP presenti nella rete che non sono associati a una subnet oppure la cui subnet non è associata a un sito di rete.</span><span class="sxs-lookup"><span data-stu-id="15b76-111">A Key Health Indicator (KHI) alert is raised, specifying a list of IP addresses that are present in your network but are either not associated with a subnet, or the subnet that includes the IP addresses is not associated with a network site.</span></span> <span data-ttu-id="15b76-112">Questo avviso non verrà generato più di una volta entro un periodo di 8 ore.</span><span class="sxs-lookup"><span data-stu-id="15b76-112">This alert will not be raised more than once within an 8-hour period.</span></span> <span data-ttu-id="15b76-113">Di seguito vengono riportati un esempio e le informazioni rilevanti dell'avviso:</span><span class="sxs-lookup"><span data-stu-id="15b76-113">The relevant alert information and an example are as follows:</span></span><BR><span data-ttu-id="15b76-114"><STRONG>Origine:</STRONG> Servizio criteri di larghezza di banda CS (Core)</span><span class="sxs-lookup"><span data-stu-id="15b76-114"><STRONG>Source:</STRONG> CS Bandwidth Policy Service (Core)</span></span><BR><span data-ttu-id="15b76-115"><STRONG>Numero evento:</STRONG> 36034</span><span class="sxs-lookup"><span data-stu-id="15b76-115"><STRONG>Event number:</STRONG> 36034</span></span><BR><span data-ttu-id="15b76-116"><STRONG>Livello:</STRONG> 2</span><span class="sxs-lookup"><span data-stu-id="15b76-116"><STRONG>Level:</STRONG> 2</span></span><BR><span data-ttu-id="15b76-117"><STRONG>Descrizione:</STRONG> Le subnet per gli indirizzi IP seguenti: &lt;elenco di indirizzi&gt; IP non sono configurati o le subnet non sono associate a un sito di rete.</span><span class="sxs-lookup"><span data-stu-id="15b76-117"><STRONG>Description:</STRONG> The subnets for the following IP addresses: &lt;List of IP Addresses&gt; are either not configured or the subnets are not associated to a Network Site.</span></span><BR><span data-ttu-id="15b76-118"><STRONG>Causa:</STRONG> Le subnet per gli indirizzi IP corrispondenti sono mancanti nelle impostazioni di configurazione di rete o le subnet non sono associate a un sito di rete.</span><span class="sxs-lookup"><span data-stu-id="15b76-118"><STRONG>Cause:</STRONG> The subnets for the corresponding IP addresses are missing from the network configuration settings or the subnets are not associated to a network site.</span></span><BR><span data-ttu-id="15b76-119"><STRONG>Soluzione:</STRONG> Aggiungere le subnet corrispondenti all'elenco di indirizzi IP nelle impostazioni di configurazione di rete e associare ogni subnet a un sito di rete.</span><span class="sxs-lookup"><span data-stu-id="15b76-119"><STRONG>Resolution:</STRONG> Add subnets corresponding to the list of IP addresses into the network configuration settings and associate every subnet to a network site.</span></span><BR><span data-ttu-id="15b76-120">Ad esempio, se l'elenco di indirizzi IP nell'avviso specifica 10.121.248.226 e 10.121.249.20, questi indirizzi IP non sono associati a una subnet o la subnet a cui sono associati non appartiene a un sito di rete.</span><span class="sxs-lookup"><span data-stu-id="15b76-120">For example, if the IP address list in the alert specifies 10.121.248.226 and 10.121.249.20, either these IP addresses are not associated with a subnet or the subnet they are associated with does not belong to a network site.</span></span> <span data-ttu-id="15b76-121">Se 10.121.248.0/24 e 10.121.249.0/24 sono le subnet corrispondenti per questi indirizzi, è possibile risolvere il problema in questo modo:</span><span class="sxs-lookup"><span data-stu-id="15b76-121">If 10.121.248.0/24 and 10.121.249.0/24 are the corresponding subnets for these addresses, you can resolve this issue as follows:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="15b76-122">Verificare che l'indirizzo IP 10.121.248.226 sia associato alla subnet 10.121.248.0/24 e che l'indirizzo IP 10.121.249.20 sia associato alla subnet 10.121.249.0/24.</span><span class="sxs-lookup"><span data-stu-id="15b76-122">Be sure that IP address 10.121.248.226 is associated with the 10.121.248.0/24 subnet and IP address 10.121.249.20 is associated with the 10.121.249.0/24 subnet.</span></span></P>
> <LI>
> <P><span data-ttu-id="15b76-123">Verificare che le subnet 10.121.248.0/24 e 10.121.249.0/24 siano associate ognuna a un sito di rete.</span><span class="sxs-lookup"><span data-stu-id="15b76-123">Be sure that the 10.121.248.0/24 and 10.121.249.0/24 subnets are each associated with a network site.</span></span></P></LI></OL>



</div>

<span data-ttu-id="15b76-124">Per informazioni dettagliate sull'utilizzo delle subnet di rete, vedere la documentazione di Lync Server Management Shell relativa ai cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="15b76-124">For details about working with network subnets, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="15b76-125">New-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="15b76-125">New-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)

  - [<span data-ttu-id="15b76-126">Get-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="15b76-126">Get-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)

  - [<span data-ttu-id="15b76-127">Set-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="15b76-127">Set-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)

  - [<span data-ttu-id="15b76-128">Remove-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="15b76-128">Remove-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)

<div>


> [!TIP]  
> <span data-ttu-id="15b76-129">Se si utilizza un numero elevato di subnet, è consigliabile utilizzare un file con valori delimitati da virgole (CSV) per associare le subnet ai siti.</span><span class="sxs-lookup"><span data-stu-id="15b76-129">If you are working with a large number of subnets, we recommend using a comma-separated values (CSV) file to associate the subnets to sites.</span></span> <span data-ttu-id="15b76-130">Il file CSV deve avere le quattro colonne seguenti: <STRONG>IPAddress</STRONG>, <STRONG>mask</STRONG>, <STRONG>Description</STRONG>, <STRONG>NetworkSiteID</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="15b76-130">The CSV file must have the following four columns: <STRONG>IPAddress</STRONG>, <STRONG>mask</STRONG>, <STRONG>description</STRONG>, <STRONG>NetworkSiteID</STRONG>.</span></span>



</div>

<div>

## <a name="to-associate-a-subnet-with-a-network-site-by-using-management-shell"></a><span data-ttu-id="15b76-131">Per associare una subnet a un sito di rete utilizzando Management Shell</span><span class="sxs-lookup"><span data-stu-id="15b76-131">To associate a subnet with a network site by using Management Shell</span></span>

1.  <span data-ttu-id="15b76-132">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="15b76-132">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="15b76-133">Eseguire il cmdlet **New-CsNetworkSubnet** per associare una subnet a un sito di rete:</span><span class="sxs-lookup"><span data-stu-id="15b76-133">Run the **New-CsNetworkSubnet** cmdlet to associate a subnet with a network site:</span></span>
    
        New-CsNetworkSubnet -SubnetID <String> -MaskBits <Int32> -NetworkSiteID <String>
    
    <span data-ttu-id="15b76-134">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="15b76-134">For example:</span></span>
    
        New-CsNetworkSubnet -SubnetID 172.11.12.13 - MaskBits 20 -NetworkSiteID Chicago
    
    <span data-ttu-id="15b76-135">In questo esempio viene creata un'associazione tra la subnet 172.11.12.13 e il sito di rete "Chicago".</span><span class="sxs-lookup"><span data-stu-id="15b76-135">In this example, you created an association between the subnet 172.11.12.13 and the network site “Chicago”.</span></span>

3.  <span data-ttu-id="15b76-136">Ripetere il passaggio 2 per tutte le subnet della topologia.</span><span class="sxs-lookup"><span data-stu-id="15b76-136">Repeat step 2 for all subnets in your topology.</span></span>

</div>

<div>

## <a name="to-associate-subnets-with-network-sites-by-importing-a-csv-file"></a><span data-ttu-id="15b76-137">Per associare subnet a siti di rete mediante l'importazione di un file CSV</span><span class="sxs-lookup"><span data-stu-id="15b76-137">To associate subnets with network sites by importing a CSV file</span></span>

1.  <span data-ttu-id="15b76-138">Creare un file CSV che includa tutte le subnet che si desidera aggiungere.</span><span class="sxs-lookup"><span data-stu-id="15b76-138">Create a CSV file that includes all of the subnets you want to add.</span></span> <span data-ttu-id="15b76-139">Ad esempio, creare un file denominato **subnet. csv** con il seguente contenuto:</span><span class="sxs-lookup"><span data-stu-id="15b76-139">For example, create a file named **subnet.csv** with the following content:</span></span>
    
    `IPAddress, mask, description, NetworkSiteID`
    
    `172.11.12.0, 24, "NA:Subnet in Portland", Portland`
    
    `172.11.13.0, 24, "NA:Subnet in Reno", Reno`
    
    `172.11.14.0, 25, "EMEA:Subnet in Warsaw", Warsaw`
    
    `172.11.15.0, 31, "EMEA:Subnet in Paris", Paris`

2.  <span data-ttu-id="15b76-140">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="15b76-140">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="15b76-141">Eseguire il cmdlet seguente per importare **subnet. csv**e quindi archiviarne il contenuto nell'archivio di gestione di Lync Server:</span><span class="sxs-lookup"><span data-stu-id="15b76-141">Run the following cmdlet to import **subnet.csv**, and then store its contents in the Lync Server management store:</span></span>
    
        import-csv subnet.csv | foreach {New-CSNCSSubnet  _.IPAddress -MaskBits $_.mask -Description $_.description -NetworkSiteID $_.NetworkSiteID}

</div>

<div>

## <a name="to-associate-a-subnet-with-a-network-site-by-using-lync-server-control-panel"></a><span data-ttu-id="15b76-142">Per associare una subnet a un sito di rete utilizzando il pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="15b76-142">To associate a subnet with a network site by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="15b76-143">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="15b76-143">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="15b76-144">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="15b76-144">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="15b76-145">Sulla barra di spostamento sinistra fare clic su **Configurazione di rete**.</span><span class="sxs-lookup"><span data-stu-id="15b76-145">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="15b76-146">Fare clic sul pulsante di spostamento della **subnet** .</span><span class="sxs-lookup"><span data-stu-id="15b76-146">Click the **Subnet** navigation button.</span></span>

4.  <span data-ttu-id="15b76-147">Fare clic su **Nuova regola**.</span><span class="sxs-lookup"><span data-stu-id="15b76-147">Click **New**.</span></span>

5.  <span data-ttu-id="15b76-148">Nella pagina **nuova subnet** fare clic su **ID Subnet**e quindi digitare il primo indirizzo nell'intervallo di indirizzi IP definito dalla subnet che si desidera associare a un sito di rete.</span><span class="sxs-lookup"><span data-stu-id="15b76-148">On the **New Subnet** page, click **Subnet ID**, and then type the first address in the IP address range defined by the subnet you want to associate with a network site.</span></span>

6.  <span data-ttu-id="15b76-149">Fare clic su **maschera**e quindi digitare la maschera di forma da applicare alla subnet.</span><span class="sxs-lookup"><span data-stu-id="15b76-149">Click **Mask**, and then type the bitmask to apply to the subnet.</span></span>

7.  <span data-ttu-id="15b76-150">Fare clic su **ID sito di rete**e quindi selezionare l'ID sito del sito a cui si sta aggiungendo la subnet.</span><span class="sxs-lookup"><span data-stu-id="15b76-150">Click **Network site ID**, and then select the site ID of the site to which you are adding this subnet.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="15b76-151">Se non sono ancora stati creati siti di rete, l'elenco sarà vuoto.</span><span class="sxs-lookup"><span data-stu-id="15b76-151">If you have not yet created network sites, this list will be empty.</span></span> <span data-ttu-id="15b76-152">Per informazioni dettagliate sulla procedura, vedere <A href="lync-server-2013-create-or-modify-a-network-site.md">creare o modificare un sito di rete in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="15b76-152">For details about the procedure, see <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or modify a network site in Lync Server 2013</A>.</span></span> <span data-ttu-id="15b76-153">È inoltre possibile recuperare gli ID di sito per la distribuzione eseguendo il cmdlet <STRONG>Get-CsNetworkSite</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="15b76-153">You can also retrieve site IDs for your deployment by running the <STRONG>Get-CsNetworkSite</STRONG> cmdlet.</span></span> <span data-ttu-id="15b76-154">Per informazioni dettagliate, vedere la documentazione relativa a Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="15b76-154">For details, see the Lync Server Management Shell documentation.</span></span>

    
    </div>

8.  <span data-ttu-id="15b76-155">Facoltativamente, fare clic su **Descrizione**e quindi digitare ulteriori informazioni per descrivere la subnet.</span><span class="sxs-lookup"><span data-stu-id="15b76-155">Optionally, click **Description**, and then type additional information to describe this subnet.</span></span>

9.  <span data-ttu-id="15b76-156">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="15b76-156">Click **Commit**.</span></span>

<span data-ttu-id="15b76-157">Ripetere questi passaggi per aggiungere altre subnet a un sito di rete.</span><span class="sxs-lookup"><span data-stu-id="15b76-157">Repeat these steps to add other subnets to a network site.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

