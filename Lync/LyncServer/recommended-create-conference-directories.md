---
title: (Scelta consigliata) Creare le directory conferenze
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: (Recommended) Create Conference Directories
ms:assetid: 787f4c94-1c96-468a-a74d-e06b7bd4b8a3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn832056(v=OCS.15)
ms:contentKeyID: 63146389
ms.date: 10/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e912beac1eeffe3214f8a8d638926d84f547a270
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978584"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="recommended-create-conference-directories"></a><span data-ttu-id="483ad-102">(Scelta consigliata) Creare le directory conferenze</span><span class="sxs-lookup"><span data-stu-id="483ad-102">(Recommended) Create Conference Directories</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="483ad-103">_**Argomento Ultima modifica:** 2014-10-03_</span><span class="sxs-lookup"><span data-stu-id="483ad-103">_**Topic Last Modified:** 2014-10-03_</span></span>

<span data-ttu-id="483ad-104">Le directory conferenza mantengono un mapping tra l'ID riunione alfanumerico usato da un partecipante per partecipare a una conferenza quando si usa Lync 2013 e l'ID conferenza solo numerico usato da un partecipante di conferenza telefonica con accesso esterno per partecipare alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="483ad-104">Conference directories maintain a mapping between the alphanumeric meeting ID that a participant uses to join a conference when using Lync 2013, and the numeric-only conference ID that a dial-in conferencing participant uses to join the conference.</span></span> <span data-ttu-id="483ad-105">Il formato dell'ID conferenza è il seguente:</span><span class="sxs-lookup"><span data-stu-id="483ad-105">The format of the conference ID is as follows:</span></span>

    <housekeeping digit (1 digit)><conference directory (usually 1-2 digits)><conference number (variable number of digits><check digit (1 digit)>

<span data-ttu-id="483ad-106">La creazione di più directory conferenza garantirà che gli ID conferenza rimarranno invariati finché non verrà creata una quantità significativa di conferenze.</span><span class="sxs-lookup"><span data-stu-id="483ad-106">Creating multiple conference directories will ensure that conference IDs will stay short until a significant amount of conferences have been created.</span></span> <span data-ttu-id="483ad-107">In un'organizzazione con un numero tipico di conferenze per ogni utente, è consigliabile creare una directory conferenza per ogni utenti di 999 nel pool.</span><span class="sxs-lookup"><span data-stu-id="483ad-107">In an organization with a typical number of conferences per user, we recommend that you create one conference directory for every 999 users in the pool.</span></span> <span data-ttu-id="483ad-108">Uso di questa guida di riferimento gli ID conferenza possono in genere essere mantenuti piccoli.</span><span class="sxs-lookup"><span data-stu-id="483ad-108">Using this guideline the conference IDs can generally be kept small.</span></span> <span data-ttu-id="483ad-109">Tuttavia, una volta che il numero di directory conferenza (tra i pool) supera 9, la lunghezza dell'ID conferenza crescerà per supportare altre conferenze.</span><span class="sxs-lookup"><span data-stu-id="483ad-109">However, once the number of conference directories (across the pools) exceed 9, the Conference ID length will grow to support additional conferences.</span></span>

<div>

## <a name="creating-a-conference-directory"></a><span data-ttu-id="483ad-110">Creazione di una directory conferenza</span><span class="sxs-lookup"><span data-stu-id="483ad-110">Creating a conference directory</span></span>

1.  <span data-ttu-id="483ad-111">In Lync Server Management Shell digitare il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="483ad-111">In Lync Server Management Shell, type the following cmdlet:</span></span>
    
        New-CsConferenceDirectory -Identity <XdsGlobalRelativeIdentity> -HomePool <String> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]
    
    <span data-ttu-id="483ad-112">Ad esempio, la seguente crea una directory congressuale con identità 42, ospitata nel pool atl-cs-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="483ad-112">For example, the following creates a conference directory with the identity 42, hosted on the pool atl-cs-001.litwareinc.com:</span></span>
    
        New-CsConferenceDirectory -Identity 42 -HomePool "atl-cs-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="483ad-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="483ad-113">See Also</span></span>


[<span data-ttu-id="483ad-114">Requisiti per i servizi di conferenza telefonica con accesso esterno in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="483ad-114">Dial-in conferencing requirements in Lync Server 2013</span></span>](lync-server-2013-dial-in-conferencing-requirements.md)  


[<span data-ttu-id="483ad-115">New-CsConferenceDirectory</span><span class="sxs-lookup"><span data-stu-id="483ad-115">New-CsConferenceDirectory</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsConferenceDirectory)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

