---
title: 'Lync Server 2013: supporto per servizi di dominio Active Directory'
description: 'Lync Server 2013: supporto dei servizi di dominio Active Directory.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory Domain Services support
ms:assetid: aeb62d5e-e424-473a-b795-9452150c98dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412831(v=OCS.15)
ms:contentKeyID: 48185136
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bb2a85bab90557c28c4802721d4202f6188cb3f1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558682"
---
# <a name="active-directory-domain-services-support-in-lync-server-2013"></a><span data-ttu-id="ff1f3-103">Supporto dei servizi di dominio Active Directory in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ff1f3-103">Active Directory Domain Services support in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ff1f3-104">_**Ultimo argomento modificato:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="ff1f3-104">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="ff1f3-105">Lync Server 2013 utilizza l'archivio di gestione centrale per archiviare i dati di configurazione per i server e i servizi, anziché basarsi su servizi di dominio Active Directory per queste informazioni, come nel passato.</span><span class="sxs-lookup"><span data-stu-id="ff1f3-105">Lync Server 2013 uses the Central Management store to store configuration data for servers and services, instead of relying on Active Directory Domain Services for this information, as in the past.</span></span> <span data-ttu-id="ff1f3-106">In servizi di dominio Active Directory Lync Server 2013 archivia ancora le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ff1f3-106">Lync Server 2013 still stores the following in AD DS:</span></span>

  - <span data-ttu-id="ff1f3-107">**Estensioni dello schema**</span><span class="sxs-lookup"><span data-stu-id="ff1f3-107">**Schema extensions**</span></span>
    
      - <span data-ttu-id="ff1f3-108">Estensioni degli oggetti utente</span><span class="sxs-lookup"><span data-stu-id="ff1f3-108">User object extensions</span></span>
    
      - <span data-ttu-id="ff1f3-109">Estensioni per le classi di Lync Server 2010 e Office Communications Server 2007 R2 per mantenere la compatibilità con le versioni precedenti supportate</span><span class="sxs-lookup"><span data-stu-id="ff1f3-109">Extensions for Lync Server 2010 and Office Communications Server 2007 R2 classes to maintain backward compatibility with previous supported versions</span></span>

  - <span data-ttu-id="ff1f3-110">**Dati** (archiviati in Lync Server 2013 Extended schema e nelle classi esistenti)</span><span class="sxs-lookup"><span data-stu-id="ff1f3-110">**Data** (stored in Lync Server 2013 extended schema and in existing classes)</span></span>
    
      - <span data-ttu-id="ff1f3-111">URI SIP dell'utente e altre impostazioni utente</span><span class="sxs-lookup"><span data-stu-id="ff1f3-111">User SIP URI and other user settings</span></span>
    
      - <span data-ttu-id="ff1f3-112">Oggetti contatto per le applicazioni, ad esempio l'applicazione Response Group e l'applicazione Operatore Conferenza.</span><span class="sxs-lookup"><span data-stu-id="ff1f3-112">Contact objects for applications (for example, the Response Group application and the Conferencing Attendant application)</span></span>
    
      - <span data-ttu-id="ff1f3-113">Dati pubblicati per la compatibilità con le versioni precedenti</span><span class="sxs-lookup"><span data-stu-id="ff1f3-113">Data published for backward compatibility</span></span>
    
      - <span data-ttu-id="ff1f3-114">Un punto di controllo del servizio (SCP) per l'archivio di gestione centrale</span><span class="sxs-lookup"><span data-stu-id="ff1f3-114">A service control point (SCP) for the Central Management store</span></span>
    
      - <span data-ttu-id="ff1f3-115">Account di autenticazione Kerberos (un oggetto computer facoltativo)</span><span class="sxs-lookup"><span data-stu-id="ff1f3-115">Kerberos Authentication Account (an optional computer object)</span></span>

<span data-ttu-id="ff1f3-116">In questa sezione vengono descritti i requisiti di supporto per servizi di dominio Active Directory per Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ff1f3-116">This section describes the AD DS support requirements for Lync Server 2013.</span></span> <span data-ttu-id="ff1f3-117">Per informazioni dettagliate sul supporto delle topologie, vedere [supportate le topologie di Active Directory in Lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) nella documentazione relativa alla supportabilità.</span><span class="sxs-lookup"><span data-stu-id="ff1f3-117">For details about topology support, see [Supported Active Directory topologies in Lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) in the Supportability documentation.</span></span>

<div>

## <a name="supported-domain-controller-operating-systems"></a><span data-ttu-id="ff1f3-118">Sistemi operativi supportati per i controller di dominio</span><span class="sxs-lookup"><span data-stu-id="ff1f3-118">Supported Domain Controller Operating Systems</span></span>

<span data-ttu-id="ff1f3-119">Lync Server 2013 supporta i controller di dominio che eseguono i sistemi operativi seguenti:</span><span class="sxs-lookup"><span data-stu-id="ff1f3-119">Lync Server 2013 supports domain controllers running the following operating systems:</span></span>

  - <span data-ttu-id="ff1f3-120">Sistema operativo Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="ff1f3-120">Windows Server 2012 R2 operating system</span></span>

  - <span data-ttu-id="ff1f3-121">Sistema operativo Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="ff1f3-121">Windows Server 2012 operating system</span></span>

  - <span data-ttu-id="ff1f3-122">Sistema operativo Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="ff1f3-122">Windows Server 2008 R2 operating system</span></span>

  - <span data-ttu-id="ff1f3-123">Sistema operativo Windows 2008</span><span class="sxs-lookup"><span data-stu-id="ff1f3-123">Windows Server 2008 operating system</span></span>

  - <span data-ttu-id="ff1f3-124">Windows Server 2008 Enterprise 32 bit</span><span class="sxs-lookup"><span data-stu-id="ff1f3-124">Windows Server 2008 Enterprise 32-Bit</span></span>

  - <span data-ttu-id="ff1f3-125">Versioni a 32 bit o a 64 bit del sistema operativo Window Server 2003 R2</span><span class="sxs-lookup"><span data-stu-id="ff1f3-125">The 32-bit or 64-bit versions of the Window Server 2003 R2 operating system</span></span>

  - <span data-ttu-id="ff1f3-126">Versioni a 32 bit o a 64 bit del sistema operativo Windows Server 2003</span><span class="sxs-lookup"><span data-stu-id="ff1f3-126">The 32-bit or 64-bit versions of the Windows Server 2003 operating system</span></span>

</div>

<div>

## <a name="forest-and-domain-functional-level"></a><span data-ttu-id="ff1f3-127">Livello di funzionalità della foresta e del dominio</span><span class="sxs-lookup"><span data-stu-id="ff1f3-127">Forest and Domain Functional Level</span></span>

<span data-ttu-id="ff1f3-128">È necessario generare tutti i domini in cui si distribuisce Lync Server 2013 a livello di funzionalità di dominio di Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 o almeno Windows Server 2003.</span><span class="sxs-lookup"><span data-stu-id="ff1f3-128">You must raise all domains in which you deploy Lync Server 2013 to a domain functional level of Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008, or at least Windows Server 2003.</span></span>

<span data-ttu-id="ff1f3-129">Tutte le foreste in cui si distribuisce Lync Server 2013 devono essere elevate a un livello di funzionalità della foresta di Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 o almeno Windows Server 2003.</span><span class="sxs-lookup"><span data-stu-id="ff1f3-129">All forests in which you deploy Lync Server 2013 must be raised to a forest functional level of Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008, or at least Windows Server 2003.</span></span>

</div>

<div>

## <a name="support-for-read-only-domain-controllers"></a><span data-ttu-id="ff1f3-130">Supporto per i controller di dominio Read-Only</span><span class="sxs-lookup"><span data-stu-id="ff1f3-130">Support for Read-Only Domain Controllers</span></span>

<span data-ttu-id="ff1f3-131">Lync Server 2013 supporta le distribuzioni di servizi di dominio Active Directory che includono i controller di dominio di sola lettura o i server di catalogo globale di sola lettura, purché siano disponibili controller di dominio scrivibili.</span><span class="sxs-lookup"><span data-stu-id="ff1f3-131">Lync Server 2013 supports Active Directory Domain Services deployments that include read-only domain controllers or read-only global catalog servers, as long as there are writable domain controllers available.</span></span>

</div>

<div>

## <a name="domain-names"></a><span data-ttu-id="ff1f3-132">Nomi di dominio</span><span class="sxs-lookup"><span data-stu-id="ff1f3-132">Domain Names</span></span>

<span data-ttu-id="ff1f3-133">Lync Server non supporta i domini con etichetta singola.</span><span class="sxs-lookup"><span data-stu-id="ff1f3-133">Lync Server does not support single-labeled domains.</span></span> <span data-ttu-id="ff1f3-134">Una foresta con un dominio radice denominato **contoso.local** ad esempio è supportata, ma un dominio radice denominato **local** non è supportato.</span><span class="sxs-lookup"><span data-stu-id="ff1f3-134">For example, a forest with a root domain named **contoso.local** is supported, but a root domain named **local** is not supported.</span></span> <span data-ttu-id="ff1f3-135">Per informazioni dettagliate, vedere l'articolo 300684 della Microsoft Knowledge Base "informazioni sulla configurazione di Windows per domini con nomi DNS con etichetta singola" all'indirizzo [https://go.microsoft.com/fwlink/p/?linkId=143752](https://go.microsoft.com/fwlink/p/?linkid=143752) .</span><span class="sxs-lookup"><span data-stu-id="ff1f3-135">For details, see Microsoft Knowledge Base article 300684, “Information about configuring Windows for domains with single-label DNS names,” at [https://go.microsoft.com/fwlink/p/?linkId=143752](https://go.microsoft.com/fwlink/p/?linkid=143752).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ff1f3-136">Lync Server non supporta la ridenominazione dei domini.</span><span class="sxs-lookup"><span data-stu-id="ff1f3-136">Lync Server does not support renaming domains.</span></span> <span data-ttu-id="ff1f3-137">Se è necessario rinominare un dominio in cui è distribuito Lync Server, è necessario innanzitutto disinstallare Lync Server, rinominare il dominio e quindi reinstallare Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ff1f3-137">If you need to rename a domain where Lync Server is deployed, you need to first uninstall Lync Server, then rename the domain, and then reinstall Lync Server.</span></span>



</div>

</div>

<div>

## <a name="locked-down-adds-environments"></a><span data-ttu-id="ff1f3-138">Ambienti di servizi di dominio Active Directory bloccati</span><span class="sxs-lookup"><span data-stu-id="ff1f3-138">Locked Down AD DS Environments</span></span>

<span data-ttu-id="ff1f3-139">In un ambiente di servizi di dominio Active Directory bloccato, gli utenti e gli oggetti computer vengono spesso inseriti in unità organizzative specifiche con l'ereditarietà delle autorizzazioni disattivata per proteggere la delega amministrativa e per consentire l'utilizzo di oggetti Criteri di gruppo per applicare i criteri di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="ff1f3-139">In a locked-down AD DS environment, Users and Computer objects are often placed in specific organizational units (OUs) with permissions inheritance disabled to help secure administrative delegation and to enable use of Group Policy objects (GPOs) to enforce security policies.</span></span> <span data-ttu-id="ff1f3-140">Lync Server 2013 può essere distribuito in un ambiente Active Directory bloccato.</span><span class="sxs-lookup"><span data-stu-id="ff1f3-140">Lync Server 2013 can be deployed in a locked-down Active Directory environment.</span></span> <span data-ttu-id="ff1f3-141">Per informazioni dettagliate sulle operazioni necessarie per la distribuzione di Lync Server in un ambiente bloccato, vedere [preparazione di servizi di dominio Active Directory bloccati in Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="ff1f3-141">For details about what is required to deploy Lync Server in a locked-down environment, see [Preparing a locked-down Active Directory Domain Services in Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md) in the Deployment documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

