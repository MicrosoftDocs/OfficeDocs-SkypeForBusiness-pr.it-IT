---
title: Modificare le route vocali per l'utilizzo del nuovo Lync Server 2013 Mediation Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Change voice routes to use the new Lync Server 2013 Mediation Server
ms:assetid: acd487b3-377c-46bf-9f71-fe6152002664
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205162(v=OCS.15)
ms:contentKeyID: 48185069
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b4998057543f6695104ecbe759135b6735160c23
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181009"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server"></a><span data-ttu-id="9b4eb-102">Modificare le route vocali per l'utilizzo del nuovo Lync Server 2013 Mediation Server</span><span class="sxs-lookup"><span data-stu-id="9b4eb-102">Change voice routes to use the new Lync Server 2013 Mediation Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9b4eb-103">_**Ultimo argomento modificato:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="9b4eb-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="9b4eb-104">Questa procedura consente di modificare le route vocali per l'utilizzo di Lync Server 2013 Mediation Server, invece del Mediation Server di Office Communications Server 2007 R2 legacy.</span><span class="sxs-lookup"><span data-stu-id="9b4eb-104">This procedure changes the voice routes to use the Lync Server 2013 Mediation Server, instead of the legacy Office Communications Server 2007 R2 Mediation Server.</span></span>

<div>

## <a name="to-change-the-voice-routes-to-use-the-new-mediation-server"></a><span data-ttu-id="9b4eb-105">Per modificare le route vocali per l'utilizzo del nuovo Mediation Server</span><span class="sxs-lookup"><span data-stu-id="9b4eb-105">To change the voice routes to use the new Mediation Server</span></span>

1.  <span data-ttu-id="9b4eb-106">Pannello di controllo di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9b4eb-106">Lync Server 2013 Control Panel</span></span>

2.  <span data-ttu-id="9b4eb-107">Nel riquadro sinistro selezionare **Routing vocale** e quindi **Route**.</span><span class="sxs-lookup"><span data-stu-id="9b4eb-107">In the left pane, select **Voice Routing** and then **Route**.</span></span>

3.  <span data-ttu-id="9b4eb-108">Fare clic su **Nuovo** per creare una nuova route vocale.</span><span class="sxs-lookup"><span data-stu-id="9b4eb-108">Click **New** to create a New Voice Route.</span></span>

4.  <span data-ttu-id="9b4eb-109">Completare i campi seguenti:</span><span class="sxs-lookup"><span data-stu-id="9b4eb-109">Fill in the following fields:</span></span>
    
      - <span data-ttu-id="9b4eb-p101">**Nome**: digitare un nome descrittivo per la route vocale. Per questo documento verrà utilizzato il nome **W15PSTNRoute**.</span><span class="sxs-lookup"><span data-stu-id="9b4eb-p101">**Name**: Type a descriptive name of the voice route. For this document we will use **W15PSTNRoute**.</span></span>
    
      - <span data-ttu-id="9b4eb-112">**Descrizione**: digitare una breve descrizione della route vocale.</span><span class="sxs-lookup"><span data-stu-id="9b4eb-112">**Description**: Type a short description of the voice route.</span></span>

5.  <span data-ttu-id="9b4eb-p102">Ignorare tutte le altre sezioni fino a **Gateway associati**. Fare clic su **Aggiungi**. Selezionare il nuovo gateway predefinito e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="9b4eb-p102">Skip all remaining sections until you reach **Associated gateways**. Click **Add**. Select the new default gateway and click **OK**.</span></span>

6.  <span data-ttu-id="9b4eb-116">In **Utilizzi PSTN associati** fare clic su **Seleziona**</span><span class="sxs-lookup"><span data-stu-id="9b4eb-116">Under **Associated PSTN Usages**, click **Select**.</span></span>

7.  <span data-ttu-id="9b4eb-117">Nella pagina **Seleziona record utilizzo PSTN** selezionare un nome di record e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="9b4eb-117">From the **Select PSTN Usage Record** page, select a record name and then click **OK**.</span></span>

8.  <span data-ttu-id="9b4eb-118">Nella pagina **Nuova route vocale** fare clic su **OK** per creare la **Route vocale**.</span><span class="sxs-lookup"><span data-stu-id="9b4eb-118">From the **New Voice Route** page, click **OK** to create the **Voice Route**.</span></span>

9.  <span data-ttu-id="9b4eb-119">Nella pagina **Routing vocale** selezionare **Route**.</span><span class="sxs-lookup"><span data-stu-id="9b4eb-119">From the **Voice Routing** page, select **Route**.</span></span>

10. <span data-ttu-id="9b4eb-120">Spostare la nuova route creata all'inizio dell'elenco e quindi selezionare **Commit**.</span><span class="sxs-lookup"><span data-stu-id="9b4eb-120">Move the newly created route to the top of the list and then select **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

