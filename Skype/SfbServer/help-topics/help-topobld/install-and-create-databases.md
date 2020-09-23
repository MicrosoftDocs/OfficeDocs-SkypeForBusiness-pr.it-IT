---
title: Installare e creare un database
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
- ms.lync.tb.InstallDatabaseCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 515754ad-1344-42dc-8219-ee973de2e4c4
description: È possibile selezionare i database da creare per la distribuzione. Per impostazione predefinita, il database verrà creato nell'SQL Server definito nel sito definito e distribuirà e configurerà automaticamente i file di database in base al server SQL su cui si stanno posizionando i database.
ms.openlocfilehash: ade264fcda73df408f6bb323dd1e3733ccdd45f1
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215387"
---
# <a name="install-and-create-databases"></a><span data-ttu-id="fc9a8-104">Installare e creare un database</span><span class="sxs-lookup"><span data-stu-id="fc9a8-104">Install and Create Databases</span></span>

<span data-ttu-id="fc9a8-105">È possibile selezionare i database da creare per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="fc9a8-105">You select the databases that you want to create for your deployment.</span></span> <span data-ttu-id="fc9a8-106">Per impostazione predefinita, il database verrà creato nell'SQL Server definito nel sito definito e distribuirà e configurerà automaticamente i file di database in base al server SQL su cui si stanno posizionando i database.</span><span class="sxs-lookup"><span data-stu-id="fc9a8-106">By default, the database will be created on the defined SQL Server in the defined site, and will automatically deploy and configure the database files based on the SQL Server you are placing the databases on.</span></span>

 <span data-ttu-id="fc9a8-p103">**Selezionare i database da creare**: selezionare la casella di controllo di ogni database che si intende distribuire e configurare. Selezionare la casella di controllo relativa a tutti i database da distribuire.</span><span class="sxs-lookup"><span data-stu-id="fc9a8-p103">**Select the databases you want to create**: Select the checkbox of any databases that you intend to deploy and configure. Select the check box of any or all databases that you will deploy.</span></span>

> [!CAUTION]
> <span data-ttu-id="fc9a8-109">È necessario che SQL Server sia già stato configurato per l'istanza (se presente) e che le porte del firewall debbano essere aperte per contenere l'istanza in cui si stanno distribuendo i database.</span><span class="sxs-lookup"><span data-stu-id="fc9a8-109">The SQL Server must already have been configured for the instance (if any) and firewall ports must be opened to accommodate the instance that you are deploying the databases to.</span></span> <span data-ttu-id="fc9a8-110">Per informazioni dettagliate, vedere [Configure SQL Server for Lync Server 2013 Preview](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx)</span><span class="sxs-lookup"><span data-stu-id="fc9a8-110">For details, see [Configure SQL Server for Lync Server 2013 Preview](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx)</span></span>

 <span data-ttu-id="fc9a8-111">**Avanzate**: fare clic su SQL Server e fare clic sul pulsante **Avanzate** per scegliere le opzioni per i percorsi dei file di database in SQL Server.</span><span class="sxs-lookup"><span data-stu-id="fc9a8-111">**Advanced**: Click on the SQL Server and click the **Advanced** button to choose options for the database file locations on your SQL Server.</span></span> <span data-ttu-id="fc9a8-112">Per informazioni dettagliate sul posizionamento avanzato dei file di database, vedere [Database Installation Using Lync Server Management Shell](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx)</span><span class="sxs-lookup"><span data-stu-id="fc9a8-112">For details on advanced database file placement, see [Database Installation Using Lync Server Management Shell](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx)</span></span>

 <span data-ttu-id="fc9a8-113">**Indietro**: fare clic su questo pulsante per tornare alla schermata precedente. Il pulsante potrebbe non essere sempre disponibile, a seconda di come si è arrivati a questa finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="fc9a8-113">**Back**: Clicking this button returns you to the previous screen (may not always be available, based on how you arrived at this dialog).</span></span>

 <span data-ttu-id="fc9a8-114">**Avanti**: fare clic su questo pulsante per eseguire il commit delle opzioni selezionate nella finestra di dialogo corrente e passare alla finestra di dialogo successiva per configurare ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="fc9a8-114">**Next**: Clicking this button commits your selection on the current dialog and takes you to the next dialog for configuring additional information</span></span>

 <span data-ttu-id="fc9a8-115">**Annulla**: fare clic su questo pulsante per uscire dalla configurazione e rimuovere le modifiche.</span><span class="sxs-lookup"><span data-stu-id="fc9a8-115">**Cancel**: Clicking this button will quit the configuration and discard your changes.</span></span> <span data-ttu-id="fc9a8-116">Alcune, ma non tutte, le schermate di configurazione chiedono se di desidera uscire e annullare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="fc9a8-116">Some, but not all configuration screens will prompt you if you want to quit and discard your changes.</span></span> <span data-ttu-id="fc9a8-117">Se si seleziona **Sì** , si chiuderà la configurazione corrente e si chiuderà la configurazione corrente e si tornerà a Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="fc9a8-117">Selecting **Yes** will close the current configuration and close the current configuration and return you to Topology Builder.</span></span> <span data-ttu-id="fc9a8-118">Scegliere **No** per tornare alla finestra di dialogo di configurazione corrente e continuare la configurazione.</span><span class="sxs-lookup"><span data-stu-id="fc9a8-118">Selecting **No** will return you to the current configuration dialog and allow you to continue the configuration.</span></span>

 <span data-ttu-id="fc9a8-119">**?**: fare clic sul pulsante **?** per visualizzare le informazioni della Guida associate alla finestra di dialogo di configurazione corrente.</span><span class="sxs-lookup"><span data-stu-id="fc9a8-119">**Help**: Clicking the **Help** button displays this help information associated with the current configuration dialog.</span></span>


