---
title: 'Lync Server 2013: creare o modificare un oggetto contatto telefonico di area comune'
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
ms.openlocfilehash: 418001642f387caf67277f408d4eb19109c98936
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035414"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-common-area-phone-contact-object-in-lync-server-2013"></a><span data-ttu-id="2607f-102">Creare o modificare un oggetto contatto telefonico di area comune in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2607f-102">Create or modify a common area phone Contact object in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2607f-103">_**Ultimo argomento modificato:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="2607f-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="2607f-104">Per creare oggetti contatto di servizi di dominio Active Directory per tutti i telefoni delle aree comuni, utilizzare il cmdlet **New-CsCommonAreaPhone** .</span><span class="sxs-lookup"><span data-stu-id="2607f-104">To create Active Directory Domain Services contact objects for all your common area phones, use the **New-CsCommonAreaPhone** cmdlet.</span></span> <span data-ttu-id="2607f-105">Questo cmdlet può creare nuovi oggetti contatto per l'utilizzo con i telefoni delle aree comuni oppure può associare gli oggetti contatto esistenti a un nuovo telefono di area comune.</span><span class="sxs-lookup"><span data-stu-id="2607f-105">This cmdlet can either create new contact objects for use with common area phones, or it can associate existing contact objects with a new common area phone.</span></span> <span data-ttu-id="2607f-106">Per modificare le proprietà degli oggetti contatto associati ai telefoni delle aree comuni, utilizzare il cmdlet **Set-CsCommonAreaPhone** .</span><span class="sxs-lookup"><span data-stu-id="2607f-106">To modify the properties of the contact objects associated with common area phones, use the **Set-CsCommonAreaPhone** cmdlet.</span></span> <span data-ttu-id="2607f-107">I parametri facoltativi per **Set-CsCommonAreaPhone** consentono di modificare gli elementi, ad esempio il nome visualizzato di Active Directory del contatto o l'URI (Uniform Resource Identifier) di linea associato al telefono e di abilitare e disabilitare l'account da utilizzare con Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2607f-107">Optional parameters for **Set-CsCommonAreaPhone** enable you to change items, such as the contact’s Active Directory display name or the line Uniform Resource Identifier (URI) associated with the phone, and enable and disable the account for use with Lync Server.</span></span> <span data-ttu-id="2607f-108">Per informazioni dettagliate su tutte le modifiche disponibili, vedere la sezione Parameters in [Set-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone).</span><span class="sxs-lookup"><span data-stu-id="2607f-108">For details about all the available modifications, see the Parameters section at [Set-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone).</span></span> <span data-ttu-id="2607f-109">Per informazioni dettagliate sui parametri **New-CsCommonAreaPhone** , vedere [New-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone).</span><span class="sxs-lookup"><span data-stu-id="2607f-109">For details about **New-CsCommonAreaPhone** parameters, see [New-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone).</span></span>

<span data-ttu-id="2607f-110">È possibile eseguire questi due cmdlet da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2607f-110">You can run these two cmdlets from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="2607f-111">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 using Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="2607f-111">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>


<div>

## <a name="creating-a-common-area-phone-contact-object"></a><span data-ttu-id="2607f-112">Creazione di un oggetto contatto telefonico di area comune</span><span class="sxs-lookup"><span data-stu-id="2607f-112">Creating a common area phone contact object</span></span>

  - <span data-ttu-id="2607f-113">Per creare un nuovo oggetto contatto telefonico per le aree comuni, utilizzare il cmdlet **New-CsCommonAreaPhone** .</span><span class="sxs-lookup"><span data-stu-id="2607f-113">To create a new common area phone contact object, use the **New-CsCommonAreaPhone** cmdlet.</span></span> <span data-ttu-id="2607f-114">Quando si crea un oggetto contatto, è necessario fornire almeno le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2607f-114">At a minimum, you must supply the following information when creating a contact object:</span></span>
    
      - <span data-ttu-id="2607f-115">**LineUri**: il numero di telefono assegnato al telefono di area comune.</span><span class="sxs-lookup"><span data-stu-id="2607f-115">**LineUri**: The telephone number assigned to the common area phone.</span></span> <span data-ttu-id="2607f-116">Tenere presente che è necessario utilizzare il formato E. 164 quando si specifica il numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="2607f-116">Note that you must use the E.164 format when specifying the phone number.</span></span>
    
      - <span data-ttu-id="2607f-117">**RegistrarPool**: il nome di dominio completo (FQDN) del pool di registrazione che ospiterà l'oggetto contatto.</span><span class="sxs-lookup"><span data-stu-id="2607f-117">**RegistrarPool**: The fully qualified domain name (FQDN) of the Registrar pool that will host the contact object.</span></span>
    
      - <span data-ttu-id="2607f-118">**Ou**: nome distinto del contenitore di Active Directory in cui verrà creato l'oggetto contatto.</span><span class="sxs-lookup"><span data-stu-id="2607f-118">**OU**: Distinguished name of the Active Directory container where the contact object will be created.</span></span>
    
    <span data-ttu-id="2607f-119">È inoltre consigliabile fornire un nome visualizzato di servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2607f-119">We also recommend that you provide an Active Directory Domain Services display name.</span></span> <span data-ttu-id="2607f-120">In caso contrario, sarà necessario utilizzare un GUID per specificare l'identità del telefono.</span><span class="sxs-lookup"><span data-stu-id="2607f-120">Otherwise, you will need to use a GUID to specify the phone Identity.</span></span> <span data-ttu-id="2607f-121">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="2607f-121">For example:</span></span>
    
        New-CsCommonAreaPhone -LineUri "tel:+12065551219" -RegistrarPool "atl-cs-001.litwareinc.com" -OU "OU=Phones,dc=litwareinc,dc=com" -DisplayName "Lobby"

</div>

<div>

## <a name="modifying-a-common-area-phone-contact-object"></a><span data-ttu-id="2607f-122">Modifica di un oggetto contatto telefonico di area comune</span><span class="sxs-lookup"><span data-stu-id="2607f-122">Modifying a common area phone contact object</span></span>

  - <span data-ttu-id="2607f-123">Per modificare le proprietà di un telefono di area comune esistente, utilizzare il cmdlet **Set-CsCommonAreaPhone** .</span><span class="sxs-lookup"><span data-stu-id="2607f-123">To modify the properties of an existing common area phone, contact object use the **Set-CsCommonAreaPhone** cmdlet.</span></span> <span data-ttu-id="2607f-124">Ad esempio, questo comando configura l'indirizzo SIP per il telefono di area comune con la lobby DisplayName:</span><span class="sxs-lookup"><span data-stu-id="2607f-124">For example, this command configures the SIP address for the common area phone with the DisplayName Lobby:</span></span>
    
        Set-CsCommonAreaPhone -Identity "Lobby" -SipAddress "sip:lobby@litwareinc.com"

</div>

<span data-ttu-id="2607f-125">Per informazioni dettagliate, vedere gli argomenti della Guida per il cmdlet [New-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone) e il cmdlet [Set-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone) .</span><span class="sxs-lookup"><span data-stu-id="2607f-125">For details, see the Help topics for the [New-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone) cmdlet and the [Set-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

