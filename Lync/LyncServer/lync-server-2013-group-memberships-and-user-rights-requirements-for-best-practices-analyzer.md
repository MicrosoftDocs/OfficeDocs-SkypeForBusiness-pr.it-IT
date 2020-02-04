---
title: Requisiti per i membri e i diritti utente per l'analizzatore delle procedure consigliate
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
ms.openlocfilehash: b9561736fc6dce1649d0a3dd29e15a7d88500a38
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757560"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="group-memberships-and-user-rights-requirements-for-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="a4740-102">Requisiti per i diritti utente e le appartenenze ai gruppi per Best Practices Analyzer in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a4740-102">Group memberships and user rights requirements for Best Practices Analyzer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a4740-103">_**Argomento Ultima modifica:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="a4740-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="a4740-104">Per eseguire correttamente l'analizzatore delle procedure consigliate, l'account utente che si usa per accedere deve essere un membro del gruppo Administrators nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="a4740-104">To successfully run Best Practices Analyzer, the user account that you use to log on must be a member of the Administrators group on the local computer.</span></span> <span data-ttu-id="a4740-105">Inoltre, per analizzare l'ambiente, l'account utente deve essere un membro dei gruppi seguenti:</span><span class="sxs-lookup"><span data-stu-id="a4740-105">Additionally, to scan your environment, the user account must be a member of the following groups:</span></span>

  - <span data-ttu-id="a4740-106">**Domain Admins**   per enumerare le informazioni sui servizi di dominio Active Directory e per chiamare i provider di Strumentazione gestione Windows (WMI) nei controller di dominio e nei server di catalogo globale.</span><span class="sxs-lookup"><span data-stu-id="a4740-106">**Domain Admins**   To enumerate Active Directory Domain Services information and to call the Windows Management Instrumentation (WMI) providers on domain controllers and global catalog servers.</span></span>

  - <span data-ttu-id="a4740-107">**Amministratori**   necessari per ogni computer interno di Lync Server 2013 e ogni Edge Server per chiamare i provider di Strumentazione gestione Windows (WMI) e per accedere al registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="a4740-107">**Administrators**   Required on each Lync Server 2013 internal computer and each Edge Server to call the Windows Management Instrumentation (WMI) providers and to access the registry.</span></span>

  - <span data-ttu-id="a4740-108">**RTCUniversalReadOnlyAdmins**   di sola lettura completa o delegata per i diritti amministrativi di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a4740-108">**RTCUniversalReadOnlyAdmins**   Full or delegated read only Lync Server 2013 administrative rights.</span></span>

  - <span data-ttu-id="a4740-109">**Exchange**   solo l'amministratore completo o delegato di Exchange solo visualizzazione amministratore nell'organizzazione di Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="a4740-109">**Exchange View Only Administrator**   Full or delegated Exchange View Only Administrator on the Microsoft Exchange organization.</span></span>

<span data-ttu-id="a4740-110">Se l'account utente non dispone di diritti utente sufficienti, sono disponibili due opzioni:</span><span class="sxs-lookup"><span data-stu-id="a4740-110">If your user account does not have sufficient user rights, you have two options:</span></span>

  - <span data-ttu-id="a4740-111">Al prompt dei comandi usare il comando **RunAs** per eseguire lo strumento in un account che dispone di diritti utente sufficienti.</span><span class="sxs-lookup"><span data-stu-id="a4740-111">At a command prompt, use the **runas** command to run the tool under an account that does have sufficient user rights.</span></span> <span data-ttu-id="a4740-112">La sintassi è la seguente:</span><span class="sxs-lookup"><span data-stu-id="a4740-112">The syntax is as follows:</span></span>
    
        runas /netonly /user:<domain>\<userName> rtcbpa.exe

  - <span data-ttu-id="a4740-113">Nella pagina **Connetti a Active Directory** impostare le credenziali per gli account che si prevede di usare per l'esecuzione di Best Practices Analyzer.</span><span class="sxs-lookup"><span data-stu-id="a4740-113">On the **Connect to Active Directory** page, set the credentials for the accounts that you plan to use to run Best Practices Analyzer.</span></span> <span data-ttu-id="a4740-114">Fare clic su **Mostra opzioni di accesso avanzato**.</span><span class="sxs-lookup"><span data-stu-id="a4740-114">Click **Show advanced login options**.</span></span> <span data-ttu-id="a4740-115">È possibile immettere tre account: uno per la connessione a servizi di dominio Active Directory, uno per la connessione a server Edge di Lync Server 2013 e uno per la connessione ai server di Exchange.</span><span class="sxs-lookup"><span data-stu-id="a4740-115">You can enter three accounts: one for connecting to Active Directory Domain Services, one for connecting to Lync Server 2013 Edge Servers, and one for connecting to the Exchange Servers.</span></span> <span data-ttu-id="a4740-116">Se non specifichi uno di questi account, viene usato l'account utente usato per accedere ed eseguire Best Practices Analyzer.</span><span class="sxs-lookup"><span data-stu-id="a4740-116">If you do not specify any of these accounts, the user account that you used to log on and run Best Practices Analyzer is used.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

