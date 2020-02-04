---
title: "Lync Server 2013: creare o modificare un oggetto contatto telefonico per l'area comune"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a common area phone Contact object
ms:assetid: eec33ad1-e4f2-49b2-91d6-d5a9d2e1714b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994083(v=OCS.15)
ms:contentKeyID: 51803995
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e9e7ddf1a4911b9afb3428531911223f62ea723
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758110"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-common-area-phone-contact-object-in-lync-server-2013"></a><span data-ttu-id="739fe-102">Creare o modificare un oggetto contatto telefonico per l'area comune in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="739fe-102">Create or modify a common area phone Contact object in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="739fe-103">_**Argomento Ultima modifica:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="739fe-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="739fe-104">Per creare oggetti di contatto di servizi di dominio Active Directory per tutti i telefoni dell'area comune, usare il cmdlet **New-CsCommonAreaPhone** .</span><span class="sxs-lookup"><span data-stu-id="739fe-104">To create Active Directory Domain Services contact objects for all your common area phones, use the **New-CsCommonAreaPhone** cmdlet.</span></span> <span data-ttu-id="739fe-105">Questo cmdlet può creare nuovi oggetti contatto da usare con i telefoni delle aree comuni oppure può associare oggetti contatto esistenti a un nuovo telefono con area comune.</span><span class="sxs-lookup"><span data-stu-id="739fe-105">This cmdlet can either create new contact objects for use with common area phones, or it can associate existing contact objects with a new common area phone.</span></span> <span data-ttu-id="739fe-106">Per modificare le proprietà degli oggetti contatto associati ai telefoni delle aree comuni, usare il cmdlet **Set-CsCommonAreaPhone** .</span><span class="sxs-lookup"><span data-stu-id="739fe-106">To modify the properties of the contact objects associated with common area phones, use the **Set-CsCommonAreaPhone** cmdlet.</span></span> <span data-ttu-id="739fe-107">I parametri facoltativi per **Set-CsCommonAreaPhone** consentono di modificare gli elementi, ad esempio il nome visualizzato di Active Directory del contatto o l'URI (Uniform Resource Identifier) line associato al telefono, e di abilitare e disabilitare l'account da usare con Lync Server.</span><span class="sxs-lookup"><span data-stu-id="739fe-107">Optional parameters for **Set-CsCommonAreaPhone** enable you to change items, such as the contact’s Active Directory display name or the line Uniform Resource Identifier (URI) associated with the phone, and enable and disable the account for use with Lync Server.</span></span> <span data-ttu-id="739fe-108">Per informazioni dettagliate su tutte le modifiche disponibili, vedere la sezione parametri in [Set-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone).</span><span class="sxs-lookup"><span data-stu-id="739fe-108">For details about all the available modifications, see the Parameters section at [Set-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone).</span></span> <span data-ttu-id="739fe-109">Per informazioni dettagliate sui parametri **New-CsCommonAreaPhone** , vedere [New-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone).</span><span class="sxs-lookup"><span data-stu-id="739fe-109">For details about **New-CsCommonAreaPhone** parameters, see [New-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone).</span></span>

<span data-ttu-id="739fe-110">È possibile eseguire questi due cmdlet da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="739fe-110">You can run these two cmdlets from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="739fe-111">Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="739fe-111">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>


<div>

## <a name="creating-a-common-area-phone-contact-object"></a><span data-ttu-id="739fe-112">Creazione di un oggetto contatto telefonico per l'area comune</span><span class="sxs-lookup"><span data-stu-id="739fe-112">Creating a common area phone contact object</span></span>

  - <span data-ttu-id="739fe-113">Per creare un nuovo oggetto contatto telefonico per l'area comune, usare il cmdlet **New-CsCommonAreaPhone** .</span><span class="sxs-lookup"><span data-stu-id="739fe-113">To create a new common area phone contact object, use the **New-CsCommonAreaPhone** cmdlet.</span></span> <span data-ttu-id="739fe-114">Quando si crea un oggetto contatto, è necessario specificare almeno le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="739fe-114">At a minimum, you must supply the following information when creating a contact object:</span></span>
    
      - <span data-ttu-id="739fe-115">**LineUri**: il numero di telefono assegnato al telefono per l'area comune.</span><span class="sxs-lookup"><span data-stu-id="739fe-115">**LineUri**: The telephone number assigned to the common area phone.</span></span> <span data-ttu-id="739fe-116">Tenere presente che è necessario usare il formato E. 164 quando si specifica il numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="739fe-116">Note that you must use the E.164 format when specifying the phone number.</span></span>
    
      - <span data-ttu-id="739fe-117">**RegistrarPool**: il nome di dominio completo (FQDN) del pool di registrar che ospiterà l'oggetto contatto.</span><span class="sxs-lookup"><span data-stu-id="739fe-117">**RegistrarPool**: The fully qualified domain name (FQDN) of the Registrar pool that will host the contact object.</span></span>
    
      - <span data-ttu-id="739fe-118">**Ou**: nome distinto del contenitore di Active Directory in cui verrà creato l'oggetto contatto.</span><span class="sxs-lookup"><span data-stu-id="739fe-118">**OU**: Distinguished name of the Active Directory container where the contact object will be created.</span></span>
    
    <span data-ttu-id="739fe-119">Ti consigliamo anche di specificare un nome visualizzato per servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="739fe-119">We also recommend that you provide an Active Directory Domain Services display name.</span></span> <span data-ttu-id="739fe-120">In caso contrario, sarà necessario usare un GUID per specificare l'identità del telefono.</span><span class="sxs-lookup"><span data-stu-id="739fe-120">Otherwise, you will need to use a GUID to specify the phone Identity.</span></span> <span data-ttu-id="739fe-121">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="739fe-121">For example:</span></span>
    
        New-CsCommonAreaPhone -LineUri "tel:+12065551219" -RegistrarPool "atl-cs-001.litwareinc.com" -OU "OU=Phones,dc=litwareinc,dc=com" -DisplayName "Lobby"

</div>

<div>

## <a name="modifying-a-common-area-phone-contact-object"></a><span data-ttu-id="739fe-122">Modifica di un oggetto contatto telefonico per l'area comune</span><span class="sxs-lookup"><span data-stu-id="739fe-122">Modifying a common area phone contact object</span></span>

  - <span data-ttu-id="739fe-123">Per modificare le proprietà di un telefono di area comune esistente, usare il cmdlet **Set-CsCommonAreaPhone** per l'oggetto contatto.</span><span class="sxs-lookup"><span data-stu-id="739fe-123">To modify the properties of an existing common area phone, contact object use the **Set-CsCommonAreaPhone** cmdlet.</span></span> <span data-ttu-id="739fe-124">Ad esempio, questo comando configura l'indirizzo SIP per il telefono per l'area comune con la lobby DisplayName:</span><span class="sxs-lookup"><span data-stu-id="739fe-124">For example, this command configures the SIP address for the common area phone with the DisplayName Lobby:</span></span>
    
        Set-CsCommonAreaPhone -Identity "Lobby" -SipAddress "sip:lobby@litwareinc.com"

</div>

<span data-ttu-id="739fe-125">Per informazioni dettagliate, vedere gli argomenti della Guida relativi al cmdlet [New-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone) e al cmdlet [Set-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone) .</span><span class="sxs-lookup"><span data-stu-id="739fe-125">For details, see the Help topics for the [New-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone) cmdlet and the [Set-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

