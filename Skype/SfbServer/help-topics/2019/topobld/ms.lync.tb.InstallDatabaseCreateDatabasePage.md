---
title: Installare e creare database
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.InstallDatabaseCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 515754ad-1344-42dc-8219-ee973de2e4c4
ROBOTS: NOINDEX, NOFOLLOW
description: Selezionare i database che si desidera creare per la distribuzione. Per impostazione predefinita, il database verrà creato nel server SQL definito nel sito definito e distribuirà e configurerà automaticamente i file di database in base a SQL Server in cui si inseriscono i database.
ms.openlocfilehash: 4bd69f1caa3322dbbf2d91a67caef54b72ece200
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41793614"
---
# <a name="install-and-create-databases"></a><span data-ttu-id="473f5-104">Installare e creare database</span><span class="sxs-lookup"><span data-stu-id="473f5-104">Install and Create Databases</span></span>

<span data-ttu-id="473f5-105">Selezionare i database che si desidera creare per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="473f5-105">You select the databases that you want to create for your deployment.</span></span> <span data-ttu-id="473f5-106">Per impostazione predefinita, il database verrà creato nel server SQL definito nel sito definito e distribuirà e configurerà automaticamente i file di database in base a SQL Server in cui si inseriscono i database.</span><span class="sxs-lookup"><span data-stu-id="473f5-106">By default, the database will be created on the defined SQL Server in the defined site, and will automatically deploy and configure the database files based on the SQL Server you are placing the databases on.</span></span>

 <span data-ttu-id="473f5-107">**Selezionare i database da creare**: selezionare la casella di controllo di tutti i database che si desidera distribuire e configurare.</span><span class="sxs-lookup"><span data-stu-id="473f5-107">**Select the databases you want to create**: Select the checkbox of any databases that you intend to deploy and configure.</span></span> <span data-ttu-id="473f5-108">Selezionare la casella di controllo di uno o di tutti i database che si vuole distribuire.</span><span class="sxs-lookup"><span data-stu-id="473f5-108">Select the check box of any or all databases that you will deploy.</span></span>

> [!CAUTION]
> <span data-ttu-id="473f5-109">SQL Server deve essere già configurato per l'istanza (se disponibile) e le porte del firewall devono essere aperte per contenere l'istanza in cui si stanno distribuendo i database.</span><span class="sxs-lookup"><span data-stu-id="473f5-109">The SQL Server must already have been configured for the instance (if any) and firewall ports must be opened to accommodate the instance that you are deploying the databases to.</span></span> <span data-ttu-id="473f5-110">Per informazioni dettagliate, vedere [configurare SQL Server](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx)</span><span class="sxs-lookup"><span data-stu-id="473f5-110">For details, see [Configure SQL Server](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx)</span></span>

 <span data-ttu-id="473f5-111">**Avanzate**: fare clic su SQL Server e fare clic sul pulsante **Avanzate** per scegliere le opzioni per i percorsi dei file di database in SQL Server.</span><span class="sxs-lookup"><span data-stu-id="473f5-111">**Advanced**: Click on the SQL Server and click the **Advanced** button to choose options for the database file locations on your SQL Server.</span></span> <span data-ttu-id="473f5-112">Per informazioni dettagliate sulla posizione avanzata dei file di database, vedere [installazione di database tramite Lync Server Management Shell](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx)</span><span class="sxs-lookup"><span data-stu-id="473f5-112">For details on advanced database file placement, see [Database Installation Using Lync Server Management Shell](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx)</span></span>

 <span data-ttu-id="473f5-113">**Indietro**: se si fa clic su questo pulsante si ritorna alla schermata precedente (potrebbe non essere sempre disponibile, in base a come è arrivata la finestra di dialogo).</span><span class="sxs-lookup"><span data-stu-id="473f5-113">**Back**: Clicking this button returns you to the previous screen (may not always be available, based on how you arrived at this dialog).</span></span>

 <span data-ttu-id="473f5-114">**Avanti**: se si fa clic su questo pulsante si esegue il commit della selezione nella finestra di dialogo corrente e si passa alla finestra di dialogo successiva per la configurazione di altre informazioni</span><span class="sxs-lookup"><span data-stu-id="473f5-114">**Next**: Clicking this button commits your selection on the current dialog and takes you to the next dialog for configuring additional information</span></span>

 <span data-ttu-id="473f5-115">**Annulla**: se si fa clic su questo pulsante si chiude la configurazione e si eliminano le modifiche.</span><span class="sxs-lookup"><span data-stu-id="473f5-115">**Cancel**: Clicking this button will quit the configuration and discard your changes.</span></span> <span data-ttu-id="473f5-116">Alcuni, ma non tutte le schermate di configurazione, ti chiederanno se vuoi chiudere e annullare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="473f5-116">Some, but not all configuration screens will prompt you if you want to quit and discard your changes.</span></span> <span data-ttu-id="473f5-117">Selezionando **Sì** si chiuderà la configurazione corrente e si chiuderà la configurazione corrente e si tornerà a Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="473f5-117">Selecting **Yes** will close the current configuration and close the current configuration and return you to Topology Builder.</span></span> <span data-ttu-id="473f5-118">Se si seleziona **No** , verrà visualizzata la finestra di dialogo configurazione corrente e si consentirà di continuare la configurazione.</span><span class="sxs-lookup"><span data-stu-id="473f5-118">Selecting **No** will return you to the current configuration dialog and allow you to continue the configuration.</span></span>

 <span data-ttu-id="473f5-119">**Guida**: se si fa clic sul pulsante della **Guida** , vengono visualizzate le informazioni della Guida associate alla finestra di dialogo configurazione corrente.</span><span class="sxs-lookup"><span data-stu-id="473f5-119">**Help**: Clicking the **Help** button displays this help information associated with the current configuration dialog.</span></span>


