---
title: Combinazione di cmdlet di Skype for business online con altri cmdlet di Windows PowerShell in
description: Combinazione di cmdlet Skype for business online con altri cmdlet di Windows PowerShell in.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Combining Skype for Business Online cmdlets with other Windows PowerShell cmdlets
ms:assetid: 8bb8800a-f966-4570-8c8b-db87a91ad783
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362816(v=OCS.15)
ms:contentKeyID: 56558835
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5bd18f60891d48a54eb2f77f189ea8417e0b5e93
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548002"
---
# <a name="combining-skype-for-business-online-cmdlets-with-other-windows-powershell-cmdlets-in"></a><span data-ttu-id="2eb99-103">Combinazione di cmdlet di Skype for business online con altri cmdlet di Windows PowerShell in</span><span class="sxs-lookup"><span data-stu-id="2eb99-103">Combining Skype for Business Online cmdlets with other Windows PowerShell cmdlets in</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2eb99-104">_**Ultimo argomento modificato:** 2013-07-05_</span><span class="sxs-lookup"><span data-stu-id="2eb99-104">_**Topic Last Modified:** 2013-07-05_</span></span>

<span data-ttu-id="2eb99-105">Quando ci si connette a Skype for business online utilizzando Windows PowerShell, circa 40 cmdlet di Skype for business online saranno disponibili per l'utilizzo.</span><span class="sxs-lookup"><span data-stu-id="2eb99-105">When you connect to Skype for Business Online by using Windows PowerShell, approximately 40 Skype for Business Online cmdlets will available for your use.</span></span> <span data-ttu-id="2eb99-106">Tuttavia, non è possibile utilizzare solo i cmdlet di 40 per la gestione di Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="2eb99-106">However, you are not limited to using just those 40 cmdlets when managing Skype for Business Online.</span></span> <span data-ttu-id="2eb99-107">Oltre ai cmdlet di Skype for business online, è possibile utilizzare anche tutti gli altri cmdlet di Windows PowerShell installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="2eb99-107">In addition to the Skype for Business Online cmdlets, you can also use any other Windows PowerShell cmdlets that are installed on your computer.</span></span> <span data-ttu-id="2eb99-108">Quando si installa Windows PowerShell 3,0, vengono installati anche centinaia di cmdlet di Windows PowerShell di base. I comandi possono combinare i cmdlet Skype for business online e tutti gli altri cmdlet disponibili nel computer.</span><span class="sxs-lookup"><span data-stu-id="2eb99-108">(When you install Windows PowerShell 3.0, hundreds of core Windows PowerShell cmdlets are installed, as well.) Your commands can mix and match Skype for Business Online cmdlets and any other cmdlets available on your computer.</span></span>

<span data-ttu-id="2eb99-109">Anche se un corso completo in Windows PowerShell 3,0 supera l'ambito di questo articolo, ecco alcuni esempi che mostrano perché si potrebbe voler combinare i cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2eb99-109">Although a complete course in Windows PowerShell 3.0 goes beyond the scope of this article, here are a few examples that show why you might want to mix and match cmdlets.</span></span> <span data-ttu-id="2eb99-110">In primo luogo, nessuno dei cmdlet di Skype for business online include un comando di stampa e non è possibile trovare tale comando nella console di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2eb99-110">First of all, none of the Skype for Business Online cmdlets include a Print command, and no such command can be found in the Windows PowerShell console, either.</span></span> <span data-ttu-id="2eb99-111">In che modo è possibile ottenere una stampa delle informazioni recuperate da un cmdlet?</span><span class="sxs-lookup"><span data-stu-id="2eb99-111">So how do you get a printout of the information retrieved by a cmdlet?</span></span> <span data-ttu-id="2eb99-112">Un modo consiste nel recuperare le informazioni e quindi inviare tali informazioni al cmdlet **Out-Printer** :</span><span class="sxs-lookup"><span data-stu-id="2eb99-112">One way is to retrieve the information, and then send that information to the **Out-Printer** cmdlet:</span></span>

    Get-CsTenant | Out-Printer

<span data-ttu-id="2eb99-113">Poiché non sono inclusi parametri aggiuntivi, tutte le informazioni restituite dal cmdlet **Out-Printer** verranno stampate sulla stampante predefinita.</span><span class="sxs-lookup"><span data-stu-id="2eb99-113">Because no additional parameters are included, all the information returned by **the Out-Printer** cmdlet will be printed to the default printer.</span></span>

<span data-ttu-id="2eb99-114">Analogamente, nessuno dei cmdlet Skype for business online include un parametro che consente di salvare i dati in un file.</span><span class="sxs-lookup"><span data-stu-id="2eb99-114">Likewise, none of the Skype for Business Online cmdlets include a parameter that allows you to save data to a file.</span></span> <span data-ttu-id="2eb99-115">Ma va bene: questo comando utilizza il cmdlet **out-file** per salvare le informazioni restituite nel file di testo C: \\ logs \\Tenants.txt:</span><span class="sxs-lookup"><span data-stu-id="2eb99-115">But that’s OK: this command uses the **Out-File** cmdlet to save the returned information to the text file C:\\Logs\\Tenants.txt:</span></span>

    Get-Tenant | Out-File -FilePath "C:\Logs\Tenants.txt"

<span data-ttu-id="2eb99-116">Questo comando utilizza il cmdlet **Select-Object** per limitare i dati restituiti e visualizzati sullo schermo.</span><span class="sxs-lookup"><span data-stu-id="2eb99-116">And this command uses the **Select-Object** cmdlet to limit the data that is returned and displayed onscreen.</span></span> <span data-ttu-id="2eb99-117">In questo esempio, il cmdlet [Get-CsOnlineUser](https://technet.microsoft.com/library/JJ994026(v=OCS.15)) recupera le informazioni per tutti gli utenti di Skype for business online e quindi il cmdlet **Select-Object** viene utilizzato per limitare i dati visualizzati al valore di identità dell'utente e ai criteri di archiviazione seguenti:</span><span class="sxs-lookup"><span data-stu-id="2eb99-117">In this example, the [Get-CsOnlineUser](https://technet.microsoft.com/library/JJ994026(v=OCS.15)) cmdlet retrieves information for all of your Skype for Business Online users, and then the **Select-Object** cmdlet is used to limit the displayed data to the user’s Identity value and their archiving policy:</span></span>

    Get-CsOnlineUser | Select-Object Identity, ArchivingPolicy

<span data-ttu-id="2eb99-118">Poiché saranno disponibili centinaia di cmdlet per l'utilizzo nel computer, potrebbe essere difficile determinare quali cmdlet sono cmdlet di Skype for business online e quali no.</span><span class="sxs-lookup"><span data-stu-id="2eb99-118">Because there will be hundreds of cmdlets available for use on your computer, you might have difficulty determining which cmdlets are Skype for Business Online cmdlets and which ones are not.</span></span> <span data-ttu-id="2eb99-119">Per restituire un elenco dei cmdlet di Skype for business online (e solo i cmdlet di Skype for business online), è necessario innanzitutto determinare il nome del modulo di Windows PowerShell temporaneo che contiene tutti i cmdlet di Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="2eb99-119">To return a list of the Skype for Business Online cmdlets (and only Skype for Business Online cmdlets), you must first determine the name of the temporary Windows PowerShell module that contains all the Skype for Business Online cmdlets.</span></span> <span data-ttu-id="2eb99-120">A tale scopo, eseguire il seguente comando dal prompt di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="2eb99-120">To do that, run this command from the Windows PowerShell prompt:</span></span>

    Get-Module

<span data-ttu-id="2eb99-121">Sullo schermo vengono visualizzate informazioni analoghe a quelle riportate di seguito:</span><span class="sxs-lookup"><span data-stu-id="2eb99-121">Information similar to the following will appear onscreen:</span></span>

    ModuleType Name                 ExportedCommands
    ---------- ----                 ----------------
    Manifest   Microsoft.PowerS...  {Add-Computer, Add-Content, A...}
    Script     tmp_5astd3uh.m5v     {Disable-CsMeetingRoom, Enabl...}

<span data-ttu-id="2eb99-122">Il modulo con lo script ModuleType è il modulo che contiene i cmdlet Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="2eb99-122">The module with the ModuleType Script is the module that contains the Skype for Business Online cmdlets.</span></span> <span data-ttu-id="2eb99-123">Per restituire un elenco di tali cmdlet, eseguire il cmdlet **Get-Command** utilizzando il nome del modulo di script come nome del modulo:</span><span class="sxs-lookup"><span data-stu-id="2eb99-123">To return a list of those cmdlets, run the **Get-Command** cmdlet, using the name of the Script module as the module name:</span></span>

    Get-Command -Module tmp_5astd3uh.m5v

<span data-ttu-id="2eb99-124">È possibile che si disponga di più moduli con un ModuleType uguale a script.</span><span class="sxs-lookup"><span data-stu-id="2eb99-124">It’s possible that you could have multiple modules with a ModuleType equal to Script.</span></span> <span data-ttu-id="2eb99-125">In tal caso, è possibile eseguire il comando riportato di seguito per individuare il modulo che include il cmdlet **Get-CsTenant** :</span><span class="sxs-lookup"><span data-stu-id="2eb99-125">In that case, you can run the following command to find out which module includes the **Get-CsTenant** cmdlet:</span></span>

    Get-Command Get-CsTenant

<span data-ttu-id="2eb99-126">Il modulo restituito per il cmdlet **Get-CsTenant** sarà il modulo contenente tutti i cmdlet di Skype for business online:</span><span class="sxs-lookup"><span data-stu-id="2eb99-126">The module returned for the **Get-CsTenant** cmdlet will be the module containing all the Skype for Business Online cmdlets:</span></span>

    CommandType     Name                                               ModuleName
    -----------     ----                                               ----------
    Function        Get-CsTenant                                       tmp_5astd3uh.m5v

<div>

## <a name="see-also"></a><span data-ttu-id="2eb99-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2eb99-127">See Also</span></span>


<span data-ttu-id="2eb99-128">[Introduzione a Windows PowerShell e Skype for business online](https://technet.microsoft.com/library/Dn362785(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2eb99-128">[An introduction to Windows PowerShell and Skype for Business Online](https://technet.microsoft.com/library/Dn362785(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

