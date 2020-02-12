---
title: Creare directory conferenza in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b124b229-7df5-4b7e-8c11-6661c8c8c051
description: 'Riepilogo: informazioni su come creare directory conferenza in Skype for Business Server.'
ms.openlocfilehash: be8983b25937b2a1c068c9629a0f44fd06d494d6
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888675"
---
# <a name="create-conference-directories-in-skype-for-business-server"></a><span data-ttu-id="0c16f-103">Creare directory conferenza in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="0c16f-103">Create conference directories in Skype for Business Server</span></span>
 
<span data-ttu-id="0c16f-104">**Riepilogo:** Informazioni su come creare directory conferenza in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="0c16f-104">**Summary:** Learn how to create conference directories in Skype for Business Server.</span></span>
  
<span data-ttu-id="0c16f-105">Le directory conferenza mantengono una mappatura tra l'ID riunione alfanumerico usato da un partecipante per partecipare a una conferenza quando si usa Skype for business e l'ID conferenza numerico che viene usato da un partecipante di conferenza telefonica con accesso esterno per partecipare alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="0c16f-105">Conference directories maintain a mapping between the alphanumeric meeting ID that a participant uses to join a conference when using Skype for Business, and the numeric-only conference ID that a dial-in conferencing participant uses to join the conference.</span></span> 
  
## <a name="create-a-conference-directory"></a><span data-ttu-id="0c16f-106">Creare una directory conferenza</span><span class="sxs-lookup"><span data-stu-id="0c16f-106">Create a conference directory</span></span>

<span data-ttu-id="0c16f-107">La creazione di più directory conferenza garantirà che gli ID conferenza rimarranno invariati finché non verrà creata una quantità significativa di conferenze.</span><span class="sxs-lookup"><span data-stu-id="0c16f-107">Creating multiple conference directories will ensure that conference IDs will stay short until a significant amount of conferences have been created.</span></span> 
  
<span data-ttu-id="0c16f-108">In un'organizzazione con un numero tipico di conferenze per ogni utente, è consigliabile creare una directory conferenza per ogni utenti di 999 nel pool.</span><span class="sxs-lookup"><span data-stu-id="0c16f-108">In an organization with a typical number of conferences per user, we recommend that you create one conference directory for every 999 users in the pool.</span></span> <span data-ttu-id="0c16f-109">Usando questa linea guida, gli ID conferenza possono in genere essere mantenuti piccoli.</span><span class="sxs-lookup"><span data-stu-id="0c16f-109">Using this guideline, the conference IDs can generally be kept small.</span></span> <span data-ttu-id="0c16f-110">Tuttavia, una volta che il numero di directory conferenza (tra i pool) supera 9, la lunghezza dell'ID conferenza crescerà per supportare altre conferenze.</span><span class="sxs-lookup"><span data-stu-id="0c16f-110">However, once the number of conference directories (across the pools) exceed 9, the Conference ID length will grow to support additional conferences.</span></span>
  
<span data-ttu-id="0c16f-111">Il formato di un ID conferenza è il seguente:</span><span class="sxs-lookup"><span data-stu-id="0c16f-111">The format of a conference ID is as follows:</span></span> 
  
```console
  <housekeeping digit (1 digit)><conference directory (usually 1-2 digits> 
  <conference number (variable number of digits><check digit (1 digit)>
```

<span data-ttu-id="0c16f-112">Per creare una directory conferenza, usare il cmdlet **New-CsConferenceDirectory** .</span><span class="sxs-lookup"><span data-stu-id="0c16f-112">To create a conference directory, use the **New-CsConferenceDirectory** cmdlet.</span></span> <span data-ttu-id="0c16f-113">Ad esempio, il comando seguente crea una directory conferenza con identità 42, ospitata nel pool atl-cs-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="0c16f-113">For example, the following command creates a conference directory with the identity 42, hosted on the pool atl-cs-001.litwareinc.com:</span></span>
  
```PowerShell
New-CsConferenceDirectory -Identity 42 -HomePool "atl-cs-001.litwareinc.com"
```

<span data-ttu-id="0c16f-114">Per altre informazioni, vedere [New-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="0c16f-114">For more information, see [New-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps).</span></span>
  

