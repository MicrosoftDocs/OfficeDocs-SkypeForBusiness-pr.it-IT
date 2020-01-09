---
title: 'Lync Server 2013: Preparazione dei domini'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Preparing domains
ms:assetid: 8eea541c-5f9d-4afc-92a8-a31d6f742544
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398721(v=OCS.15)
ms:contentKeyID: 48184816
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6cd8c09346c8f5b562a72e77b9ba40915b480c91
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991381"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-domains-for-lync-server-2013"></a><span data-ttu-id="d502e-102">Preparazione dei domini per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d502e-102">Preparing domains for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d502e-103">_**Argomento Ultima modifica:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="d502e-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="d502e-104">La preparazione del dominio è il passaggio finale della preparazione dei servizi di dominio Active Directory per Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d502e-104">Domain preparation is the final step in preparing Active Directory Domain Services for Lync Server 2013.</span></span> <span data-ttu-id="d502e-105">Il passaggio preparazione del dominio aggiunge le voci di controllo di accesso (ACE) necessarie ai gruppi universali che assegnano le autorizzazioni per ospitare e gestire gli utenti all'interno del dominio.</span><span class="sxs-lookup"><span data-stu-id="d502e-105">The domain preparation step adds the necessary access control entries (ACEs) to universal groups that grant permissions to host and manage users within the domain.</span></span> <span data-ttu-id="d502e-106">La preparazione del dominio crea ACE nella radice del dominio e tre contenitori predefiniti: User, computer e Domain controller.</span><span class="sxs-lookup"><span data-stu-id="d502e-106">Domain preparation creates ACEs on the domain root and three built-in containers: User, Computers, and Domain Controllers.</span></span>

<span data-ttu-id="d502e-107">È possibile eseguire la preparazione del dominio in qualsiasi computer del dominio in cui si sta distribuendo Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d502e-107">You can run domain preparation on any computer in the domain where you are deploying Lync Server.</span></span> <span data-ttu-id="d502e-108">È necessario preparare ogni dominio che ospiterà Lync Server o gli utenti.</span><span class="sxs-lookup"><span data-stu-id="d502e-108">You must prepare every domain that will host Lync Server or users.</span></span>

<span data-ttu-id="d502e-109">Se l'ereditarietà delle autorizzazioni è disabilitata o le autorizzazioni dell'utente autenticate sono disabilitate nell'organizzazione, è necessario eseguire ulteriori passaggi durante la preparazione del dominio.</span><span class="sxs-lookup"><span data-stu-id="d502e-109">If permissions inheritance is disabled or authenticated user permissions are disabled in your organization, you must perform additional steps during domain preparation.</span></span> <span data-ttu-id="d502e-110">Per informazioni dettagliate, vedere [preparazione di servizi di dominio Active Directory bloccati in Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md).</span><span class="sxs-lookup"><span data-stu-id="d502e-110">For details, see [Preparing a locked-down Active Directory Domain Services in Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md).</span></span>

<span data-ttu-id="d502e-111">Se l'organizzazione USA unità organizzative (OU) anziché i tre contenitori predefiniti, ovvero utenti, computer e controller di dominio, è necessario concedere l'accesso in lettura alle unità organizzative per il gruppo Authenticated Users.</span><span class="sxs-lookup"><span data-stu-id="d502e-111">If your organization uses organizational units (OU) instead of the three built-in containers (that is, Users, Computers, and Domain Controllers), you must grant read access to the OUs for the Authenticated Users group.</span></span> <span data-ttu-id="d502e-112">Per la preparazione del dominio è necessaria l'accesso in lettura ai contenitori.</span><span class="sxs-lookup"><span data-stu-id="d502e-112">Read access to the containers is required for domain preparation.</span></span> <span data-ttu-id="d502e-113">Se il gruppo Authenticated Users non ha accesso in lettura all'unità organizzativa, eseguire il cmdlet **Grant-CsOUPermission** come illustrato negli esempi di codice seguenti per concedere le autorizzazioni di lettura per ogni ou.</span><span class="sxs-lookup"><span data-stu-id="d502e-113">If the Authenticated Users group does not have read access to the OU, run the **Grant-CsOuPermission** cmdlet as illustrated in the following code examples to grant read permissions for each OU.</span></span>

   ```PowerShell
    Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU > 
   ```

   ```PowerShell
    Grant-CsOuPermission -ObjectType "user","contact",inetOrgPerson" -OU "ou=Redmond,dc=contoso,dc=net"
   ```

<span data-ttu-id="d502e-114">Per informazioni dettagliate sul cmdlet **Grant-CsOUPermission** , vedere la documentazione di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="d502e-114">For details about the **Grant-CsOuPermission** cmdlet, see the Lync Server Management Shell documentation.</span></span>

<div class="">


> [!TIP]  
> <span data-ttu-id="d502e-115">Per informazioni dettagliate sulle voci ACE create nella radice del dominio e nei contenitori utenti, computer e controller di dominio, vedere <A href="lync-server-2013-changes-made-by-domain-preparation.md">modifiche apportate dalla preparazione del dominio in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="d502e-115">For details about the ACEs created on the domain root and in the Users, Computers, and Domain Controllers containers, see <A href="lync-server-2013-changes-made-by-domain-preparation.md">Changes made by domain preparation in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d502e-116">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="d502e-116">In This Section</span></span>

  - [<span data-ttu-id="d502e-117">Esecuzione della preparazione del dominio per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d502e-117">Running domain preparation for Lync Server 2013</span></span>](lync-server-2013-running-domain-preparation.md)

  - [<span data-ttu-id="d502e-118">Utilizzo di cmdlet per ripristinare la preparazione del dominio per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d502e-118">Using cmdlets to reverse domain preparation for Lync Server 2013</span></span>](lync-server-2013-using-cmdlets-to-reverse-domain-preparation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

