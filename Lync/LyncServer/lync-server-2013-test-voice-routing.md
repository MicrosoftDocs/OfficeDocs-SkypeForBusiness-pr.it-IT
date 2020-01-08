---
title: 'Lync Server 2013: Testare il routing vocale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test voice routing
ms:assetid: d3aae909-fef6-440f-b144-0b62dc82bf5d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398915(v=OCS.15)
ms:contentKeyID: 48185444
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0ac9fdac24178bfec7ebce97cbdfdd15707913d1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980775"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-voice-routing-in-lync-server-2013"></a><span data-ttu-id="a8687-102">Testare il routing vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a8687-102">Test voice routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a8687-103">_**Argomento Ultima modifica:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="a8687-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="a8687-104">Puoi usare la scheda **routing vocale di test** del pannello di controllo di Lync Server per configurare gli scenari dei casi di test.</span><span class="sxs-lookup"><span data-stu-id="a8687-104">You can use the Lync Server Control Panel **Test Voice Routing** tab to configure test case scenarios.</span></span> <span data-ttu-id="a8687-105">Per definire un test case, specificare il dial plan, il criterio vocale, l'uso PSTN e la route vocale per testare un numero di telefono specificato.</span><span class="sxs-lookup"><span data-stu-id="a8687-105">To define a test case, you specify the dial plan, voice policy, PSTN usage, and voice route against which to test a specified phone number.</span></span>

<span data-ttu-id="a8687-106">Prima di distribuire effettivamente la configurazione del routing vocale, è consigliabile testarla su vari numeri di telefono per verificare che i risultati siano quello previsto.</span><span class="sxs-lookup"><span data-stu-id="a8687-106">Before you actually deploy your voice routing configuration, we recommend that you test it on various phone numbers to make sure that the results are what you're expecting.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="a8687-107">È possibile usare i comandi <STRONG>Esporta</STRONG> test case e <STRONG>Importa test case</STRONG> per salvare i casi di test di routing vocale e importarli per l'uso in un altro computer.</span><span class="sxs-lookup"><span data-stu-id="a8687-107">You can use the <STRONG>Export test cases</STRONG> and <STRONG>Import test cases</STRONG> commands to save voice routing test cases and import them for use on another computer.</span></span>



</div>

<div>


> [!WARNING]  
> <span data-ttu-id="a8687-108">Se si elimina una parte della configurazione del routing vocale, ad esempio un dial plan, un criterio vocale, una route vocale o un uso telefonico, è necessario rivedere e aggiornare i casi di test di routing vocale.</span><span class="sxs-lookup"><span data-stu-id="a8687-108">If you delete any part of your voice routing configuration, such as a dial plan, voice policy, voice route, or phone usage, you should review and update your voice routing test cases.</span></span> <span data-ttu-id="a8687-109">Il pannello di controllo di Lync Server non avvisa i casi di test non più validi a causa delle configurazioni modificate.</span><span class="sxs-lookup"><span data-stu-id="a8687-109">The Lync Server Control Panel will not alert you to test cases that are no longer valid due to changed configurations.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a8687-110">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="a8687-110">In This Section</span></span>

  - [<span data-ttu-id="a8687-111">Creare un test case di routing vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a8687-111">Create a voice routing test case in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-routing-test-case.md)

  - [<span data-ttu-id="a8687-112">Esportare test case di routing vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a8687-112">Export voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-export-voice-routing-test-cases.md)

  - [<span data-ttu-id="a8687-113">Importare test case di routing vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a8687-113">Import voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-import-voice-routing-test-cases.md)

  - [<span data-ttu-id="a8687-114">Esecuzione di test del routing vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a8687-114">Running voice routing tests in Lync Server 2013</span></span>](lync-server-2013-running-voice-routing-tests.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

