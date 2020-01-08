---
title: "Lync Server 2013: Gestione dell'archiviazione"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing Lync Server 2013 Archiving
ms:assetid: 48c6cc8c-c2c1-4534-9a8a-fd5eb738076a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520990(v=OCS.15)
ms:contentKeyID: 48184003
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 88e5176ec32b5039b9351202f72ee32502959f60
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976161"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-lync-server-2013-archiving"></a><span data-ttu-id="794c8-102">Gestione dell'archiviazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="794c8-102">Managing Lync Server 2013 Archiving</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="794c8-103">_**Argomento Ultima modifica:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="794c8-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="794c8-104">Quando si distribuisce l'archiviazione per l'organizzazione, è necessario specificare la configurazione iniziale durante la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="794c8-104">When you deploy Archiving for your organization, you specify the initial configuration during deployment.</span></span> <span data-ttu-id="794c8-105">In alcuni casi, tuttavia, può essere necessario modificare la modalità di implementazione del supporto dell'archiviazione per la gestione giornaliera o per soddisfare i nuovi requisiti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="794c8-105">However, there may be times when you want to change how you implement archiving support for day-to-day management or to meet new requirements in your organization.</span></span> <span data-ttu-id="794c8-106">Ad esempio, potrebbe essere necessario configurare il supporto dell'archiviazione in modo diverso per un sito, un pool o un utente specifico all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="794c8-106">For example, you may need to set up archiving support differently for a specific site, pool, or users within your organization.</span></span> <span data-ttu-id="794c8-107">Per gli utenti residenti in Lync Server 2013, è possibile creare e personalizzare i criteri di archiviazione e le configurazioni.</span><span class="sxs-lookup"><span data-stu-id="794c8-107">For users homed on Lync Server 2013, you do this be creating and customizing archiving policies and configurations.</span></span> <span data-ttu-id="794c8-108">Se si usa l'integrazione di Microsoft Exchange, è anche necessario configurare le impostazioni di Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="794c8-108">If you use Microsoft Exchange integration, you must also configure Exchange 2013 settings.</span></span> <span data-ttu-id="794c8-109">Questa sezione fornisce informazioni e procedure per consentire di apportare modifiche alla distribuzione di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="794c8-109">This section provides information and procedures to enable you to make changes to your Archiving deployment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="794c8-110">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="794c8-110">In This Section</span></span>

  - [<span data-ttu-id="794c8-111">Funzionamento dell'archiviazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="794c8-111">How Archiving works in Lync Server 2013</span></span>](lync-server-2013-how-archiving-works.md)

  - [<span data-ttu-id="794c8-112">Gestione dell'archiviazione delle comunicazioni interne ed esterne in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="794c8-112">Managing the Archiving of internal and external communications in Lync Server 2013</span></span>](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)

  - [<span data-ttu-id="794c8-113">Gestione delle opzioni di configurazione dell'archiviazione in Lync Server 2013 per l'organizzazione, i siti e i pool</span><span class="sxs-lookup"><span data-stu-id="794c8-113">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</span></span>](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)

  - [<span data-ttu-id="794c8-114">Modifica delle opzioni di archiviazione del database in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="794c8-114">Changing Archiving database options in Lync Server 2013</span></span>](lync-server-2013-changing-archiving-database-options.md)

  - [<span data-ttu-id="794c8-115">Esportazione di dati archiviati da Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="794c8-115">Exporting archived data from Lync Server 2013</span></span>](lync-server-2013-exporting-archived-data.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

