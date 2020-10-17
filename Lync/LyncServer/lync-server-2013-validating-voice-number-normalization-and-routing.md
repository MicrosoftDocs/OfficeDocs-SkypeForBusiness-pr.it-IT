---
title: 'Lync Server 2013: convalidare la normalizzazione e il routing dei numeri vocali'
description: 'Lync Server 2013: convalidare la normalizzazione e il routing dei numeri vocali.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating voice number normalization and routing
ms:assetid: a6a825c7-6928-4e80-b7e9-803b7f7ebd13
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720922(v=OCS.15)
ms:contentKeyID: 63969633
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5f28f679cbb991bdb90362eb61c9c7b68879791e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547142"
---
# <a name="validating-voice-number-normalization-and-routing-in-lync-server-2013"></a><span data-ttu-id="54f9c-103">Convalidare la normalizzazione e il routing dei numeri vocali in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="54f9c-103">Validating voice number normalization and routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="54f9c-104">_**Ultimo argomento modificato:** 2014-05-19_</span><span class="sxs-lookup"><span data-stu-id="54f9c-104">_**Topic Last Modified:** 2014-05-19_</span></span>

<span data-ttu-id="54f9c-105">La normalizzazione e il routing dei numeri corretti è molto importante per l'ambiente funzionale VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="54f9c-105">Correct number normalization and routing is very important for functional Enterprise Voice environment.</span></span> <span data-ttu-id="54f9c-106">Soprattutto durante le migrazioni da PBX (Private Branch Exchange) a un ambiente Lync Server autonomo, una delle chiavi per la migrazione è quella di rivelare e documentare tutte le regole di composizione esistenti e creare regole di normalizzazione appropriate, criteri vocali, utilizzi telefonici e route.</span><span class="sxs-lookup"><span data-stu-id="54f9c-106">Especially during migrations from private branch exchange (PBX) to stand-alone Lync Server environment, one of the keys to successful migration is to reveal and document all existing dialing rules, and create appropriate normalization rules, voice policies, phone usages and routes.</span></span>

<span data-ttu-id="54f9c-107">La convalida della normalizzazione e del routing dei numeri è importante non solo durante la migrazione, ma anche durante il normale e stabile funzionamento del sistema.</span><span class="sxs-lookup"><span data-stu-id="54f9c-107">Validating number normalization and routing is important not only during migrations but also during normal, stable operation of the system.</span></span>

<span data-ttu-id="54f9c-108">È consigliabile eseguire questa convalida giornalmente utilizzando il pannello di controllo di Lync Server, iniziando con lo sviluppo di un set di test case robusto rispetto all'insieme corrente di regole di normalizzazione pubblicate nelle impostazioni globali di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="54f9c-108">We recommend conducting this validation daily by using the Lync Server Control Panel, starting with developing a robust set of test cases against the current set of normalization rules that were published in the Lync Server global settings.</span></span> <span data-ttu-id="54f9c-109">Questi test case devono essere eseguiti ogni giorno per evidenziare eventuali modifiche indesiderate apportate e salvate nel dial plan.</span><span class="sxs-lookup"><span data-stu-id="54f9c-109">These test cases should be run daily to highlight any unwanted changes that were made and committed to the dial plan.</span></span>

<span data-ttu-id="54f9c-110">Il pannello di controllo di Lync Server consente inoltre di visualizzare, testare, modificare, archiviare e condividere informazioni sulla configurazione del routing vocale e di modificare le regole di normalizzazione dei numeri di VoIP aziendale, dial plan, criteri vocali e route.</span><span class="sxs-lookup"><span data-stu-id="54f9c-110">Lync Server Control Panel also helps you visualize, test, change, archive, and share configuration information about voice routing and in changing Enterprise Voice number normalization rules, dial plans, voice policy, and routes.</span></span> <span data-ttu-id="54f9c-111">Sono disponibili funzionalità aggiuntive per eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="54f9c-111">It has additional features for doing the following:</span></span>

  - <span data-ttu-id="54f9c-112">Esportare e importare o eseguire il backup dei dati di routing vocale tra sistemi.</span><span class="sxs-lookup"><span data-stu-id="54f9c-112">Exporting and importing or backing up voice routing data between systems.</span></span>

  - <span data-ttu-id="54f9c-113">Verifica delle modifiche apportate alla configurazione prima del caricamento in un sistema attivo.</span><span class="sxs-lookup"><span data-stu-id="54f9c-113">Testing configuration changes before uploading them to a live system.</span></span>

  - <span data-ttu-id="54f9c-114">Creazione ed esecuzione di test case di configurazione per garantire l'usabilità dei dati di routing dopo aver apportato le modifiche, ma prima di eseguire il commit delle modifiche apportate a un sistema distribuito.</span><span class="sxs-lookup"><span data-stu-id="54f9c-114">Creating and running configuration test cases to help ensure the usability of routing data after you make changes to it, but before committing them the changes to a deployed system.</span></span>

  - <span data-ttu-id="54f9c-115">Creazione e modifica di regole di normalizzazione dei numeri, profili località, criteri vocali e dati di routing senza scrivere le espressioni regolari necessarie.</span><span class="sxs-lookup"><span data-stu-id="54f9c-115">Creating and changing number normalization rules, location profiles, voice policy, and routing data without writing the necessary regular expressions.</span></span>

  - <span data-ttu-id="54f9c-116">Analisi di un profilo percorso per la compatibilità con Lync Server Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="54f9c-116">Analyzing a location profile for compatibility with the Lync Server Phone Edition.</span></span>

  - <span data-ttu-id="54f9c-117">Per ulteriori informazioni sui test di routing vocale, vedere [test Voice routing in Lync Server 2013](lync-server-2013-test-voice-routing.md)</span><span class="sxs-lookup"><span data-stu-id="54f9c-117">More information about voice routing tests can be found at [Test voice routing in Lync Server 2013](lync-server-2013-test-voice-routing.md)</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="54f9c-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="54f9c-118">See Also</span></span>


[<span data-ttu-id="54f9c-119">Testare il routing vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="54f9c-119">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

