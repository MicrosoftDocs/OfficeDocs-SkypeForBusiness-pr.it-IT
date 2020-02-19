---
title: 'Lync Server 2013: testare il routing vocale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test voice routing
ms:assetid: d3aae909-fef6-440f-b144-0b62dc82bf5d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398915(v=OCS.15)
ms:contentKeyID: 48185444
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eff0d59de7822f738cc7e2253cf728690dd45b50
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141562"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-voice-routing-in-lync-server-2013"></a><span data-ttu-id="1b1df-102">Testare il routing vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1b1df-102">Test voice routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1b1df-103">_**Ultimo argomento modificato:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="1b1df-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="1b1df-104">È possibile utilizzare la scheda **routing vocale di test** del pannello di controllo di Lync Server per configurare gli scenari di test case.</span><span class="sxs-lookup"><span data-stu-id="1b1df-104">You can use the Lync Server Control Panel **Test Voice Routing** tab to configure test case scenarios.</span></span> <span data-ttu-id="1b1df-105">Per definire un test case, specificare il dial plan, il criterio vocale, l'utilizzo PSTN e la route vocale in base ai quali testare un numero di telefono specificato.</span><span class="sxs-lookup"><span data-stu-id="1b1df-105">To define a test case, you specify the dial plan, voice policy, PSTN usage, and voice route against which to test a specified phone number.</span></span>

<span data-ttu-id="1b1df-106">Prima di distribuire effettivamente la configurazione del routing vocale, è consigliabile testarla su vari numeri di telefono per assicurarsi che i risultati siano quelli previsti.</span><span class="sxs-lookup"><span data-stu-id="1b1df-106">Before you actually deploy your voice routing configuration, we recommend that you test it on various phone numbers to make sure that the results are what you're expecting.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="1b1df-107">È possibile utilizzare i comandi <STRONG>Esporta test case</STRONG> e <STRONG>Importa test case</STRONG> per salvare i test case del routing vocale e importarli per l'uso su un altro computer.</span><span class="sxs-lookup"><span data-stu-id="1b1df-107">You can use the <STRONG>Export test cases</STRONG> and <STRONG>Import test cases</STRONG> commands to save voice routing test cases and import them for use on another computer.</span></span>



</div>

<div>


> [!WARNING]  
> <span data-ttu-id="1b1df-108">Se si elimina una parte della configurazione del routing vocale, ad esempio un dial plan, un criterio vocale, una route vocale o un utilizzo del telefono, è necessario controllare e aggiornare i test case del routing vocale.</span><span class="sxs-lookup"><span data-stu-id="1b1df-108">If you delete any part of your voice routing configuration, such as a dial plan, voice policy, voice route, or phone usage, you should review and update your voice routing test cases.</span></span> <span data-ttu-id="1b1df-109">Nel pannello di controllo di Lync Server non verrà avvisato di testare i casi che non sono più validi a causa di configurazioni modificate.</span><span class="sxs-lookup"><span data-stu-id="1b1df-109">The Lync Server Control Panel will not alert you to test cases that are no longer valid due to changed configurations.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="1b1df-110">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="1b1df-110">In This Section</span></span>

  - [<span data-ttu-id="1b1df-111">Creare un test case di routing vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1b1df-111">Create a voice routing test case in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-routing-test-case.md)

  - [<span data-ttu-id="1b1df-112">Esportare test case di routing vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1b1df-112">Export voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-export-voice-routing-test-cases.md)

  - [<span data-ttu-id="1b1df-113">Importare test case di routing vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1b1df-113">Import voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-import-voice-routing-test-cases.md)

  - [<span data-ttu-id="1b1df-114">Esecuzione di test del routing vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1b1df-114">Running voice routing tests in Lync Server 2013</span></span>](lync-server-2013-running-voice-routing-tests.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

