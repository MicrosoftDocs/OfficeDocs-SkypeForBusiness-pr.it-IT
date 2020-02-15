---
title: Appartenenze a gruppi e requisiti per i diritti utente per Best Practices Analyzer
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
ms.openlocfilehash: b552f9aadfe9ed4c99c12b7e3f9524e4de143e23
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030379"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="group-memberships-and-user-rights-requirements-for-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="74293-102">Appartenenze a gruppi e requisiti per i diritti utente per Best Practices Analyzer in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="74293-102">Group memberships and user rights requirements for Best Practices Analyzer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="74293-103">_**Ultimo argomento modificato:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="74293-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="74293-p101">Per eseguire correttamente Best Practices Analyzer, è necessario che l'account utente utilizzato per accedere sia un membro del gruppo Administrators nel computer locale. Inoltre, per analizzare l'ambiente, è necessario che l'utente sia un membro dei gruppi seguenti:</span><span class="sxs-lookup"><span data-stu-id="74293-p101">To successfully run Best Practices Analyzer, the user account that you use to log on must be a member of the Administrators group on the local computer. Additionally, to scan your environment, the user account must be a member of the following groups:</span></span>

  - <span data-ttu-id="74293-106">**Domain Admins**   per enumerare le informazioni sui servizi di dominio Active Directory e per chiamare i provider di Strumentazione gestione Windows (WMI) sui controller di dominio e i server di catalogo globale.</span><span class="sxs-lookup"><span data-stu-id="74293-106">**Domain Admins**   To enumerate Active Directory Domain Services information and to call the Windows Management Instrumentation (WMI) providers on domain controllers and global catalog servers.</span></span>

  - <span data-ttu-id="74293-107">**Amministratori**   necessari per ogni computer interno di Lync Server 2013 e per ogni server perimetrale per chiamare i provider di Strumentazione gestione Windows (WMI) e per accedere al registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="74293-107">**Administrators**   Required on each Lync Server 2013 internal computer and each Edge Server to call the Windows Management Instrumentation (WMI) providers and to access the registry.</span></span>

  - <span data-ttu-id="74293-108">**RTCUniversalReadOnlyAdmins**   di sola lettura completa o delegata per i diritti amministrativi di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="74293-108">**RTCUniversalReadOnlyAdmins**   Full or delegated read only Lync Server 2013 administrative rights.</span></span>

  - <span data-ttu-id="74293-109">\*\*\*\*   Amministratore solo visualizzazione di Exchange solo amministratore di Exchange solo visualizzazione con delega nell'organizzazione di Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="74293-109">**Exchange View Only Administrator**   Full or delegated Exchange View Only Administrator on the Microsoft Exchange organization.</span></span>

<span data-ttu-id="74293-110">Se l'account utente non dispone di diritti utente sufficienti, sono disponibili due opzioni:</span><span class="sxs-lookup"><span data-stu-id="74293-110">If your user account does not have sufficient user rights, you have two options:</span></span>

  - <span data-ttu-id="74293-111">Nel prompt dei comandi utilizzare il comando **runas** per eseguire lo strumento in un account che non dispone diritti utenti sufficienti.</span><span class="sxs-lookup"><span data-stu-id="74293-111">At a command prompt, use the **runas** command to run the tool under an account that does have sufficient user rights.</span></span> <span data-ttu-id="74293-112">Di seguito viene illustrata la sintassi del comando:</span><span class="sxs-lookup"><span data-stu-id="74293-112">The syntax is as follows:</span></span>
    
        runas /netonly /user:<domain>\<userName> rtcbpa.exe

  - <span data-ttu-id="74293-113">Nella pagina **Connessione a Active Directory** impostare le credenziali per gli account che si prevede di utilizzare per eseguire lo strumento Best Practices Analyzer.</span><span class="sxs-lookup"><span data-stu-id="74293-113">On the **Connect to Active Directory** page, set the credentials for the accounts that you plan to use to run Best Practices Analyzer.</span></span> <span data-ttu-id="74293-114">Fare clic su **Mostra opzioni di accesso avanzate**.</span><span class="sxs-lookup"><span data-stu-id="74293-114">Click **Show advanced login options**.</span></span> <span data-ttu-id="74293-115">È possibile immettere tre account: uno per la connessione a servizi di dominio Active Directory, uno per la connessione ai server perimetrali di Lync Server 2013 e uno per la connessione ai server di Exchange.</span><span class="sxs-lookup"><span data-stu-id="74293-115">You can enter three accounts: one for connecting to Active Directory Domain Services, one for connecting to Lync Server 2013 Edge Servers, and one for connecting to the Exchange Servers.</span></span> <span data-ttu-id="74293-116">Se non si specifica nessuno dei tre account, verrà utilizzato l'account utente utilizzato per accedere ed eseguire lo strumento Best Practices Analyzer.</span><span class="sxs-lookup"><span data-stu-id="74293-116">If you do not specify any of these accounts, the user account that you used to log on and run Best Practices Analyzer is used.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

