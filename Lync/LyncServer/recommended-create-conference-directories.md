---
title: Consigliato Creare directory conferenze
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: (Recommended) Create Conference Directories
ms:assetid: 787f4c94-1c96-468a-a74d-e06b7bd4b8a3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn832056(v=OCS.15)
ms:contentKeyID: 63146389
ms.date: 10/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d5ce338c6eb67f545439bfe1e9f2134cd7f1e6d1
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44757167"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="recommended-create-conference-directories"></a><span data-ttu-id="3485f-102">Consigliato Creare directory conferenze</span><span class="sxs-lookup"><span data-stu-id="3485f-102">(Recommended) Create Conference Directories</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3485f-103">_**Ultimo argomento modificato:** 2014-10-03_</span><span class="sxs-lookup"><span data-stu-id="3485f-103">_**Topic Last Modified:** 2014-10-03_</span></span>

<span data-ttu-id="3485f-104">Le directory conferenze mantengono un mapping tra l'ID riunione alfanumerico utilizzato da un partecipante per partecipare a una conferenza quando si utilizza Lync 2013 e l'ID conferenza solo numerico utilizzato da un partecipante di conferenze telefoniche con accesso esterno per partecipare alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="3485f-104">Conference directories maintain a mapping between the alphanumeric meeting ID that a participant uses to join a conference when using Lync 2013, and the numeric-only conference ID that a dial-in conferencing participant uses to join the conference.</span></span> <span data-ttu-id="3485f-105">Il formato dell'ID conferenza è il seguente:</span><span class="sxs-lookup"><span data-stu-id="3485f-105">The format of the conference ID is as follows:</span></span>

    <housekeeping digit (1 digit)><conference directory (usually 1-2 digits)><conference number (variable number of digits><check digit (1 digit)>

<span data-ttu-id="3485f-106">La creazione di più directory conferenze garantirà che gli ID conferenza rimarranno invariati fino a quando non verrà creata una quantità significativa di conferenze.</span><span class="sxs-lookup"><span data-stu-id="3485f-106">Creating multiple conference directories will ensure that conference IDs will stay short until a significant amount of conferences have been created.</span></span> <span data-ttu-id="3485f-107">In un'organizzazione che dispone di un numero tipico di conferenze per utente, si consiglia di creare una directory conferenze per ogni 999 utenti nel pool.</span><span class="sxs-lookup"><span data-stu-id="3485f-107">In an organization with a typical number of conferences per user, we recommend that you create one conference directory for every 999 users in the pool.</span></span> <span data-ttu-id="3485f-108">Utilizzo di questa guida di riferimento gli ID conferenza possono generalmente essere mantenuti piccoli.</span><span class="sxs-lookup"><span data-stu-id="3485f-108">Using this guideline the conference IDs can generally be kept small.</span></span> <span data-ttu-id="3485f-109">Tuttavia, una volta che il numero di directory conferenze (tra i pool) è superiore a 9, la lunghezza dell'ID conferenza crescerà per supportare altre conferenze.</span><span class="sxs-lookup"><span data-stu-id="3485f-109">However, once the number of conference directories (across the pools) exceed 9, the Conference ID length will grow to support additional conferences.</span></span>

<div>

## <a name="creating-a-conference-directory"></a><span data-ttu-id="3485f-110">Creazione di una directory conferenze</span><span class="sxs-lookup"><span data-stu-id="3485f-110">Creating a conference directory</span></span>

1.  <span data-ttu-id="3485f-111">In Lync Server Management Shell, digitare il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="3485f-111">In Lync Server Management Shell, type the following cmdlet:</span></span>
    
        New-CsConferenceDirectory -Identity <XdsGlobalRelativeIdentity> -HomePool <String> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]
    
    <span data-ttu-id="3485f-112">Ad esempio, di seguito viene creata una directory conferenze con identità 42, ospitata nel pool atl-cs-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="3485f-112">For example, the following creates a conference directory with the identity 42, hosted on the pool atl-cs-001.litwareinc.com:</span></span>
    
        New-CsConferenceDirectory -Identity 42 -HomePool "atl-cs-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3485f-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3485f-113">See Also</span></span>


[<span data-ttu-id="3485f-114">Requisiti per le conferenze telefoniche con accesso esterno in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3485f-114">Dial-in conferencing requirements in Lync Server 2013</span></span>](lync-server-2013-dial-in-conferencing-requirements.md)  


[<span data-ttu-id="3485f-115">New-CsConferenceDirectory</span><span class="sxs-lookup"><span data-stu-id="3485f-115">New-CsConferenceDirectory</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsConferenceDirectory)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

