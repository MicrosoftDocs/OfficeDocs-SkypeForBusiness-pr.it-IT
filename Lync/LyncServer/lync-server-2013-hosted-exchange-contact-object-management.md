---
title: 'Lync Server 2013: gestione di oggetti contatto di Exchange ospitati'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted Exchange Contact object management
ms:assetid: eead9d76-bc4f-4c1c-9779-683cb7a88410
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412978(v=OCS.15)
ms:contentKeyID: 48185748
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 15abe045504653fe7a64d8bc6ef82af3ac87ba37
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42047350"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-contact-object-management-in-lync-server-2013"></a><span data-ttu-id="07ec7-102">Gestione di oggetti contatto di Exchange ospitati in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="07ec7-102">Hosted Exchange Contact object management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="07ec7-103">_**Ultimo argomento modificato:** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="07ec7-103">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="07ec7-104">È necessario configurare un oggetto contatto per ogni numero di operatore automatico e per ogni numero di accesso sottoscrittore per una distribuzione su più computer.</span><span class="sxs-lookup"><span data-stu-id="07ec7-104">You need to configure a Contact object for each auto-attendant number and subscriber access number in your cross-premises deployment.</span></span>

<span data-ttu-id="07ec7-105">Per l'integrazione con la messaggistica unificata di Exchange ospitata, non è possibile utilizzare ocsumutil.exe per gestire oggetti contatto, perché questa utilità dipende dalle impostazioni di Active Directory della messaggistica unificata di Exchange.</span><span class="sxs-lookup"><span data-stu-id="07ec7-105">For integration with hosted Exchange UM, ocsumutil.exe cannot be used to manage Contact objects, because it depends on Active Directory Exchange UM settings.</span></span> <span data-ttu-id="07ec7-106">In una distribuzione cross-premise, Lync Server 2013 e la messaggistica unificata di Exchange ospitata vengono installate in foreste separate senza alcuna relazione di trust tra di essi.</span><span class="sxs-lookup"><span data-stu-id="07ec7-106">In a cross-premises deployment, Lync Server 2013 and hosted Exchange UM are installed in separate forests with no trust between them.</span></span> <span data-ttu-id="07ec7-107">Per motivi di sicurezza, gli amministratori di Lync Server 2013 non dispongono di accesso diretto alle impostazioni di Active Directory di messaggistica unificata di Exchange.</span><span class="sxs-lookup"><span data-stu-id="07ec7-107">For security reasons, Lync Server 2013 administrators have no direct access to Exchange UM Active Directory settings.</span></span> <span data-ttu-id="07ec7-108">Di conseguenza, Lync Server 2013 fornisce un modello diverso per la gestione degli oggetti contatto in uno *spazio di indirizzi SIP condiviso* accessibile sia per lync Server 2013 che per il servizio di messaggistica unificata di Exchange ospitato.</span><span class="sxs-lookup"><span data-stu-id="07ec7-108">As a result, Lync Server 2013 provides a different model for managing Contact objects in a *shared SIP address space* that is accessible to both Lync Server 2013 and the hosted Exchange UM service.</span></span>

<div>

## <a name="hosted-contact-object-workflow"></a><span data-ttu-id="07ec7-109">Flusso di lavoro degli oggetti contatto ospitati</span><span class="sxs-lookup"><span data-stu-id="07ec7-109">Hosted Contact Object Workflow</span></span>

<span data-ttu-id="07ec7-110">Di seguito sono riportate le operazioni generali per collaborare con l'amministratore del tenant di Exchange condiviso nella gestione degli oggetti contatto:</span><span class="sxs-lookup"><span data-stu-id="07ec7-110">The following are the general steps for working with your hosted Exchange tenant administrator to manage contact objects:</span></span>

1.  <span data-ttu-id="07ec7-111">L'amministratore di Exchange richiede i numero di telefono per gli oggetti contatto di accesso di sottoscrittori e di operatore automatico della messaggistica unificata di Exchange.</span><span class="sxs-lookup"><span data-stu-id="07ec7-111">The Exchange administrator requests phone numbers for the Exchange UM subscriber access and auto-attendant Contact objects.</span></span>

2.  <span data-ttu-id="07ec7-112">L'amministratore di Lync Server 2013 crea un oggetto contatto per ogni numero di telefono e assegna un criterio di segreteria telefonica ospitata a ogni oggetto contatto.</span><span class="sxs-lookup"><span data-stu-id="07ec7-112">The Lync Server 2013 administrator creates a Contact object for each phone number and assigns a hosted voice mail policy to each Contact object.</span></span>

3.  <span data-ttu-id="07ec7-113">L'amministratore di Lync Server 2013 fornisce i numeri di telefono all'amministratore di Exchange.</span><span class="sxs-lookup"><span data-stu-id="07ec7-113">The Lync Server 2013 administrator provides the phone numbers to the Exchange administrator.</span></span>

4.  <span data-ttu-id="07ec7-114">L'amministratore di Exchange assegna i numeri di telefono ai dial plan della messaggistica unificata di Exchange per operatori automatici e per l'accesso di sottoscrittori.</span><span class="sxs-lookup"><span data-stu-id="07ec7-114">The Exchange administrator assigns the phone numbers to appropriate Exchange UM dial plans for auto attendants and subscriber access.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="07ec7-115">Non è necessario configurare le impostazioni del dial plan di Lync Server 2013 sugli oggetti contatto come nelle distribuzioni locali.</span><span class="sxs-lookup"><span data-stu-id="07ec7-115">There is no need to configure any Lync Server 2013 dial plan settings on the Contact objects as there is with on-premises deployments.</span></span>



</div>

</div>

<div>

## <a name="configuring-hosted-contact-objects"></a><span data-ttu-id="07ec7-116">Configurazione di oggetti contatto ospitati</span><span class="sxs-lookup"><span data-stu-id="07ec7-116">Configuring Hosted Contact Objects</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="07ec7-117">Prima di poter abilitare gli oggetti contatto di Lync Server 2013 per la messaggistica unificata di Exchange ospitata, è necessario distribuire un criterio di segreteria telefonica ospitata.</span><span class="sxs-lookup"><span data-stu-id="07ec7-117">Before Lync Server 2013 Contact objects can be enabled for hosted Exchange UM, a hosted voice mail policy that applies to them must be deployed.</span></span> <span data-ttu-id="07ec7-118">Il criterio può essere di ambito globale, a livello di sito o per utente, purché applicato all'oggetto contatto che si desidera abilitare.</span><span class="sxs-lookup"><span data-stu-id="07ec7-118">The policy can be of global, site-level, or per-user scope, as long as it applies to the contact object you want to enable.</span></span> <span data-ttu-id="07ec7-119">Per ulteriori informazioni, vedere <A href="lync-server-2013-hosted-voice-mail-policies.md">criteri di segreteria telefonica ospitata in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="07ec7-119">For details, see <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted voice mail policies in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="07ec7-120">Per configurare oggetti contatto di accesso dei sottoscrittori e di operatori automatici ospitati in una distribuzione tra più uffici, è necessario utilizzare i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="07ec7-120">To configure hosted auto-attendant and subscriber access Contact objects in a cross-premises deployment, you must use the following cmdlets:</span></span>

  - <span data-ttu-id="07ec7-121">**New-CsExUmContact** crea un nuovo oggetto contatto per la messaggistica unificata ospitata.</span><span class="sxs-lookup"><span data-stu-id="07ec7-121">**New-CsExUmContact** creates a new Contact object for hosted UM.</span></span>

  - <span data-ttu-id="07ec7-122">**Set-CsExUmContact** modifica un contatto oggetto esistente per la messaggistica unificata di Exchange ospitata.</span><span class="sxs-lookup"><span data-stu-id="07ec7-122">**Set-CsExUmContact** modifies an existing Contact object for hosted Exchange UM.</span></span>

<span data-ttu-id="07ec7-123">Nell'esempio seguente viene creato un oggetto contatto di operatore automatico:</span><span class="sxs-lookup"><span data-stu-id="07ec7-123">The following example creates an auto-attendant Contact object:</span></span>

    New-CsExUmContact -SipAddress sip:exumaa1@fabrikam.com -RegistrarPool RedmondPool.litwareinc.com -OU "OU=ExUmContacts,DC=litwareinc,DC=com" -DisplayNumber 2065559876 -AutoAttendant $True

<span data-ttu-id="07ec7-124">In questo esempio viene creato un nuovo oggetto contatto della messaggistica unificata di Exchange, con l'indirizzo SIP sip:exumaa1@fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="07ec7-124">This example creates a new Exchange UM Contact object with the SIP address sip:exumaa1@fabrikam.com.</span></span> <span data-ttu-id="07ec7-125">Il nome del pool in cui è in esecuzione il servizio di registrazione di Lync Server 2013 è RedmondPool.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="07ec7-125">The name of the pool where the Lync Server 2013 Registrar service is running is RedmondPool.litwareinc.com.</span></span> <span data-ttu-id="07ec7-126">L'unità organizzativa in cui verranno archiviate queste informazioni è OU=ExUmContacts,DC=litwareinc,DC=com.</span><span class="sxs-lookup"><span data-stu-id="07ec7-126">The Active Directory organizational unit where this information will be stored is OU=ExUmContacts,DC=litwareinc,DC=com.</span></span> <span data-ttu-id="07ec7-127">Il numero di telefono dell'oggetto contatto è 2065554567.</span><span class="sxs-lookup"><span data-stu-id="07ec7-127">The phone number of the Contact object is 2065554567.</span></span> <span data-ttu-id="07ec7-128">Il parametro facoltativo -AutoAttendant $True specifica che si tratta di un oggetto contatto di operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="07ec7-128">The optional -AutoAttendant $True parameter specifies that this object is an auto-attendant Contact object.</span></span> <span data-ttu-id="07ec7-129">Se il parametro -AutoAttendant è impostato su False (impostazione predefinita) specifica un oggetto contatto di accesso di sottoscrittori.</span><span class="sxs-lookup"><span data-stu-id="07ec7-129">Setting the -AutoAttendant parameter to False (the default) specifies a subscriber access Contact object.</span></span>

<span data-ttu-id="07ec7-130">Per informazioni dettagliate sui cmdlet New-CsExUmContact e Set-CsExUmContact, vedere la documentazione di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="07ec7-130">For details about the New-CsExUmContact and Set-CsExUmContact cmdlets, see the Lync Server Management Shell documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

