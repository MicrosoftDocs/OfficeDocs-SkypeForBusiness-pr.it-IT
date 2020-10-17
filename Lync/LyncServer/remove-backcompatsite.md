---
title: Rimuovere BackCompatSite
description: Rimuovere BackCompatSite.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove BackCompatSite
ms:assetid: 039650e3-541b-45c2-a682-c4fa08423118
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204637(v=OCS.15)
ms:contentKeyID: 48183265
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 809324320ec1869ac0c9d324b8fc270a3cf8f174
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570272"
---
# <a name="remove-backcompatsite"></a><span data-ttu-id="feb0c-103">Rimuovere BackCompatSite</span><span class="sxs-lookup"><span data-stu-id="feb0c-103">Remove BackCompatSite</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="feb0c-104">_**Ultimo argomento modificato:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="feb0c-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="feb0c-105">Dopo avere disattivato tutti i pool e avere disinstallato tutti i server perimetrali, eseguire la procedura di unione guidata del Generatore di topologie per rimuovere **BackCompatSite**.</span><span class="sxs-lookup"><span data-stu-id="feb0c-105">After all pools are deactivated and all Edge Servers have been uninstalled, run the Topology Builder Merge wizard to remove the **BackCompatSite**.</span></span>

<div>

## <a name="to-remove-backcompat-site-from-topology-builder"></a><span data-ttu-id="feb0c-106">Per rimuovere BackCompatSite dal Generatore di topologie</span><span class="sxs-lookup"><span data-stu-id="feb0c-106">To remove BackCompat site from Topology Builder</span></span>

1.  <span data-ttu-id="feb0c-107">Aprire una distribuzione esistente dal Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="feb0c-107">Open an existing deployment from Topology Builder.</span></span>

2.  <span data-ttu-id="feb0c-108">Scegliere **Unisci topologia 2007 R2** dal menu **Azione**.</span><span class="sxs-lookup"><span data-stu-id="feb0c-108">In the **Action** menu, click **Merge 2007 R2 Topology**.</span></span>

3.  <span data-ttu-id="feb0c-109">Fare clic su **Avanti** per continuare.</span><span class="sxs-lookup"><span data-stu-id="feb0c-109">Click **Next** to continue.</span></span>

4.  <span data-ttu-id="feb0c-p101">Nella pagina **Specifica il server perimetrale legacy** assicurarsi che l'elenco di server perimetrali sia vuoto. Se l'elenco non è vuoto, utilizzare il pulsante **Rimuovi** per rimuovere tutti i server perimetrali legacy e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="feb0c-p101">On the **Specify Legacy Edge** page, ensure that list of Edge Servers is empty. If the list is not empty, use the **Remove** button to remove all the legacy Edge Servers, and then click **Next**.</span></span>
    
    <span data-ttu-id="feb0c-112">![Procedura guidata per la topologia di Unione, specificare la pagina installazione Edge](images/JJ204637.fb35a59a-711e-4259-b177-7311df1fed3c(OCS.15).jpg "Procedura guidata per la topologia di Unione, specificare la pagina installazione Edge")</span><span class="sxs-lookup"><span data-stu-id="feb0c-112">![Merge Topology Wizard, Specify Edge Setup page](images/JJ204637.fb35a59a-711e-4259-b177-7311df1fed3c(OCS.15).jpg "Merge Topology Wizard, Specify Edge Setup page")</span></span>  

5.  <span data-ttu-id="feb0c-113">Nella pagina **Specificare la porta SIP interna** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="feb0c-113">On the **Specify Internal SIP port setting** page, click **Next**.</span></span>

6.  <span data-ttu-id="feb0c-114">Nella pagina **Riepilogo** fare clic su **Avanti** per iniziare a unire le topologie per rimuovere il sito legacy.</span><span class="sxs-lookup"><span data-stu-id="feb0c-114">On the **Summary** page, click **Next** to begin merging the topologies to remove the legacy site.</span></span>

7.  <span data-ttu-id="feb0c-115">Verificare che nella colonna **Stato** sia visualizzato il valore **Esito positivo** e quindi fare clic su **Fine** per chiudere la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="feb0c-115">In the **Status** column, verify that the value is **Success** and then click **Finish** to close the wizard.</span></span>

8.  <span data-ttu-id="feb0c-116">Nel riquadro sinistro del Generatore di topologie espandere BackCompatSite e verificare che non siano elencati server.</span><span class="sxs-lookup"><span data-stu-id="feb0c-116">In the left pane of Topology Builder, expand the BackCompatSite and ensure no servers are listed.</span></span>

9.  <span data-ttu-id="feb0c-117">Fare clic con il pulsante destro del mouse su **BackCompatSite** e quindi scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="feb0c-117">Right-click the **BackCompatSite**, and then click **Delete**.</span></span>

10. <span data-ttu-id="feb0c-118">In **Generatore di topologie** selezionare il nodo di primo livello **Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="feb0c-118">In **Topology Builder**, select the top-most node **Lync Server**.</span></span>

11. <span data-ttu-id="feb0c-119">Nel menu **Azioni** selezionare **Pubblica topologia** e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="feb0c-119">From the **Action** menu, select **Publish Topology** and then click **Next**.</span></span>

12. <span data-ttu-id="feb0c-120">Al termine della **Pubblicazione guidata**, fare clic su **Fine** per chiudere la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="feb0c-120">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

