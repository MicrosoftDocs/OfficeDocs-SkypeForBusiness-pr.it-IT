---
title: Appartenenze a gruppi e requisiti per i diritti utente per Best Practices Analyzer
description: Appartenenze a gruppi e requisiti per i diritti utente per Best Practices Analyzer.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Group memberships and user rights requirements for Best Practices Analyzer
ms:assetid: f812e343-8f75-454e-b7a8-1b404e32071a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591354(v=OCS.15)
ms:contentKeyID: 48185869
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 64a7d785a77701c6796488178a7cce10caf54f42
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564192"
---
# <a name="group-memberships-and-user-rights-requirements-for-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="9f7a0-103">Appartenenze a gruppi e requisiti per i diritti utente per Best Practices Analyzer in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9f7a0-103">Group memberships and user rights requirements for Best Practices Analyzer in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9f7a0-104">_**Ultimo argomento modificato:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="9f7a0-104">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="9f7a0-p101">Per eseguire correttamente Best Practices Analyzer, è necessario che l'account utente utilizzato per accedere sia un membro del gruppo Administrators nel computer locale. Inoltre, per analizzare l'ambiente, è necessario che l'utente sia un membro dei gruppi seguenti:</span><span class="sxs-lookup"><span data-stu-id="9f7a0-p101">To successfully run Best Practices Analyzer, the user account that you use to log on must be a member of the Administrators group on the local computer. Additionally, to scan your environment, the user account must be a member of the following groups:</span></span>

  - <span data-ttu-id="9f7a0-107">**Amministratori**     di dominio Per enumerare le informazioni sui servizi di dominio Active Directory e per chiamare i provider di Strumentazione gestione Windows (WMI) sui controller di dominio e i server di catalogo globale.</span><span class="sxs-lookup"><span data-stu-id="9f7a0-107">**Domain Admins**   To enumerate Active Directory Domain Services information and to call the Windows Management Instrumentation (WMI) providers on domain controllers and global catalog servers.</span></span>

  - <span data-ttu-id="9f7a0-108">**Amministratori**     Obbligatorio su ogni computer interno di Lync Server 2013 e su ogni server perimetrale per chiamare i provider di Strumentazione gestione Windows (WMI) e per accedere al registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="9f7a0-108">**Administrators**   Required on each Lync Server 2013 internal computer and each Edge Server to call the Windows Management Instrumentation (WMI) providers and to access the registry.</span></span>

  - <span data-ttu-id="9f7a0-109">**RTCUniversalReadOnlyAdmins**     Diritti amministrativi completi o delegati di sola lettura Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9f7a0-109">**RTCUniversalReadOnlyAdmins**   Full or delegated read only Lync Server 2013 administrative rights.</span></span>

  - <span data-ttu-id="9f7a0-110">Amministratore di Exchange **solo visualizzazione**     Amministratore di Exchange solo visualizzazione delegata o completo nell'organizzazione di Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="9f7a0-110">**Exchange View Only Administrator**   Full or delegated Exchange View Only Administrator on the Microsoft Exchange organization.</span></span>

<span data-ttu-id="9f7a0-111">Se l'account utente non dispone di diritti utente sufficienti, sono disponibili due opzioni:</span><span class="sxs-lookup"><span data-stu-id="9f7a0-111">If your user account does not have sufficient user rights, you have two options:</span></span>

  - <span data-ttu-id="9f7a0-112">Nel prompt dei comandi utilizzare il comando **runas** per eseguire lo strumento in un account che non dispone diritti utenti sufficienti.</span><span class="sxs-lookup"><span data-stu-id="9f7a0-112">At a command prompt, use the **runas** command to run the tool under an account that does have sufficient user rights.</span></span> <span data-ttu-id="9f7a0-113">Di seguito viene illustrata la sintassi del comando:</span><span class="sxs-lookup"><span data-stu-id="9f7a0-113">The syntax is as follows:</span></span>
    
        runas /netonly /user:<domain>\<userName> rtcbpa.exe

  - <span data-ttu-id="9f7a0-114">Nella pagina **Connessione a Active Directory** impostare le credenziali per gli account che si prevede di utilizzare per eseguire lo strumento Best Practices Analyzer.</span><span class="sxs-lookup"><span data-stu-id="9f7a0-114">On the **Connect to Active Directory** page, set the credentials for the accounts that you plan to use to run Best Practices Analyzer.</span></span> <span data-ttu-id="9f7a0-115">Fare clic su **Mostra opzioni di accesso avanzate**.</span><span class="sxs-lookup"><span data-stu-id="9f7a0-115">Click **Show advanced login options**.</span></span> <span data-ttu-id="9f7a0-116">È possibile immettere tre account: uno per la connessione a servizi di dominio Active Directory, uno per la connessione ai server perimetrali di Lync Server 2013 e uno per la connessione ai server di Exchange.</span><span class="sxs-lookup"><span data-stu-id="9f7a0-116">You can enter three accounts: one for connecting to Active Directory Domain Services, one for connecting to Lync Server 2013 Edge Servers, and one for connecting to the Exchange Servers.</span></span> <span data-ttu-id="9f7a0-117">Se non si specifica nessuno dei tre account, verrà utilizzato l'account utente utilizzato per accedere ed eseguire lo strumento Best Practices Analyzer.</span><span class="sxs-lookup"><span data-stu-id="9f7a0-117">If you do not specify any of these accounts, the user account that you used to log on and run Best Practices Analyzer is used.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

