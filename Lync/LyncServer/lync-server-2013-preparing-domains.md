---
title: 'Lync Server 2013: preparazione di domini'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing domains
ms:assetid: 8eea541c-5f9d-4afc-92a8-a31d6f742544
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398721(v=OCS.15)
ms:contentKeyID: 48184816
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f77c37b1694383284ec80667eba745109814c58
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139137"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="preparing-domains-for-lync-server-2013"></a><span data-ttu-id="febfc-102">Preparazione dei domini per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="febfc-102">Preparing domains for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="febfc-103">_**Ultimo argomento modificato:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="febfc-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="febfc-104">La preparazione del dominio è il passaggio finale nella preparazione di servizi di dominio Active Directory per Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="febfc-104">Domain preparation is the final step in preparing Active Directory Domain Services for Lync Server 2013.</span></span> <span data-ttu-id="febfc-105">Questa operazione comporta l'aggiunta delle voci di controllo di accesso necessarie ai gruppi universali che concedono autorizzazioni per ospitare e gestire gli utenti nell'ambito del dominio.</span><span class="sxs-lookup"><span data-stu-id="febfc-105">The domain preparation step adds the necessary access control entries (ACEs) to universal groups that grant permissions to host and manage users within the domain.</span></span> <span data-ttu-id="febfc-106">Con la preparazione del dominio vengono create voci di controllo di accesso nella radice del dominio e tre contenitori predefiniti per utenti, computer e controller di dominio.</span><span class="sxs-lookup"><span data-stu-id="febfc-106">Domain preparation creates ACEs on the domain root and three built-in containers: User, Computers, and Domain Controllers.</span></span>

<span data-ttu-id="febfc-107">È possibile eseguire la preparazione del dominio in qualsiasi computer del dominio in cui si distribuisce Lync Server.</span><span class="sxs-lookup"><span data-stu-id="febfc-107">You can run domain preparation on any computer in the domain where you are deploying Lync Server.</span></span> <span data-ttu-id="febfc-108">È necessario preparare tutti i domini che ospiteranno Lync Server o gli utenti.</span><span class="sxs-lookup"><span data-stu-id="febfc-108">You must prepare every domain that will host Lync Server or users.</span></span>

<span data-ttu-id="febfc-109">Se l'ereditarietà delle autorizzazioni è disabilitata o le autorizzazioni degli utenti autenticati sono disabilitate nell'organizzazione, durante la preparazione del dominio sono necessari alcuni passaggi aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="febfc-109">If permissions inheritance is disabled or authenticated user permissions are disabled in your organization, you must perform additional steps during domain preparation.</span></span> <span data-ttu-id="febfc-110">Per ulteriori informazioni, vedere [preparazione di servizi di dominio Active Directory bloccati in Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md).</span><span class="sxs-lookup"><span data-stu-id="febfc-110">For details, see [Preparing a locked-down Active Directory Domain Services in Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md).</span></span>

<span data-ttu-id="febfc-111">Se nell'organizzazione vengono utilizzate unità organizzative anziché i tre contenitori predefiniti, ovvero Utenti, Computer e Controller di dominio, sarà necessario concedere al gruppo Authenticated Users l'accesso in lettura alle unità organizzative.</span><span class="sxs-lookup"><span data-stu-id="febfc-111">If your organization uses organizational units (OU) instead of the three built-in containers (that is, Users, Computers, and Domain Controllers), you must grant read access to the OUs for the Authenticated Users group.</span></span> <span data-ttu-id="febfc-112">L'accesso in lettura ai contenitori è necessario per la preparazione del dominio.</span><span class="sxs-lookup"><span data-stu-id="febfc-112">Read access to the containers is required for domain preparation.</span></span> <span data-ttu-id="febfc-113">Se il gruppo Utenti autenticati non dispone di accesso in lettura all'unità organizzativa, eseguire il cmdlet **Grant-CsOuPermission** come illustrato negli esempi di codice seguenti per concedere l'autorizzazione di lettura per ogni unità organizzativa.</span><span class="sxs-lookup"><span data-stu-id="febfc-113">If the Authenticated Users group does not have read access to the OU, run the **Grant-CsOuPermission** cmdlet as illustrated in the following code examples to grant read permissions for each OU.</span></span>

   ```PowerShell
    Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU > 
   ```

   ```PowerShell
    Grant-CsOuPermission -ObjectType "user","contact",inetOrgPerson" -OU "ou=Redmond,dc=contoso,dc=net"
   ```

<span data-ttu-id="febfc-114">Per informazioni dettagliate sul cmdlet **Grant-CsOUPermission** , vedere la documentazione di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="febfc-114">For details about the **Grant-CsOuPermission** cmdlet, see the Lync Server Management Shell documentation.</span></span>

<div class="">


> [!TIP]  
> <span data-ttu-id="febfc-115">Per informazioni dettagliate sulle voci di controllo di accesso create nella radice del dominio e nei contenitori utenti, computer e controller di dominio, vedere <A href="lync-server-2013-changes-made-by-domain-preparation.md">changes made by domain preparation in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="febfc-115">For details about the ACEs created on the domain root and in the Users, Computers, and Domain Controllers containers, see <A href="lync-server-2013-changes-made-by-domain-preparation.md">Changes made by domain preparation in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="febfc-116">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="febfc-116">In This Section</span></span>

  - [<span data-ttu-id="febfc-117">Esecuzione della preparazione del dominio per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="febfc-117">Running domain preparation for Lync Server 2013</span></span>](lync-server-2013-running-domain-preparation.md)

  - [<span data-ttu-id="febfc-118">Utilizzo dei cmdlet per annullare la preparazione del dominio per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="febfc-118">Using cmdlets to reverse domain preparation for Lync Server 2013</span></span>](lync-server-2013-using-cmdlets-to-reverse-domain-preparation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

