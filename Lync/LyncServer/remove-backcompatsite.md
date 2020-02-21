---
title: Rimuovere BackCompatSite
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove BackCompatSite
ms:assetid: 039650e3-541b-45c2-a682-c4fa08423118
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204637(v=OCS.15)
ms:contentKeyID: 48183265
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d41d333e834dba34da2a1a04854571d721e94e38
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42209450"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-backcompatsite"></a><span data-ttu-id="2a468-102">Rimuovere BackCompatSite</span><span class="sxs-lookup"><span data-stu-id="2a468-102">Remove BackCompatSite</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2a468-103">_**Ultimo argomento modificato:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="2a468-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="2a468-104">Dopo avere disattivato tutti i pool e avere disinstallato tutti i server perimetrali, eseguire la procedura di unione guidata del Generatore di topologie per rimuovere **BackCompatSite**.</span><span class="sxs-lookup"><span data-stu-id="2a468-104">After all pools are deactivated and all Edge Servers have been uninstalled, run the Topology Builder Merge wizard to remove the **BackCompatSite**.</span></span>

<div>

## <a name="to-remove-backcompat-site-from-topology-builder"></a><span data-ttu-id="2a468-105">Per rimuovere BackCompatSite dal Generatore di topologie</span><span class="sxs-lookup"><span data-stu-id="2a468-105">To remove BackCompat site from Topology Builder</span></span>

1.  <span data-ttu-id="2a468-106">Aprire una distribuzione esistente dal Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="2a468-106">Open an existing deployment from Topology Builder.</span></span>

2.  <span data-ttu-id="2a468-107">Scegliere **Unisci topologia 2007 R2** dal menu **Azione**.</span><span class="sxs-lookup"><span data-stu-id="2a468-107">In the **Action** menu, click **Merge 2007 R2 Topology**.</span></span>

3.  <span data-ttu-id="2a468-108">Fare clic su **Avanti** per continuare.</span><span class="sxs-lookup"><span data-stu-id="2a468-108">Click **Next** to continue.</span></span>

4.  <span data-ttu-id="2a468-p101">Nella pagina **Specifica il server perimetrale legacy** assicurarsi che l'elenco di server perimetrali sia vuoto. Se l'elenco non è vuoto, utilizzare il pulsante **Rimuovi** per rimuovere tutti i server perimetrali legacy e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="2a468-p101">On the **Specify Legacy Edge** page, ensure that list of Edge Servers is empty. If the list is not empty, use the **Remove** button to remove all the legacy Edge Servers, and then click **Next**.</span></span>
    
    <span data-ttu-id="2a468-111">![Procedura guidata per la topologia di Unione, specificare la pagina installazione Edge](images/JJ204637.fb35a59a-711e-4259-b177-7311df1fed3c(OCS.15).jpg "Procedura guidata per la topologia di Unione, specificare la pagina installazione Edge")</span><span class="sxs-lookup"><span data-stu-id="2a468-111">![Merge Topology Wizard, Specify Edge Setup page](images/JJ204637.fb35a59a-711e-4259-b177-7311df1fed3c(OCS.15).jpg "Merge Topology Wizard, Specify Edge Setup page")</span></span>  

5.  <span data-ttu-id="2a468-112">Nella pagina **Specificare la porta SIP interna** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="2a468-112">On the **Specify Internal SIP port setting** page, click **Next**.</span></span>

6.  <span data-ttu-id="2a468-113">Nella pagina **Riepilogo** fare clic su **Avanti** per iniziare a unire le topologie per rimuovere il sito legacy.</span><span class="sxs-lookup"><span data-stu-id="2a468-113">On the **Summary** page, click **Next** to begin merging the topologies to remove the legacy site.</span></span>

7.  <span data-ttu-id="2a468-114">Verificare che nella colonna **Stato** sia visualizzato il valore **Esito positivo** e quindi fare clic su **Fine** per chiudere la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="2a468-114">In the **Status** column, verify that the value is **Success** and then click **Finish** to close the wizard.</span></span>

8.  <span data-ttu-id="2a468-115">Nel riquadro sinistro del Generatore di topologie espandere BackCompatSite e verificare che non siano elencati server.</span><span class="sxs-lookup"><span data-stu-id="2a468-115">In the left pane of Topology Builder, expand the BackCompatSite and ensure no servers are listed.</span></span>

9.  <span data-ttu-id="2a468-116">Fare clic con il pulsante destro del mouse su **BackCompatSite** e quindi scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="2a468-116">Right-click the **BackCompatSite**, and then click **Delete**.</span></span>

10. <span data-ttu-id="2a468-117">In **Generatore di topologie** selezionare il nodo di primo livello **Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="2a468-117">In **Topology Builder**, select the top-most node **Lync Server**.</span></span>

11. <span data-ttu-id="2a468-118">Nel menu **Azioni** selezionare **Pubblica topologia** e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="2a468-118">From the **Action** menu, select **Publish Topology** and then click **Next**.</span></span>

12. <span data-ttu-id="2a468-119">Al termine della **Pubblicazione guidata**, fare clic su **Fine** per chiudere la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="2a468-119">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

