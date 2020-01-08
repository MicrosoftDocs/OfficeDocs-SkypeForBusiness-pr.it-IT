---
title: Rimuovere BackCompatSite
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Remove BackCompatSite
ms:assetid: 039650e3-541b-45c2-a682-c4fa08423118
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204637(v=OCS.15)
ms:contentKeyID: 48183265
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe6a3d1dc92e45bc99892e7827394376b6f28b12
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975773"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-backcompatsite"></a><span data-ttu-id="2bef8-102">Rimuovere BackCompatSite</span><span class="sxs-lookup"><span data-stu-id="2bef8-102">Remove BackCompatSite</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2bef8-103">_**Argomento Ultima modifica:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="2bef8-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="2bef8-104">Dopo che tutti i pool sono stati disattivati e tutti i server perimetrali sono stati disinstallati, eseguire la procedura guidata unione di generatore di topologia per rimuovere **BackCompatSite**.</span><span class="sxs-lookup"><span data-stu-id="2bef8-104">After all pools are deactivated and all Edge Servers have been uninstalled, run the Topology Builder Merge wizard to remove the **BackCompatSite**.</span></span>

<div>

## <a name="to-remove-backcompat-site-from-topology-builder"></a><span data-ttu-id="2bef8-105">Per rimuovere il sito BackCompat da generatore di topologie</span><span class="sxs-lookup"><span data-stu-id="2bef8-105">To remove BackCompat site from Topology Builder</span></span>

1.  <span data-ttu-id="2bef8-106">Aprire una distribuzione esistente da generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="2bef8-106">Open an existing deployment from Topology Builder.</span></span>

2.  <span data-ttu-id="2bef8-107">Nel menu **azione** fare clic su **Unisci topologia di 2007 R2**.</span><span class="sxs-lookup"><span data-stu-id="2bef8-107">In the **Action** menu, click **Merge 2007 R2 Topology**.</span></span>

3.  <span data-ttu-id="2bef8-108">Fare clic su **Avanti** per continuare.</span><span class="sxs-lookup"><span data-stu-id="2bef8-108">Click **Next** to continue.</span></span>

4.  <span data-ttu-id="2bef8-109">Nella pagina **specifica legacy Edge** verificare che l'elenco di Edge Server sia vuoto.</span><span class="sxs-lookup"><span data-stu-id="2bef8-109">On the **Specify Legacy Edge** page, ensure that list of Edge Servers is empty.</span></span> <span data-ttu-id="2bef8-110">Se l'elenco non è vuoto, usare il pulsante **Rimuovi** per rimuovere tutti i server perimetrali legacy e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="2bef8-110">If the list is not empty, use the **Remove** button to remove all the legacy Edge Servers, and then click **Next**.</span></span>
    
    <span data-ttu-id="2bef8-111">![Creazione guidata topologia Unione, specificare]la configurazione(images/JJ204637.fb35a59a-711e-4259-b177-7311df1fed3c(OCS.15).jpg "guidata della topologia di Unione, specificare la pagina di configurazione del bordo")</span><span class="sxs-lookup"><span data-stu-id="2bef8-111">![Merge Topology Wizard, Specify Edge Setup page](images/JJ204637.fb35a59a-711e-4259-b177-7311df1fed3c(OCS.15).jpg "Merge Topology Wizard, Specify Edge Setup page")</span></span>  

5.  <span data-ttu-id="2bef8-112">Nella pagina **specificare l'impostazione della porta SIP interna** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="2bef8-112">On the **Specify Internal SIP port setting** page, click **Next**.</span></span>

6.  <span data-ttu-id="2bef8-113">Nella pagina **Riepilogo** fare clic su **Avanti** per iniziare a unire le topologie per rimuovere il sito legacy.</span><span class="sxs-lookup"><span data-stu-id="2bef8-113">On the **Summary** page, click **Next** to begin merging the topologies to remove the legacy site.</span></span>

7.  <span data-ttu-id="2bef8-114">Nella colonna **stato** verificare che il valore sia **successo** e quindi fare clic su **fine** per chiudere la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="2bef8-114">In the **Status** column, verify that the value is **Success** and then click **Finish** to close the wizard.</span></span>

8.  <span data-ttu-id="2bef8-115">Nel riquadro sinistro di generatore di topologia espandere il BackCompatSite e assicurarsi che nessun server sia elencato.</span><span class="sxs-lookup"><span data-stu-id="2bef8-115">In the left pane of Topology Builder, expand the BackCompatSite and ensure no servers are listed.</span></span>

9.  <span data-ttu-id="2bef8-116">Fare clic con il pulsante destro del mouse sul **BackCompatSite**e quindi scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="2bef8-116">Right-click the **BackCompatSite**, and then click **Delete**.</span></span>

10. <span data-ttu-id="2bef8-117">In **Generatore di topologie**selezionare il più alto nodo **Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="2bef8-117">In **Topology Builder**, select the top-most node **Lync Server**.</span></span>

11. <span data-ttu-id="2bef8-118">Scegliere **Pubblica topologia** dal menu **azione** e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="2bef8-118">From the **Action** menu, select **Publish Topology** and then click **Next**.</span></span>

12. <span data-ttu-id="2bef8-119">Al termine della **pubblicazione guidata** , fare clic su **fine** per chiudere la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="2bef8-119">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

