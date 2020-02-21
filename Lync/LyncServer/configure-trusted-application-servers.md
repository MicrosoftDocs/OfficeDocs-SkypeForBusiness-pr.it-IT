---
title: Configurare i server applicazioni attendibili
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure trusted application servers
ms:assetid: 20c3815f-3048-4940-8c0f-cdfcd0801d5d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204735(v=OCS.15)
ms:contentKeyID: 48183592
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cee36f365eeaf4d95dea824d8f3a3afa2544b1d3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180759"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-trusted-application-servers"></a><span data-ttu-id="11cf4-102">Configurare i server applicazioni attendibili</span><span class="sxs-lookup"><span data-stu-id="11cf4-102">Configure trusted application servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="11cf4-103">_**Ultimo argomento modificato:** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="11cf4-103">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="11cf4-104">In un ambiente misto, se si crea un nuovo server applicazioni attendibili, è necessario impostare il pool dell'hop successivo come pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="11cf4-104">In a mixed environment, if you create a new trusted application server, you must set the next hop pool to be a Lync Server 2013 pool.</span></span> <span data-ttu-id="11cf4-105">In un ambiente misto, sia il pool di Lync Server 2010 legacy che il pool di Lync Server 2013 vengono visualizzati nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="11cf4-105">In a mixed environment, both the legacy Lync Server 2010 pool and the Lync Server 2013 pool appear in the drop down list.</span></span> <span data-ttu-id="11cf4-106">La selezione del pool legacy non è supportata.</span><span class="sxs-lookup"><span data-stu-id="11cf4-106">Selecting the legacy pool is not supported.</span></span>

<span data-ttu-id="11cf4-107">**Selezionare Lync Server 2013 come hop successivo durante la creazione di un server applicazioni attendibile**</span><span class="sxs-lookup"><span data-stu-id="11cf4-107">**Select Lync Server 2013 as next hop when creating a Trusted application server**</span></span>

1.  <span data-ttu-id="11cf4-108">Apre lo strumento di generazione topologia</span><span class="sxs-lookup"><span data-stu-id="11cf4-108">Open Topology Builder.</span></span>

2.  <span data-ttu-id="11cf4-109">Nel riquadro di sinistra fare clic con il pulsante destro del mouse su **Server applicazioni attendibili** e quindi scegliere **Nuovo pool di applicazioni attendibili**.</span><span class="sxs-lookup"><span data-stu-id="11cf4-109">In the left pane, right click **Trusted application servers** and click **New Trusted Application Pool**.</span></span>

3.  <span data-ttu-id="11cf4-110">Immettere il nome FQDN del pool di applicazioni attendibili in **FQDN pool** e specificare se sarà un pool a server singolo o a più server.</span><span class="sxs-lookup"><span data-stu-id="11cf4-110">Enter the **Pool FQDN** of the trusted application pool and select whether it will be a single-server or multiple-server.</span></span>

4.  <span data-ttu-id="11cf4-111">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="11cf4-111">Click **Next**.</span></span>

5.  <span data-ttu-id="11cf4-112">Nell'elenco nella pagina **selezionare l'hop successivo** selezionare il pool Front End di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="11cf4-112">On the **Select the next hop** page, from the list, select the Lync Server 2013 Front End pool.</span></span>

6.  <span data-ttu-id="11cf4-113">Fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="11cf4-113">Click **Finish**.</span></span>

7.  <span data-ttu-id="11cf4-114">Selezionare il nodo principale **Lync Server** e nel menu **Azioni** selezionare **Pubblica**.</span><span class="sxs-lookup"><span data-stu-id="11cf4-114">Select the top node **Lync Server** and from the **Action** menu, select **Publish**.</span></span>
    
    <span data-ttu-id="11cf4-115">Verificare che il **Pool di applicazioni attendibili** sia stato creato correttamente e sia associato al pool Front End corretto.</span><span class="sxs-lookup"><span data-stu-id="11cf4-115">Verify the **Trusted Application Pool** has been created successfully and is associated with the correct Front End pool.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

