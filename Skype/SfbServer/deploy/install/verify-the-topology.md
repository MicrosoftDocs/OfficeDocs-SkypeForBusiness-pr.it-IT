---
title: Verificare la topologia in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/14/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a4f4bad1-fc59-47ce-a3ea-b1b893769db6
description: "Riepilogo: informazioni su come verificare che la topologia di Skype for Business Server e i server Active Directory funzionino come previsto. Scaricare una versione di valutazione gratuita di Skype for Business Server dal Microsoft Evaluation Center all' https://www.microsoft.com/evalcenter/evaluate-skype-for-business-serverIndirizzo:."
ms.openlocfilehash: aa631e5b08ff8cbe9cb6db17009f286dcc975679
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41791714"
---
# <a name="verify-the-topology-in-skype-for-business-server"></a><span data-ttu-id="9aa63-104">Verificare la topologia in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="9aa63-104">Verify the topology in Skype for Business Server</span></span>
 
<span data-ttu-id="9aa63-105">**Riepilogo:** Informazioni su come verificare che la topologia di Skype for Business Server e i server Active Directory funzionino come previsto.</span><span class="sxs-lookup"><span data-stu-id="9aa63-105">**Summary:** Learn how to verify the Skype for Business Server topology and Active Directory servers are working as expected.</span></span> <span data-ttu-id="9aa63-106">Scaricare una versione di valutazione gratuita di Skype for Business Server dal [Microsoft Evaluation Center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span><span class="sxs-lookup"><span data-stu-id="9aa63-106">Download a free trial of Skype for Business Server from the [Microsoft Evaluation center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="9aa63-107">Dopo avere pubblicato la topologia e i componenti di sistema di Skype for Business Server installati in ognuno dei server della topologia, si è pronti per verificare che la topologia funzioni come previsto.</span><span class="sxs-lookup"><span data-stu-id="9aa63-107">After you have the topology published and the Skype for Business Server system components installed on each of the servers in the topology, you are ready to verify that the topology is working as expected.</span></span> <span data-ttu-id="9aa63-108">Ciò include verificare che la configurazione si sia propagata a tutti i server di Active Directory in modo che l'intero dominio sappia che Skype for business è disponibile nel dominio.</span><span class="sxs-lookup"><span data-stu-id="9aa63-108">This includes verifying that the configuration has propagated out to all of the Active Directory servers so that the entire domain knows Skype for Business is available in the domain.</span></span> <span data-ttu-id="9aa63-109">È possibile eseguire i passaggi da 1 a 5 in qualsiasi ordine.</span><span class="sxs-lookup"><span data-stu-id="9aa63-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="9aa63-110">Tuttavia, è necessario eseguire i passaggi 6, 7 e 8 in ordine e dopo i passaggi da 1 a 5, come illustrato nel diagramma.</span><span class="sxs-lookup"><span data-stu-id="9aa63-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="9aa63-111">La verifica della topologia è il passaggio 8 di 8.</span><span class="sxs-lookup"><span data-stu-id="9aa63-111">Verifying the topology is step 8 of 8.</span></span>
  
![Diagramma di panoramica.](../../media/c8698b53-1282-4978-a9a6-ca3f7a778f60.png)
  
## <a name="test-the-front-end-pool-deployment"></a><span data-ttu-id="9aa63-113">Testare la distribuzione del pool Front-End</span><span class="sxs-lookup"><span data-stu-id="9aa63-113">Test the Front End pool deployment</span></span>

<span data-ttu-id="9aa63-114">Il passaggio finale consiste nel testare il pool Front-end e verificare che i client Skype for business possano comunicare tra loro.</span><span class="sxs-lookup"><span data-stu-id="9aa63-114">The final step is to test the Front End pool and confirm that Skype for Business clients can communicate with each other.</span></span> 
  
### <a name="add-users-and-verify-client-connectivity"></a><span data-ttu-id="9aa63-115">Aggiungere utenti e verificare la connettività del client</span><span class="sxs-lookup"><span data-stu-id="9aa63-115">Add users and verify client connectivity</span></span>

1. <span data-ttu-id="9aa63-116">Usare i computer e gli utenti di Active Directory per aggiungere l'oggetto utente di Active Directory del ruolo di amministratore per la distribuzione di Skype for Business Server (in cui è installato il pannello di controllo di Skype for Business Server) nel gruppo **CsAdministrator** .</span><span class="sxs-lookup"><span data-stu-id="9aa63-116">Use Active Directory Computers and Users to add the Active Directory user object of the administrator role for the Skype for Business Server deployment (on which Skype for Business Server Control Panel is installed) to the **CSAdministrator** group.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="9aa63-117">Se non si aggiungono gli utenti e i gruppi appropriati al gruppo CsAdministors, viene visualizzato un messaggio di errore quando si apre il pannello di controllo di Skype for Business Server che legge "non autorizzato: l'accesso è negato a causa di un errore di autorizzazione del controllo di accesso basato sui ruoli (RBAC) ."</span><span class="sxs-lookup"><span data-stu-id="9aa63-117">If you do not add the appropriate users and groups to the CsAdministors group, you will receive an error when you open Skype for Business Server Control Panel which reads, "Unauthorized: Access is denied due to a role-based access control (RBAC) authorization failure."</span></span> 
  
2. <span data-ttu-id="9aa63-118">Se l'oggetto utente è attualmente connesso, disconnettersi e quindi accedere di nuovo per registrare la nuova assegnazione del gruppo.</span><span class="sxs-lookup"><span data-stu-id="9aa63-118">If the user object is currently logged on, log off and then log on again to register the new group assignment.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9aa63-119">L'account utente non può essere l'amministratore locale di qualsiasi server che esegua Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="9aa63-119">The user account cannot be the local administrator of any server running Skype for Business Server.</span></span> 
  
3. <span data-ttu-id="9aa63-120">Usare l'account amministrativo per accedere al computer in cui è installato il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="9aa63-120">Use the administrative account to log on to the computer where Skype for Business Server Control Panel is installed.</span></span>
    
4. <span data-ttu-id="9aa63-121">Avviare il pannello di controllo di Skype for Business Server e quindi specificare le credenziali, se richiesto.</span><span class="sxs-lookup"><span data-stu-id="9aa63-121">Start Skype for Business Server Control Panel, and then provide credentials, if prompted.</span></span> <span data-ttu-id="9aa63-122">Il pannello di controllo di Skype for Business Server Visualizza le informazioni sulla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="9aa63-122">Skype for Business Server Control Panel displays deployment information.</span></span>
    
5. <span data-ttu-id="9aa63-123">Nella barra di spostamento sinistra fare clic su **topologia**e quindi verificare che lo stato del servizio visualizzi un computer con una freccia verde e che un segno di spunta verde per lo stato di replica sia accanto a ogni ruolo di Skype for Business Server distribuito e portato online.</span><span class="sxs-lookup"><span data-stu-id="9aa63-123">In the left navigation bar, click **Topology**, and then confirm that the service status shows a computer with a green arrow and that a green check mark for replication status is next to each Skype for Business Server role that has been deployed and brought online.</span></span> 
    
6. <span data-ttu-id="9aa63-124">Sulla barra di spostamento sinistra fare clic su **utenti**e quindi su **Abilita utenti**.</span><span class="sxs-lookup"><span data-stu-id="9aa63-124">In the left navigation bar, click **Users**, and then click **Enable users**.</span></span> 
    
7. <span data-ttu-id="9aa63-125">Nella **nuova pagina utente di Skype for Business Server** fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="9aa63-125">On the **New Skype for Business Server User** page, click **Add**.</span></span>
    
8. <span data-ttu-id="9aa63-126">Per definire i parametri di ricerca per gli oggetti che si desidera trovare, nella pagina **Seleziona da Active Directory** è possibile selezionare **ricerca**e quindi fare clic su **Aggiungi filtro**.</span><span class="sxs-lookup"><span data-stu-id="9aa63-126">To define search parameters for the objects you want to find, on the **Select from Active Directory** page, you can select **Search**, and then optionally click **Add Filter**.</span></span> <span data-ttu-id="9aa63-127">È anche possibile selezionare **ricerca LDAP** e immettere un'espressione LDAP per filtrare o limitare gli oggetti che verranno restituiti.</span><span class="sxs-lookup"><span data-stu-id="9aa63-127">You can also select **LDAP search** and enter an LDAP expression to filter or limit the objects that will be returned.</span></span> <span data-ttu-id="9aa63-128">Dopo aver deciso le opzioni di ricerca, fare clic su **trova**.</span><span class="sxs-lookup"><span data-stu-id="9aa63-128">After you have decided on your Search options, click **Find**.</span></span>
    
9. <span data-ttu-id="9aa63-129">Nel riquadro Risultati ricerca selezionare gli utenti che si desidera aggiungere e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="9aa63-129">In the Search results pane, select the users you want to add, and then click **OK**.</span></span>
    
10. <span data-ttu-id="9aa63-130">Nella **nuova pagina utente di Skype for Business Server** gli utenti selezionati si trovano nella visualizzazione **utenti** .</span><span class="sxs-lookup"><span data-stu-id="9aa63-130">On the **New Skype for Business Server User** page, the users you selected are in the **Users** display.</span></span> <span data-ttu-id="9aa63-131">Nell'elenco **Assegna utenti a un pool** selezionare il server in cui devono risiedere gli utenti.</span><span class="sxs-lookup"><span data-stu-id="9aa63-131">In the **Assign users to a pool** list, select the server where the users should reside.</span></span>
    
    <span data-ttu-id="9aa63-132">Di seguito è riportato un elenco di opzioni che è possibile usare per configurare gli oggetti.</span><span class="sxs-lookup"><span data-stu-id="9aa63-132">The following is a list of options you can use to configure the objects.</span></span>
    
    - <span data-ttu-id="9aa63-133">**Generare l'URI SIP dell'utente**</span><span class="sxs-lookup"><span data-stu-id="9aa63-133">**Generate user's SIP URI**</span></span>
    
    - <span data-ttu-id="9aa63-134">**Telefonia**</span><span class="sxs-lookup"><span data-stu-id="9aa63-134">**Telephony**</span></span>
    
    - <span data-ttu-id="9aa63-135">**URI di linea**</span><span class="sxs-lookup"><span data-stu-id="9aa63-135">**Line URI**</span></span>
    
    - <span data-ttu-id="9aa63-136">**Criteri di conferenza**</span><span class="sxs-lookup"><span data-stu-id="9aa63-136">**Conferencing policy**</span></span>
    
    - <span data-ttu-id="9aa63-137">**Criteri di versione client**</span><span class="sxs-lookup"><span data-stu-id="9aa63-137">**Client version policy**</span></span>
    
    - <span data-ttu-id="9aa63-138">**Criteri PIN**</span><span class="sxs-lookup"><span data-stu-id="9aa63-138">**PIN policy**</span></span>
    
    - <span data-ttu-id="9aa63-139">**Criteri di accesso esterno**</span><span class="sxs-lookup"><span data-stu-id="9aa63-139">**External access policy**</span></span>
    
    - <span data-ttu-id="9aa63-140">**Criteri di archiviazione**</span><span class="sxs-lookup"><span data-stu-id="9aa63-140">**Archiving policy**</span></span>
    
    - <span data-ttu-id="9aa63-141">**Criteri posizione**</span><span class="sxs-lookup"><span data-stu-id="9aa63-141">**Location policy**</span></span>
    
    - <span data-ttu-id="9aa63-142">**Criteri client**</span><span class="sxs-lookup"><span data-stu-id="9aa63-142">**Client policy**</span></span>
    
    <span data-ttu-id="9aa63-143">Per testare le funzionalità di base, selezionare l'opzione che si preferisce per l'impostazione **URI SIP dell'utente** (le altre opzioni nella configurazione usano le impostazioni predefinite) e quindi fare clic su **Abilita**, come illustrato nella figura.</span><span class="sxs-lookup"><span data-stu-id="9aa63-143">To test the basic functionality, select the option you prefer for the **Generate user's SIP URI** setting (the other options in the configuration use default settings), and then click **Enable**, as shown in the figure.</span></span>
    
     ![Abilitare gli utenti nel pannello di controllo.](../../media/7ee8717d-9a1f-4864-8f45-71071c88878f.png)
  
11. <span data-ttu-id="9aa63-145">Viene visualizzata una pagina di riepilogo che mostra un segno di spunta nella colonna **Enabled** per indicare che gli utenti sono impostati.</span><span class="sxs-lookup"><span data-stu-id="9aa63-145">A summary page is displayed that shows a check mark in the **Enabled** column to indicate that the users are setup.</span></span> <span data-ttu-id="9aa63-146">Nella colonna **indirizzo SIP** viene visualizzato l'indirizzo necessario per la configurazione di accesso dell'utente.</span><span class="sxs-lookup"><span data-stu-id="9aa63-146">The **SIP address** column displays the address you need for the user sign-in configuration.</span></span>
    
     ![Utenti aggiunti al pannello di controllo di Skype for Business Server.](../../media/8960548a-8d6d-44c5-bc01-6f9fb11b7588.png)
  
12. <span data-ttu-id="9aa63-148">È necessario registrare un utente in un computer a cui è associato il dominio e un altro utente in un altro computer del dominio.</span><span class="sxs-lookup"><span data-stu-id="9aa63-148">Log one user on to a computer that is joined to the domain and another user on to another computer in the domain.</span></span>
    
13. <span data-ttu-id="9aa63-149">Installare client Skype for business in ognuno dei due computer client e quindi verificare che entrambi gli utenti possano accedere a Skype for Business Server e inviare messaggi istantanei a vicenda.</span><span class="sxs-lookup"><span data-stu-id="9aa63-149">Install Skype for Business client on each of the two client computers, and then verify that both users can sign in to Skype for Business Server and can send instant messages to each other.</span></span>
    

