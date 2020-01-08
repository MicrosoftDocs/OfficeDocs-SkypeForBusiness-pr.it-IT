---
title: Distribuzione di una porta e di un alias non standard di SQL Server in Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying a SQL Server nonstandard port and alias in Lync Server 2013
ms:assetid: 2da92c1f-250e-407a-8651-fb2aec76aeb0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn776290(v=OCS.15)
ms:contentKeyID: 62634609
ms.date: 09/17/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 35365cbd43aa3bea9afe5cdd036bd3834fae5037
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980842"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-a-sql-server-nonstandard-port-and-alias-in-lync-server-2013"></a><span data-ttu-id="9af8f-102">Distribuzione di una porta e di un alias non standard di SQL Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9af8f-102">Deploying a SQL Server nonstandard port and alias in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9af8f-103">_**Argomento Ultima modifica:** 2015-09-16_</span><span class="sxs-lookup"><span data-stu-id="9af8f-103">_**Topic Last Modified:** 2015-09-16_</span></span>

<span data-ttu-id="9af8f-104">Microsoft Lync Server 2013 supporta l'uso di una porta e un alias non standard in SQL Server.</span><span class="sxs-lookup"><span data-stu-id="9af8f-104">Microsoft Lync Server 2013 supports using a non-standard port and alias in SQL Server.</span></span> <span data-ttu-id="9af8f-105">L'uso di una porta non standard di SQL Server e di un alias aumenta la sicurezza e crea un ambiente più flessibile per la distribuzione di Lync.</span><span class="sxs-lookup"><span data-stu-id="9af8f-105">Using a SQL Server non-standard port and an alias increases security and creates a more flexible environment for the Lync deployment.</span></span> <span data-ttu-id="9af8f-106">Questi passaggi sono solo un singolo passaggio per proteggere correttamente l'ambiente Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9af8f-106">These steps are only a single step in properly securing your Lync Server 2013 environment.</span></span> <span data-ttu-id="9af8f-107">È necessario eseguire ulteriori operazioni per ridurre la superficie di attacco di un'implementazione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9af8f-107">Additional steps should be taken to reduce the attack surface of a Lync Server 2013 implementation.</span></span>

<span data-ttu-id="9af8f-108">L'articolo seguente descrive i passaggi necessari per configurare una porta non standard e un alias di SQL Server in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9af8f-108">The following article describes the steps required to setup a SQL Server non-standard port and alias in Lync Server 2013.</span></span>

<div>

## <a name="deploying-a-sql-server-non-standard-port-and-alias-in-lync-server-2013"></a><span data-ttu-id="9af8f-109">Distribuzione di una porta e un alias non standard di SQL Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9af8f-109">Deploying a SQL Server Non-Standard Port and Alias in Lync Server 2013</span></span>

<span data-ttu-id="9af8f-110">Il generatore di topologia di Lync Server 2013 supporta l'uso di un alias di SQL Server come nome di dominio completo (FQDN) anziché l'FQDN effettivo di SQL Server durante la configurazione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9af8f-110">Lync Server 2013 Topology Builder supports using a SQL Server alias as the Fully Qualified Domain Name (FQDN) instead of the actual SQL Server FQDN when configuring Lync Server 2013.</span></span> <span data-ttu-id="9af8f-111">In questo modo l'FQDN effettivo di SQL Server deve essere nascosto da qualsiasi utente malintenzionato.</span><span class="sxs-lookup"><span data-stu-id="9af8f-111">This allows the actual SQL Server FQDN to be hidden from any malicious attacker.</span></span> <span data-ttu-id="9af8f-112">Inoltre, l'uso di una porta non standard oscura la porta effettiva da qualsiasi utente malintenzionato tenti di attaccare il database nella porta standard 1433, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="9af8f-112">In addition, using a non-standard port obscures the actual port from any would be attacker attempting to attack the database on the standard port 1433, as shown in the following figure.</span></span>

<span data-ttu-id="9af8f-113">![Un hacker non conosce il numero di porta da attaccare.] (images/Dn776290.2f3923e0-2bdc-416b-a66b-bf56599eb14e(OCS.15).jpg "Un hacker non conosce il numero di porta da attaccare.")</span><span class="sxs-lookup"><span data-stu-id="9af8f-113">![A hacker doesn't know the port number to attack.](images/Dn776290.2f3923e0-2bdc-416b-a66b-bf56599eb14e(OCS.15).jpg "A hacker doesn't know the port number to attack.")</span></span>

<span data-ttu-id="9af8f-114">Per avere successo nel determinare la porta che Lync Server 2013 USA per comunicare con SQL Server, l'aggressore dovrà analizzare tutte le porte per ottenere le informazioni sulla porta.</span><span class="sxs-lookup"><span data-stu-id="9af8f-114">In order to be successful in determining the port Lync Server 2013 is using to communicate with SQL Server, the attacker would need to scan all ports to obtain the port information.</span></span> <span data-ttu-id="9af8f-115">Un'analisi della porta da parte di un utente malintenzionato aumenta le probabilità che la sicurezza possa rilevare e interrompere l'istruzione.</span><span class="sxs-lookup"><span data-stu-id="9af8f-115">A port scan by an attacker increases the chances that security can detect and stop the instruction.</span></span> <span data-ttu-id="9af8f-116">Oltre ad aggiungere maggiore sicurezza con una porta non standard, puoi anche usare un alias di SQL Server per garantirti la flessibilità per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="9af8f-116">In addition to adding increased security with a non-standard port, you can also use a SQL Server alias to provide flexibility for the deployment.</span></span> <span data-ttu-id="9af8f-117">Questa operazione è utile per ridurre le modifiche alla configurazione nelle situazioni in cui è necessaria una modifica del nome di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="9af8f-117">This is valuable in order to reduce configuration changes in situations where a SQL Server name change is required.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9af8f-118">SQL Server offre due metodi di tolleranza dell'errore (clustering di failover e mirroring).</span><span class="sxs-lookup"><span data-stu-id="9af8f-118">SQL Server provides two fault tolerance methods (Failover Clustering and Mirroring).</span></span> <span data-ttu-id="9af8f-119">Entrambi i metodi di tolleranza di errore di SQL Server sono supportati usando una porta non standard di SQL Server e un alias con Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9af8f-119">Both SQL Server fault tolerance methods are supported using a SQL Server non-standard port and alias with Lync Server 2013.</span></span> <span data-ttu-id="9af8f-120">Se il backend di SQL Server usato dal pool si trova in una configurazione con mirroring, il servizio SQL browser nei server di backend di SQL Server dovrebbe essere in funzione per i server front-end per connettersi al database con mirroring quando i database non vengono superati nell'SQL con mirroring Server.</span><span class="sxs-lookup"><span data-stu-id="9af8f-120">If the SQL Server backend used by the pool is in a mirrored configuration, then the SQL browser service on the SQL Server backend servers should be running for Front End servers to connect to the mirrored database when the databases are failed over to the mirrored SQL Server.</span></span>



</div>

<span data-ttu-id="9af8f-121">Quando si configura la connettività di database di SQL Server dall'interno del generatore di topologia o quando si usa il cmdlet Install-CsDatabase, non è possibile definire in modo esplicito un numero di porta non standard di SQL Server e associarlo a un'istanza SQL.</span><span class="sxs-lookup"><span data-stu-id="9af8f-121">When configuring SQL Server database connectivity from within Topology Builder, or when using the Install-CsDatabase cmdlet, it’s not possible to explicitly define a SQL Server non-standard port number and associate it with a SQL instance.</span></span> <span data-ttu-id="9af8f-122">Per impostare una porta non standard, è necessario usare le utilità SQL Server e Windows Server.</span><span class="sxs-lookup"><span data-stu-id="9af8f-122">To set a non-standard port, you’ll need to use SQL Server and Windows Server utilities.</span></span>

<span data-ttu-id="9af8f-123">Per configurare una porta e un alias di SQL Server non standard da usare con Lync Server 2013, sarà necessario completare tre passaggi principali.</span><span class="sxs-lookup"><span data-stu-id="9af8f-123">To set up a SQL Server non-standard port and alias for use with Lync Server 2013, you will need to complete three primary steps.</span></span> <span data-ttu-id="9af8f-124">Questi passaggi sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="9af8f-124">These steps are:</span></span>

  - <span data-ttu-id="9af8f-125">Verificare che in Lync Server 2013 siano applicati gli aggiornamenti più recenti.</span><span class="sxs-lookup"><span data-stu-id="9af8f-125">Confirm that Lync Server 2013 has the Latest Updates Applied.</span></span>

  - <span data-ttu-id="9af8f-126">Configurare la porta e l'alias non standard di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="9af8f-126">Setup the SQL Server Non-Standard Port and Alias.</span></span>

  - <span data-ttu-id="9af8f-127">Configurare Lync Server 2013 con l'alias di SQL Server tramite Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="9af8f-127">Configure Lync Server 2013 with the SQL Server alias using Topology Builder.</span></span>

  - <span data-ttu-id="9af8f-128">Pubblicare la topologia e verificare il database.</span><span class="sxs-lookup"><span data-stu-id="9af8f-128">Publish the Topology, and Verify the Database.</span></span>

<div>

## <a name="confirm-that-lync-server-2013-has-the-latest-updates-applied"></a><span data-ttu-id="9af8f-129">Verificare che in Lync Server 2013 siano applicati gli aggiornamenti più recenti</span><span class="sxs-lookup"><span data-stu-id="9af8f-129">Confirm that Lync Server 2013 has the Latest Updates Applied</span></span>

<span data-ttu-id="9af8f-130">È importante impedire che Lync Server 2013 sia aggiornato.</span><span class="sxs-lookup"><span data-stu-id="9af8f-130">It is important to keep Lync Server 2013 up to date.</span></span> <span data-ttu-id="9af8f-131">Per verificare la disponibilità degli aggiornamenti più recenti e delle informazioni su come applicarli, vedere [aggiornamenti per Lync Server 2013](http://support.microsoft.com/kb/2809243).</span><span class="sxs-lookup"><span data-stu-id="9af8f-131">To check for the most recent updates and information on how to apply them, see [Updates for Lync Server 2013](http://support.microsoft.com/kb/2809243).</span></span>

</div>

<div>

## <a name="setup-the-sql-server-non-standard-port-and-alias"></a><span data-ttu-id="9af8f-132">Configurare la porta non standard e l'alias di SQL Server</span><span class="sxs-lookup"><span data-stu-id="9af8f-132">Setup the SQL Server Non-Standard Port and Alias</span></span>

<span data-ttu-id="9af8f-133">La porta e l'alias di SQL Server non standard devono essere configurati nell'istanza del database prima di poter fare riferimento a un generatore di topologia di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9af8f-133">The SQL Server non-standard port and alias must be set up on the database instance before it can be referenced from Lync Server 2013 Topology Builder.</span></span> <span data-ttu-id="9af8f-134">Per configurare una porta e un alias di SQL Server non standard, sarà necessario completare tre passaggi principali.</span><span class="sxs-lookup"><span data-stu-id="9af8f-134">To set up a SQL Server non-standard port and alias, you will have to complete three primary steps.</span></span> <span data-ttu-id="9af8f-135">Questi passaggi sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="9af8f-135">These steps are as follows:</span></span>

  - <span data-ttu-id="9af8f-136">Modificare i valori di protocollo TCP/IP predefiniti.</span><span class="sxs-lookup"><span data-stu-id="9af8f-136">Change the Default TCP/IP Protocol Values.</span></span>

  - <span data-ttu-id="9af8f-137">Creare e configurare un alias di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="9af8f-137">Create and Configure a SQL Server Alias.</span></span>

  - <span data-ttu-id="9af8f-138">Creare un record di risorse DNS (Domain Name System) (CNAME) nome canonico.</span><span class="sxs-lookup"><span data-stu-id="9af8f-138">Create a Domain Name System (DNS) Canonical Name (CNAME) Resource Record.</span></span>

<span data-ttu-id="9af8f-139">**Modificare i valori di protocollo TCP/IP predefiniti**</span><span class="sxs-lookup"><span data-stu-id="9af8f-139">**Modify the Default TCP/IP Protocol Values**</span></span>

1.  <span data-ttu-id="9af8f-140">Selezionare **Start**e scegliere **Gestione configurazione SQL Server**, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="9af8f-140">Select **Start**, and choose **SQL Server Configuration Manager**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="9af8f-141">Icona di ![SQL Server Management Studio]con(images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "l'icona di SQL Server Management Studio")</span><span class="sxs-lookup"><span data-stu-id="9af8f-141">![The SQL Server Management Studio icon](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "The SQL Server Management Studio icon")</span></span>

2.  <span data-ttu-id="9af8f-142">Nel riquadro di spostamento scegliere per espandere l' **istanza di SQL Server**, scegliere Espandi **configurazione di rete SQL Server**e scegliere **protocolli per \<il nome\>dell'istanza**, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="9af8f-142">In the navigation pane, choose to expand the **SQL Server instance**, choose to expand **SQL Server Network Configuration**, and choose **Protocols for \<instance name\>**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="9af8f-143">![Passare alle proprietà TCP/IP](images/Dn776290.3d7a964c-f17e-47fd-8f0c-535453da7fad(OCS.15).jpg "per passare alle proprietà TCP/IP")</span><span class="sxs-lookup"><span data-stu-id="9af8f-143">![Navigate to TCP/IP Properties](images/Dn776290.3d7a964c-f17e-47fd-8f0c-535453da7fad(OCS.15).jpg "Navigate to TCP/IP Properties")</span></span>

3.  <span data-ttu-id="9af8f-144">Nel riquadro destro fare clic con il pulsante destro del mouse su **TCP/IP**e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="9af8f-144">In the right pane, right-click **TCP/IP**, and select **Properties**.</span></span> <span data-ttu-id="9af8f-145">Viene visualizzata la finestra di dialogo Proprietà TCP/IP.</span><span class="sxs-lookup"><span data-stu-id="9af8f-145">The TCP/IP Properties dialog box is displayed.</span></span>

4.  <span data-ttu-id="9af8f-146">Selezionare la scheda **indirizzi IP** . La scheda indirizzi IP Mostra tutti gli indirizzi IP attivi nel server.</span><span class="sxs-lookup"><span data-stu-id="9af8f-146">Select the **IP Addresses** tab. The IP Addresses tab shows all of the active IP addresses on the server.</span></span> <span data-ttu-id="9af8f-147">Questi sono nel formato IP1, IP2, fino a IPAll, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="9af8f-147">These are in the format IP1, IP2, up to IPAll, as shown in the following figure.</span></span>
    
    <span data-ttu-id="9af8f-148">![Aprire le proprietà TCP/IP.] (images/Dn776290.ed2fd70d-1836-4ebf-80fe-09191d96585e(OCS.15).jpg "Aprire le proprietà TCP/IP.")</span><span class="sxs-lookup"><span data-stu-id="9af8f-148">![Open TCP/IP properties.](images/Dn776290.ed2fd70d-1836-4ebf-80fe-09191d96585e(OCS.15).jpg "Open TCP/IP properties.")</span></span>

5.  <span data-ttu-id="9af8f-149">Deselezionare il campo **porte dinamiche TCP** per tutti gli indirizzi IP.</span><span class="sxs-lookup"><span data-stu-id="9af8f-149">Clear the **TCP Dynamic Ports** field for all IP addresses.</span></span> <span data-ttu-id="9af8f-150">Se il campo contiene un carattere zero, significa che SQL Server è in ascolto sulle porte dinamiche.</span><span class="sxs-lookup"><span data-stu-id="9af8f-150">If the field contains a zero character, then it means SQL Server is listening on dynamic ports.</span></span> <span data-ttu-id="9af8f-151">Verificare che questi campi siano deselezionati e che non contengano uno zero.</span><span class="sxs-lookup"><span data-stu-id="9af8f-151">Make sure these fields are cleared and do not contain a zero.</span></span>

6.  <span data-ttu-id="9af8f-152">Per l'indirizzo IP che verrà usato da Lync Server per la connessione al database, verificare che **Enabled** sia impostato su **Sì**, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="9af8f-152">For the IP address that Lync Server will be using to connect to the database, make sure that **Enabled** is set to **Yes**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="9af8f-153">![Impostare Enabled come Sì per l'indirizzo IP corretto.] (images/Dn776290.7f818b91-0793-4594-8932-90447270fad9(OCS.15).jpg "Impostare Enabled come Sì per l'indirizzo IP corretto.")</span><span class="sxs-lookup"><span data-stu-id="9af8f-153">![Set enabled as Yes for the correct IP.](images/Dn776290.7f818b91-0793-4594-8932-90447270fad9(OCS.15).jpg "Set enabled as Yes for the correct IP.")</span></span>

7.  <span data-ttu-id="9af8f-154">Nella sezione **IPAll** nella parte inferiore della finestra di dialogo immettere la porta desiderata nel campo della **porta TCP** , come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="9af8f-154">In the **IPAll** section at the bottom of the dialog, enter the desired port in the **TCP Port** field, as shown in the following figure.</span></span> <span data-ttu-id="9af8f-155">In questo esempio usiamo la porta 50062, ma è possibile usare qualsiasi porta tra 49152 e 65535.</span><span class="sxs-lookup"><span data-stu-id="9af8f-155">In this example, we use port 50062, but you can use any port between 49152 and 65535.</span></span> <span data-ttu-id="9af8f-156">Queste sono le porte assegnate a un uso dinamico e privato e questo garantisce che non ci siano conflitti con altre porte usate nella distribuzione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9af8f-156">These are the ports assigned to dynamic and private use, and this ensures you won’t conflict with other ports being used in the Lync Server 2013 deployment.</span></span>
    
    <span data-ttu-id="9af8f-157">![Impostare la porta nella sezione IPAll.] (images/Dn776290.b5af53e2-7961-4664-b586-3ca8f3a17f06(OCS.15).jpg "Impostare la porta nella sezione IPAll.")</span><span class="sxs-lookup"><span data-stu-id="9af8f-157">![Set port in IPAll section.](images/Dn776290.b5af53e2-7961-4664-b586-3ca8f3a17f06(OCS.15).jpg "Set port in IPAll section.")</span></span>

8.  <span data-ttu-id="9af8f-158">Scegliere **OK** per uscire dalla finestra di dialogo Proprietà TCP/IP.</span><span class="sxs-lookup"><span data-stu-id="9af8f-158">Choose **OK** to exit the TCP/IP Properties dialog.</span></span>

9.  <span data-ttu-id="9af8f-159">Riavviare l'istanza di SQL Server selezionando **servizi SQL Server** nel riquadro sinistro di gestione configurazione SQL Server.</span><span class="sxs-lookup"><span data-stu-id="9af8f-159">Restart the SQL Server instance by selecting **SQL Server Services** in the left pane of SQL Server Configuration Manager.</span></span> <span data-ttu-id="9af8f-160">Fare quindi clic con il pulsante destro del mouse su **nome \<\> istanza di SQL Server** nel riquadro destro e scegliere **Riavvia**, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="9af8f-160">Then right-click **SQL Server \<instance name\>** in the right pane, and select **Restart**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="9af8f-161">![Reimpostare il servizio SQL Server ad esempio.] (images/Dn776290.a965c8cf-f769-4b52-bb38-c48a438cf491(OCS.15).jpg "Reimpostare il servizio SQL Server ad esempio.")</span><span class="sxs-lookup"><span data-stu-id="9af8f-161">![Reset the SQL Server service for instance.](images/Dn776290.a965c8cf-f769-4b52-bb38-c48a438cf491(OCS.15).jpg "Reset the SQL Server service for instance.")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="9af8f-162">Assicurarsi di aggiornare le impostazioni del firewall in modo che siano adatte alla nuova porta di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="9af8f-162">Make sure you update your firewall settings to accommodate the new SQL Server port.</span></span>



</div>

<span data-ttu-id="9af8f-163">**Creare e configurare un alias di SQL Server**</span><span class="sxs-lookup"><span data-stu-id="9af8f-163">**Create and Configure a SQL Server Alias**</span></span>

1.  <span data-ttu-id="9af8f-164">Selezionare **Start**e scegliere **Gestione configurazione SQL Server**, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="9af8f-164">Select **Start**, and choose **SQL Server Configuration Manager**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="9af8f-165">Icona di ![SQL Server Management Studio]con(images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "l'icona di SQL Server Management Studio")</span><span class="sxs-lookup"><span data-stu-id="9af8f-165">![The SQL Server Management Studio icon](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "The SQL Server Management Studio icon")</span></span>

2.  <span data-ttu-id="9af8f-166">Nel riquadro sinistro scegliere Espandi **istanza di SQL Server**, scegliere di espandere la **configurazione della versione\> di \<SQL Native Client**e quindi scegliere **alias**, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="9af8f-166">In the left pane, choose to expand **SQL Server instance**, choose to expand **SQL Native Client \<version\> Configuration**, and then choose **Aliases**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="9af8f-167">![Alias in Gestione configurazione SQL Server.] (images/Dn776290.95341826-55d7-425f-ae19-d47d6668c5d8(OCS.15).jpg "Alias in Gestione configurazione SQL Server.")</span><span class="sxs-lookup"><span data-stu-id="9af8f-167">![Aliases in SQL Server Configuration Manager.](images/Dn776290.95341826-55d7-425f-ae19-d47d6668c5d8(OCS.15).jpg "Aliases in SQL Server Configuration Manager.")</span></span>

3.  <span data-ttu-id="9af8f-168">Fare clic con il pulsante destro del mouse su **alias**e scegliere **nuovo alias.**</span><span class="sxs-lookup"><span data-stu-id="9af8f-168">Right-click **Aliases**, and select **New Alias…**.</span></span>

4.  <span data-ttu-id="9af8f-169">Immettere il **nome dell'alias**, il **numero di porta**, il **protocollo**e il **Server**, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="9af8f-169">Enter the **Alias Name**, **Port Number**, **Protocol**, and **Server**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="9af8f-170">![Creazione di un nuovo alias]per(images/Dn776290.03653588-aecf-4fdd-b58a-95f5b372d478(OCS.15).jpg "la creazione di un nuovo alias")</span><span class="sxs-lookup"><span data-stu-id="9af8f-170">![Creating a new alias](images/Dn776290.03653588-aecf-4fdd-b58a-95f5b372d478(OCS.15).jpg "Creating a new alias")</span></span>
    
    <div>
    

    > [!CAUTION]  
    > <span data-ttu-id="9af8f-171">Assicurarsi di immettere la stessa porta non standard usata nel passaggio precedente, perché la porta verrà ascoltata da SQL Server.</span><span class="sxs-lookup"><span data-stu-id="9af8f-171">Make sure to enter the same non-standard port you used in the previous step since that is the port SQL Server will be listening on.</span></span> <span data-ttu-id="9af8f-172">Se un alias configurato si connette all'istanza o al nome FQDN di SQL Server errato, disabilitare e quindi riattivare il protocollo di rete associato.</span><span class="sxs-lookup"><span data-stu-id="9af8f-172">If a configured alias is connecting to the wrong SQL Server FQDN or Instance, disable and then re-enable the associated network protocol.</span></span> <span data-ttu-id="9af8f-173">Questa operazione cancella le informazioni sulla connessione memorizzate nella cache e consente al client di connettersi correttamente.</span><span class="sxs-lookup"><span data-stu-id="9af8f-173">Doing this clears any cached connection information and allows the client to connect correctly.</span></span>

    
    </div>

<span data-ttu-id="9af8f-174">**Creare un record di risorse DNS CNAME**</span><span class="sxs-lookup"><span data-stu-id="9af8f-174">**Create a DNS CNAME Resource Record**</span></span>

1.  <span data-ttu-id="9af8f-175">Accedere al computer per la gestione del DNS.</span><span class="sxs-lookup"><span data-stu-id="9af8f-175">Sign into the computer managing DNS.</span></span>

2.  <span data-ttu-id="9af8f-176">Selezionare **Start**e scegliere **Server Manager**, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="9af8f-176">Select **Start**, and choose **Server Manager**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="9af8f-177">![Apertura]di Server Manager che(images/Dn776290.3e4bd8ad-2a65-4a05-af40-c8dd3583bc8f(OCS.15).jpg "apre Server Manager")</span><span class="sxs-lookup"><span data-stu-id="9af8f-177">![Opening Server Manager](images/Dn776290.3e4bd8ad-2a65-4a05-af40-c8dd3583bc8f(OCS.15).jpg "Opening Server Manager")</span></span>

3.  <span data-ttu-id="9af8f-178">Scegliere l'elenco a discesa **strumenti** e selezionare **DNS**, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="9af8f-178">Choose the **Tools** drop-down, and select **DNS**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="9af8f-179">![Apertura di DNS da Server Manager.] (images/Dn776290.415e1da1-7c9a-4a4e-a896-ca34a76aaeff(OCS.15).jpg "Apertura di DNS da Server Manager.")</span><span class="sxs-lookup"><span data-stu-id="9af8f-179">![Opening DNS from Server Manager.](images/Dn776290.415e1da1-7c9a-4a4e-a896-ca34a76aaeff(OCS.15).jpg "Opening DNS from Server Manager.")</span></span>

4.  <span data-ttu-id="9af8f-180">Nel riquadro sinistro espandere il nodo nome server, espandere il nodo zone di ricerca in avanti e scegliere il dominio pertinente.</span><span class="sxs-lookup"><span data-stu-id="9af8f-180">In the left pane, expand the server name node, expand the Forward Lookup Zones node, and choose the relevant domain.</span></span>

5.  <span data-ttu-id="9af8f-181">Fare clic con il pulsante destro del mouse sul dominio e scegliere **nuovo alias (CNAME)...**, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="9af8f-181">Right-click the domain, and select **New Alias (CNAME)…**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="9af8f-182">![Selezione dell'opzione per creare un nuovo alias CNAME](images/Dn776290.abe66cca-b53c-427a-9094-1a59dc6840ca(OCS.15).jpg "selezionando l'opzione per creare un nuovo alias CNAME")</span><span class="sxs-lookup"><span data-stu-id="9af8f-182">![Selecting option to create a new alias CNAME](images/Dn776290.abe66cca-b53c-427a-9094-1a59dc6840ca(OCS.15).jpg "Selecting option to create a new alias CNAME")</span></span>

6.  <span data-ttu-id="9af8f-183">Immettere il **nome dell'alias** e l' **FQDN per SQL Server**, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="9af8f-183">Enter the **Alias Name** and the **FQDN for SQL Server**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="9af8f-184">![Riempimento della finestra di dialogo nuovo alias CNAME.] (images/Dn776290.dd0ebd2d-3407-4459-8bd9-2b389a7bc440(OCS.15).jpg "Riempimento della finestra di dialogo nuovo alias CNAME.")</span><span class="sxs-lookup"><span data-stu-id="9af8f-184">![Filling in the new alias CNAME dialog.](images/Dn776290.dd0ebd2d-3407-4459-8bd9-2b389a7bc440(OCS.15).jpg "Filling in the new alias CNAME dialog.")</span></span>

7.  <span data-ttu-id="9af8f-185">Scegliere **OK** per salvare il CNAME e visualizzarlo in DNS Manager.</span><span class="sxs-lookup"><span data-stu-id="9af8f-185">Choose **OK** to save the CNAME and view it in DNS Manager.</span></span>

</div>

<div>

## <a name="validate-database-connectivity"></a><span data-ttu-id="9af8f-186">Convalidare la connettività del database</span><span class="sxs-lookup"><span data-stu-id="9af8f-186">Validate Database Connectivity</span></span>

<span data-ttu-id="9af8f-187">Esistono molti modi diversi per verificare che funzioni.</span><span class="sxs-lookup"><span data-stu-id="9af8f-187">There are many different ways to make sure it is working.</span></span> <span data-ttu-id="9af8f-188">Si vuole verificare che il database di SQL Server sia in ascolto sulla porta specificata usando l'alias.</span><span class="sxs-lookup"><span data-stu-id="9af8f-188">You want to make sure that the SQL Server database is listening on the specified port using the alias.</span></span> <span data-ttu-id="9af8f-189">Un controllo rapido può essere completato usando i comandi **netstat** e **Telnet** .</span><span class="sxs-lookup"><span data-stu-id="9af8f-189">A quick check can be completed using the **netstat** and **telnet** commands.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9af8f-190">Client Telnet è una funzionalità fornita con Windows Server, ma che deve essere installata.</span><span class="sxs-lookup"><span data-stu-id="9af8f-190">Telnet Client is a Feature that comes with Windows Server but that must be installed.</span></span> <span data-ttu-id="9af8f-191">Una caratteristica di Windows Server può essere installata aprendo Server Manager e selezionando Aggiungi ruoli e funzionalità dal menu Gestisci.</span><span class="sxs-lookup"><span data-stu-id="9af8f-191">A Windows Server Feature can be installed by opening Server Manager and selecting Add Roles and Features from the Manage menu.</span></span>



</div>

<span data-ttu-id="9af8f-192">**Usare netstat e Telnet per verificare la connettività del database**</span><span class="sxs-lookup"><span data-stu-id="9af8f-192">**Use netstat and telnet to verify database connectivity**</span></span>

1.  <span data-ttu-id="9af8f-193">Selezionare **Start**e digitare **cmd** per aprire un prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="9af8f-193">Select **Start**, and type **cmd** to open a command prompt.</span></span>

2.  <span data-ttu-id="9af8f-194">Digitare **netstat-a-f**e verificare che SQL Server sia in uso con la porta corretta, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="9af8f-194">Type **netstat -a -f**, and confirm that SQL Server is running with the correct port, as shown in the following figure.</span></span>
    
    <span data-ttu-id="9af8f-195">![Usare netstat per verificare la porta.] (images/Dn776290.4ff3a1b2-c5eb-4496-8be7-374c351fa027(OCS.15).jpg "Usare netstat per verificare la porta.")</span><span class="sxs-lookup"><span data-stu-id="9af8f-195">![Using netstat to verify port.](images/Dn776290.4ff3a1b2-c5eb-4496-8be7-374c351fa027(OCS.15).jpg "Using netstat to verify port.")</span></span>

3.  <span data-ttu-id="9af8f-196">Digitare \*\*Telnet \<alias\> \<Port \# \*\* per confermare la connessione all'istanza di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="9af8f-196">Type **telnet \<alias name\> \<port \#\>** to confirm the connection to the SQL Server instance.</span></span> <span data-ttu-id="9af8f-197">Se la connessione ha esito positivo, Telnet si connette e non dovrebbe essere visualizzato un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="9af8f-197">If the connection is successful, telnet will connect and you shouldn’t see an error.</span></span> <span data-ttu-id="9af8f-198">Questo dimostra che l'istanza di SQL Server sta ascoltando la porta corretta con l'alias corretto.</span><span class="sxs-lookup"><span data-stu-id="9af8f-198">This shows that the SQL Server instance is listening on the correct port with the correct alias.</span></span> <span data-ttu-id="9af8f-199">In caso di problemi di connessione al database di SQL Server, Telnet Mostra un errore che la connessione non può essere eseguita.</span><span class="sxs-lookup"><span data-stu-id="9af8f-199">If there’s a problem connecting to the SQL Server database, then telnet shows an error that the connection cannot be made.</span></span> <span data-ttu-id="9af8f-200">Ora che è stata selezionata la connettività del database nel server di database, è possibile eseguire la stessa operazione da Lync Server (tramite la rete) e verificare che non ci siano firewall che bloccano l'accesso lungo il percorso.</span><span class="sxs-lookup"><span data-stu-id="9af8f-200">Now that you have checked database connectivity on the database server, you can do the same thing from Lync Server (over the network) and make sure there aren’t any firewalls blocking access along the way.</span></span>

</div>

<div>

## <a name="conclusion"></a><span data-ttu-id="9af8f-201">Conclusione</span><span class="sxs-lookup"><span data-stu-id="9af8f-201">Conclusion</span></span>

<span data-ttu-id="9af8f-202">Dopo aver configurato l'alias di SQL Server, è possibile usarlo per creare una topologia di Lync Server 2013 nello strumento generatore di topologia.</span><span class="sxs-lookup"><span data-stu-id="9af8f-202">Once the SQL Server alias has been configured, you can use it to create a Lync Server 2013 topology in the Topology Builder tool.</span></span> <span data-ttu-id="9af8f-203">Per altre informazioni sulle topologie, vedere [definizione e configurazione della topologia in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span><span class="sxs-lookup"><span data-stu-id="9af8f-203">For more information about topologies, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9af8f-204">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9af8f-204">See Also</span></span>


<span data-ttu-id="9af8f-205">[Microsoft Lync Server 2013](microsoft-lync-server-2013.md) 
[pianificazione della sicurezza in Lync Server 2013](lync-server-2013-planning-for-security.md)</span><span class="sxs-lookup"><span data-stu-id="9af8f-205">[Microsoft Lync Server 2013](microsoft-lync-server-2013.md) 
[Planning for security in Lync Server 2013](lync-server-2013-planning-for-security.md)</span></span>  
[<span data-ttu-id="9af8f-206">Definizione e configurazione della topologia in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9af8f-206">Defining and configuring the topology in Lync Server 2013</span></span>](lync-server-2013-defining-and-configuring-the-topology.md)  
[<span data-ttu-id="9af8f-207">Distribuzione di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9af8f-207">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

