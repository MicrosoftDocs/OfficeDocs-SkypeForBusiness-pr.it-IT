---
title: Pagina per l'aggiunta dell'archivio di monitoraggio per Front End Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndMonitoringStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e8587d-a9d2-4fc5-acc5-2bf0abf133c6
description: "È possibile definire l'archivio SQL Server per il monitoraggio configurando le proprietà seguenti:"
ms.openlocfilehash: 85b8518bb533de68423dea93f259fc7b927ed9ba
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218877"
---
# <a name="add-front-end-monitoring-store-page"></a><span data-ttu-id="18ac9-103">Pagina per l'aggiunta dell'archivio di monitoraggio per Front End Server</span><span class="sxs-lookup"><span data-stu-id="18ac9-103">Add Front End Monitoring Store Page</span></span>
 
<span data-ttu-id="18ac9-104">È possibile **definire l'archivio SQL Server per il monitoraggio** configurando le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="18ac9-104">You **Define the Monitoring SQL Server store** by configuring the following properties:</span></span>
  
- <span data-ttu-id="18ac9-105">**Monitoraggio dell'archivio SQL Server**: selezionare un nome di dominio completo di SQL Server (e, facoltativamente, un'istanza) dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="18ac9-105">**Monitoring SQL Server store**: Select a SQL Server fully qualified domain name (and, optionally an instance) from the list.</span></span>
    
    <span data-ttu-id="18ac9-106">Fare clic su **nuovo** per creare una nuova definizione FQDN di SQL Server e facoltativamente un nome di istanza per l'archivio di Monitoring Server.</span><span class="sxs-lookup"><span data-stu-id="18ac9-106">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the Monitoring Server store.</span></span>
    
- <span data-ttu-id="18ac9-107">Selezionare la casella di controllo **Abilita mirroring dell'archivio SQL Server** se si desidera aggiungere il mirroring del database per il Monitoring Server.</span><span class="sxs-lookup"><span data-stu-id="18ac9-107">Select the **Enable SQL Server store mirroring** check box if you want to add database mirroring for the Monitoring Server.</span></span>
    
    <span data-ttu-id="18ac9-108">Selezionare un mirror archivio nell'elenco **Mirror archivio SQL Server monitoraggio**.</span><span class="sxs-lookup"><span data-stu-id="18ac9-108">Select an existing **Monitoring SQL Server store mirror** from the list.</span></span>
    
    <span data-ttu-id="18ac9-109">Fare clic su **nuovo** per creare una nuova definizione FQDN di SQL Server e facoltativamente un nome di istanza per l'archivio mirror.</span><span class="sxs-lookup"><span data-stu-id="18ac9-109">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the mirror store.</span></span>
    
- <span data-ttu-id="18ac9-110">Se è stata selezionata l'opzione **Abilita mirroring dell'archivio SQL Server**, facoltativamente, selezionare Usa controllo del **mirroring di SQL Server per abilitare il failover automatico** per selezionare un archivio di controllo del mirroring di SQL Server nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="18ac9-110">If you selected **Enable SQL Server store mirroring**, optionally select **Use SQL Server mirroring witness to enable automatic failover** to select a SQL Server mirroring witness store from the list.</span></span>
    
    <span data-ttu-id="18ac9-111">Fare clic su **nuovo** per creare una nuova definizione FQDN di SQL Server e facoltativamente un nome di istanza per l'archivio dei testimoni del mirroring.</span><span class="sxs-lookup"><span data-stu-id="18ac9-111">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the mirroring witness store.</span></span>
    
<span data-ttu-id="18ac9-112">Fare clic su **Indietro** per tornare alla finestra di dialogo per la definizione del pool precedente.</span><span class="sxs-lookup"><span data-stu-id="18ac9-112">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="18ac9-113">Fare clic su **Avanti** dopo avere specificato le opzioni per questa finestra di dialogo per continuare con la configurazione.</span><span class="sxs-lookup"><span data-stu-id="18ac9-113">Click **Next** after you have finished entering the options for this dialog to proceed with the configuration.</span></span>
  
<span data-ttu-id="18ac9-114">Fare clic su **Annulla** per annullare tutte le modifiche e terminare la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="18ac9-114">Click **Cancel** to discard all changes and end the wizard.</span></span>
  
<span data-ttu-id="18ac9-115">Fare clic su **?** per accedere alla Guida sensibile al contesto, come questa pagina.</span><span class="sxs-lookup"><span data-stu-id="18ac9-115">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="18ac9-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="18ac9-116">See also</span></span>

[<span data-ttu-id="18ac9-117">Associare un archivio di monitoraggio a un pool Front end in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="18ac9-117">Associate a monitoring store with a Front End pool in Skype for Business Server 2015</span></span>](../../deploy/deploy-monitoring/associate-a-monitoring-store.md)
