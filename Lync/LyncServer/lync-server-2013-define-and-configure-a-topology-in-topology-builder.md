---
title: 'Lync Server 2013: definire e configurare una topologia in Generatore di topologie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define and configure a topology in Topology Builder
ms:assetid: 99231ff5-1c21-432b-ad65-8675fcd484f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398788(v=OCS.15)
ms:contentKeyID: 48184953
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e3877b19bac01991856313302378c92065bacf22
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036616"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-and-configure-a-topology-in-topology-builder-for-lync-server-2013"></a><span data-ttu-id="62011-102">Definire e configurare una topologia in Generatore di topologie per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="62011-102">Define and configure a topology in Topology Builder for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="62011-103">_**Ultimo argomento modificato:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="62011-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="62011-104">L'esecuzione di generatore di topologie per definire una nuova topologia o per modificare una topologia esistente non richiede l'appartenenza a un amministratore locale o a un gruppo di dominio privilegiato.</span><span class="sxs-lookup"><span data-stu-id="62011-104">Running Topology Builder to define a new topology or to modify an existing topology does not require membership in a local administrator or privileged domain group.</span></span> <span data-ttu-id="62011-105">In Generatore di topologie vengono illustrati i passaggi necessari per definire la topologia per un pool Enterprise Edition front end o una versione standard, in base ai requisiti di configurazione.</span><span class="sxs-lookup"><span data-stu-id="62011-105">Topology Builder guides you through the steps necessary to define your topology for an Enterprise Edition Front End pool or a Standard Edition, based on your configuration requirements.</span></span>

<span data-ttu-id="62011-106">Per poter installare Lync Server 2013 sui server, è necessario utilizzare Generatore di topologie per completare e pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="62011-106">You must use Topology Builder to complete and publish the topology before you can install Lync Server 2013 on servers.</span></span> <span data-ttu-id="62011-107">La procedura seguente include i passaggi per definizione di una nuova topologia.</span><span class="sxs-lookup"><span data-stu-id="62011-107">The following procedure includes the steps required to define a new topology.</span></span>

<div>

## <a name="to-define-a-topology"></a><span data-ttu-id="62011-108">Per definire una topologia</span><span class="sxs-lookup"><span data-stu-id="62011-108">To define a topology</span></span>

1.  <span data-ttu-id="62011-109">Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Generatore di topologie**.</span><span class="sxs-lookup"><span data-stu-id="62011-109">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="62011-110">In Generatore di topologie selezionare **nuova topologia**.</span><span class="sxs-lookup"><span data-stu-id="62011-110">In Topology Builder, select **New Topology**.</span></span> <span data-ttu-id="62011-111">Verrà richiesto di inserire un percorso e un nome file per il salvataggio della topologia.</span><span class="sxs-lookup"><span data-stu-id="62011-111">You are prompted for a location and file name for saving the topology.</span></span> <span data-ttu-id="62011-112">Assegnare alla topologia un nome significativo e accettare l'estensione predefinita tbxml.</span><span class="sxs-lookup"><span data-stu-id="62011-112">Give the topology file a meaningful name and accept the default extension of .tbxml.</span></span> <span data-ttu-id="62011-113">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="62011-113">Click **OK**.</span></span>

3.  <span data-ttu-id="62011-114">Passare al percorso in cui si desidera salvare il file XML della nuova topologia, immettere un nome per il file e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="62011-114">Navigate to the location where you want to save the new topology XML file, enter a name for the file, and then click **Save**.</span></span>

4.  <span data-ttu-id="62011-115">Nella pagina **Definire il dominio primario** immettere il nome del dominio SIP primario per l'organizzazione e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="62011-115">On the **Define the primary domain** page, enter the name of the primary SIP domain for your organization, and then click **Next**.</span></span>

5.  <span data-ttu-id="62011-116">Nella pagina **Specificare i domini aggiuntivi supportati** immettere i nomi degli eventuali domini aggiuntivi e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="62011-116">On the **Specify additional supported domains** page, enter the names of additional domains, if any, and then click **Next**.</span></span>

6.  <span data-ttu-id="62011-117">Nella pagina **Definire il primo sito** immettere il nome e la descrizione del primo sito e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="62011-117">On the **Define the first site** page, enter a name and a description for the first site, and then click **Next**.</span></span>

7.  <span data-ttu-id="62011-118">Nella pagina **Specificare i dettagli del sito** immettere le informazioni relative alla posizione del sito e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="62011-118">On the **Specify site details** page, enter the location information for the site, and then click **Next**.</span></span>

8.  <span data-ttu-id="62011-119">Nella pagina **nuova topologia è stata definita correttamente** , verificare che la casella di controllo **Apri la procedura guidata nuovo front-end al termine della procedura guidata** sia selezionata e quindi fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="62011-119">On the **New topology was successfully defined** page, make sure the **Open the New Front End Wizard when this wizard closes** check box is selected, and then click **Finish**.</span></span>

<span data-ttu-id="62011-120">Dopo aver definito e salvato la topologia, utilizzare la nuova procedura guidata front-end per definire un pool Front end o un server Standard Edition per il sito.</span><span class="sxs-lookup"><span data-stu-id="62011-120">After you’ve defined and saved the topology, use the New Front End Wizard to define a Front End pool or Standard Edition server for your site.</span></span> <span data-ttu-id="62011-121">Per informazioni dettagliate, vedere [define and Configure a front end pool or Standard Edition server in Lync server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md).</span><span class="sxs-lookup"><span data-stu-id="62011-121">For details, see [Define and configure a Front End pool or Standard Edition server in Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

