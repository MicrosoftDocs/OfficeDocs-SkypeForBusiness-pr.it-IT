---
title: Get-CcSiteLogDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6625494d-1b63-4d99-a589-c8c69c4addba
description: Il cmdlet Get-CcSiteLogDirectory Mostra la directory corrente in cui sono archiviati i registri a livello di sito per Skype for Business Cloud Connector Edition.
ms.openlocfilehash: a03c4c0cc3e993fb5e1426f3f27f76a68d081c26
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003356"
---
# <a name="get-ccsitelogdirectory"></a><span data-ttu-id="76920-103">Get-CcSiteLogDirectory</span><span class="sxs-lookup"><span data-stu-id="76920-103">Get-CcSiteLogDirectory</span></span>
 
<span data-ttu-id="76920-104">Il cmdlet Get-CcSiteLogDirectory Mostra la directory corrente in cui sono archiviati i registri a livello di sito per Skype for Business Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="76920-104">The Get-CcSiteLogDirectory cmdlet shows the current directory where the site level logs for Skype for Business Cloud Connector Edition are stored.</span></span> 
  
<span data-ttu-id="76920-105">Questo cmdlet si applica a Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="76920-105">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Get-CcSiteLogDirectory
```

## <a name="parameters"></a><span data-ttu-id="76920-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="76920-106">Parameters</span></span>

<span data-ttu-id="76920-107">Nessuno</span><span class="sxs-lookup"><span data-stu-id="76920-107">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="76920-108">Esempi</span><span class="sxs-lookup"><span data-stu-id="76920-108">Examples</span></span>
<span data-ttu-id="76920-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="76920-109"></span></span>

### <a name="example-1"></a><span data-ttu-id="76920-110">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="76920-110">Example 1</span></span>

<span data-ttu-id="76920-111">L'esempio seguente mostra la cartella corrente in cui sono archiviati i file di log per il sito del connettore Cloud:</span><span class="sxs-lookup"><span data-stu-id="76920-111">The following example shows the current folder where the log files for the Cloud Connector site are stored:</span></span>
  
```powershell
Get-CcSiteLogDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="76920-112">Descrizione dettagliata</span><span class="sxs-lookup"><span data-stu-id="76920-112">Detailed Description</span></span>
<span data-ttu-id="76920-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="76920-113"></span></span>

<span data-ttu-id="76920-114">La cartella predefinita è C:\Users\%UserProfile%\CloudConnector\SiteRoot\Logs.</span><span class="sxs-lookup"><span data-stu-id="76920-114">The default folder is C:\Users\%userprofile%\CloudConnector\SiteRoot\Logs.</span></span> <span data-ttu-id="76920-115">È possibile modificare la cartella eseguendo il cmdlet Set-CcSiteDirectory.</span><span class="sxs-lookup"><span data-stu-id="76920-115">You can change the folder by running the Set-CcSiteDirectory cmdlet.</span></span> <span data-ttu-id="76920-116">Non esiste un cmdlet distinto che modifichi solo il percorso della cartella del log senza modificare la directory del sito.</span><span class="sxs-lookup"><span data-stu-id="76920-116">There is no separate cmdlet that changes only the log folder location without changing the site directory.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="76920-117">Tipi di input</span><span class="sxs-lookup"><span data-stu-id="76920-117">Input Types</span></span>
<span data-ttu-id="76920-118"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="76920-118"></span></span>

<span data-ttu-id="76920-119">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="76920-119">None.</span></span> <span data-ttu-id="76920-120">Il cmdlet Get-CcSiteLogDirectory non accetta l'input da pipeline.</span><span class="sxs-lookup"><span data-stu-id="76920-120">The Get-CcSiteLogDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="76920-121">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="76920-121">Return Types</span></span>
<span data-ttu-id="76920-122"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="76920-122"></span></span>

<span data-ttu-id="76920-123">Il comando restituisce un percorso di file.</span><span class="sxs-lookup"><span data-stu-id="76920-123">The command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="76920-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="76920-124">See also</span></span>
<span data-ttu-id="76920-125"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="76920-125"></span></span>

[<span data-ttu-id="76920-126">Set-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="76920-126">Set-CcSiteDirectory</span></span>](set-ccsitedirectory.md)
  

