---
title: Distribuzione di una porta non standard e di un alias di SQL Server in Lync Server 2013
description: Distribuzione di una porta non standard e di un alias di SQL Server in Lync Server 2013.
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
ms.openlocfilehash: da76db2b946a47e13fe3549d7184b0b12894a83a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551232"
---
# <a name="deploying-a-sql-server-nonstandard-port-and-alias-in-lync-server-2013"></a><span data-ttu-id="68559-103">Distribuzione di una porta non standard e di un alias di SQL Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68559-103">Deploying a SQL Server nonstandard port and alias in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="68559-104">_**Ultimo argomento modificato:** 2015-09-16_</span><span class="sxs-lookup"><span data-stu-id="68559-104">_**Topic Last Modified:** 2015-09-16_</span></span>

<span data-ttu-id="68559-105">Microsoft Lync Server 2013 supporta l'utilizzo di una porta non standard e di un alias in SQL Server.</span><span class="sxs-lookup"><span data-stu-id="68559-105">Microsoft Lync Server 2013 supports using a non-standard port and alias in SQL Server.</span></span> <span data-ttu-id="68559-106">L'utilizzo di una porta non standard di SQL Server e di un alias aumenta la sicurezza e crea un ambiente più flessibile per la distribuzione di Lync.</span><span class="sxs-lookup"><span data-stu-id="68559-106">Using a SQL Server non-standard port and an alias increases security and creates a more flexible environment for the Lync deployment.</span></span> <span data-ttu-id="68559-107">Questi passaggi sono solo un singolo passaggio per garantire il corretto funzionamento dell'ambiente Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="68559-107">These steps are only a single step in properly securing your Lync Server 2013 environment.</span></span> <span data-ttu-id="68559-108">È necessario eseguire ulteriori operazioni per ridurre la superficie di attacco di un'implementazione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="68559-108">Additional steps should be taken to reduce the attack surface of a Lync Server 2013 implementation.</span></span>

<span data-ttu-id="68559-109">Nell'articolo seguente vengono descritti i passaggi necessari per configurare una porta non standard e un alias di SQL Server in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="68559-109">The following article describes the steps required to setup a SQL Server non-standard port and alias in Lync Server 2013.</span></span>

<div>

## <a name="deploying-a-sql-server-non-standard-port-and-alias-in-lync-server-2013"></a><span data-ttu-id="68559-110">Distribuzione di una porta non standard e di un alias di SQL Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68559-110">Deploying a SQL Server Non-Standard Port and Alias in Lync Server 2013</span></span>

<span data-ttu-id="68559-111">Il generatore di topologie di Lync Server 2013 supporta l'utilizzo di un alias di SQL Server come nome di dominio completo (FQDN) anziché come FQDN effettivo di SQL Server durante la configurazione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="68559-111">Lync Server 2013 Topology Builder supports using a SQL Server alias as the Fully Qualified Domain Name (FQDN) instead of the actual SQL Server FQDN when configuring Lync Server 2013.</span></span> <span data-ttu-id="68559-112">In questo modo il nome FQDN effettivo di SQL Server deve essere nascosto da qualsiasi utente malintenzionato.</span><span class="sxs-lookup"><span data-stu-id="68559-112">This allows the actual SQL Server FQDN to be hidden from any malicious attacker.</span></span> <span data-ttu-id="68559-113">Inoltre, l'utilizzo di una porta non standard nasconde la porta effettiva da qualsiasi utente malintenzionato che tenta di attaccare il database sulla porta standard 1433, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="68559-113">In addition, using a non-standard port obscures the actual port from any would be attacker attempting to attack the database on the standard port 1433, as shown in the following figure.</span></span>

<span data-ttu-id="68559-114">![Un hacker non conosce il numero di porta da attaccare.](images/Dn776290.2f3923e0-2bdc-416b-a66b-bf56599eb14e(OCS.15).jpg "Un hacker non conosce il numero di porta da attaccare.")</span><span class="sxs-lookup"><span data-stu-id="68559-114">![A hacker doesn't know the port number to attack.](images/Dn776290.2f3923e0-2bdc-416b-a66b-bf56599eb14e(OCS.15).jpg "A hacker doesn't know the port number to attack.")</span></span>

<span data-ttu-id="68559-115">Per avere esito positivo nel determinare la porta che Lync Server 2013 utilizza per comunicare con SQL Server, l'utente malintenzionato dovrà analizzare tutte le porte per ottenere le informazioni sulla porta.</span><span class="sxs-lookup"><span data-stu-id="68559-115">In order to be successful in determining the port Lync Server 2013 is using to communicate with SQL Server, the attacker would need to scan all ports to obtain the port information.</span></span> <span data-ttu-id="68559-116">L'analisi di una porta eseguita da un utente malintenzionato aumenta le possibilità che la sicurezza possa rilevare e arrestare l'istruzione.</span><span class="sxs-lookup"><span data-stu-id="68559-116">A port scan by an attacker increases the chances that security can detect and stop the instruction.</span></span> <span data-ttu-id="68559-117">Oltre ad aggiungere maggiore sicurezza con una porta non standard, è anche possibile utilizzare un alias di SQL Server per fornire flessibilità per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="68559-117">In addition to adding increased security with a non-standard port, you can also use a SQL Server alias to provide flexibility for the deployment.</span></span> <span data-ttu-id="68559-118">Ciò è utile per ridurre le modifiche apportate alla configurazione in situazioni in cui è necessaria una modifica del nome di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="68559-118">This is valuable in order to reduce configuration changes in situations where a SQL Server name change is required.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="68559-119">In SQL Server sono disponibili due metodi di tolleranza di errore (clustering di failover e mirroring).</span><span class="sxs-lookup"><span data-stu-id="68559-119">SQL Server provides two fault tolerance methods (Failover Clustering and Mirroring).</span></span> <span data-ttu-id="68559-120">Entrambi i metodi di tolleranza di errore di SQL Server sono supportati utilizzando una porta non standard e un alias di SQL Server con Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="68559-120">Both SQL Server fault tolerance methods are supported using a SQL Server non-standard port and alias with Lync Server 2013.</span></span> <span data-ttu-id="68559-121">Se il backend di SQL Server utilizzato dal pool è in una configurazione con mirroring, è necessario che il servizio SQL browser sui server back-end di SQL Server sia in esecuzione affinché i server front endpoint si connettano al database con mirroring quando i database non vengono riavviati nel server SQL con mirroring.</span><span class="sxs-lookup"><span data-stu-id="68559-121">If the SQL Server backend used by the pool is in a mirrored configuration, then the SQL browser service on the SQL Server backend servers should be running for Front End servers to connect to the mirrored database when the databases are failed over to the mirrored SQL Server.</span></span>



</div>

<span data-ttu-id="68559-122">Quando si configura la connettività dei database di SQL Server dall'interno di generatore di topologie o quando si utilizza il cmdlet Install-CsDatabase, non è possibile definire in modo esplicito un numero di porta non standard di SQL Server e associarlo a un'istanza di SQL.</span><span class="sxs-lookup"><span data-stu-id="68559-122">When configuring SQL Server database connectivity from within Topology Builder, or when using the Install-CsDatabase cmdlet, it’s not possible to explicitly define a SQL Server non-standard port number and associate it with a SQL instance.</span></span> <span data-ttu-id="68559-123">Per impostare una porta non standard, è necessario utilizzare le utilità SQL Server e Windows Server.</span><span class="sxs-lookup"><span data-stu-id="68559-123">To set a non-standard port, you’ll need to use SQL Server and Windows Server utilities.</span></span>

<span data-ttu-id="68559-124">Per impostare una porta non standard e un alias di SQL Server per l'utilizzo con Lync Server 2013, sarà necessario completare tre passaggi principali.</span><span class="sxs-lookup"><span data-stu-id="68559-124">To set up a SQL Server non-standard port and alias for use with Lync Server 2013, you will need to complete three primary steps.</span></span> <span data-ttu-id="68559-125">I passaggi sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="68559-125">These steps are:</span></span>

  - <span data-ttu-id="68559-126">Verificare che in Lync Server 2013 siano stati applicati gli aggiornamenti più recenti.</span><span class="sxs-lookup"><span data-stu-id="68559-126">Confirm that Lync Server 2013 has the Latest Updates Applied.</span></span>

  - <span data-ttu-id="68559-127">Configurare la porta non standard e l'alias di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="68559-127">Setup the SQL Server Non-Standard Port and Alias.</span></span>

  - <span data-ttu-id="68559-128">Configurare Lync Server 2013 con l'alias di SQL Server tramite Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="68559-128">Configure Lync Server 2013 with the SQL Server alias using Topology Builder.</span></span>

  - <span data-ttu-id="68559-129">Pubblicare la topologia e verificare il database.</span><span class="sxs-lookup"><span data-stu-id="68559-129">Publish the Topology, and Verify the Database.</span></span>

<div>

## <a name="confirm-that-lync-server-2013-has-the-latest-updates-applied"></a><span data-ttu-id="68559-130">Verificare che in Lync Server 2013 siano stati applicati gli aggiornamenti più recenti</span><span class="sxs-lookup"><span data-stu-id="68559-130">Confirm that Lync Server 2013 has the Latest Updates Applied</span></span>

<span data-ttu-id="68559-131">È importante mantenere Lync Server 2013 aggiornato.</span><span class="sxs-lookup"><span data-stu-id="68559-131">It is important to keep Lync Server 2013 up to date.</span></span> <span data-ttu-id="68559-132">Per verificare la disponibilità degli aggiornamenti e delle informazioni più recenti su come applicarli, vedere [Updates for Lync Server 2013](https://support.microsoft.com/kb/2809243).</span><span class="sxs-lookup"><span data-stu-id="68559-132">To check for the most recent updates and information on how to apply them, see [Updates for Lync Server 2013](https://support.microsoft.com/kb/2809243).</span></span>

</div>

<div>

## <a name="setup-the-sql-server-non-standard-port-and-alias"></a><span data-ttu-id="68559-133">Configurare la porta e l'alias di SQL Server non standard</span><span class="sxs-lookup"><span data-stu-id="68559-133">Setup the SQL Server Non-Standard Port and Alias</span></span>

<span data-ttu-id="68559-134">La porta non standard e l'alias di SQL Server devono essere configurati nell'istanza del database prima di poter fare riferimento a un generatore di topologie di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="68559-134">The SQL Server non-standard port and alias must be set up on the database instance before it can be referenced from Lync Server 2013 Topology Builder.</span></span> <span data-ttu-id="68559-135">Per impostare una porta non standard e un alias di SQL Server, sarà necessario completare tre passaggi principali.</span><span class="sxs-lookup"><span data-stu-id="68559-135">To set up a SQL Server non-standard port and alias, you will have to complete three primary steps.</span></span> <span data-ttu-id="68559-136">Questi passaggi sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="68559-136">These steps are as follows:</span></span>

  - <span data-ttu-id="68559-137">Modificare i valori predefiniti del protocollo TCP/IP.</span><span class="sxs-lookup"><span data-stu-id="68559-137">Change the Default TCP/IP Protocol Values.</span></span>

  - <span data-ttu-id="68559-138">Creare e configurare un alias di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="68559-138">Create and Configure a SQL Server Alias.</span></span>

  - <span data-ttu-id="68559-139">Creare un record di risorse DNS (Domain Name System) (CNAME).</span><span class="sxs-lookup"><span data-stu-id="68559-139">Create a Domain Name System (DNS) Canonical Name (CNAME) Resource Record.</span></span>

<span data-ttu-id="68559-140">**Modificare i valori predefiniti del protocollo TCP/IP**</span><span class="sxs-lookup"><span data-stu-id="68559-140">**Modify the Default TCP/IP Protocol Values**</span></span>

1.  <span data-ttu-id="68559-141">Fare clic su **Start**e scegliere **Gestione configurazione SQL Server**, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="68559-141">Select **Start**, and choose **SQL Server Configuration Manager**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="68559-142">![Icona di SQL Server Management Studio](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "Icona di SQL Server Management Studio")</span><span class="sxs-lookup"><span data-stu-id="68559-142">![The SQL Server Management Studio icon](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "The SQL Server Management Studio icon")</span></span>

2.  <span data-ttu-id="68559-143">Nel riquadro di spostamento scegliere di espandere l' **istanza di SQL Server**, scegliere di espandere **configurazione di rete di SQL Server**e scegliere \*\*protocolli \<instance name\> per \*\*, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="68559-143">In the navigation pane, choose to expand the **SQL Server instance**, choose to expand **SQL Server Network Configuration**, and choose **Protocols for \<instance name\>**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="68559-144">![Passare a proprietà TCP/IP](images/Dn776290.3d7a964c-f17e-47fd-8f0c-535453da7fad(OCS.15).jpg "Passare a proprietà TCP/IP")</span><span class="sxs-lookup"><span data-stu-id="68559-144">![Navigate to TCP/IP Properties](images/Dn776290.3d7a964c-f17e-47fd-8f0c-535453da7fad(OCS.15).jpg "Navigate to TCP/IP Properties")</span></span>

3.  <span data-ttu-id="68559-145">Nel riquadro destro fare clic con il pulsante destro del mouse su **TCP/IP**e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="68559-145">In the right pane, right-click **TCP/IP**, and select **Properties**.</span></span> <span data-ttu-id="68559-146">Verrà visualizzata la finestra di dialogo Proprietà TCP/IP.</span><span class="sxs-lookup"><span data-stu-id="68559-146">The TCP/IP Properties dialog box is displayed.</span></span>

4.  <span data-ttu-id="68559-147">Selezionare la scheda **indirizzi IP** . La scheda indirizzi IP Visualizza tutti gli indirizzi IP attivi sul server.</span><span class="sxs-lookup"><span data-stu-id="68559-147">Select the **IP Addresses** tab. The IP Addresses tab shows all of the active IP addresses on the server.</span></span> <span data-ttu-id="68559-148">Si tratta del formato IP1, IP2, fino a IPAll, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="68559-148">These are in the format IP1, IP2, up to IPAll, as shown in the following figure.</span></span>
    
    <span data-ttu-id="68559-149">![Aprire le proprietà TCP/IP.](images/Dn776290.ed2fd70d-1836-4ebf-80fe-09191d96585e(OCS.15).jpg "Aprire le proprietà TCP/IP.")</span><span class="sxs-lookup"><span data-stu-id="68559-149">![Open TCP/IP properties.](images/Dn776290.ed2fd70d-1836-4ebf-80fe-09191d96585e(OCS.15).jpg "Open TCP/IP properties.")</span></span>

5.  <span data-ttu-id="68559-150">Cancellare il campo **porte dinamiche TCP** per tutti gli indirizzi IP.</span><span class="sxs-lookup"><span data-stu-id="68559-150">Clear the **TCP Dynamic Ports** field for all IP addresses.</span></span> <span data-ttu-id="68559-151">Se il campo contiene un carattere zero, significa che SQL Server è in attesa su porte dinamiche.</span><span class="sxs-lookup"><span data-stu-id="68559-151">If the field contains a zero character, then it means SQL Server is listening on dynamic ports.</span></span> <span data-ttu-id="68559-152">Verificare che questi campi siano deselezionati e che non contengano uno zero.</span><span class="sxs-lookup"><span data-stu-id="68559-152">Make sure these fields are cleared and do not contain a zero.</span></span>

6.  <span data-ttu-id="68559-153">Per l'indirizzo IP che verrà utilizzato da Lync Server per la connessione al database, verificare che **Enabled** sia impostato su **Sì**, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="68559-153">For the IP address that Lync Server will be using to connect to the database, make sure that **Enabled** is set to **Yes**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="68559-154">![Impostare attivato come Sì per l'indirizzo IP corretto.](images/Dn776290.7f818b91-0793-4594-8932-90447270fad9(OCS.15).jpg "Impostare attivato come Sì per l'indirizzo IP corretto.")</span><span class="sxs-lookup"><span data-stu-id="68559-154">![Set enabled as Yes for the correct IP.](images/Dn776290.7f818b91-0793-4594-8932-90447270fad9(OCS.15).jpg "Set enabled as Yes for the correct IP.")</span></span>

7.  <span data-ttu-id="68559-155">Nella sezione **IPAll** nella parte inferiore della finestra di dialogo, immettere la porta desiderata nel campo **porta TCP** , come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="68559-155">In the **IPAll** section at the bottom of the dialog, enter the desired port in the **TCP Port** field, as shown in the following figure.</span></span> <span data-ttu-id="68559-156">In questo esempio viene utilizzata la porta 50062, ma è possibile utilizzare qualsiasi porta tra 49152 e 65535.</span><span class="sxs-lookup"><span data-stu-id="68559-156">In this example, we use port 50062, but you can use any port between 49152 and 65535.</span></span> <span data-ttu-id="68559-157">Si tratta delle porte assegnate a un utilizzo dinamico e privato e questo garantisce che non vi siano conflitti con le altre porte utilizzate nella distribuzione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="68559-157">These are the ports assigned to dynamic and private use, and this ensures you won’t conflict with other ports being used in the Lync Server 2013 deployment.</span></span>
    
    <span data-ttu-id="68559-158">![Impostare la porta nella sezione IPAll.](images/Dn776290.b5af53e2-7961-4664-b586-3ca8f3a17f06(OCS.15).jpg "Impostare la porta nella sezione IPAll.")</span><span class="sxs-lookup"><span data-stu-id="68559-158">![Set port in IPAll section.](images/Dn776290.b5af53e2-7961-4664-b586-3ca8f3a17f06(OCS.15).jpg "Set port in IPAll section.")</span></span>

8.  <span data-ttu-id="68559-159">Fare clic su **OK** per uscire dalla finestra di dialogo delle proprietà TCP/IP.</span><span class="sxs-lookup"><span data-stu-id="68559-159">Choose **OK** to exit the TCP/IP Properties dialog.</span></span>

9.  <span data-ttu-id="68559-160">Riavviare l'istanza di SQL Server selezionando **servizi SQL Server** nel riquadro sinistro di gestione configurazione SQL Server.</span><span class="sxs-lookup"><span data-stu-id="68559-160">Restart the SQL Server instance by selecting **SQL Server Services** in the left pane of SQL Server Configuration Manager.</span></span> <span data-ttu-id="68559-161">Fare quindi clic con il pulsante destro del mouse su \*\*SQL Server \<instance name\> \*\* nel riquadro destro e scegliere **Riavvia**, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="68559-161">Then right-click **SQL Server \<instance name\>** in the right pane, and select **Restart**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="68559-162">![Reimpostare il servizio SQL Server per l'istanza.](images/Dn776290.a965c8cf-f769-4b52-bb38-c48a438cf491(OCS.15).jpg "Reimpostare il servizio SQL Server per l'istanza.")</span><span class="sxs-lookup"><span data-stu-id="68559-162">![Reset the SQL Server service for instance.](images/Dn776290.a965c8cf-f769-4b52-bb38-c48a438cf491(OCS.15).jpg "Reset the SQL Server service for instance.")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="68559-163">Assicurarsi di aggiornare le impostazioni del firewall per ospitare la nuova porta di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="68559-163">Make sure you update your firewall settings to accommodate the new SQL Server port.</span></span>



</div>

<span data-ttu-id="68559-164">**Creare e configurare un alias di SQL Server**</span><span class="sxs-lookup"><span data-stu-id="68559-164">**Create and Configure a SQL Server Alias**</span></span>

1.  <span data-ttu-id="68559-165">Fare clic su **Start**e scegliere **Gestione configurazione SQL Server**, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="68559-165">Select **Start**, and choose **SQL Server Configuration Manager**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="68559-166">![Icona di SQL Server Management Studio](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "Icona di SQL Server Management Studio")</span><span class="sxs-lookup"><span data-stu-id="68559-166">![The SQL Server Management Studio icon](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "The SQL Server Management Studio icon")</span></span>

2.  <span data-ttu-id="68559-167">Nel riquadro sinistro, scegliere di espandere l' **istanza di SQL Server**, scegliere di espandere \*\* \<version\> configurazione SQL Native Client\*\*e quindi scegliere **alias**, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="68559-167">In the left pane, choose to expand **SQL Server instance**, choose to expand **SQL Native Client \<version\> Configuration**, and then choose **Aliases**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="68559-168">![Alias in Gestione configurazione SQL Server.](images/Dn776290.95341826-55d7-425f-ae19-d47d6668c5d8(OCS.15).jpg "Alias in Gestione configurazione SQL Server.")</span><span class="sxs-lookup"><span data-stu-id="68559-168">![Aliases in SQL Server Configuration Manager.](images/Dn776290.95341826-55d7-425f-ae19-d47d6668c5d8(OCS.15).jpg "Aliases in SQL Server Configuration Manager.")</span></span>

3.  <span data-ttu-id="68559-169">Fare clic con il pulsante destro del mouse su **alias**e scegliere **nuovo alias...**.</span><span class="sxs-lookup"><span data-stu-id="68559-169">Right-click **Aliases**, and select **New Alias…**.</span></span>

4.  <span data-ttu-id="68559-170">Immettere il **nome dell'alias**, il **numero di porta**, il **protocollo**e il **Server**, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="68559-170">Enter the **Alias Name**, **Port Number**, **Protocol**, and **Server**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="68559-171">![Creazione di un nuovo alias](images/Dn776290.03653588-aecf-4fdd-b58a-95f5b372d478(OCS.15).jpg "Creazione di un nuovo alias")</span><span class="sxs-lookup"><span data-stu-id="68559-171">![Creating a new alias](images/Dn776290.03653588-aecf-4fdd-b58a-95f5b372d478(OCS.15).jpg "Creating a new alias")</span></span>
    
    <div>
    

    > [!CAUTION]  
    > <span data-ttu-id="68559-172">Assicurarsi di immettere la stessa porta non standard utilizzata nel passaggio precedente, poiché quella è la porta che verrà ascoltata da SQL Server.</span><span class="sxs-lookup"><span data-stu-id="68559-172">Make sure to enter the same non-standard port you used in the previous step since that is the port SQL Server will be listening on.</span></span> <span data-ttu-id="68559-173">Se un alias configurato è connesso all'istanza o all'FQDN di SQL Server errato, disabilitare e quindi riattivare il protocollo di rete associato.</span><span class="sxs-lookup"><span data-stu-id="68559-173">If a configured alias is connecting to the wrong SQL Server FQDN or Instance, disable and then re-enable the associated network protocol.</span></span> <span data-ttu-id="68559-174">In questo modo vengono eliminate tutte le informazioni sulla connessione memorizzate nella cache e il client si connette correttamente.</span><span class="sxs-lookup"><span data-stu-id="68559-174">Doing this clears any cached connection information and allows the client to connect correctly.</span></span>

    
    </div>

<span data-ttu-id="68559-175">**Creare un record di risorse DNS CNAME**</span><span class="sxs-lookup"><span data-stu-id="68559-175">**Create a DNS CNAME Resource Record**</span></span>

1.  <span data-ttu-id="68559-176">Accedere al computer che gestisce DNS.</span><span class="sxs-lookup"><span data-stu-id="68559-176">Sign into the computer managing DNS.</span></span>

2.  <span data-ttu-id="68559-177">Fare clic su **Start**e scegliere **Server Manager**, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="68559-177">Select **Start**, and choose **Server Manager**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="68559-178">![Apertura di Server Manager](images/Dn776290.3e4bd8ad-2a65-4a05-af40-c8dd3583bc8f(OCS.15).jpg "Apertura di Server Manager")</span><span class="sxs-lookup"><span data-stu-id="68559-178">![Opening Server Manager](images/Dn776290.3e4bd8ad-2a65-4a05-af40-c8dd3583bc8f(OCS.15).jpg "Opening Server Manager")</span></span>

3.  <span data-ttu-id="68559-179">Scegliere il menu a discesa **strumenti** e selezionare **DNS**, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="68559-179">Choose the **Tools** drop-down, and select **DNS**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="68559-180">![Apertura di DNS da Server Manager.](images/Dn776290.415e1da1-7c9a-4a4e-a896-ca34a76aaeff(OCS.15).jpg "Apertura di DNS da Server Manager.")</span><span class="sxs-lookup"><span data-stu-id="68559-180">![Opening DNS from Server Manager.](images/Dn776290.415e1da1-7c9a-4a4e-a896-ca34a76aaeff(OCS.15).jpg "Opening DNS from Server Manager.")</span></span>

4.  <span data-ttu-id="68559-181">Nel riquadro sinistro espandere il nodo nome server, espandere il nodo zone di ricerca diretta e scegliere il dominio pertinente.</span><span class="sxs-lookup"><span data-stu-id="68559-181">In the left pane, expand the server name node, expand the Forward Lookup Zones node, and choose the relevant domain.</span></span>

5.  <span data-ttu-id="68559-182">Fare clic con il pulsante destro del mouse sul dominio e scegliere **nuovo alias (CNAME)...**, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="68559-182">Right-click the domain, and select **New Alias (CNAME)…**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="68559-183">![Selezionare l'opzione per creare un nuovo alias CNAME](images/Dn776290.abe66cca-b53c-427a-9094-1a59dc6840ca(OCS.15).jpg "Selezionare l'opzione per creare un nuovo alias CNAME")</span><span class="sxs-lookup"><span data-stu-id="68559-183">![Selecting option to create a new alias CNAME](images/Dn776290.abe66cca-b53c-427a-9094-1a59dc6840ca(OCS.15).jpg "Selecting option to create a new alias CNAME")</span></span>

6.  <span data-ttu-id="68559-184">Immettere il **nome dell'alias** e l' **FQDN per SQL Server**, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="68559-184">Enter the **Alias Name** and the **FQDN for SQL Server**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="68559-185">![Compilazione della nuova finestra di dialogo CNAME alias.](images/Dn776290.dd0ebd2d-3407-4459-8bd9-2b389a7bc440(OCS.15).jpg "Compilazione della nuova finestra di dialogo CNAME alias.")</span><span class="sxs-lookup"><span data-stu-id="68559-185">![Filling in the new alias CNAME dialog.](images/Dn776290.dd0ebd2d-3407-4459-8bd9-2b389a7bc440(OCS.15).jpg "Filling in the new alias CNAME dialog.")</span></span>

7.  <span data-ttu-id="68559-186">Scegliere **OK** per salvare CNAME e visualizzarlo in gestione DNS.</span><span class="sxs-lookup"><span data-stu-id="68559-186">Choose **OK** to save the CNAME and view it in DNS Manager.</span></span>

</div>

<div>

## <a name="validate-database-connectivity"></a><span data-ttu-id="68559-187">Convalidare la connettività dei database</span><span class="sxs-lookup"><span data-stu-id="68559-187">Validate Database Connectivity</span></span>

<span data-ttu-id="68559-188">Esistono diversi modi per assicurarsi che funzioni.</span><span class="sxs-lookup"><span data-stu-id="68559-188">There are many different ways to make sure it is working.</span></span> <span data-ttu-id="68559-189">Si desidera verificare che il database di SQL Server sia in attesa sulla porta specificata utilizzando l'alias.</span><span class="sxs-lookup"><span data-stu-id="68559-189">You want to make sure that the SQL Server database is listening on the specified port using the alias.</span></span> <span data-ttu-id="68559-190">Un controllo rapido può essere completato utilizzando i comandi **netstat** e **Telnet** .</span><span class="sxs-lookup"><span data-stu-id="68559-190">A quick check can be completed using the **netstat** and **telnet** commands.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="68559-191">Il client Telnet è una funzionalità che viene fornita con Windows Server, ma che deve essere installata.</span><span class="sxs-lookup"><span data-stu-id="68559-191">Telnet Client is a Feature that comes with Windows Server but that must be installed.</span></span> <span data-ttu-id="68559-192">È possibile installare una funzionalità di Windows Server aprendo Server Manager e selezionando Aggiungi ruoli e funzionalità dal menu Gestisci.</span><span class="sxs-lookup"><span data-stu-id="68559-192">A Windows Server Feature can be installed by opening Server Manager and selecting Add Roles and Features from the Manage menu.</span></span>



</div>

<span data-ttu-id="68559-193">**Utilizzo di netstat e Telnet per verificare la connettività dei database**</span><span class="sxs-lookup"><span data-stu-id="68559-193">**Use netstat and telnet to verify database connectivity**</span></span>

1.  <span data-ttu-id="68559-194">Fare clic su **Start**e digitare **cmd** per aprire un prompt di comandi.</span><span class="sxs-lookup"><span data-stu-id="68559-194">Select **Start**, and type **cmd** to open a command prompt.</span></span>

2.  <span data-ttu-id="68559-195">Digitare **netstat-a-f**e verificare che SQL Server sia in esecuzione con la porta corretta, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="68559-195">Type **netstat -a -f**, and confirm that SQL Server is running with the correct port, as shown in the following figure.</span></span>
    
    <span data-ttu-id="68559-196">![Utilizzo di netstat per verificare la porta.](images/Dn776290.4ff3a1b2-c5eb-4496-8be7-374c351fa027(OCS.15).jpg "Utilizzo di netstat per verificare la porta.")</span><span class="sxs-lookup"><span data-stu-id="68559-196">![Using netstat to verify port.](images/Dn776290.4ff3a1b2-c5eb-4496-8be7-374c351fa027(OCS.15).jpg "Using netstat to verify port.")</span></span>

3.  <span data-ttu-id="68559-197">Digitare \*\*Telnet \<alias name\> \<port \#\> \*\* per confermare la connessione all'istanza di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="68559-197">Type **telnet \<alias name\> \<port \#\>** to confirm the connection to the SQL Server instance.</span></span> <span data-ttu-id="68559-198">Se la connessione ha esito positivo, Telnet si collegherà e non dovrebbe essere visualizzato un errore.</span><span class="sxs-lookup"><span data-stu-id="68559-198">If the connection is successful, telnet will connect and you shouldn’t see an error.</span></span> <span data-ttu-id="68559-199">Questo dimostra che l'istanza di SQL Server è in ascolto sulla porta corretta con l'alias corretto.</span><span class="sxs-lookup"><span data-stu-id="68559-199">This shows that the SQL Server instance is listening on the correct port with the correct alias.</span></span> <span data-ttu-id="68559-200">Se si verifica un problema di connessione al database di SQL Server, viene visualizzato un errore che indica che non è possibile effettuare la connessione.</span><span class="sxs-lookup"><span data-stu-id="68559-200">If there’s a problem connecting to the SQL Server database, then telnet shows an error that the connection cannot be made.</span></span> <span data-ttu-id="68559-201">Dopo aver verificato la connettività dei database nel server di database, è possibile eseguire la stessa operazione da Lync Server (sulla rete) e assicurarsi che non vi siano firewall che impediscono l'accesso lungo la strada.</span><span class="sxs-lookup"><span data-stu-id="68559-201">Now that you have checked database connectivity on the database server, you can do the same thing from Lync Server (over the network) and make sure there aren’t any firewalls blocking access along the way.</span></span>

</div>

<div>

## <a name="conclusion"></a><span data-ttu-id="68559-202">Conclusione</span><span class="sxs-lookup"><span data-stu-id="68559-202">Conclusion</span></span>

<span data-ttu-id="68559-203">Dopo aver configurato l'alias di SQL Server, è possibile utilizzarlo per creare una topologia di Lync Server 2013 nello strumento generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="68559-203">Once the SQL Server alias has been configured, you can use it to create a Lync Server 2013 topology in the Topology Builder tool.</span></span> <span data-ttu-id="68559-204">Per ulteriori informazioni sulle topologie, vedere [definizione e configurazione della topologia in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span><span class="sxs-lookup"><span data-stu-id="68559-204">For more information about topologies, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="68559-205">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="68559-205">See Also</span></span>


<span data-ttu-id="68559-206">[Microsoft Lync Server 2013](microsoft-lync-server-2013.md)  
 [Pianificazione della sicurezza in Lync Server 2013](lync-server-2013-planning-for-security.md)</span><span class="sxs-lookup"><span data-stu-id="68559-206">[Microsoft Lync Server 2013](microsoft-lync-server-2013.md) 
[Planning for security in Lync Server 2013](lync-server-2013-planning-for-security.md)</span></span>  
[<span data-ttu-id="68559-207">Definizione e configurazione della topologia in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68559-207">Defining and configuring the topology in Lync Server 2013</span></span>](lync-server-2013-defining-and-configuring-the-topology.md)  
[<span data-ttu-id="68559-208">Distribuzione di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68559-208">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

