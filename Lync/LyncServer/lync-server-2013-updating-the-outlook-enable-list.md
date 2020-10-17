---
title: "Lync Server 2013: aggiornamento dell'elenco di abilitazione di Outlook"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Updating the Outlook enable list
ms:assetid: 5db120dc-52f9-4dde-acb9-3824ae245086
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215438(v=OCS.15)
ms:contentKeyID: 48242739
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3702e8976c0afeef364fdec52616bb4f4d1b8d86
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506663"
---
# <a name="updating-the-outlook-enable-list-in-lync-server-2013"></a><span data-ttu-id="0732d-102">Aggiornamento dell'elenco di abilitazione di Outlook in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0732d-102">Updating the Outlook enable list in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0732d-103">_**Ultimo argomento modificato:** 2013-01-07_</span><span class="sxs-lookup"><span data-stu-id="0732d-103">_**Topic Last Modified:** 2013-01-07_</span></span>

<span data-ttu-id="0732d-104">È possibile verificare che il componente aggiuntivo per riunioni online per Microsoft Lync 2013 rimanga sempre abilitato per gli utenti creando un criterio che lo includa nell'elenco di gestione del componente aggiuntivo per Outlook.</span><span class="sxs-lookup"><span data-stu-id="0732d-104">You can ensure that Online Meeting Add-in for Microsoft Lync 2013 always remains enabled for users by creating a policy that includes it in the Add-in Management List for Outlook.</span></span> <span data-ttu-id="0732d-105">I criteri per l'elenco di gestione dei componenti aggiuntivi sono inclusi nei file dei modelli amministrativi di Office per la console di gestione di Criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="0732d-105">The Add-in Management List policy is included in the Office administrative template files for the Group Policy Management Console.</span></span> <span data-ttu-id="0732d-106">Crea una chiave del registro di sistema in HKCU \\ software \\ Policies \\ Microsoft \\ Office \\ 15,0 \\ Outlook15 \\ resilienza \\ AddIn.</span><span class="sxs-lookup"><span data-stu-id="0732d-106">It creates a registry key under HKCU\\Software\\Policies\\Microsoft\\Office\\15.0\\Outlook15\\Resiliency\\AddinList.</span></span> <span data-ttu-id="0732d-107">È possibile aggiungere un valore per la ucaddin.dll a questa chiave e configurare il valore di ucaddin.dll in modo che sia sempre abilitato e in modo che gli utenti non possano disabilitarlo manualmente</span><span class="sxs-lookup"><span data-stu-id="0732d-107">You can add a value for the ucaddin.dll to this key, and configure the ucaddin.dll value so that it is always enabled and so that users cannot manually disable it</span></span>

<div>

## <a name="to-add-ucaddindll-to-the-outlook-add-in-list"></a><span data-ttu-id="0732d-108">Per aggiungere ucaddin.dll all'elenco del componente aggiuntivo di Outlook</span><span class="sxs-lookup"><span data-stu-id="0732d-108">To Add ucaddin.dll to the Outlook Add-in List</span></span>

  - <span data-ttu-id="0732d-109">Per la chiave del registro di sistema di AddIn, che si trova in HKCU \\ software \\ Policies \\ Microsoft \\ Office \\ 15,0 \\ Outlook15 \\ resilienza \\ AddIn, aggiungere il seguente valore:</span><span class="sxs-lookup"><span data-stu-id="0732d-109">To the AddinList registry key, located under HKCU\\Software\\Policies\\Microsoft\\Office\\15.0\\Outlook15\\Resiliency\\AddinList, add the following value:</span></span>
    
      - <span data-ttu-id="0732d-110">Tipo di registro = REG \_ SZ</span><span class="sxs-lookup"><span data-stu-id="0732d-110">Registry Type = REG\_SZ</span></span>
    
      - <span data-ttu-id="0732d-111">Nome = ucaddin.dll</span><span class="sxs-lookup"><span data-stu-id="0732d-111">Name = ucaddin.dll</span></span>
    
      - <span data-ttu-id="0732d-112">Valore = 1 (specifica che il componente aggiuntivo è sempre abilitato e non può essere gestito dall'utente finale)</span><span class="sxs-lookup"><span data-stu-id="0732d-112">Value = 1 (specifies that the add-in is always enabled and cannot be managed by the end user)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

