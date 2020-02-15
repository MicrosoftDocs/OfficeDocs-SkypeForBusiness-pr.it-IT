---
title: Distribuzione di una porta non standard e di un alias di SQL Server in Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying a SQL Server nonstandard port and alias in Lync Server 2013
ms:assetid: 2da92c1f-250e-407a-8651-fb2aec76aeb0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn776290(v=OCS.15)
ms:contentKeyID: 62634609
ms.date: 09/17/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ef6082c4d2df6936557cf6f6c82a1d495888f55
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006422"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-a-sql-server-nonstandard-port-and-alias-in-lync-server-2013"></a><span data-ttu-id="73b88-102">Distribuzione di una porta non standard e di un alias di SQL Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="73b88-102">Deploying a SQL Server nonstandard port and alias in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="73b88-103">_**Ultimo argomento modificato:** 2015-09-16_</span><span class="sxs-lookup"><span data-stu-id="73b88-103">_**Topic Last Modified:** 2015-09-16_</span></span>

<span data-ttu-id="73b88-104">Microsoft Lync Server 2013 supporta l'utilizzo di una porta non standard e di un alias in SQL Server.</span><span class="sxs-lookup"><span data-stu-id="73b88-104">Microsoft Lync Server 2013 supports using a non-standard port and alias in SQL Server.</span></span> <span data-ttu-id="73b88-105">L'utilizzo di una porta non standard di SQL Server e di un alias aumenta la sicurezza e crea un ambiente più flessibile per la distribuzione di Lync.</span><span class="sxs-lookup"><span data-stu-id="73b88-105">Using a SQL Server non-standard port and an alias increases security and creates a more flexible environment for the Lync deployment.</span></span> <span data-ttu-id="73b88-106">Questi passaggi sono solo un singolo passaggio per garantire il corretto funzionamento dell'ambiente Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="73b88-106">These steps are only a single step in properly securing your Lync Server 2013 environment.</span></span> <span data-ttu-id="73b88-107">È necessario eseguire ulteriori operazioni per ridurre la superficie di attacco di un'implementazione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="73b88-107">Additional steps should be taken to reduce the attack surface of a Lync Server 2013 implementation.</span></span>

<span data-ttu-id="73b88-108">Nell'articolo seguente vengono descritti i passaggi necessari per configurare una porta non standard e un alias di SQL Server in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="73b88-108">The following article describes the steps required to setup a SQL Server non-standard port and alias in Lync Server 2013.</span></span>

<div>

## <a name="deploying-a-sql-server-non-standard-port-and-alias-in-lync-server-2013"></a><span data-ttu-id="73b88-109">Distribuzione di una porta non standard e di un alias di SQL Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="73b88-109">Deploying a SQL Server Non-Standard Port and Alias in Lync Server 2013</span></span>

<span data-ttu-id="73b88-110">Il generatore di topologie di Lync Server 2013 supporta l'utilizzo di un alias di SQL Server come nome di dominio completo (FQDN) anziché come FQDN effettivo di SQL Server durante la configurazione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="73b88-110">Lync Server 2013 Topology Builder supports using a SQL Server alias as the Fully Qualified Domain Name (FQDN) instead of the actual SQL Server FQDN when configuring Lync Server 2013.</span></span> <span data-ttu-id="73b88-111">In questo modo il nome FQDN effettivo di SQL Server deve essere nascosto da qualsiasi utente malintenzionato.</span><span class="sxs-lookup"><span data-stu-id="73b88-111">This allows the actual SQL Server FQDN to be hidden from any malicious attacker.</span></span> <span data-ttu-id="73b88-112">Inoltre, l'utilizzo di una porta non standard nasconde la porta effettiva da qualsiasi utente malintenzionato che tenta di attaccare il database sulla porta standard 1433, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="73b88-112">In addition, using a non-standard port obscures the actual port from any would be attacker attempting to attack the database on the standard port 1433, as shown in the following figure.</span></span>

<span data-ttu-id="73b88-113">![Un hacker non conosce il numero di porta da attaccare.](images/Dn776290.2f3923e0-2bdc-416b-a66b-bf56599eb14e(OCS.15).jpg "Un hacker non conosce il numero di porta da attaccare.")</span><span class="sxs-lookup"><span data-stu-id="73b88-113">![A hacker doesn't know the port number to attack.](images/Dn776290.2f3923e0-2bdc-416b-a66b-bf56599eb14e(OCS.15).jpg "A hacker doesn't know the port number to attack.")</span></span>

<span data-ttu-id="73b88-114">Per avere esito positivo nel determinare la porta che Lync Server 2013 utilizza per comunicare con SQL Server, l'utente malintenzionato dovrà analizzare tutte le porte per ottenere le informazioni sulla porta.</span><span class="sxs-lookup"><span data-stu-id="73b88-114">In order to be successful in determining the port Lync Server 2013 is using to communicate with SQL Server, the attacker would need to scan all ports to obtain the port information.</span></span> <span data-ttu-id="73b88-115">L'analisi di una porta eseguita da un utente malintenzionato aumenta le possibilità che la sicurezza possa rilevare e arrestare l'istruzione.</span><span class="sxs-lookup"><span data-stu-id="73b88-115">A port scan by an attacker increases the chances that security can detect and stop the instruction.</span></span> <span data-ttu-id="73b88-116">Oltre ad aggiungere maggiore sicurezza con una porta non standard, è anche possibile utilizzare un alias di SQL Server per fornire flessibilità per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="73b88-116">In addition to adding increased security with a non-standard port, you can also use a SQL Server alias to provide flexibility for the deployment.</span></span> <span data-ttu-id="73b88-117">Ciò è utile per ridurre le modifiche apportate alla configurazione in situazioni in cui è necessaria una modifica del nome di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="73b88-117">This is valuable in order to reduce configuration changes in situations where a SQL Server name change is required.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="73b88-118">In SQL Server sono disponibili due metodi di tolleranza di errore (clustering di failover e mirroring).</span><span class="sxs-lookup"><span data-stu-id="73b88-118">SQL Server provides two fault tolerance methods (Failover Clustering and Mirroring).</span></span> <span data-ttu-id="73b88-119">Entrambi i metodi di tolleranza di errore di SQL Server sono supportati utilizzando una porta non standard e un alias di SQL Server con Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="73b88-119">Both SQL Server fault tolerance methods are supported using a SQL Server non-standard port and alias with Lync Server 2013.</span></span> <span data-ttu-id="73b88-120">Se il backend di SQL Server utilizzato dal pool è in una configurazione con mirroring, è necessario che il servizio SQL browser sui server back-end di SQL Server sia in esecuzione affinché i server front endpoint si connettano al database con mirroring quando i database non vengono riavviati nell'SQL con mirroring. Server.</span><span class="sxs-lookup"><span data-stu-id="73b88-120">If the SQL Server backend used by the pool is in a mirrored configuration, then the SQL browser service on the SQL Server backend servers should be running for Front End servers to connect to the mirrored database when the databases are failed over to the mirrored SQL Server.</span></span>



</div>

<span data-ttu-id="73b88-121">Quando si configura la connettività dei database di SQL Server dall'interno di generatore di topologie o quando si utilizza il cmdlet Install-CsDatabase, non è possibile definire in modo esplicito un numero di porta non standard di SQL Server e associarlo a un'istanza di SQL.</span><span class="sxs-lookup"><span data-stu-id="73b88-121">When configuring SQL Server database connectivity from within Topology Builder, or when using the Install-CsDatabase cmdlet, it’s not possible to explicitly define a SQL Server non-standard port number and associate it with a SQL instance.</span></span> <span data-ttu-id="73b88-122">Per impostare una porta non standard, è necessario utilizzare le utilità SQL Server e Windows Server.</span><span class="sxs-lookup"><span data-stu-id="73b88-122">To set a non-standard port, you’ll need to use SQL Server and Windows Server utilities.</span></span>

<span data-ttu-id="73b88-123">Per impostare una porta non standard e un alias di SQL Server per l'utilizzo con Lync Server 2013, sarà necessario completare tre passaggi principali.</span><span class="sxs-lookup"><span data-stu-id="73b88-123">To set up a SQL Server non-standard port and alias for use with Lync Server 2013, you will need to complete three primary steps.</span></span> <span data-ttu-id="73b88-124">I passaggi sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="73b88-124">These steps are:</span></span>

  - <span data-ttu-id="73b88-125">Verificare che in Lync Server 2013 siano stati applicati gli aggiornamenti più recenti.</span><span class="sxs-lookup"><span data-stu-id="73b88-125">Confirm that Lync Server 2013 has the Latest Updates Applied.</span></span>

  - <span data-ttu-id="73b88-126">Configurare la porta non standard e l'alias di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="73b88-126">Setup the SQL Server Non-Standard Port and Alias.</span></span>

  - <span data-ttu-id="73b88-127">Configurare Lync Server 2013 con l'alias di SQL Server tramite Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="73b88-127">Configure Lync Server 2013 with the SQL Server alias using Topology Builder.</span></span>

  - <span data-ttu-id="73b88-128">Pubblicare la topologia e verificare il database.</span><span class="sxs-lookup"><span data-stu-id="73b88-128">Publish the Topology, and Verify the Database.</span></span>

<div>

## <a name="confirm-that-lync-server-2013-has-the-latest-updates-applied"></a><span data-ttu-id="73b88-129">Verificare che in Lync Server 2013 siano stati applicati gli aggiornamenti più recenti</span><span class="sxs-lookup"><span data-stu-id="73b88-129">Confirm that Lync Server 2013 has the Latest Updates Applied</span></span>

<span data-ttu-id="73b88-130">È importante mantenere Lync Server 2013 aggiornato.</span><span class="sxs-lookup"><span data-stu-id="73b88-130">It is important to keep Lync Server 2013 up to date.</span></span> <span data-ttu-id="73b88-131">Per verificare la disponibilità degli aggiornamenti e delle informazioni più recenti su come applicarli, vedere [Updates for Lync Server 2013](http://support.microsoft.com/kb/2809243).</span><span class="sxs-lookup"><span data-stu-id="73b88-131">To check for the most recent updates and information on how to apply them, see [Updates for Lync Server 2013](http://support.microsoft.com/kb/2809243).</span></span>

</div>

<div>

## <a name="setup-the-sql-server-non-standard-port-and-alias"></a><span data-ttu-id="73b88-132">Configurare la porta e l'alias di SQL Server non standard</span><span class="sxs-lookup"><span data-stu-id="73b88-132">Setup the SQL Server Non-Standard Port and Alias</span></span>

<span data-ttu-id="73b88-133">La porta non standard e l'alias di SQL Server devono essere configurati nell'istanza del database prima di poter fare riferimento a un generatore di topologie di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="73b88-133">The SQL Server non-standard port and alias must be set up on the database instance before it can be referenced from Lync Server 2013 Topology Builder.</span></span> <span data-ttu-id="73b88-134">Per impostare una porta non standard e un alias di SQL Server, sarà necessario completare tre passaggi principali.</span><span class="sxs-lookup"><span data-stu-id="73b88-134">To set up a SQL Server non-standard port and alias, you will have to complete three primary steps.</span></span> <span data-ttu-id="73b88-135">Questi passaggi sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="73b88-135">These steps are as follows:</span></span>

  - <span data-ttu-id="73b88-136">Modificare i valori predefiniti del protocollo TCP/IP.</span><span class="sxs-lookup"><span data-stu-id="73b88-136">Change the Default TCP/IP Protocol Values.</span></span>

  - <span data-ttu-id="73b88-137">Creare e configurare un alias di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="73b88-137">Create and Configure a SQL Server Alias.</span></span>

  - <span data-ttu-id="73b88-138">Creare un record di risorse DNS (Domain Name System) (CNAME).</span><span class="sxs-lookup"><span data-stu-id="73b88-138">Create a Domain Name System (DNS) Canonical Name (CNAME) Resource Record.</span></span>

<span data-ttu-id="73b88-139">**Modificare i valori predefiniti del protocollo TCP/IP**</span><span class="sxs-lookup"><span data-stu-id="73b88-139">**Modify the Default TCP/IP Protocol Values**</span></span>

1.  <span data-ttu-id="73b88-140">Fare clic su **Start**e scegliere **Gestione configurazione SQL Server**, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="73b88-140">Select **Start**, and choose **SQL Server Configuration Manager**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="73b88-141">![Icona di SQL Server Management Studio](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "Icona di SQL Server Management Studio")</span><span class="sxs-lookup"><span data-stu-id="73b88-141">![The SQL Server Management Studio icon](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "The SQL Server Management Studio icon")</span></span>

2.  <span data-ttu-id="73b88-142">Nel riquadro di spostamento scegliere di espandere l' **istanza di SQL Server**, scegliere di espandere **configurazione di rete di SQL Server**e scegliere **protocolli \<come nome\>di istanza**, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="73b88-142">In the navigation pane, choose to expand the **SQL Server instance**, choose to expand **SQL Server Network Configuration**, and choose **Protocols for \<instance name\>**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="73b88-143">![Passare a proprietà TCP/IP](images/Dn776290.3d7a964c-f17e-47fd-8f0c-535453da7fad(OCS.15).jpg "Passare a proprietà TCP/IP")</span><span class="sxs-lookup"><span data-stu-id="73b88-143">![Navigate to TCP/IP Properties](images/Dn776290.3d7a964c-f17e-47fd-8f0c-535453da7fad(OCS.15).jpg "Navigate to TCP/IP Properties")</span></span>

3.  <span data-ttu-id="73b88-144">Nel riquadro destro fare clic con il pulsante destro del mouse su **TCP/IP**e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="73b88-144">In the right pane, right-click **TCP/IP**, and select **Properties**.</span></span> <span data-ttu-id="73b88-145">Verrà visualizzata la finestra di dialogo Proprietà TCP/IP.</span><span class="sxs-lookup"><span data-stu-id="73b88-145">The TCP/IP Properties dialog box is displayed.</span></span>

4.  <span data-ttu-id="73b88-146">Selezionare la scheda **indirizzi IP** . La scheda indirizzi IP Visualizza tutti gli indirizzi IP attivi sul server.</span><span class="sxs-lookup"><span data-stu-id="73b88-146">Select the **IP Addresses** tab. The IP Addresses tab shows all of the active IP addresses on the server.</span></span> <span data-ttu-id="73b88-147">Si tratta del formato IP1, IP2, fino a IPAll, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="73b88-147">These are in the format IP1, IP2, up to IPAll, as shown in the following figure.</span></span>
    
    <span data-ttu-id="73b88-148">![Aprire le proprietà TCP/IP.](images/Dn776290.ed2fd70d-1836-4ebf-80fe-09191d96585e(OCS.15).jpg "Aprire le proprietà TCP/IP.")</span><span class="sxs-lookup"><span data-stu-id="73b88-148">![Open TCP/IP properties.](images/Dn776290.ed2fd70d-1836-4ebf-80fe-09191d96585e(OCS.15).jpg "Open TCP/IP properties.")</span></span>

5.  <span data-ttu-id="73b88-149">Cancellare il campo **porte dinamiche TCP** per tutti gli indirizzi IP.</span><span class="sxs-lookup"><span data-stu-id="73b88-149">Clear the **TCP Dynamic Ports** field for all IP addresses.</span></span> <span data-ttu-id="73b88-150">Se il campo contiene un carattere zero, significa che SQL Server è in attesa su porte dinamiche.</span><span class="sxs-lookup"><span data-stu-id="73b88-150">If the field contains a zero character, then it means SQL Server is listening on dynamic ports.</span></span> <span data-ttu-id="73b88-151">Verificare che questi campi siano deselezionati e che non contengano uno zero.</span><span class="sxs-lookup"><span data-stu-id="73b88-151">Make sure these fields are cleared and do not contain a zero.</span></span>

6.  <span data-ttu-id="73b88-152">Per l'indirizzo IP che verrà utilizzato da Lync Server per la connessione al database, verificare che **Enabled** sia impostato su **Sì**, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="73b88-152">For the IP address that Lync Server will be using to connect to the database, make sure that **Enabled** is set to **Yes**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="73b88-153">![Impostare attivato come Sì per l'indirizzo IP corretto.](images/Dn776290.7f818b91-0793-4594-8932-90447270fad9(OCS.15).jpg "Impostare attivato come Sì per l'indirizzo IP corretto.")</span><span class="sxs-lookup"><span data-stu-id="73b88-153">![Set enabled as Yes for the correct IP.](images/Dn776290.7f818b91-0793-4594-8932-90447270fad9(OCS.15).jpg "Set enabled as Yes for the correct IP.")</span></span>

7.  <span data-ttu-id="73b88-154">Nella sezione **IPAll** nella parte inferiore della finestra di dialogo, immettere la porta desiderata nel campo **porta TCP** , come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="73b88-154">In the **IPAll** section at the bottom of the dialog, enter the desired port in the **TCP Port** field, as shown in the following figure.</span></span> <span data-ttu-id="73b88-155">In questo esempio viene utilizzata la porta 50062, ma è possibile utilizzare qualsiasi porta tra 49152 e 65535.</span><span class="sxs-lookup"><span data-stu-id="73b88-155">In this example, we use port 50062, but you can use any port between 49152 and 65535.</span></span> <span data-ttu-id="73b88-156">Si tratta delle porte assegnate a un utilizzo dinamico e privato e questo garantisce che non vi siano conflitti con le altre porte utilizzate nella distribuzione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="73b88-156">These are the ports assigned to dynamic and private use, and this ensures you won’t conflict with other ports being used in the Lync Server 2013 deployment.</span></span>
    
    <span data-ttu-id="73b88-157">![Impostare la porta nella sezione IPAll.](images/Dn776290.b5af53e2-7961-4664-b586-3ca8f3a17f06(OCS.15).jpg "Impostare la porta nella sezione IPAll.")</span><span class="sxs-lookup"><span data-stu-id="73b88-157">![Set port in IPAll section.](images/Dn776290.b5af53e2-7961-4664-b586-3ca8f3a17f06(OCS.15).jpg "Set port in IPAll section.")</span></span>

8.  <span data-ttu-id="73b88-158">Fare clic su **OK** per uscire dalla finestra di dialogo delle proprietà TCP/IP.</span><span class="sxs-lookup"><span data-stu-id="73b88-158">Choose **OK** to exit the TCP/IP Properties dialog.</span></span>

9.  <span data-ttu-id="73b88-159">Riavviare l'istanza di SQL Server selezionando **servizi SQL Server** nel riquadro sinistro di gestione configurazione SQL Server.</span><span class="sxs-lookup"><span data-stu-id="73b88-159">Restart the SQL Server instance by selecting **SQL Server Services** in the left pane of SQL Server Configuration Manager.</span></span> <span data-ttu-id="73b88-160">Fare quindi clic con il pulsante destro del mouse su **nome \<\> dell'istanza di SQL Server** nel riquadro destro e scegliere **Riavvia**, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="73b88-160">Then right-click **SQL Server \<instance name\>** in the right pane, and select **Restart**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="73b88-161">![Reimpostare il servizio SQL Server per l'istanza.](images/Dn776290.a965c8cf-f769-4b52-bb38-c48a438cf491(OCS.15).jpg "Reimpostare il servizio SQL Server per l'istanza.")</span><span class="sxs-lookup"><span data-stu-id="73b88-161">![Reset the SQL Server service for instance.](images/Dn776290.a965c8cf-f769-4b52-bb38-c48a438cf491(OCS.15).jpg "Reset the SQL Server service for instance.")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="73b88-162">Assicurarsi di aggiornare le impostazioni del firewall per ospitare la nuova porta di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="73b88-162">Make sure you update your firewall settings to accommodate the new SQL Server port.</span></span>



</div>

<span data-ttu-id="73b88-163">**Creare e configurare un alias di SQL Server**</span><span class="sxs-lookup"><span data-stu-id="73b88-163">**Create and Configure a SQL Server Alias**</span></span>

1.  <span data-ttu-id="73b88-164">Fare clic su **Start**e scegliere **Gestione configurazione SQL Server**, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="73b88-164">Select **Start**, and choose **SQL Server Configuration Manager**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="73b88-165">![Icona di SQL Server Management Studio](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "Icona di SQL Server Management Studio")</span><span class="sxs-lookup"><span data-stu-id="73b88-165">![The SQL Server Management Studio icon](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "The SQL Server Management Studio icon")</span></span>

2.  <span data-ttu-id="73b88-166">Nel riquadro sinistro scegliere Espandi **istanza di SQL Server**, fare clic su Espandi **Configurazione versione \<\> SQL Native Client**e quindi scegliere **alias**, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="73b88-166">In the left pane, choose to expand **SQL Server instance**, choose to expand **SQL Native Client \<version\> Configuration**, and then choose **Aliases**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="73b88-167">![Alias in Gestione configurazione SQL Server.](images/Dn776290.95341826-55d7-425f-ae19-d47d6668c5d8(OCS.15).jpg "Alias in Gestione configurazione SQL Server.")</span><span class="sxs-lookup"><span data-stu-id="73b88-167">![Aliases in SQL Server Configuration Manager.](images/Dn776290.95341826-55d7-425f-ae19-d47d6668c5d8(OCS.15).jpg "Aliases in SQL Server Configuration Manager.")</span></span>

3.  <span data-ttu-id="73b88-168">Fare clic con il pulsante destro del mouse su **alias**e scegliere **nuovo alias...**.</span><span class="sxs-lookup"><span data-stu-id="73b88-168">Right-click **Aliases**, and select **New Alias…**.</span></span>

4.  <span data-ttu-id="73b88-169">Immettere il **nome dell'alias**, il **numero di porta**, il **protocollo**e il **Server**, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="73b88-169">Enter the **Alias Name**, **Port Number**, **Protocol**, and **Server**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="73b88-170">![Creazione di un nuovo alias](images/Dn776290.03653588-aecf-4fdd-b58a-95f5b372d478(OCS.15).jpg "Creazione di un nuovo alias")</span><span class="sxs-lookup"><span data-stu-id="73b88-170">![Creating a new alias](images/Dn776290.03653588-aecf-4fdd-b58a-95f5b372d478(OCS.15).jpg "Creating a new alias")</span></span>
    
    <div>
    

    > [!CAUTION]  
    > <span data-ttu-id="73b88-171">Assicurarsi di immettere la stessa porta non standard utilizzata nel passaggio precedente, poiché quella è la porta che verrà ascoltata da SQL Server.</span><span class="sxs-lookup"><span data-stu-id="73b88-171">Make sure to enter the same non-standard port you used in the previous step since that is the port SQL Server will be listening on.</span></span> <span data-ttu-id="73b88-172">Se un alias configurato è connesso all'istanza o all'FQDN di SQL Server errato, disabilitare e quindi riattivare il protocollo di rete associato.</span><span class="sxs-lookup"><span data-stu-id="73b88-172">If a configured alias is connecting to the wrong SQL Server FQDN or Instance, disable and then re-enable the associated network protocol.</span></span> <span data-ttu-id="73b88-173">In questo modo vengono eliminate tutte le informazioni sulla connessione memorizzate nella cache e il client si connette correttamente.</span><span class="sxs-lookup"><span data-stu-id="73b88-173">Doing this clears any cached connection information and allows the client to connect correctly.</span></span>

    
    </div>

<span data-ttu-id="73b88-174">**Creare un record di risorse DNS CNAME**</span><span class="sxs-lookup"><span data-stu-id="73b88-174">**Create a DNS CNAME Resource Record**</span></span>

1.  <span data-ttu-id="73b88-175">Accedere al computer che gestisce DNS.</span><span class="sxs-lookup"><span data-stu-id="73b88-175">Sign into the computer managing DNS.</span></span>

2.  <span data-ttu-id="73b88-176">Fare clic su **Start**e scegliere **Server Manager**, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="73b88-176">Select **Start**, and choose **Server Manager**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="73b88-177">![Apertura di Server Manager](images/Dn776290.3e4bd8ad-2a65-4a05-af40-c8dd3583bc8f(OCS.15).jpg "Apertura di Server Manager")</span><span class="sxs-lookup"><span data-stu-id="73b88-177">![Opening Server Manager](images/Dn776290.3e4bd8ad-2a65-4a05-af40-c8dd3583bc8f(OCS.15).jpg "Opening Server Manager")</span></span>

3.  <span data-ttu-id="73b88-178">Scegliere il menu a discesa **strumenti** e selezionare **DNS**, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="73b88-178">Choose the **Tools** drop-down, and select **DNS**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="73b88-179">![Apertura di DNS da Server Manager.](images/Dn776290.415e1da1-7c9a-4a4e-a896-ca34a76aaeff(OCS.15).jpg "Apertura di DNS da Server Manager.")</span><span class="sxs-lookup"><span data-stu-id="73b88-179">![Opening DNS from Server Manager.](images/Dn776290.415e1da1-7c9a-4a4e-a896-ca34a76aaeff(OCS.15).jpg "Opening DNS from Server Manager.")</span></span>

4.  <span data-ttu-id="73b88-180">Nel riquadro sinistro espandere il nodo nome server, espandere il nodo zone di ricerca diretta e scegliere il dominio pertinente.</span><span class="sxs-lookup"><span data-stu-id="73b88-180">In the left pane, expand the server name node, expand the Forward Lookup Zones node, and choose the relevant domain.</span></span>

5.  <span data-ttu-id="73b88-181">Fare clic con il pulsante destro del mouse sul dominio e scegliere **nuovo alias (CNAME)...**, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="73b88-181">Right-click the domain, and select **New Alias (CNAME)…**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="73b88-182">![Selezionare l'opzione per creare un nuovo alias CNAME](images/Dn776290.abe66cca-b53c-427a-9094-1a59dc6840ca(OCS.15).jpg "Selezionare l'opzione per creare un nuovo alias CNAME")</span><span class="sxs-lookup"><span data-stu-id="73b88-182">![Selecting option to create a new alias CNAME](images/Dn776290.abe66cca-b53c-427a-9094-1a59dc6840ca(OCS.15).jpg "Selecting option to create a new alias CNAME")</span></span>

6.  <span data-ttu-id="73b88-183">Immettere il **nome dell'alias** e l' **FQDN per SQL Server**, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="73b88-183">Enter the **Alias Name** and the **FQDN for SQL Server**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="73b88-184">![Compilazione della nuova finestra di dialogo CNAME alias.](images/Dn776290.dd0ebd2d-3407-4459-8bd9-2b389a7bc440(OCS.15).jpg "Compilazione della nuova finestra di dialogo CNAME alias.")</span><span class="sxs-lookup"><span data-stu-id="73b88-184">![Filling in the new alias CNAME dialog.](images/Dn776290.dd0ebd2d-3407-4459-8bd9-2b389a7bc440(OCS.15).jpg "Filling in the new alias CNAME dialog.")</span></span>

7.  <span data-ttu-id="73b88-185">Scegliere **OK** per salvare CNAME e visualizzarlo in gestione DNS.</span><span class="sxs-lookup"><span data-stu-id="73b88-185">Choose **OK** to save the CNAME and view it in DNS Manager.</span></span>

</div>

<div>

## <a name="validate-database-connectivity"></a><span data-ttu-id="73b88-186">Convalidare la connettività dei database</span><span class="sxs-lookup"><span data-stu-id="73b88-186">Validate Database Connectivity</span></span>

<span data-ttu-id="73b88-187">Esistono diversi modi per assicurarsi che funzioni.</span><span class="sxs-lookup"><span data-stu-id="73b88-187">There are many different ways to make sure it is working.</span></span> <span data-ttu-id="73b88-188">Si desidera verificare che il database di SQL Server sia in attesa sulla porta specificata utilizzando l'alias.</span><span class="sxs-lookup"><span data-stu-id="73b88-188">You want to make sure that the SQL Server database is listening on the specified port using the alias.</span></span> <span data-ttu-id="73b88-189">Un controllo rapido può essere completato utilizzando i comandi **netstat** e **Telnet** .</span><span class="sxs-lookup"><span data-stu-id="73b88-189">A quick check can be completed using the **netstat** and **telnet** commands.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="73b88-190">Il client Telnet è una funzionalità che viene fornita con Windows Server, ma che deve essere installata.</span><span class="sxs-lookup"><span data-stu-id="73b88-190">Telnet Client is a Feature that comes with Windows Server but that must be installed.</span></span> <span data-ttu-id="73b88-191">È possibile installare una funzionalità di Windows Server aprendo Server Manager e selezionando Aggiungi ruoli e funzionalità dal menu Gestisci.</span><span class="sxs-lookup"><span data-stu-id="73b88-191">A Windows Server Feature can be installed by opening Server Manager and selecting Add Roles and Features from the Manage menu.</span></span>



</div>

<span data-ttu-id="73b88-192">**Utilizzo di netstat e Telnet per verificare la connettività dei database**</span><span class="sxs-lookup"><span data-stu-id="73b88-192">**Use netstat and telnet to verify database connectivity**</span></span>

1.  <span data-ttu-id="73b88-193">Fare clic su **Start**e digitare **cmd** per aprire un prompt di comandi.</span><span class="sxs-lookup"><span data-stu-id="73b88-193">Select **Start**, and type **cmd** to open a command prompt.</span></span>

2.  <span data-ttu-id="73b88-194">Digitare **netstat-a-f**e verificare che SQL Server sia in esecuzione con la porta corretta, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="73b88-194">Type **netstat -a -f**, and confirm that SQL Server is running with the correct port, as shown in the following figure.</span></span>
    
    <span data-ttu-id="73b88-195">![Utilizzo di netstat per verificare la porta.](images/Dn776290.4ff3a1b2-c5eb-4496-8be7-374c351fa027(OCS.15).jpg "Utilizzo di netstat per verificare la porta.")</span><span class="sxs-lookup"><span data-stu-id="73b88-195">![Using netstat to verify port.](images/Dn776290.4ff3a1b2-c5eb-4496-8be7-374c351fa027(OCS.15).jpg "Using netstat to verify port.")</span></span>

3.  <span data-ttu-id="73b88-196">Digitare **la \<\> \<porta \# nome Telnet alias** per confermare la connessione all'istanza di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="73b88-196">Type **telnet \<alias name\> \<port \#\>** to confirm the connection to the SQL Server instance.</span></span> <span data-ttu-id="73b88-197">Se la connessione ha esito positivo, Telnet si collegherà e non dovrebbe essere visualizzato un errore.</span><span class="sxs-lookup"><span data-stu-id="73b88-197">If the connection is successful, telnet will connect and you shouldn’t see an error.</span></span> <span data-ttu-id="73b88-198">Questo dimostra che l'istanza di SQL Server è in ascolto sulla porta corretta con l'alias corretto.</span><span class="sxs-lookup"><span data-stu-id="73b88-198">This shows that the SQL Server instance is listening on the correct port with the correct alias.</span></span> <span data-ttu-id="73b88-199">Se si verifica un problema di connessione al database di SQL Server, viene visualizzato un errore che indica che non è possibile effettuare la connessione.</span><span class="sxs-lookup"><span data-stu-id="73b88-199">If there’s a problem connecting to the SQL Server database, then telnet shows an error that the connection cannot be made.</span></span> <span data-ttu-id="73b88-200">Dopo aver verificato la connettività dei database nel server di database, è possibile eseguire la stessa operazione da Lync Server (sulla rete) e assicurarsi che non vi siano firewall che impediscono l'accesso lungo la strada.</span><span class="sxs-lookup"><span data-stu-id="73b88-200">Now that you have checked database connectivity on the database server, you can do the same thing from Lync Server (over the network) and make sure there aren’t any firewalls blocking access along the way.</span></span>

</div>

<div>

## <a name="conclusion"></a><span data-ttu-id="73b88-201">Conclusione</span><span class="sxs-lookup"><span data-stu-id="73b88-201">Conclusion</span></span>

<span data-ttu-id="73b88-202">Dopo aver configurato l'alias di SQL Server, è possibile utilizzarlo per creare una topologia di Lync Server 2013 nello strumento generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="73b88-202">Once the SQL Server alias has been configured, you can use it to create a Lync Server 2013 topology in the Topology Builder tool.</span></span> <span data-ttu-id="73b88-203">Per ulteriori informazioni sulle topologie, vedere [definizione e configurazione della topologia in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span><span class="sxs-lookup"><span data-stu-id="73b88-203">For more information about topologies, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="73b88-204">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="73b88-204">See Also</span></span>


<span data-ttu-id="73b88-205">[Microsoft Lync Server 2013](microsoft-lync-server-2013.md) 
[pianificazione della sicurezza in Lync Server 2013](lync-server-2013-planning-for-security.md)</span><span class="sxs-lookup"><span data-stu-id="73b88-205">[Microsoft Lync Server 2013](microsoft-lync-server-2013.md) 
[Planning for security in Lync Server 2013](lync-server-2013-planning-for-security.md)</span></span>  
[<span data-ttu-id="73b88-206">Definizione e configurazione della topologia in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="73b88-206">Defining and configuring the topology in Lync Server 2013</span></span>](lync-server-2013-defining-and-configuring-the-topology.md)  
[<span data-ttu-id="73b88-207">Distribuzione di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="73b88-207">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

