---
title: "Lync Server 2013: requisiti dell'infrastruttura di Active Directory"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory infrastructure requirements
ms:assetid: c2086f7b-662f-4179-ab99-2c0311ebd903
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412955(v=OCS.15)
ms:contentKeyID: 48185318
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 14980b886ac9a00b9ea23a0d915bc34ac3956c7f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008548"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="active-directory-infrastructure-requirements-for-lync-server-2013"></a><span data-ttu-id="d6ea2-102">Requisiti dell'infrastruttura di Active Directory per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d6ea2-102">Active Directory infrastructure requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d6ea2-103">_**Ultimo argomento modificato:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="d6ea2-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="d6ea2-104">Prima di iniziare il processo di preparazione di servizi di dominio Active Directory per Lync Server 2013, verificare che l'infrastruttura di Active Directory soddisfi i prerequisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="d6ea2-104">Before you start the process of preparing Active Directory Domain Services for Lync Server 2013, make sure that your Active Directory infrastructure meets the following prerequisites:</span></span>

  - <span data-ttu-id="d6ea2-105">Tutti i controller di dominio (che includono tutti i server di catalogo globale) nella foresta in cui si distribuisce Lync Server eseguono uno dei sistemi operativi seguenti:</span><span class="sxs-lookup"><span data-stu-id="d6ea2-105">All domain controllers (which include all global catalog servers) in the forest where you deploy Lync Server run one of the following operating systems:</span></span>
    
      - <span data-ttu-id="d6ea2-106">Sistema operativo Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="d6ea2-106">Windows Server 2012 R2 operating system</span></span>
    
      - <span data-ttu-id="d6ea2-107">Sistema operativo Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="d6ea2-107">Windows Server 2012 operating system</span></span>
    
      - <span data-ttu-id="d6ea2-108">Sistema operativo Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="d6ea2-108">Windows Server 2008 R2 operating system</span></span>
    
      - <span data-ttu-id="d6ea2-109">Sistema operativo Windows 2008</span><span class="sxs-lookup"><span data-stu-id="d6ea2-109">Windows Server 2008 operating system</span></span>
    
      - <span data-ttu-id="d6ea2-110">Windows Server 2008 Enterprise 32 bit</span><span class="sxs-lookup"><span data-stu-id="d6ea2-110">Windows Server 2008 Enterprise 32-Bit</span></span>
    
      - <span data-ttu-id="d6ea2-111">Versioni a 32 bit o a 64 bit del sistema operativo Windows Server 2003 R2</span><span class="sxs-lookup"><span data-stu-id="d6ea2-111">32-bit or 64-bit versions of the Windows Server 2003 R2 operating system</span></span>
    
      - <span data-ttu-id="d6ea2-112">versioni a 32 bit o a 64 bit del sistema operativo Windows Server 2003</span><span class="sxs-lookup"><span data-stu-id="d6ea2-112">32-bit or 64-bit versions of the Windows Server 2003 operating system</span></span>

  - <span data-ttu-id="d6ea2-113">Tutti i domini in cui si distribuisce Lync Server vengono innalzati a un livello di funzionalità di dominio di Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 o almeno Windows Server 2003.</span><span class="sxs-lookup"><span data-stu-id="d6ea2-113">All domains in which you deploy Lync Server are raised to a domain functional level of Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008, or at least Windows Server 2003.</span></span>

  - <span data-ttu-id="d6ea2-114">La foresta in cui si distribuisce Lync Server viene innalzata a un livello di funzionalità della foresta di Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 o almeno Windows Server 2003.</span><span class="sxs-lookup"><span data-stu-id="d6ea2-114">The forest in which you deploy Lync Server is raised to a forest functional level of Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008, or at least Windows Server 2003.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d6ea2-115">Per modificare il dominio o il livello di funzionalità della foresta, vedere "innalzamento dei livelli di funzionalità del dominio e <A href="http://go.microsoft.com/fwlink/p/?linkid=263775">http://go.microsoft.com/fwlink/p/?LinkId=263775</A>della foresta" nella libreria TechNet all'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="d6ea2-115">To change your domain or forest functional level, see "Raising domain and forest functional levels" in the TechNet Library at <A href="http://go.microsoft.com/fwlink/p/?linkid=263775">http://go.microsoft.com/fwlink/p/?LinkId=263775</A>.</span></span>

    
    </div>

  - <span data-ttu-id="d6ea2-116">Un catalogo globale viene distribuito in tutti i domini in cui vengono distribuiti computer o utenti di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d6ea2-116">A global catalog is deployed in every domain where you deploy Lync Server computers or users.</span></span>

<span data-ttu-id="d6ea2-117">Lync Server 2013 supporta i gruppi universali nei sistemi operativi Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 e Windows Server 2003.</span><span class="sxs-lookup"><span data-stu-id="d6ea2-117">Lync Server 2013 supports the universal groups in the Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008, and Windows Server 2003 operating systems.</span></span> <span data-ttu-id="d6ea2-118">Ai membri dei gruppi universali, che possono includere altri gruppi e account di qualsiasi dominio della foresta o dell'albero di dominio, è possibile assegnare autorizzazioni in qualsiasi dominio della foresta o dell'albero di dominio.</span><span class="sxs-lookup"><span data-stu-id="d6ea2-118">Members of universal groups can include other groups and accounts from any domain in the domain tree or forest and can be assigned permissions in any domain in the domain tree or forest.</span></span> <span data-ttu-id="d6ea2-119">Il supporto di gruppo universale, Unito alla delega dell'amministratore, semplifica la gestione di una distribuzione di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d6ea2-119">Universal group support, combined with administrator delegation, simplifies the management of a Lync Server deployment.</span></span> <span data-ttu-id="d6ea2-120">Non è più necessario, ad esempio, aggiungere un dominio a un altro per consentire a un amministratore di gestirli entrambi.</span><span class="sxs-lookup"><span data-stu-id="d6ea2-120">For example, it is not necessary to add one domain to another to enable an administrator to manage both.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

