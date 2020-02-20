---
title: "Lync Server 2013: impostazione dei criteri utente per l'archiviazione in Lync Server"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up user policies for Archiving in Lync Server
ms:assetid: 22d6cc76-6b5c-4a8c-bb8a-7996450ec085
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204742(v=OCS.15)
ms:contentKeyID: 48183626
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 78a30684619a67fc1e48f3692a2bc40ccae55b14
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142782"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-user-policies-for-archiving-in-lync-server-2013"></a><span data-ttu-id="07add-102">Configurazione dei criteri utente per l'archiviazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="07add-102">Setting up user policies for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="07add-103">_**Ultimo argomento modificato:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="07add-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="07add-104">L'abilitazione o disabilitazione dell'archiviazione per utenti specifici ospitati in Lync Server 2013 richiede la creazione e la configurazione di uno o più criteri utente e l'applicazione del criterio appropriato a specifici utenti o gruppi di utenti.</span><span class="sxs-lookup"><span data-stu-id="07add-104">Enabling or disabling Archiving for specific users homed on Lync Server 2013 requires creating and configuring one or more user policies, and then applying the appropriate policy to specific users or user groups.</span></span> <span data-ttu-id="07add-105">I criteri utente hanno la precedenza sul sito e sui criteri globali, ma solo per gli utenti ospitati in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="07add-105">User policies override site and global policies, but only for users homed on Lync Server 2013.</span></span>

<span data-ttu-id="07add-106">Gli utenti sono sempre ospitati in Lync Server.</span><span class="sxs-lookup"><span data-stu-id="07add-106">Users are always homed in Lync Server.</span></span> <span data-ttu-id="07add-107">Se l'integrazione di Microsoft Exchange è abilitata, gli utenti le cui cassette postali si trovano in Microsoft Exchange Server 2013 non è necessario che i criteri di archiviazione vengano gestiti in Lync Server.</span><span class="sxs-lookup"><span data-stu-id="07add-107">If Microsoft Exchange integration is enabled, users whose mailboxes are in Microsoft Exchange Server 2013 don’t need to have their Archiving policies in Lync Server managed.</span></span> <span data-ttu-id="07add-108">Questi utenti con archiviazione verranno gestiti tramite il blocco sul posto di Exchange.</span><span class="sxs-lookup"><span data-stu-id="07add-108">These users with Archiving will be managed by Exchange In-Place Hold.</span></span>

<span data-ttu-id="07add-109">Per informazioni dettagliate sul funzionamento dei criteri di archiviazione, inclusa la gerarchia per i criteri globali, sito e utente, vedere [How Archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) nella documentazione relativa alla pianificazione, alla distribuzione o alla documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="07add-109">For details about how Archiving policies work, including the hierarchy for global, site, and user policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="07add-110">Se è stata abilitata l'integrazione di Microsoft Exchange per la distribuzione, i criteri di conservazione sul posto di Exchange controllano se l'archiviazione è abilitata per gli utenti ospitati in Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="07add-110">If you enabled Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange 2013.</span></span> <span data-ttu-id="07add-111">L'archiviazione per questi utenti richiede che abbiano le cassette postali archiviate sul posto.</span><span class="sxs-lookup"><span data-stu-id="07add-111">Archiving for these users requires that they have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="07add-112">Per informazioni dettagliate, vedere <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">impostazione dei criteri per l'archiviazione in Lync server 2013 quando si utilizza l'integrazione di Exchange Server</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="07add-112">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="07add-113">Specificare tutte le opzioni appropriate nelle configurazioni di archiviazione prima di abilitare l'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="07add-113">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span> <span data-ttu-id="07add-114">Per ulteriori informazioni, vedere <A href="lync-server-2013-configuring-archiving-options.md">configurazione delle opzioni di archiviazione in Lync Server 2013</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="07add-114">For details, see <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving options in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="07add-115">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="07add-115">In This Section</span></span>

  - [<span data-ttu-id="07add-116">Creazione e configurazione dei criteri utente per l'archiviazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="07add-116">Creating and configuring user policies for Archiving in Lync Server 2013</span></span>](lync-server-2013-creating-and-configuring-user-policies-for-archiving-in-lync-server.md)

  - [<span data-ttu-id="07add-117">Applicazione di un criterio di archiviazione di Lync Server a un utente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="07add-117">Applying a Lync Server Archiving policy to a user in Lync Server 2013</span></span>](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

