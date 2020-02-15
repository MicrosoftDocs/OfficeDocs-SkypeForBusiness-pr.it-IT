---
title: 'Lync Server 2013: telefoni delle aree comuni'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Common area phones
ms:assetid: d63bb3de-154e-4347-9251-9fa94e7d593a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994076(v=OCS.15)
ms:contentKeyID: 51803987
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 736aa12c9de027aa485cfc89a6f5cd820a460833
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045818"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="common-area-phones-in-lync-server-2013"></a><span data-ttu-id="02688-102">Telefoni delle aree comuni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02688-102">Common area phones in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="02688-103">_**Ultimo argomento modificato:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="02688-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="02688-104">I telefoni delle aree comuni sono telefoni IP che non sono associati a un singolo utente.</span><span class="sxs-lookup"><span data-stu-id="02688-104">Common area phones are IP phones that are not associated with an individual user.</span></span> <span data-ttu-id="02688-105">Invece di trovarsi nell'ufficio di qualcuno, i telefoni delle aree comuni si trovano tipicamente nelle lobby degli edifici, nelle caffetterie, nei salotti dei dipendenti, nelle sale riunioni e in altre posizioni in cui è probabile che si riunisca un numero elevato di persone.</span><span class="sxs-lookup"><span data-stu-id="02688-105">Instead of being located in someone’s office, common area phones are typically located in building lobbies, cafeterias, employee lounges, meeting rooms, and other locations where a large number of people are likely to gather.</span></span> <span data-ttu-id="02688-106">A differenza di altri telefoni in Lync Server, che in genere vengono gestiti utilizzando criteri vocali e dial plan assegnati a singoli utenti, i telefoni delle aree comuni non dispongono di singoli utenti assegnati.</span><span class="sxs-lookup"><span data-stu-id="02688-106">Unlike other phones in Lync Server, which are typically maintained by using voice policies and dial plans that are assigned to individual users, common area phones do not have individual users assigned to them.</span></span> <span data-ttu-id="02688-107">Questo significa che deve essere gestito in modo diverso rispetto agli altri telefoni.</span><span class="sxs-lookup"><span data-stu-id="02688-107">This means that they must be managed differently than your other phones.</span></span>

<span data-ttu-id="02688-108">Per gestire i telefoni delle aree comuni, è possibile creare oggetti contatto di servizi di dominio Active Directory per tutti i telefoni delle aree comuni che, come gli account utente, possono essere assegnati a criteri e piani vocali.</span><span class="sxs-lookup"><span data-stu-id="02688-108">To manage common area phones, you create Active Directory Domain Services contact objects for all your common area phones that, like user accounts, can be assigned policies and voice plans.</span></span> <span data-ttu-id="02688-109">Questo approccio consente di mantenere il controllo sui telefoni delle aree comuni, anche se tali telefoni non sono associati a un singolo utente.</span><span class="sxs-lookup"><span data-stu-id="02688-109">This approach enables you to maintain control over common area phones, even though those phones are not associated with an individual user.</span></span>

<span data-ttu-id="02688-110">Utilizzare gli argomenti in questa sezione per informazioni su come creare gli oggetti contatto per i telefoni delle aree comuni, modificarli ed eliminarli e configurare e visualizzare le informazioni di configurazione relative ai telefoni delle aree comuni nella distribuzione.</span><span class="sxs-lookup"><span data-stu-id="02688-110">Use the topics in this section to learn how to create contact objects for common area phones, modify and delete them, and configure and view configuration information about the common area phones in your deployment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="02688-111">Sono disponibili tre opzioni per i telefoni delle aree comuni: Aastra 6721ip common area Phone, HP 4110 IP Phone e The Polycom CX500 IP common area Phone.</span><span class="sxs-lookup"><span data-stu-id="02688-111">You have three options for common area phones: the Aastra 6721ip common area phone, the HP 4110 IP Phone, and the Polycom CX500 IP common area phone.</span></span> <span data-ttu-id="02688-112">Polycom CX3000 IP Conferencing Phone è un'altra variante del telefono di area comune.</span><span class="sxs-lookup"><span data-stu-id="02688-112">The Polycom CX3000 IP conferencing phone is another variant common area phone.</span></span> <span data-ttu-id="02688-113">Tuttavia, è progettato per essere utilizzato nelle sale conferenze.</span><span class="sxs-lookup"><span data-stu-id="02688-113">However, it is intended for use in conference rooms.</span></span> <span data-ttu-id="02688-114">Per informazioni dettagliate sui telefoni delle aree comuni, vedere la sezione telefoni delle aree comuni per la <A href="http://technet.microsoft.com/library/gg398958(v=ocs.14).aspx">scelta dei nuovi dispositivi</A>.</span><span class="sxs-lookup"><span data-stu-id="02688-114">For details about common area phones, see the Common Area Phones section of <A href="http://technet.microsoft.com/library/gg398958(v=ocs.14).aspx">Choosing New Devices</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="02688-115">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="02688-115">In This Section</span></span>

  - [<span data-ttu-id="02688-116">Visualizzare le informazioni sui telefoni delle aree comuni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02688-116">View common area phone information in Lync Server 2013</span></span>](lync-server-2013-view-common-area-phone-information.md)

  - [<span data-ttu-id="02688-117">Creare o modificare un oggetto contatto telefonico di area comune in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02688-117">Create or modify a common area phone Contact object in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-common-area-phone-contact-object.md)

  - [<span data-ttu-id="02688-118">Abilitare o disabilitare l'hot desking in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02688-118">Enable or disable hot desking in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-hot-desking.md)

  - [<span data-ttu-id="02688-119">Eliminare un oggetto contatto telefonico di area comune in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02688-119">Delete a common area phone Contact object in Lync Server 2013</span></span>](lync-server-2013-delete-a-common-area-phone-contact-object.md)

  - [<span data-ttu-id="02688-120">Assegnare criteri in Lync Server 2013 a un telefono di area comune</span><span class="sxs-lookup"><span data-stu-id="02688-120">Assign policies in Lync Server 2013 to a common area phone</span></span>](lync-server-2013-assign-policies-to-a-common-area-phone.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

