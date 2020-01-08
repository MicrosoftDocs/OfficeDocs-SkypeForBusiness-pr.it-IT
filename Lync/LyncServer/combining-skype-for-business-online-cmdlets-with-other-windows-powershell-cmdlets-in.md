---
title: Combinazione dei cmdlet di Skype for business online con altri cmdlet di Windows PowerShell in
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Combining Skype for Business Online cmdlets with other Windows PowerShell cmdlets
ms:assetid: 8bb8800a-f966-4570-8c8b-db87a91ad783
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362816(v=OCS.15)
ms:contentKeyID: 56558835
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: afcd352521285e619c9ceeb55a0699b4d4ea73e7
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "40981199"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="combining-skype-for-business-online-cmdlets-with-other-windows-powershell-cmdlets-in"></a><span data-ttu-id="c8d1b-102">Combinazione dei cmdlet di Skype for business online con altri cmdlet di Windows PowerShell in</span><span class="sxs-lookup"><span data-stu-id="c8d1b-102">Combining Skype for Business Online cmdlets with other Windows PowerShell cmdlets in</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c8d1b-103">_**Argomento Ultima modifica:** 2013-07-05_</span><span class="sxs-lookup"><span data-stu-id="c8d1b-103">_**Topic Last Modified:** 2013-07-05_</span></span>

<span data-ttu-id="c8d1b-104">Quando ci si connette a Skype for business online con Windows PowerShell, saranno disponibili circa 40 cmdlet Skype for business online per l'uso.</span><span class="sxs-lookup"><span data-stu-id="c8d1b-104">When you connect to Skype for Business Online by using Windows PowerShell, approximately 40 Skype for Business Online cmdlets will available for your use.</span></span> <span data-ttu-id="c8d1b-105">Tuttavia, non si è limitati a usare solo i cmdlet di 40 per la gestione di Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="c8d1b-105">However, you are not limited to using just those 40 cmdlets when managing Skype for Business Online.</span></span> <span data-ttu-id="c8d1b-106">Oltre ai cmdlet di Skype for business online, è possibile usare anche altri cmdlet di Windows PowerShell installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="c8d1b-106">In addition to the Skype for Business Online cmdlets, you can also use any other Windows PowerShell cmdlets that are installed on your computer.</span></span> <span data-ttu-id="c8d1b-107">Quando si installa Windows PowerShell 3,0, vengono installati anche centinaia di cmdlet di Windows PowerShell principali. I comandi possono combinare e abbinare i cmdlet di Skype for business online e gli eventuali altri cmdlet disponibili nel computer.</span><span class="sxs-lookup"><span data-stu-id="c8d1b-107">(When you install Windows PowerShell 3.0, hundreds of core Windows PowerShell cmdlets are installed, as well.) Your commands can mix and match Skype for Business Online cmdlets and any other cmdlets available on your computer.</span></span>

<span data-ttu-id="c8d1b-108">Anche se un corso completo in Windows PowerShell 3,0 supera l'ambito di questo articolo, ecco alcuni esempi che illustrano il motivo per cui potresti voler combinare i cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c8d1b-108">Although a complete course in Windows PowerShell 3.0 goes beyond the scope of this article, here are a few examples that show why you might want to mix and match cmdlets.</span></span> <span data-ttu-id="c8d1b-109">Prima di tutto, nessuno dei cmdlet di Skype for business online include un comando stampa e non è possibile trovare tale comando nella console di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c8d1b-109">First of all, none of the Skype for Business Online cmdlets include a Print command, and no such command can be found in the Windows PowerShell console, either.</span></span> <span data-ttu-id="c8d1b-110">Come si ottiene una stampa delle informazioni recuperate da un cmdlet?</span><span class="sxs-lookup"><span data-stu-id="c8d1b-110">So how do you get a printout of the information retrieved by a cmdlet?</span></span> <span data-ttu-id="c8d1b-111">Un modo consiste nel recuperare le informazioni e quindi inviarle al cmdlet **Out-Printer** :</span><span class="sxs-lookup"><span data-stu-id="c8d1b-111">One way is to retrieve the information, and then send that information to the **Out-Printer** cmdlet:</span></span>

    Get-CsTenant | Out-Printer

<span data-ttu-id="c8d1b-112">Poiché non sono inclusi parametri aggiuntivi, tutte le informazioni restituite dal cmdlet **Out-Printer** verranno stampate nella stampante predefinita.</span><span class="sxs-lookup"><span data-stu-id="c8d1b-112">Because no additional parameters are included, all the information returned by **the Out-Printer** cmdlet will be printed to the default printer.</span></span>

<span data-ttu-id="c8d1b-113">Allo stesso modo, nessuno dei cmdlet di Skype for business online include un parametro che consente di salvare i dati in un file.</span><span class="sxs-lookup"><span data-stu-id="c8d1b-113">Likewise, none of the Skype for Business Online cmdlets include a parameter that allows you to save data to a file.</span></span> <span data-ttu-id="c8d1b-114">Ma va bene: questo comando usa il cmdlet **out-file** per salvare le informazioni restituite nel file di testo C:\\logs\\Tenants. txt:</span><span class="sxs-lookup"><span data-stu-id="c8d1b-114">But that’s OK: this command uses the **Out-File** cmdlet to save the returned information to the text file C:\\Logs\\Tenants.txt:</span></span>

    Get-Tenant | Out-File -FilePath "C:\Logs\Tenants.txt"

<span data-ttu-id="c8d1b-115">Questo comando usa il cmdlet **Select-Object** per limitare i dati restituiti e visualizzati sullo schermo.</span><span class="sxs-lookup"><span data-stu-id="c8d1b-115">And this command uses the **Select-Object** cmdlet to limit the data that is returned and displayed onscreen.</span></span> <span data-ttu-id="c8d1b-116">In questo esempio, il cmdlet [Get-CsOnlineUser](https://technet.microsoft.com/en-us/library/JJ994026(v=OCS.15)) recupera le informazioni per tutti gli utenti di Skype for business online e quindi il cmdlet **Select-Object** viene usato per limitare i dati visualizzati al valore di identità dell'utente e ai relativi criteri di archiviazione:</span><span class="sxs-lookup"><span data-stu-id="c8d1b-116">In this example, the [Get-CsOnlineUser](https://technet.microsoft.com/en-us/library/JJ994026(v=OCS.15)) cmdlet retrieves information for all of your Skype for Business Online users, and then the **Select-Object** cmdlet is used to limit the displayed data to the user’s Identity value and their archiving policy:</span></span>

    Get-CsOnlineUser | Select-Object Identity, ArchivingPolicy

<span data-ttu-id="c8d1b-117">Poiché ci saranno centinaia di cmdlet disponibili per l'uso nel computer, potresti avere difficoltà a determinare quali cmdlet sono i cmdlet Skype for business online e quali no.</span><span class="sxs-lookup"><span data-stu-id="c8d1b-117">Because there will be hundreds of cmdlets available for use on your computer, you might have difficulty determining which cmdlets are Skype for Business Online cmdlets and which ones are not.</span></span> <span data-ttu-id="c8d1b-118">Per restituire un elenco dei cmdlet di Skype for business online (e solo i cmdlet di Skype for business online), devi prima determinare il nome del modulo di Windows PowerShell temporaneo che contiene tutti i cmdlet di Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="c8d1b-118">To return a list of the Skype for Business Online cmdlets (and only Skype for Business Online cmdlets), you must first determine the name of the temporary Windows PowerShell module that contains all the Skype for Business Online cmdlets.</span></span> <span data-ttu-id="c8d1b-119">A questo scopo, Esegui questo comando dal prompt di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="c8d1b-119">To do that, run this command from the Windows PowerShell prompt:</span></span>

    Get-Module

<span data-ttu-id="c8d1b-120">Le informazioni simili a quelle seguenti verranno visualizzate sullo schermo:</span><span class="sxs-lookup"><span data-stu-id="c8d1b-120">Information similar to the following will appear onscreen:</span></span>

    ModuleType Name                 ExportedCommands
    ---------- ----                 ----------------
    Manifest   Microsoft.PowerS...  {Add-Computer, Add-Content, A...}
    Script     tmp_5astd3uh.m5v     {Disable-CsMeetingRoom, Enabl...}

<span data-ttu-id="c8d1b-121">Il modulo con lo script ModuleType è il modulo che contiene i cmdlet di Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="c8d1b-121">The module with the ModuleType Script is the module that contains the Skype for Business Online cmdlets.</span></span> <span data-ttu-id="c8d1b-122">Per restituire un elenco di questi cmdlet, eseguire il cmdlet **Get-Command** usando il nome del modulo di script come nome del modulo:</span><span class="sxs-lookup"><span data-stu-id="c8d1b-122">To return a list of those cmdlets, run the **Get-Command** cmdlet, using the name of the Script module as the module name:</span></span>

    Get-Command -Module tmp_5astd3uh.m5v

<span data-ttu-id="c8d1b-123">È possibile che si disponga di più moduli con un ModuleType uguale a script.</span><span class="sxs-lookup"><span data-stu-id="c8d1b-123">It’s possible that you could have multiple modules with a ModuleType equal to Script.</span></span> <span data-ttu-id="c8d1b-124">In questo caso, puoi eseguire il comando seguente per scoprire il modulo che include il cmdlet **Get-CsTenant** :</span><span class="sxs-lookup"><span data-stu-id="c8d1b-124">In that case, you can run the following command to find out which module includes the **Get-CsTenant** cmdlet:</span></span>

    Get-Command Get-CsTenant

<span data-ttu-id="c8d1b-125">Il modulo restituito per il cmdlet **Get-CsTenant** sarà il modulo contenente tutti i cmdlet di Skype for business online:</span><span class="sxs-lookup"><span data-stu-id="c8d1b-125">The module returned for the **Get-CsTenant** cmdlet will be the module containing all the Skype for Business Online cmdlets:</span></span>

    CommandType     Name                                               ModuleName
    -----------     ----                                               ----------
    Function        Get-CsTenant                                       tmp_5astd3uh.m5v

<div>

## <a name="see-also"></a><span data-ttu-id="c8d1b-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c8d1b-126">See Also</span></span>


<span data-ttu-id="c8d1b-127">[Introduzione a Windows Powershell e Skype for Business online](https://technet.microsoft.com/en-us/library/Dn362785(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c8d1b-127">[An introduction to Windows PowerShell and Skype for Business Online](https://technet.microsoft.com/en-us/library/Dn362785(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

