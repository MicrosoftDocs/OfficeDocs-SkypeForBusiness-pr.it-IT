---
title: Gestire i database con un gruppo di disponibilità AlwaysOn in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 026c4469-f471-4e4f-a77d-a7d22a925e5a
description: 'Riepilogo: informazioni su come aggiungere altri database di Skype for Business Server a un gruppo di disponibilità AlwaysOn esistente e sui passaggi aggiuntivi necessari dopo aver patchato o aggiornato un server back-end che fa parte di un gruppo di disponibilità AlwaysOn in Skype for Business Server.'
ms.openlocfilehash: 444194c9cda5f4c3f82e6f3f7698395dce1a5d07
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826366"
---
# <a name="manage-databases-with-an-alwayson-availability-group-in-skype-for-business-server"></a><span data-ttu-id="19ff1-103">Gestire i database con un gruppo di disponibilità AlwaysOn in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="19ff1-103">Manage databases with an AlwaysOn Availability Group in Skype for Business Server</span></span>

<span data-ttu-id="19ff1-104">Seguire i passaggi descritti in questo articolo per aggiungere altri database di Skype for Business Server a un gruppo di disponibilità AlwaysOn esistente in Skype for Business Server e scoprire i passaggi aggiuntivi necessari dopo aver patchato o aggiornato un server back-end che fa parte di un gruppo di disponibilità AlwaysOn in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="19ff1-104">Use the steps in this article to add more Skype for Business Server databases to an existing AlwaysOn Availability Group in Skype for Business Server, and find out about the necessary additional steps after you patch or upgrade a Back End Server that is part of a AlwaysOn Availability Group in Skype for Business Server.</span></span>

## <a name="add-databases-to-an-alwayson-availability-group"></a><span data-ttu-id="19ff1-105">Aggiungere database a un gruppo di disponibilità AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="19ff1-105">Add databases to an AlwaysOn Availability Group</span></span> 

1. <span data-ttu-id="19ff1-106">Aprire SQL Server Management Studio e passare al gruppo di disponibilità AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="19ff1-106">Open SQL Server Management Studio, and navigate to the AlwaysOn Availability Group.</span></span> <span data-ttu-id="19ff1-107">Eseguire il failover alla replica primaria.</span><span class="sxs-lookup"><span data-stu-id="19ff1-107">Fail it over to the primary replica.</span></span>
    
2. <span data-ttu-id="19ff1-108">In Generatore di topologie impostare l SQL Server FQDN del gruppo di disponibilità AlwaysOn sul nome di dominio completo del nodo primario di tale gruppo.</span><span class="sxs-lookup"><span data-stu-id="19ff1-108">In Topology Builder, set the SQL Server FQDN of the AlwaysOn Availability Group to the FQDN of the primary node of that group.</span></span>
    
   - <span data-ttu-id="19ff1-109">Aprire Generatore di topologie, selezionare **Scarica topologia dalla distribuzione esistente** e fare clic su **OK.**</span><span class="sxs-lookup"><span data-stu-id="19ff1-109">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
   - <span data-ttu-id="19ff1-110">Espandere Skype for Business Server, espandere la topologia ed espandere SQL Server **store.**</span><span class="sxs-lookup"><span data-stu-id="19ff1-110">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="19ff1-111">Fare clic con il pulsante destro SQL'archivio del nuovo gruppo di disponibilità AlwaysOn e scegliere **Modifica proprietà.**</span><span class="sxs-lookup"><span data-stu-id="19ff1-111">Right-click the SQL store of the new AlwaysOn Availability Group, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="19ff1-112">Nella parte inferiore della pagina, nella casella **SQL Server FQDN,** digitare il nome di dominio completo del nodo primario del gruppo di disponibilità AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="19ff1-112">At the bottom of the page, in the **SQL Server FQDN** box, type in the FQDN of the primary node of the AlwaysOn Availability Group.</span></span>
    
3. <span data-ttu-id="19ff1-113">Pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="19ff1-113">Publish the topology.</span></span> <span data-ttu-id="19ff1-114">Scegliere **Topologia** dal menu Azione **e** quindi **Pubblica.**</span><span class="sxs-lookup"><span data-stu-id="19ff1-114">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="19ff1-115">Nella pagina di conferma fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="19ff1-115">Then in the confirmation page click **Next**.</span></span>
    
4. <span data-ttu-id="19ff1-116">Utilizzare SQL Server Management Studio aggiungere il nuovo database al gruppo di disponibilità AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="19ff1-116">Use SQL Server Management Studio to add the new database to the AlwaysOn Availability Group.</span></span>
    
## <a name="patch-or-update-a-sql-server-in-an-alwayson-availability-group"></a><span data-ttu-id="19ff1-117">Applicare patch o aggiornare un SQL Server in un gruppo di disponibilità AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="19ff1-117">Patch or update a SQL Server in an AlwaysOn Availability Group</span></span>

<span data-ttu-id="19ff1-118">Dopo aver patchato un server back-end che fa parte di un gruppo di disponibilità AlwaysOn, è necessario ripubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="19ff1-118">After patching a Back End Server that is part of an AlwaysOn Availability Group, you must republish the topology.</span></span>

1. <span data-ttu-id="19ff1-119">Installare l'aggiornamento sul server o sui server Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="19ff1-119">Install the update on your Skype for Business server or servers.</span></span>
    
2. <span data-ttu-id="19ff1-120">Eseguire il seguente comando di PowerShell in Skype for Business Management Shell (connesso con un account autorizzato in modo appropriato per applicare le modifiche ai database AlwaysOn di SQL) come segue:</span><span class="sxs-lookup"><span data-stu-id="19ff1-120">Run the following PowerShell command in your Skype for Business Management Shell (logged in with an account that's appropriately permissioned to apply changes to the SQL AlwaysOn databases) as follows:</span></span>
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn [sqlpool.contoso.com] -Verbose
    ```

    <span data-ttu-id="19ff1-121">Dove [sqlpool.contoso.com] viene sostituito con il nome di dominio completo (FQDN) del gruppo di disponibilità AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="19ff1-121">Where [sqlpool.contoso.com] is replaced with the fully qualified domain name (FQDN) of your AlwaysOn availability group.</span></span>
