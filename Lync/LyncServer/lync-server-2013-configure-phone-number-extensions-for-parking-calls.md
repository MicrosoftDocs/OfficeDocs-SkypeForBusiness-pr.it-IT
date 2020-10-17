---
title: 'Lync Server 2013: configurare le estensioni dei numeri di telefono per le chiamate di parcheggio'
description: 'Lync Server 2013: configurare le estensioni dei numeri di telefono per il parcheggio delle chiamate.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure phone number extensions for parking calls
ms:assetid: fbf97624-9587-42a6-b276-1b69c574a74d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182611(v=OCS.15)
ms:contentKeyID: 48185980
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6219e04243d0c19bc37251f7d113f7ebdd09fb72
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548832"
---
# <a name="configure-phone-number-extensions-for-parking-calls-in-lync-server-2013"></a><span data-ttu-id="2d7ea-103">Configurare le estensioni dei numeri di telefono per il parcheggio delle chiamate in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2d7ea-103">Configure phone number extensions for parking calls in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2d7ea-104">_**Ultimo argomento modificato:** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="2d7ea-104">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="2d7ea-105">L'applicazione Parcheggio di chiamata utilizza i numeri di interno nella tabella orbit del parcheggio di chiamata per parcheggiare le chiamate.</span><span class="sxs-lookup"><span data-stu-id="2d7ea-105">The Call Park application uses extension numbers in the Call Park orbit table to park calls.</span></span> <span data-ttu-id="2d7ea-106">È necessario configurare la tabella orbit del parcheggio di chiamata con gli intervalli di numeri di interno riserve dall'organizzazione per le chiamate parcheggiate.</span><span class="sxs-lookup"><span data-stu-id="2d7ea-106">You need to configure the Call Park orbit table with the ranges of extension numbers that your organization reserves for parked calls.</span></span> <span data-ttu-id="2d7ea-107">Questi interni devono essere virtuali (ossia interni a cui non è assegnato alcun utente o telefono).</span><span class="sxs-lookup"><span data-stu-id="2d7ea-107">These extensions need to be virtual extensions (that is, extensions that have no user or phone assigned to them).</span></span> <span data-ttu-id="2d7ea-108">Ogni pool di Lync Server in cui viene distribuita e configurata un'applicazione del parcheggio di chiamata può disporre di uno o più intervalli di Orbit.</span><span class="sxs-lookup"><span data-stu-id="2d7ea-108">Each Lync Server pool where a Call Park application is deployed and configured can have one or more orbit ranges.</span></span> <span data-ttu-id="2d7ea-109">Gli intervalli di Orbit devono essere univoci a livello globale nella distribuzione di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2d7ea-109">Orbit ranges must be globally unique across the Lync Server deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2d7ea-110">È necessario selezionare la casella di controllo <STRONG>Abilita il parcheggio di chiamata</STRONG> nel criterio vocale prima di poter utilizzare il parcheggio di chiamata.</span><span class="sxs-lookup"><span data-stu-id="2d7ea-110">You must select the <STRONG>Enable call park</STRONG> check box in your voice policy before you can use Call Park.</span></span> <span data-ttu-id="2d7ea-111">Per impostazione predefinita, questa opzione non è selezionata.</span><span class="sxs-lookup"><span data-stu-id="2d7ea-111">By default, this option is not selected.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="2d7ea-112">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="2d7ea-112">In This Section</span></span>

  - [<span data-ttu-id="2d7ea-113">Creare o modificare un intervallo di codici orbit del parcheggio di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2d7ea-113">Create or modify a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)

  - [<span data-ttu-id="2d7ea-114">Eliminare un intervallo di codici orbit del parcheggio di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2d7ea-114">Delete a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-delete-a-call-park-orbit-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

