---
title: 'Lync Server 2013: Gestione di oggetti contatto di Exchange ospitati'
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
ms.openlocfilehash: c63e9952abab192e7f8f4a71e97a660d2798d3b9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739066"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-contact-object-management-in-lync-server-2013"></a><span data-ttu-id="48172-102">Gestione di oggetti contatto di Exchange ospitati in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="48172-102">Hosted Exchange Contact object management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="48172-103">_**Argomento Ultima modifica:** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="48172-103">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="48172-104">È necessario configurare un oggetto contatto per ogni numero di operatore automatico e numero di accesso del Sottoscrittore nella distribuzione tra più locali.</span><span class="sxs-lookup"><span data-stu-id="48172-104">You need to configure a Contact object for each auto-attendant number and subscriber access number in your cross-premises deployment.</span></span>

<span data-ttu-id="48172-105">Per l'integrazione con la messaggistica unificata di Exchange ospitata, OcsUmUtil. exe non può essere usato per gestire gli oggetti contatto, perché dipende dalle impostazioni della messaggistica unificata di Exchange in Active Directory.</span><span class="sxs-lookup"><span data-stu-id="48172-105">For integration with hosted Exchange UM, ocsumutil.exe cannot be used to manage Contact objects, because it depends on Active Directory Exchange UM settings.</span></span> <span data-ttu-id="48172-106">In una distribuzione interlocale Lync Server 2013 e la messaggistica unificata di Exchange ospitati vengono installati in foreste separate senza attendibilità.</span><span class="sxs-lookup"><span data-stu-id="48172-106">In a cross-premises deployment, Lync Server 2013 and hosted Exchange UM are installed in separate forests with no trust between them.</span></span> <span data-ttu-id="48172-107">Per motivi di sicurezza, gli amministratori di Lync Server 2013 non hanno accesso diretto alle impostazioni di Active Directory UM di Exchange.</span><span class="sxs-lookup"><span data-stu-id="48172-107">For security reasons, Lync Server 2013 administrators have no direct access to Exchange UM Active Directory settings.</span></span> <span data-ttu-id="48172-108">Di conseguenza, Lync Server 2013 offre un modello diverso per la gestione degli oggetti contatto in uno *spazio di indirizzi SIP condiviso* accessibile sia a lync Server 2013 che al servizio di messaggistica unificata di Exchange ospitati.</span><span class="sxs-lookup"><span data-stu-id="48172-108">As a result, Lync Server 2013 provides a different model for managing Contact objects in a *shared SIP address space* that is accessible to both Lync Server 2013 and the hosted Exchange UM service.</span></span>

<div>

## <a name="hosted-contact-object-workflow"></a><span data-ttu-id="48172-109">Flusso di lavoro di oggetti contatto ospitati</span><span class="sxs-lookup"><span data-stu-id="48172-109">Hosted Contact Object Workflow</span></span>

<span data-ttu-id="48172-110">Di seguito sono riportate le procedure generali per l'uso dell'amministratore del tenant ospitante di Exchange per la gestione degli oggetti contatto:</span><span class="sxs-lookup"><span data-stu-id="48172-110">The following are the general steps for working with your hosted Exchange tenant administrator to manage contact objects:</span></span>

1.  <span data-ttu-id="48172-111">L'amministratore di Exchange richiede i numeri di telefono per gli oggetti contatto di messaggistica unificata di Exchange e l'operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="48172-111">The Exchange administrator requests phone numbers for the Exchange UM subscriber access and auto-attendant Contact objects.</span></span>

2.  <span data-ttu-id="48172-112">L'amministratore di Lync Server 2013 crea un oggetto contatto per ogni numero di telefono e assegna un criterio di segreteria telefonica ospitata a ogni oggetto contatto.</span><span class="sxs-lookup"><span data-stu-id="48172-112">The Lync Server 2013 administrator creates a Contact object for each phone number and assigns a hosted voice mail policy to each Contact object.</span></span>

3.  <span data-ttu-id="48172-113">L'amministratore di Lync Server 2013 fornisce i numeri di telefono all'amministratore di Exchange.</span><span class="sxs-lookup"><span data-stu-id="48172-113">The Lync Server 2013 administrator provides the phone numbers to the Exchange administrator.</span></span>

4.  <span data-ttu-id="48172-114">L'amministratore di Exchange assegna i numeri di telefono ai dial plan di messaggistica unificata di Exchange appropriati per gli operatori automatici e l'accesso sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="48172-114">The Exchange administrator assigns the phone numbers to appropriate Exchange UM dial plans for auto attendants and subscriber access.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="48172-115">Non è necessario configurare le impostazioni di dial plan di Lync Server 2013 sugli oggetti contatto in quanto esiste con distribuzioni locali.</span><span class="sxs-lookup"><span data-stu-id="48172-115">There is no need to configure any Lync Server 2013 dial plan settings on the Contact objects as there is with on-premises deployments.</span></span>



</div>

</div>

<div>

## <a name="configuring-hosted-contact-objects"></a><span data-ttu-id="48172-116">Configurazione di oggetti contatto ospitati</span><span class="sxs-lookup"><span data-stu-id="48172-116">Configuring Hosted Contact Objects</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="48172-117">Prima che gli oggetti contatto di Lync Server 2013 possano essere abilitati per la messaggistica unificata di Exchange ospitata, è necessario distribuire un criterio di segreteria telefonica ospitata.</span><span class="sxs-lookup"><span data-stu-id="48172-117">Before Lync Server 2013 Contact objects can be enabled for hosted Exchange UM, a hosted voice mail policy that applies to them must be deployed.</span></span> <span data-ttu-id="48172-118">Il criterio può essere di ambito globale, a livello di sito o per utente, purché si applichi all'oggetto contatto che si vuole abilitare.</span><span class="sxs-lookup"><span data-stu-id="48172-118">The policy can be of global, site-level, or per-user scope, as long as it applies to the contact object you want to enable.</span></span> <span data-ttu-id="48172-119">Per informazioni dettagliate, vedere Criteri per la segreteria <A href="lync-server-2013-hosted-voice-mail-policies.md">telefonica ospitati in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="48172-119">For details, see <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted voice mail policies in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="48172-120">Per configurare gli oggetti di contatto per l'operatore automatico ospitati e i contatti degli abbonati in una distribuzione tra più locali, è necessario usare i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="48172-120">To configure hosted auto-attendant and subscriber access Contact objects in a cross-premises deployment, you must use the following cmdlets:</span></span>

  - <span data-ttu-id="48172-121">**New-CsExUmContact** crea un nuovo oggetto contatto per la messaggistica unificata ospitata.</span><span class="sxs-lookup"><span data-stu-id="48172-121">**New-CsExUmContact** creates a new Contact object for hosted UM.</span></span>

  - <span data-ttu-id="48172-122">**Set-CsExUmContact** modifica un oggetto contatto esistente per la messaggistica unificata di Exchange ospitata.</span><span class="sxs-lookup"><span data-stu-id="48172-122">**Set-CsExUmContact** modifies an existing Contact object for hosted Exchange UM.</span></span>

<span data-ttu-id="48172-123">L'esempio seguente crea un oggetto contatto di operatore automatico:</span><span class="sxs-lookup"><span data-stu-id="48172-123">The following example creates an auto-attendant Contact object:</span></span>

    New-CsExUmContact -SipAddress sip:exumaa1@fabrikam.com -RegistrarPool RedmondPool.litwareinc.com -OU "OU=ExUmContacts,DC=litwareinc,DC=com" -DisplayNumber 2065559876 -AutoAttendant $True

<span data-ttu-id="48172-124">Questo esempio crea un nuovo oggetto contatto di messaggistica unificata di Exchange con l'indirizzo SIP sip:exumaa1@fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="48172-124">This example creates a new Exchange UM Contact object with the SIP address sip:exumaa1@fabrikam.com.</span></span> <span data-ttu-id="48172-125">Il nome del pool in cui è in uso il servizio di registrazione di Lync Server 2013 è RedmondPool.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="48172-125">The name of the pool where the Lync Server 2013 Registrar service is running is RedmondPool.litwareinc.com.</span></span> <span data-ttu-id="48172-126">L'unità organizzativa di Active Directory in cui verranno archiviate le informazioni è OU = ExUmContacts, DC = litwareinc, DC = com.</span><span class="sxs-lookup"><span data-stu-id="48172-126">The Active Directory organizational unit where this information will be stored is OU=ExUmContacts,DC=litwareinc,DC=com.</span></span> <span data-ttu-id="48172-127">Il numero di telefono dell'oggetto contatto è 2065554567.</span><span class="sxs-lookup"><span data-stu-id="48172-127">The phone number of the Contact object is 2065554567.</span></span> <span data-ttu-id="48172-128">Il parametro facoltativo-AutoAttendant $True specifica che questo oggetto è un oggetto contatto di operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="48172-128">The optional -AutoAttendant $True parameter specifies that this object is an auto-attendant Contact object.</span></span> <span data-ttu-id="48172-129">L'impostazione del parametro-AutoAttendant su false (impostazione predefinita) specifica un oggetto contatto di accesso del Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="48172-129">Setting the -AutoAttendant parameter to False (the default) specifies a subscriber access Contact object.</span></span>

<span data-ttu-id="48172-130">Per informazioni dettagliate sui cmdlet New-CsExUmContact e Set-CsExUmContact, vedere la documentazione di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="48172-130">For details about the New-CsExUmContact and Set-CsExUmContact cmdlets, see the Lync Server Management Shell documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

