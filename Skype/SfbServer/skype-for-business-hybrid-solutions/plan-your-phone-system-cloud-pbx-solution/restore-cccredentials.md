---
title: Restore-CcCredentials
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aeca610b-db0a-45cf-95b9-ae9a6bbccb45
description: Il cmdlet Restore CC-Credentials Ripristina tutte le credenziali della distribuzione corrente di Skype for Business Cloud Connector Edition.
ms.openlocfilehash: adac3f0b9ca6cf392b537a9c5d0f2095021c7120
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003246"
---
# <a name="restore-cccredentials"></a><span data-ttu-id="33c7b-103">Restore-CcCredentials</span><span class="sxs-lookup"><span data-stu-id="33c7b-103">Restore-CcCredentials</span></span>
 
<span data-ttu-id="33c7b-104">Il cmdlet Restore CC-Credentials Ripristina tutte le credenziali della distribuzione corrente di Skype for Business Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="33c7b-104">The Restore Cc-Credentials cmdlet restores all credentials of the current Skype for Business Cloud Connector Edition deployment.</span></span> 
  
<span data-ttu-id="33c7b-105">Questo cmdlet si applica a Skype for Business Cloud Connector Edition 2,1.</span><span class="sxs-lookup"><span data-stu-id="33c7b-105">This cmdlet applies to Skype for Business Cloud Connector Edition 2.1.</span></span>
  
```powershell
Restore-CcCredentials 
```

## <a name="detailed-description"></a><span data-ttu-id="33c7b-106">Descrizione dettagliata</span><span class="sxs-lookup"><span data-stu-id="33c7b-106">Detailed Description</span></span>

<span data-ttu-id="33c7b-107">Il cmdlet Restore-CcCredentials pulisce tutte le credenziali e chiede di immettere di nuovo tutte le credenziali usate per la distribuzione del Cloud Connector Skype for business corrente.</span><span class="sxs-lookup"><span data-stu-id="33c7b-107">The Restore-CcCredentials cmdlet cleans up all credentials and prompts you to re-enter all the credentials used for the current Skype for Business Cloud Connector deployment.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="33c7b-108">Parametri</span><span class="sxs-lookup"><span data-stu-id="33c7b-108">Parameters</span></span>

<span data-ttu-id="33c7b-109">Nessuno</span><span class="sxs-lookup"><span data-stu-id="33c7b-109">None</span></span>
  
## <a name="input-types"></a><span data-ttu-id="33c7b-110">Tipi di input</span><span class="sxs-lookup"><span data-stu-id="33c7b-110">Input Types</span></span>

<span data-ttu-id="33c7b-111">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="33c7b-111">None.</span></span> <span data-ttu-id="33c7b-112">Il cmdlet Restore-CcCredentials non accetta l'input da pipeline.</span><span class="sxs-lookup"><span data-stu-id="33c7b-112">The Restore-CcCredentials cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="33c7b-113">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="33c7b-113">Return Types</span></span>

<span data-ttu-id="33c7b-114">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="33c7b-114">None.</span></span>
  
## <a name="example"></a><span data-ttu-id="33c7b-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="33c7b-115">Example</span></span>

<span data-ttu-id="33c7b-116">L'esempio seguente ripristina tutte le credenziali della distribuzione di Cloud Connector corrente:</span><span class="sxs-lookup"><span data-stu-id="33c7b-116">The following example restores all credentials of the current Cloud Connector deployment:</span></span>
  
```powershell
    PS C:\>Restore-CcCredentials
```

## <a name="see-also"></a><span data-ttu-id="33c7b-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="33c7b-117">See also</span></span>

[<span data-ttu-id="33c7b-118">Get-CcCredential</span><span class="sxs-lookup"><span data-stu-id="33c7b-118">Get-CcCredential</span></span>](get-cccredential.md)
  
[<span data-ttu-id="33c7b-119">Set-CcCredential</span><span class="sxs-lookup"><span data-stu-id="33c7b-119">Set-CcCredential</span></span>](set-cccredential.md)
  

