---
title: 'Lync Server 2013: impostazione dei criteri di archiviazione per gli utenti'
description: 'Lync Server 2013: impostazione dei criteri di archiviazione per gli utenti.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up Archiving policies for users
ms:assetid: 1bbb45df-0590-4c66-9d65-d25526f57790
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204722(v=OCS.15)
ms:contentKeyID: 48183549
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c18a15c1a0611f49a6fd9a4983f3ce87104332e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559522"
---
# <a name="setting-up-archiving-policies-for-users-in-lync-server-2013"></a><span data-ttu-id="3de46-103">Configurazione dei criteri di archiviazione per gli utenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3de46-103">Setting up Archiving policies for users in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3de46-104">_**Ultimo argomento modificato:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="3de46-104">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="3de46-105">L'archiviazione può essere abilitata o disabilitata per utenti specifici creando e configurando criteri di archiviazione per gli utenti, quindi applicando i criteri a utenti o a gruppi di utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="3de46-105">You can enable or disable Archiving for specific users by creating and configuring an Archiving policy for users, and then applying the policy to specific users or user groups.</span></span> <span data-ttu-id="3de46-106">I criteri utente sostituiscono eventuali criteri globali o sito.</span><span class="sxs-lookup"><span data-stu-id="3de46-106">User policies override any global policy or site policies.</span></span> <span data-ttu-id="3de46-107">I criteri di archiviazione si applicano solo se non si utilizza l'integrazione di Microsoft Exchange o, se si utilizza l'integrazione di Microsoft Exchange, ma alcuni utenti non sono ospitati in Exchange 2013 e le relative cassette postali vengono inserite In-Place.</span><span class="sxs-lookup"><span data-stu-id="3de46-107">Archiving policies only apply if you do not use Microsoft Exchange integration or, if you do use Microsoft Exchange integration, but have some users who are not homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span>

<span data-ttu-id="3de46-108">Per informazioni dettagliate sul funzionamento dei criteri di archiviazione, inclusa la gerarchia per i criteri globali, sito e utente, vedere [How Archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) Planning documentation, Deployment documentation, or Operations Documentation.</span><span class="sxs-lookup"><span data-stu-id="3de46-108">For details about how Archiving policies work, including the hierarchy for global, site, and user policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3de46-109">Se si Abilita l'integrazione di Microsoft Exchange per la distribuzione, i criteri di Exchange In-Place conservazione determinano se l'archiviazione è abilitata per gli utenti ospitati in Exchange 2013 e le relative cassette postali vengono inserite In-Place blocco.</span><span class="sxs-lookup"><span data-stu-id="3de46-109">If you enable Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="3de46-110">Per informazioni dettagliate, vedere <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">impostazione dei criteri per l'archiviazione in Lync server 2013 quando si utilizza l'integrazione di Exchange Server</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="3de46-110">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="3de46-111">È necessario specificare tutte le opzioni appropriate nelle configurazioni di archiviazione prima di abilitare l'archiviazione di comunicazioni interne o esterne nei criteri di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="3de46-111">You should specify all appropriate options in the Archiving configurations before enabling Archiving of internal or external communications in the Archiving policies.</span></span> <span data-ttu-id="3de46-112">Per ulteriori informazioni, vedere <A href="lync-server-2013-configuring-archiving-options.md">configurazione delle opzioni di archiviazione in Lync Server 2013</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="3de46-112">For details, see <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving options in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="3de46-113">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="3de46-113">In This Section</span></span>

  - [<span data-ttu-id="3de46-114">Configurazione dei criteri utente per l'archiviazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3de46-114">Setting up user policies for Archiving in Lync Server 2013</span></span>](lync-server-2013-setting-up-user-policies-for-archiving-in-lync-server.md)

  - [<span data-ttu-id="3de46-115">Impostazione dei criteri per l'archiviazione in Lync Server 2013 quando si utilizza l'integrazione di Exchange Server</span><span class="sxs-lookup"><span data-stu-id="3de46-115">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</span></span>](lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

