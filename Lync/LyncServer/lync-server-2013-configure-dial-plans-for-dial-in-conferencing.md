---
title: 'Lync Server 2013: configurare dial plan per le conferenze telefoniche con accesso esterno'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure dial plans for dial-in conferencing
ms:assetid: a3e0958e-384f-43e5-b4c9-686b6ecac7ed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412768(v=OCS.15)
ms:contentKeyID: 48185051
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f934c4888ac725439ee1ded2f9c6e95345e292c1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140409"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-dial-plans-for-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="0f288-102">Configurare i dial plan per le conferenze telefoniche con accesso esterno in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f288-102">Configure dial plans for dial-in conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0f288-103">_**Ultimo argomento modificato:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="0f288-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="0f288-104">Quando si distribuiscono le conferenze telefoniche con accesso esterno, è necessario creare o modificare uno o più dial plan per il routing dei numeri di telefono di accessi.</span><span class="sxs-lookup"><span data-stu-id="0f288-104">When you deploy dial-in conferencing, you need to create or modify one or more dial plans for routing dial-in access phone numbers.</span></span> <span data-ttu-id="0f288-105">Assicurarsi che almeno una regola di normalizzazione in ogni dial plan converta le estensioni telefoniche in numeri di telefono completi nel formato E. 164.</span><span class="sxs-lookup"><span data-stu-id="0f288-105">Make sure that at least one normalization rule in each dial plan converts telephone extensions into complete phone numbers in E.164 format.</span></span> <span data-ttu-id="0f288-106">Gli utenti delle conferenze telefoniche con accesso esterno partecipano alle conferenze come utenti autenticati dell'organizzazione immettendo il proprio PIN (Personal Identification Number) e il relativo numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="0f288-106">Users of dial-in conferencing join conferences as authenticated enterprise users by entering their personal identification number (PIN) and their phone number.</span></span> <span data-ttu-id="0f288-107">È necessaria una regola di normalizzazione per convertire le estensioni in numeri di telefono completi in modo che gli utenti possano essere autenticati quando immettono solo un interno telefonico.</span><span class="sxs-lookup"><span data-stu-id="0f288-107">You need a normalization rule to convert extensions into complete phone numbers so that users can be authenticated when they enter just a telephone extension.</span></span>

<span data-ttu-id="0f288-108">Per impostare i dial plan per le conferenze telefoniche con accesso esterno, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0f288-108">To set up dial plans for dial-in conferencing, do the following:</span></span>

  - <span data-ttu-id="0f288-109">Se si distribuisce o meno VoIP aziendale, modificare il dial plan globale per aggiungere un'area di conferenza telefonica con accesso esterno e per assicurarsi che una regola di normalizzazione converta con precisione i numeri di accesso telefonico in ingresso.</span><span class="sxs-lookup"><span data-stu-id="0f288-109">Whether or not you deploy Enterprise Voice, modify the global dial plan to add a dial-in conferencing region and to make sure that a normalization rule accurately converts your dial-in access numbers.</span></span> <span data-ttu-id="0f288-110">Per istruzioni dettagliate, vedere [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span><span class="sxs-lookup"><span data-stu-id="0f288-110">For detailed instructions, see [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span></span>

  - <span data-ttu-id="0f288-111">Se non è stata distribuita VoIP aziendale, creare i dial plan per i numeri di accesso per le conferenze telefoniche con chiamata in ingresso.</span><span class="sxs-lookup"><span data-stu-id="0f288-111">If you did not deploy Enterprise Voice, create dial plans for your dial-in conferencing access numbers.</span></span> <span data-ttu-id="0f288-112">Assicurarsi di includere un'area di conferenza telefonica con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="0f288-112">Be sure to include a dial-in conferencing region.</span></span> <span data-ttu-id="0f288-113">Per istruzioni dettagliate, vedere [creazione di un dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span><span class="sxs-lookup"><span data-stu-id="0f288-113">For detailed instructions, see [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span></span>

  - <span data-ttu-id="0f288-114">Se è stata distribuita VoIP aziendale, modificare i piani di chiamata VoIP aziendale in base alle esigenze per includere le aree geografiche e utilizzare le regole di normalizzazione appropriate per i numeri di accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="0f288-114">If you deployed Enterprise Voice, modify Enterprise Voice dial plans as necessary to include regions and use appropriate normalization rules for dial-in access numbers.</span></span> <span data-ttu-id="0f288-115">Per istruzioni dettagliate, vedere [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span><span class="sxs-lookup"><span data-stu-id="0f288-115">For detailed instructions, see [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span></span> <span data-ttu-id="0f288-116">È inoltre possibile creare piani di chiamata dedicati che vengono utilizzati solo per i numeri di accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="0f288-116">You can also create dedicated dial plans that are used only for dial-in access numbers.</span></span> <span data-ttu-id="0f288-117">Per istruzioni dettagliate, vedere [creazione di un dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span><span class="sxs-lookup"><span data-stu-id="0f288-117">For detailed instructions, see [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span></span>

<span data-ttu-id="0f288-118">Per informazioni dettagliate sulla pianificazione delle aree geografiche, vedere Servizi di [conferenza telefonica con accesso esterno in Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="0f288-118">For details about planning regions, see [Dial-in conferencing requirements in Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md) in the Planning documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="0f288-119">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="0f288-119">In This Section</span></span>

  - [<span data-ttu-id="0f288-120">Visualizzare le informazioni sul dial plan in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f288-120">View dial plan information in Lync Server 2013</span></span>](lync-server-2013-view-dial-plan-information.md)

  - [<span data-ttu-id="0f288-121">Creare un dial plan in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f288-121">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)

  - [<span data-ttu-id="0f288-122">Modificare un dial plan in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f288-122">Modify a dial plan in Lync Server 2013</span></span>](lync-server-2013-modify-a-dial-plan.md)

  - [<span data-ttu-id="0f288-123">Definizione di regole di normalizzazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f288-123">Defining normalization rules in Lync Server 2013</span></span>](lync-server-2013-defining-normalization-rules.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

