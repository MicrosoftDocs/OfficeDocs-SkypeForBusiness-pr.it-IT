---
title: Modificare le route vocali per usare il nuovo server di mediazione Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: Admin
TOCTitle: Change voice routes to use the new Lync Server 2013 Mediation Server
ms:assetid: acd487b3-377c-46bf-9f71-fe6152002664
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205162(v=OCS.15)
ms:contentKeyID: 48185069
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba933ec7c51b62e7f5008ad9f767a0695c88ebb2
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "40974758"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server"></a><span data-ttu-id="99212-102">Modificare le route vocali per usare il nuovo server di mediazione Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99212-102">Change voice routes to use the new Lync Server 2013 Mediation Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="99212-103">_**Argomento Ultima modifica:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="99212-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="99212-104">Questa procedura modifica le route vocali per l'uso di Lync Server 2013 Mediation Server, invece dell'legacy Office Communications Server 2007 R2 Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="99212-104">This procedure changes the voice routes to use the Lync Server 2013 Mediation Server, instead of the legacy Office Communications Server 2007 R2 Mediation Server.</span></span>

<div>

## <a name="to-change-the-voice-routes-to-use-the-new-mediation-server"></a><span data-ttu-id="99212-105">Per modificare le route vocali in uso del nuovo Mediation Server</span><span class="sxs-lookup"><span data-stu-id="99212-105">To change the voice routes to use the new Mediation Server</span></span>

1.  <span data-ttu-id="99212-106">Pannello di controllo di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99212-106">Lync Server 2013 Control Panel</span></span>

2.  <span data-ttu-id="99212-107">Nel riquadro sinistro selezionare **routing vocale** e quindi **Route**.</span><span class="sxs-lookup"><span data-stu-id="99212-107">In the left pane, select **Voice Routing** and then **Route**.</span></span>

3.  <span data-ttu-id="99212-108">Fare clic su **nuovo** per creare una nuova route vocale.</span><span class="sxs-lookup"><span data-stu-id="99212-108">Click **New** to create a New Voice Route.</span></span>

4.  <span data-ttu-id="99212-109">Compilare i campi seguenti:</span><span class="sxs-lookup"><span data-stu-id="99212-109">Fill in the following fields:</span></span>
    
      - <span data-ttu-id="99212-110">**Nome**: digitare un nome descrittivo della route vocale.</span><span class="sxs-lookup"><span data-stu-id="99212-110">**Name**: Type a descriptive name of the voice route.</span></span> <span data-ttu-id="99212-111">Per questo documento useremo **W15PSTNRoute**.</span><span class="sxs-lookup"><span data-stu-id="99212-111">For this document we will use **W15PSTNRoute**.</span></span>
    
      - <span data-ttu-id="99212-112">**Descrizione**: digitare una breve descrizione della route vocale.</span><span class="sxs-lookup"><span data-stu-id="99212-112">**Description**: Type a short description of the voice route.</span></span>

5.  <span data-ttu-id="99212-113">Ignorare tutte le sezioni rimanenti fino a raggiungere i **gateway associati**.</span><span class="sxs-lookup"><span data-stu-id="99212-113">Skip all remaining sections until you reach **Associated gateways**.</span></span> <span data-ttu-id="99212-114">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="99212-114">Click **Add**.</span></span> <span data-ttu-id="99212-115">Selezionare il nuovo gateway predefinito e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="99212-115">Select the new default gateway and click **OK**.</span></span>

6.  <span data-ttu-id="99212-116">In **usi PSTN associati**fare clic su **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="99212-116">Under **Associated PSTN Usages**, click **Select**.</span></span>

7.  <span data-ttu-id="99212-117">Nella pagina **Seleziona record utilizzo PSTN** selezionare un nome di record e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="99212-117">From the **Select PSTN Usage Record** page, select a record name and then click **OK**.</span></span>

8.  <span data-ttu-id="99212-118">Nella pagina **nuova route vocale** fare clic su **OK** per creare la **Route vocale**.</span><span class="sxs-lookup"><span data-stu-id="99212-118">From the **New Voice Route** page, click **OK** to create the **Voice Route**.</span></span>

9.  <span data-ttu-id="99212-119">Nella pagina **routing vocale** selezionare **Route**.</span><span class="sxs-lookup"><span data-stu-id="99212-119">From the **Voice Routing** page, select **Route**.</span></span>

10. <span data-ttu-id="99212-120">Passare la route appena creata all'inizio dell'elenco e quindi selezionare **commit**.</span><span class="sxs-lookup"><span data-stu-id="99212-120">Move the newly created route to the top of the list and then select **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

