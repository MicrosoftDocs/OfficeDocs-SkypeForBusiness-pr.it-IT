---
title: 'Lync Server 2013: Definire e configurare una topologia in Generatore di topologie'
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
ms.openlocfilehash: 876651b0d0c5ed33d4e82429822585de4a2b8579
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728426"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-and-configure-a-topology-in-topology-builder-for-lync-server-2013"></a><span data-ttu-id="7d311-102">Definire e configurare una topologia in Generatore di topologie per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7d311-102">Define and configure a topology in Topology Builder for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7d311-103">_**Argomento Ultima modifica:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="7d311-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="7d311-104">L'uso di generatore di topologia per definire una nuova topologia o per modificare una topologia esistente non richiede l'appartenenza a un amministratore locale o a un gruppo di domini privilegiati.</span><span class="sxs-lookup"><span data-stu-id="7d311-104">Running Topology Builder to define a new topology or to modify an existing topology does not require membership in a local administrator or privileged domain group.</span></span> <span data-ttu-id="7d311-105">Generatore di topologia guida i passaggi necessari per definire la topologia per un pool di front end Enterprise Edition o una versione standard in base ai requisiti di configurazione.</span><span class="sxs-lookup"><span data-stu-id="7d311-105">Topology Builder guides you through the steps necessary to define your topology for an Enterprise Edition Front End pool or a Standard Edition, based on your configuration requirements.</span></span>

<span data-ttu-id="7d311-106">È necessario usare generatore di topologia per completare e pubblicare la topologia prima di poter installare Lync Server 2013 nei server.</span><span class="sxs-lookup"><span data-stu-id="7d311-106">You must use Topology Builder to complete and publish the topology before you can install Lync Server 2013 on servers.</span></span> <span data-ttu-id="7d311-107">La procedura seguente include i passaggi necessari per definire una nuova topologia.</span><span class="sxs-lookup"><span data-stu-id="7d311-107">The following procedure includes the steps required to define a new topology.</span></span>

<div>

## <a name="to-define-a-topology"></a><span data-ttu-id="7d311-108">Per definire una topologia</span><span class="sxs-lookup"><span data-stu-id="7d311-108">To define a topology</span></span>

1.  <span data-ttu-id="7d311-109">Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Generatore di topologia di Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="7d311-109">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="7d311-110">In Generatore di topologie selezionare **nuova topologia**.</span><span class="sxs-lookup"><span data-stu-id="7d311-110">In Topology Builder, select **New Topology**.</span></span> <span data-ttu-id="7d311-111">Viene richiesto di richiedere un percorso e un nome di file per il salvataggio della topologia.</span><span class="sxs-lookup"><span data-stu-id="7d311-111">You are prompted for a location and file name for saving the topology.</span></span> <span data-ttu-id="7d311-112">Assegna al file della topologia un nome significativo e accetta l'estensione predefinita di. tbxml.</span><span class="sxs-lookup"><span data-stu-id="7d311-112">Give the topology file a meaningful name and accept the default extension of .tbxml.</span></span> <span data-ttu-id="7d311-113">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="7d311-113">Click **OK**.</span></span>

3.  <span data-ttu-id="7d311-114">Passare al percorso in cui si vuole salvare il nuovo file XML della topologia, immettere un nome per il file e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="7d311-114">Navigate to the location where you want to save the new topology XML file, enter a name for the file, and then click **Save**.</span></span>

4.  <span data-ttu-id="7d311-115">Nella pagina **Definisci il dominio principale** immettere il nome del dominio SIP principale per l'organizzazione e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="7d311-115">On the **Define the primary domain** page, enter the name of the primary SIP domain for your organization, and then click **Next**.</span></span>

5.  <span data-ttu-id="7d311-116">Nella pagina **specifica altri domini supportati** immettere i nomi di altri domini, se presenti, e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="7d311-116">On the **Specify additional supported domains** page, enter the names of additional domains, if any, and then click **Next**.</span></span>

6.  <span data-ttu-id="7d311-117">Nella pagina **Definisci il primo sito** immettere un nome e una descrizione per il primo sito e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="7d311-117">On the **Define the first site** page, enter a name and a description for the first site, and then click **Next**.</span></span>

7.  <span data-ttu-id="7d311-118">Nella pagina **specifica i dettagli del sito** immettere le informazioni sulla posizione per il sito e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="7d311-118">On the **Specify site details** page, enter the location information for the site, and then click **Next**.</span></span>

8.  <span data-ttu-id="7d311-119">Nella **nuova topologia la pagina è stata definita correttamente** , verificare che la casella di controllo **Apri la nuova creazione guidata front-end al termine della procedura** guidata sia selezionata e quindi fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="7d311-119">On the **New topology was successfully defined** page, make sure the **Open the New Front End Wizard when this wizard closes** check box is selected, and then click **Finish**.</span></span>

<span data-ttu-id="7d311-120">Dopo aver definito e salvato la topologia, usare la nuova procedura guidata front-end per definire un pool Front-end o un server Standard Edition per il sito.</span><span class="sxs-lookup"><span data-stu-id="7d311-120">After you’ve defined and saved the topology, use the New Front End Wizard to define a Front End pool or Standard Edition server for your site.</span></span> <span data-ttu-id="7d311-121">Per informazioni dettagliate, vedere [definire e configurare un pool Front-end o un server Standard Edition in Lync server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md).</span><span class="sxs-lookup"><span data-stu-id="7d311-121">For details, see [Define and configure a Front End pool or Standard Edition server in Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

