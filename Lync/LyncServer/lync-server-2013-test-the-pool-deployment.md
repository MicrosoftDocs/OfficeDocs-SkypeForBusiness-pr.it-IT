---
title: 'Lync Server 2013: Testare la distribuzione di pool'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test the pool deployment
ms:assetid: ffd80617-155a-4041-bbeb-74503e7938dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413092(v=OCS.15)
ms:contentKeyID: 48185976
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cfde95e7323d68f05e78f670a6b027a5949f0169
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746066"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-the-pool-deployment-in-lync-server-2013"></a><span data-ttu-id="9e449-102">Testare la distribuzione di pool in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9e449-102">Test the pool deployment in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9e449-103">_**Argomento Ultima modifica:** 2013-09-25_</span><span class="sxs-lookup"><span data-stu-id="9e449-103">_**Topic Last Modified:** 2013-09-25_</span></span>

<span data-ttu-id="9e449-104">La procedura seguente descrive come testare la distribuzione del pool Front-end.</span><span class="sxs-lookup"><span data-stu-id="9e449-104">The following procedure describes how to test the deployment of the Front End pool.</span></span>

<div>

## <a name="to-test-the-pool-deployment"></a><span data-ttu-id="9e449-105">Per testare la distribuzione del pool</span><span class="sxs-lookup"><span data-stu-id="9e449-105">To test the pool deployment</span></span>

1.  <span data-ttu-id="9e449-106">Usare i computer e gli utenti di Active Directory per aggiungere l'oggetto utente di Active Directory del ruolo di amministratore per la distribuzione di Lync Server 2013 (in cui è installato il pannello di controllo di Lync Server 2013) al gruppo **CsAdministrator** .</span><span class="sxs-lookup"><span data-stu-id="9e449-106">Use Active Directory Computers and Users to add the Active Directory user object of the administrator role for the Lync Server 2013 deployment (on which Lync Server 2013 Control Panel is installed) to the **CSAdministrator** group.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="9e449-107">Se non si aggiungono gli utenti e i gruppi appropriati al gruppo CsAdministors, viene visualizzato un messaggio di errore quando si apre il pannello di controllo di Lync Server, in cui viene indicato che non è stato autorizzato l'accesso a causa di un errore di autorizzazione del controllo di accesso basato sui ruoli (RBAC).</span><span class="sxs-lookup"><span data-stu-id="9e449-107">If you do not add the appropriate users and groups to the CsAdministors group, you will receive an error when opening Lync Server Control Panel, which states that “Unauthorized: Access is denied due to a role-based access control (RBAC) authorization failure.”</span></span>

    
    </div>

2.  <span data-ttu-id="9e449-108">Se l'oggetto utente è attualmente connesso, disconnettersi e quindi accedere di nuovo per registrare la nuova assegnazione del gruppo.</span><span class="sxs-lookup"><span data-stu-id="9e449-108">If the user object is currently logged on, log off and then log on again to register the new group assignment.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9e449-109">L'account utente non può essere l'amministratore locale di qualsiasi server che esegua Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9e449-109">The user account cannot be the local administrator of any server running Lync Server 2013.</span></span>

    
    </div>

3.  <span data-ttu-id="9e449-110">Usare l'account amministrativo per accedere al computer in cui è installato il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9e449-110">Use the administrative account to log on to the computer where Lync Server Control Panel is installed.</span></span>

4.  <span data-ttu-id="9e449-111">Avviare il pannello di controllo di Lync Server e quindi specificare le credenziali, se richiesto.</span><span class="sxs-lookup"><span data-stu-id="9e449-111">Start Lync Server Control Panel, and then provide credentials, if prompted.</span></span> <span data-ttu-id="9e449-112">Il pannello di controllo di Lync Server Visualizza le informazioni sulla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="9e449-112">Lync Server Control Panel displays deployment information.</span></span>

5.  <span data-ttu-id="9e449-113">Nella barra di spostamento sinistra fare clic su **topologia**e quindi verificare che lo stato del servizio visualizzi un computer con una freccia verde e che un segno di spunta verde per lo stato di replica sia accanto a ogni ruolo di Lync Server Server distribuito e portato online.</span><span class="sxs-lookup"><span data-stu-id="9e449-113">In the left navigation bar, click **Topology**, and then confirm that the service status shows a computer with a green arrow and that a green check mark for replication status is next to each Lync Server server role that has been deployed and brought online.</span></span>

6.  <span data-ttu-id="9e449-114">Sulla barra di spostamento sinistra fare clic su **utenti**e quindi su **Abilita utenti**.</span><span class="sxs-lookup"><span data-stu-id="9e449-114">In the left navigation bar, click **Users**, and then click **Enable users**.</span></span>

7.  <span data-ttu-id="9e449-115">Nella pagina **nuovo utente di Lync Server** fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="9e449-115">On the **New Lync Server User** page, click **Add**.</span></span>

8.  <span data-ttu-id="9e449-116">Per definire i parametri di ricerca per gli oggetti che si desidera trovare, nella pagina **Seleziona da Active Directory** è possibile selezionare **ricerca**e quindi fare clic su **Aggiungi filtro**.</span><span class="sxs-lookup"><span data-stu-id="9e449-116">To define search parameters for the objects you want to find, on the **Select from Active Directory** page, you can select **Search**, and then optionally click **Add Filter**.</span></span> <span data-ttu-id="9e449-117">È anche possibile selezionare **ricerca LDAP** e immettere un'espressione LDAP per filtrare o limitare gli oggetti che verranno restituiti.</span><span class="sxs-lookup"><span data-stu-id="9e449-117">You can also select **LDAP search** and enter an LDAP expression to filter or limit the objects that will be returned.</span></span> <span data-ttu-id="9e449-118">Dopo aver deciso le opzioni di ricerca, vedere Clink **Find**.</span><span class="sxs-lookup"><span data-stu-id="9e449-118">After you have decided on your Search options, clink **Find**.</span></span>

9.  <span data-ttu-id="9e449-119">Nel riquadro Risultati ricerca selezionare tutti gli oggetti per la sessione di ricerca e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="9e449-119">In the Search results pane, select all the objects for this search session, and then click **OK**.</span></span>

10. <span data-ttu-id="9e449-120">Nella **nuova pagina utente di Lync Server** l'oggetto o gli oggetti selezionati si trovano nella visualizzazione **utenti** .</span><span class="sxs-lookup"><span data-stu-id="9e449-120">On the **New Lync Server User** page, the object or objects you selected are in the **Users** display.</span></span> <span data-ttu-id="9e449-121">Nell'elenco **Assegna utenti a un pool** selezionare il server in cui devono essere assegnati gli oggetti.</span><span class="sxs-lookup"><span data-stu-id="9e449-121">In the **Assign users to a pool** list, select the server where the objects should be homed.</span></span>
    
    <span data-ttu-id="9e449-122">Di seguito sono riportate alcune opzioni per la configurazione degli oggetti.</span><span class="sxs-lookup"><span data-stu-id="9e449-122">Following are a number of options for configuring the objects.</span></span>
    
      - <span data-ttu-id="9e449-123">**Generare l'URI SIP dell'utente**</span><span class="sxs-lookup"><span data-stu-id="9e449-123">**Generate user’s SIP URI**</span></span>
    
      - <span data-ttu-id="9e449-124">**Telefonia**</span><span class="sxs-lookup"><span data-stu-id="9e449-124">**Telephony**</span></span>
    
      - <span data-ttu-id="9e449-125">**URI di linea**</span><span class="sxs-lookup"><span data-stu-id="9e449-125">**Line URI**</span></span>
    
      - <span data-ttu-id="9e449-126">**Criteri di conferenza**</span><span class="sxs-lookup"><span data-stu-id="9e449-126">**Conferencing policy**</span></span>
    
      - <span data-ttu-id="9e449-127">**Criteri di versione client**</span><span class="sxs-lookup"><span data-stu-id="9e449-127">**Client version policy**</span></span>
    
      - <span data-ttu-id="9e449-128">**Criteri PIN**</span><span class="sxs-lookup"><span data-stu-id="9e449-128">**PIN policy**</span></span>
    
      - <span data-ttu-id="9e449-129">**Criteri di accesso esterno**</span><span class="sxs-lookup"><span data-stu-id="9e449-129">**External access policy**</span></span>
    
      - <span data-ttu-id="9e449-130">**Criteri di archiviazione**</span><span class="sxs-lookup"><span data-stu-id="9e449-130">**Archiving policy**</span></span>
    
      - <span data-ttu-id="9e449-131">**Criteri posizione**</span><span class="sxs-lookup"><span data-stu-id="9e449-131">**Location policy**</span></span>
    
      - <span data-ttu-id="9e449-132">**Criteri client**</span><span class="sxs-lookup"><span data-stu-id="9e449-132">**Client policy**</span></span>
    
    <span data-ttu-id="9e449-133">Per testare le funzionalità di base, selezionare l'opzione preferita per l'impostazione **URI SIP dell'utente** (le altre opzioni della configurazione utilizzeranno le impostazioni predefinite) e quindi fare clic su **Abilita**.</span><span class="sxs-lookup"><span data-stu-id="9e449-133">For the purposes of testing the basic functionality, select the option you prefer for the **Generate user’s SIP URI** setting (the other options in the configuration will use default settings), and then click **Enable**.</span></span>

11. <span data-ttu-id="9e449-134">Viene visualizzata una pagina di riepilogo che mostra un segno di spunta nella colonna **Enabled** per indicare che gli oggetti sono ora pronti per l'uso.</span><span class="sxs-lookup"><span data-stu-id="9e449-134">A summary page is displayed that shows a check mark in the **Enabled** column to indicate that the objects are now ready for use.</span></span> <span data-ttu-id="9e449-135">Nella colonna **indirizzo SIP** viene visualizzato l'indirizzo necessario per la configurazione di accesso dell'utente.</span><span class="sxs-lookup"><span data-stu-id="9e449-135">The **SIP address** column displays the address you need for the user sign-in configuration.</span></span>

12. <span data-ttu-id="9e449-136">È necessario registrare un utente in un computer collegato al dominio e un altro utente in un altro computer del dominio.</span><span class="sxs-lookup"><span data-stu-id="9e449-136">Log one user on to a computer that is joined to the domain, and another user on to another computer in the domain.</span></span>

13. <span data-ttu-id="9e449-137">Installare Lync 2013 in ognuno dei due computer client e verificare che entrambi gli utenti possano accedere a Lync Server 2013 e inviare messaggi istantanei.</span><span class="sxs-lookup"><span data-stu-id="9e449-137">Install Lync 2013 on each of the two client computers, and then verify that both users can sign in to Lync Server 2013 and can send instant messages to each other.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9e449-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9e449-138">See Also</span></span>


[<span data-ttu-id="9e449-139">Distribuzione di client e dispositivi in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9e449-139">Deploying clients and devices in Lync Server 2013</span></span>](lync-server-2013-deploying-clients-and-devices.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

