---
title: Configurare i server applicazioni attendibili
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure trusted application servers
ms:assetid: 47a9e72e-566c-4c23-bec2-760a3098a974
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204865(v=OCS.15)
ms:contentKeyID: 48184056
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 92e7f2c808e9ea5a3e8dfbf3010715c86e02596e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728946"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-trusted-application-servers"></a><span data-ttu-id="504d4-102">Configurare i server applicazioni attendibili</span><span class="sxs-lookup"><span data-stu-id="504d4-102">Configure trusted application servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="504d4-103">_**Argomento Ultima modifica:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="504d4-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="504d4-104">In un ambiente misto, se si crea un nuovo server delle applicazioni attendibile dopo l'Unione della topologia legacy di Office Communications Server con Lync Server 2013 e si definisce un nuovo server applicazioni attendibile tramite Generatore di topologie, è necessario impostare il pool di hop successivo come un Pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="504d4-104">In a mixed environment, if you create a new trusted application server after merging the legacy Office Communications Server topology with Lync Server 2013, and you define a new trusted application server using Topology Builder, you must set the next hop pool to be a Lync Server 2013 pool.</span></span> <span data-ttu-id="504d4-105">In un ambiente Unito sia il pool legacy di Office Communications Server che il pool di Lync Server 2013 vengono visualizzati nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="504d4-105">In a merged environment, both the legacy Office Communications Server pool and the Lync Server 2013 pool appear in the drop down list.</span></span> <span data-ttu-id="504d4-106">La selezione del pool legacy *non* è supportata.</span><span class="sxs-lookup"><span data-stu-id="504d4-106">Selecting the legacy pool is *not* supported.</span></span>

<div>

## <a name="to-select-lync-server-2013-as-next-hop-when-creating-a-trusted-application-server"></a><span data-ttu-id="504d4-107">Per selezionare Lync Server 2013 come hop successivo quando si crea un server applicazioni attendibile</span><span class="sxs-lookup"><span data-stu-id="504d4-107">To select Lync Server 2013 as next hop when creating a Trusted application server</span></span>

1.  <span data-ttu-id="504d4-108">Aprire una topologia esistente in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="504d4-108">Open an existing topology in Topology Builder.</span></span>

2.  <span data-ttu-id="504d4-109">Nel riquadro sinistro fare clic con il pulsante destro del mouse su **server applicazioni attendibili** e scegliere **nuovo pool di applicazioni attendibili**.</span><span class="sxs-lookup"><span data-stu-id="504d4-109">In the left pane, right click **Trusted application servers** and click **New Trusted Application Pool**.</span></span>

3.  <span data-ttu-id="504d4-110">Immettere il **nome di dominio completo del pool** di applicazioni attendibili e scegliere se si tratta di una distribuzione a server singolo o a più server.</span><span class="sxs-lookup"><span data-stu-id="504d4-110">Enter the **Pool FQDN** of the trusted application pool and select whether it will be a single-server or multiple-server deployment.</span></span>

4.  <span data-ttu-id="504d4-111">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="504d4-111">Click **Next**.</span></span>

5.  <span data-ttu-id="504d4-112">Nella pagina **selezionare l'hop successivo** , nell'elenco, selezionare il pool di front end di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="504d4-112">On the **Select the next hop** page, from the list, select the Lync Server 2013 Front End pool.</span></span>
    
    <span data-ttu-id="504d4-113">![Finestra di dialogo Definisci nuovo pool di applicazioni attendibili](images/JJ204865.ecfe2bb8-758b-4b36-8146-573005c4ab09(OCS.15).jpg "Finestra di dialogo Definisci nuovo pool di applicazioni attendibili")</span><span class="sxs-lookup"><span data-stu-id="504d4-113">![Define New Trusted Application Pool dialog](images/JJ204865.ecfe2bb8-758b-4b36-8146-573005c4ab09(OCS.15).jpg "Define New Trusted Application Pool dialog")</span></span>  

6.  <span data-ttu-id="504d4-114">Fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="504d4-114">Click **Finish**.</span></span>

7.  <span data-ttu-id="504d4-115">Selezionare il nodo superiore **Lync Server** e scegliere **pubblica**dal riquadro **azioni** .</span><span class="sxs-lookup"><span data-stu-id="504d4-115">Select the top node **Lync Server** and from the **Actions** pane, select **Publish**.</span></span>

8.  <span data-ttu-id="504d4-116">Verificare che il **pool di applicazioni attendibili** sia stato creato correttamente ed è associato al pool Front-end corretto.</span><span class="sxs-lookup"><span data-stu-id="504d4-116">Verify the **Trusted Application Pool** was created successfully and is associated with the correct Front End pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

