---
title: Gestire i database con un gruppo di disponibilità AlwaysOn in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 026c4469-f471-4e4f-a77d-a7d22a925e5a
description: "Riepilogo: informazioni su come aggiungere altri database di Skype for Business Server a un gruppo di disponibilità AlwaysOn esistente e informazioni sui passaggi aggiuntivi necessari dopo la patch o l'aggiornamento di un server back-end che fa parte di un gruppo di disponibilità AlwaysOn in Skype for Business Server."
ms.openlocfilehash: 221964eb7d8dfcbb0303a0e1148de4fcef6cec51
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991541"
---
# <a name="manage-databases-with-an-alwayson-availability-group-in-skype-for-business-server"></a><span data-ttu-id="d3264-103">Gestire i database con un gruppo di disponibilità AlwaysOn in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="d3264-103">Manage databases with an AlwaysOn Availability Group in Skype for Business Server</span></span>

<span data-ttu-id="d3264-104">Seguire i passaggi di questo articolo per aggiungere altri database di Skype for Business Server a un gruppo di disponibilità AlwaysOn esistente in Skype for Business Server e scoprire i passaggi aggiuntivi necessari dopo la patch o l'aggiornamento di un server back-end che fa parte di un AlwaysOn Gruppo di disponibilità in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="d3264-104">Use the steps in this article to add more Skype for Business Server databases to an existing AlwaysOn Availability Group in Skype for Business Server, and find out about the necessary additional steps after you patch or upgrade a Back End Server that is part of a AlwaysOn Availability Group in Skype for Business Server.</span></span>

## <a name="add-databases-to-an-alwayson-availability-group"></a><span data-ttu-id="d3264-105">Aggiungere database a un gruppo di disponibilità AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="d3264-105">Add databases to an AlwaysOn Availability Group</span></span> 

1. <span data-ttu-id="d3264-106">Aprire SQL Server Management Studio e passare al gruppo di disponibilità AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="d3264-106">Open SQL Server Management Studio, and navigate to the AlwaysOn Availability Group.</span></span> <span data-ttu-id="d3264-107">Non superarlo nella replica primaria.</span><span class="sxs-lookup"><span data-stu-id="d3264-107">Fail it over to the primary replica.</span></span>
    
2. <span data-ttu-id="d3264-108">In Generatore di topologie impostare il nome di dominio completo di SQL Server del gruppo di disponibilità AlwaysOn sul nome di dominio completo del nodo principale di tale gruppo.</span><span class="sxs-lookup"><span data-stu-id="d3264-108">In Topology Builder, set the SQL Server FQDN of the AlwaysOn Availability Group to the FQDN of the primary node of that group.</span></span>
    
   - <span data-ttu-id="d3264-109">Aprire Generatore di topologie, selezionare **Scarica topologia dalla distribuzione esistente**e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d3264-109">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
   - <span data-ttu-id="d3264-110">Espandi Skype for Business Server, Espandi la topologia ed Espandi gli **archivi di SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="d3264-110">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="d3264-111">Fare clic con il pulsante destro del mouse sull'archivio SQL del nuovo gruppo di disponibilità AlwaysOn e scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="d3264-111">Right-click the SQL store of the new AlwaysOn Availability Group, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="d3264-112">Nella parte inferiore della pagina, nella casella **FQDN di SQL Server** , digitare il nome di dominio completo del nodo principale del gruppo di disponibilità AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="d3264-112">At the bottom of the page, in the **SQL Server FQDN** box, type in the FQDN of the primary node of the AlwaysOn Availability Group.</span></span>
    
3. <span data-ttu-id="d3264-113">Pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="d3264-113">Publish the topology.</span></span> <span data-ttu-id="d3264-114">Nel menu **azioni** fare clic su **topologia** e quindi su **pubblica**.</span><span class="sxs-lookup"><span data-stu-id="d3264-114">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="d3264-115">Nella pagina di conferma fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="d3264-115">Then in the confirmation page click **Next**.</span></span>
    
4. <span data-ttu-id="d3264-116">Usare SQL Server Management Studio per aggiungere il nuovo database al gruppo di disponibilità AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="d3264-116">Use SQL Server Management Studio to add the new database to the AlwaysOn Availability Group.</span></span>
    
## <a name="patch-or-update-a-sql-server-in-an-alwayson-availability-group"></a><span data-ttu-id="d3264-117">Patch o aggiornamento di un server SQL in un gruppo di disponibilità AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="d3264-117">Patch or update a SQL Server in an AlwaysOn Availability Group</span></span>

<span data-ttu-id="d3264-118">Dopo aver patchato un server back-end che fa parte di un gruppo di disponibilità AlwaysOn, è necessario ripubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="d3264-118">After patching a Back End Server that is part of an AlwaysOn Availability Group, you must republish the topology.</span></span>

1. <span data-ttu-id="d3264-119">Installare l'aggiornamento in un server o server Skype for business.</span><span class="sxs-lookup"><span data-stu-id="d3264-119">Install the update on your Skype for Business server or servers.</span></span>
    
2. <span data-ttu-id="d3264-120">Eseguire il comando di PowerShell seguente in Skype for Business Management Shell (effettuato l'accesso con un account autorizzato a applicare le modifiche apportate ai database SQL AlwaysOn) nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="d3264-120">Run the following PowerShell command in your Skype for Business Management Shell (logged in with an account that's appropriately permissioned to apply changes to the SQL AlwaysOn databases) as follows:</span></span>
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn [sqlpool.contoso.com] -Verbose
    ```

    <span data-ttu-id="d3264-121">Dove [sqlpool.contoso.com] viene sostituito con il nome di dominio completo (FQDN) del gruppo di disponibilità AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="d3264-121">Where [sqlpool.contoso.com] is replaced with the fully qualified domain name (FQDN) of your AlwaysOn availability group.</span></span>
