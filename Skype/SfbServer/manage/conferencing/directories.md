---
title: Creare directory conferenze in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b124b229-7df5-4b7e-8c11-6661c8c8c051
description: 'Riepilogo: informazioni su come creare directory conferenze in Skype for Business Server.'
ms.openlocfilehash: e4d73cc73a5c3c343e8a4734923cf80fb2590211
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119475"
---
# <a name="create-conference-directories-in-skype-for-business-server"></a><span data-ttu-id="a7b1d-103">Creare directory conferenze in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="a7b1d-103">Create conference directories in Skype for Business Server</span></span>
 
<span data-ttu-id="a7b1d-104">**Riepilogo:** Informazioni su come creare directory conferenze in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a7b1d-104">**Summary:** Learn how to create conference directories in Skype for Business Server.</span></span>
  
<span data-ttu-id="a7b1d-105">Le directory conferenze mantengono un mapping tra l'ID riunione alfanumerico utilizzato da un partecipante per partecipare a una conferenza quando si utilizza Skype for Business e l'ID conferenza solo numerico utilizzato da un partecipante alla conferenza telefonica con accesso esterno per partecipare alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="a7b1d-105">Conference directories maintain a mapping between the alphanumeric meeting ID that a participant uses to join a conference when using Skype for Business, and the numeric-only conference ID that a dial-in conferencing participant uses to join the conference.</span></span> 
  
## <a name="create-a-conference-directory"></a><span data-ttu-id="a7b1d-106">Creare una directory conferenze</span><span class="sxs-lookup"><span data-stu-id="a7b1d-106">Create a conference directory</span></span>

<span data-ttu-id="a7b1d-107">La creazione di più directory conferenze garantisce che gli ID conferenza rimangano brevi fino a quando non viene creata una quantità significativa di conferenze.</span><span class="sxs-lookup"><span data-stu-id="a7b1d-107">Creating multiple conference directories will ensure that conference IDs will stay short until a significant amount of conferences have been created.</span></span> 
  
<span data-ttu-id="a7b1d-108">In un'organizzazione con un numero tipico di conferenze per utente, è consigliabile creare una directory conferenze per ogni 999 utenti del pool.</span><span class="sxs-lookup"><span data-stu-id="a7b1d-108">In an organization with a typical number of conferences per user, we recommend that you create one conference directory for every 999 users in the pool.</span></span> <span data-ttu-id="a7b1d-109">Utilizzando questa linea guida, gli ID conferenza in genere possono essere mantenuti piccoli.</span><span class="sxs-lookup"><span data-stu-id="a7b1d-109">Using this guideline, the conference IDs can generally be kept small.</span></span> <span data-ttu-id="a7b1d-110">Tuttavia, una volta che il numero di directory conferenze (tra i pool) supera 9, la lunghezza dell'ID conferenza crescerà per supportare conferenze aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="a7b1d-110">However, once the number of conference directories (across the pools) exceed 9, the Conference ID length will grow to support additional conferences.</span></span>
  
<span data-ttu-id="a7b1d-111">Il formato di un ID conferenza è il seguente:</span><span class="sxs-lookup"><span data-stu-id="a7b1d-111">The format of a conference ID is as follows:</span></span> 
  
```console
  <housekeeping digit (1 digit)><conference directory (usually 1-2 digits> 
  <conference number (variable number of digits><check digit (1 digit)>
```

<span data-ttu-id="a7b1d-112">Per creare una directory conferenze, utilizzare il cmdlet **New-CsConferenceDirectory.**</span><span class="sxs-lookup"><span data-stu-id="a7b1d-112">To create a conference directory, use the **New-CsConferenceDirectory** cmdlet.</span></span> <span data-ttu-id="a7b1d-113">Ad esempio, il comando seguente crea una directory conferenze con identità 42, ospitata nel pool atl-cs-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="a7b1d-113">For example, the following command creates a conference directory with the identity 42, hosted on the pool atl-cs-001.litwareinc.com:</span></span>
  
```PowerShell
New-CsConferenceDirectory -Identity 42 -HomePool "atl-cs-001.litwareinc.com"
```

<span data-ttu-id="a7b1d-114">Per ulteriori informazioni, vedere [New-CsConferenceDirectory](/powershell/module/skype/new-csconferencedirectory?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="a7b1d-114">For more information, see [New-CsConferenceDirectory](/powershell/module/skype/new-csconferencedirectory?view=skype-ps).</span></span>
