---
title: "Lync Server 2013: gestione dell'archiviazione"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing Lync Server 2013 Archiving
ms:assetid: 48c6cc8c-c2c1-4534-9a8a-fd5eb738076a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520990(v=OCS.15)
ms:contentKeyID: 48184003
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1d2fa271af82ce1c590d4eaaf8b8ac89dc4197c4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146079"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-lync-server-2013-archiving"></a><span data-ttu-id="e7203-102">Gestione dell'archiviazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e7203-102">Managing Lync Server 2013 Archiving</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e7203-103">_**Ultimo argomento modificato:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="e7203-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="e7203-104">Quando si distribuisce Archiviazione per un'organizzazione, si specifica la configurazione iniziale durante la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="e7203-104">When you deploy Archiving for your organization, you specify the initial configuration during deployment.</span></span> <span data-ttu-id="e7203-105">Esistono tuttavia situazioni in cui si desidera cambiare la modalità di implementazione del supporto di archiviazione per la gestione giornaliera o per soddisfare nuovi requisiti aziendali.</span><span class="sxs-lookup"><span data-stu-id="e7203-105">However, there may be times when you want to change how you implement archiving support for day-to-day management or to meet new requirements in your organization.</span></span> <span data-ttu-id="e7203-106">Può ad esempio essere necessario configurare il supporto di archiviazione in modo diverso per siti, pool o utenti specifici dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e7203-106">For example, you may need to set up archiving support differently for a specific site, pool, or users within your organization.</span></span> <span data-ttu-id="e7203-107">Per gli utenti ospitati in Lync Server 2013, è necessario creare e personalizzare i criteri e le configurazioni di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="e7203-107">For users homed on Lync Server 2013, you do this be creating and customizing archiving policies and configurations.</span></span> <span data-ttu-id="e7203-108">Se si utilizza l'integrazione di Microsoft Exchange, è inoltre necessario configurare le impostazioni di Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="e7203-108">If you use Microsoft Exchange integration, you must also configure Exchange 2013 settings.</span></span> <span data-ttu-id="e7203-109">In questa sezione vengono riportate le informazioni e le procedure necessarie per apportare modifiche alla distribuzione di Archiviazione.</span><span class="sxs-lookup"><span data-stu-id="e7203-109">This section provides information and procedures to enable you to make changes to your Archiving deployment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e7203-110">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="e7203-110">In This Section</span></span>

  - [<span data-ttu-id="e7203-111">Funzionamento dell'archiviazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e7203-111">How Archiving works in Lync Server 2013</span></span>](lync-server-2013-how-archiving-works.md)

  - [<span data-ttu-id="e7203-112">Gestione dell'archiviazione delle comunicazioni interne ed esterne in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e7203-112">Managing the Archiving of internal and external communications in Lync Server 2013</span></span>](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)

  - [<span data-ttu-id="e7203-113">Gestione delle opzioni di configurazione dell'archiviazione in Lync Server 2013 per l'organizzazione, i siti e i pool</span><span class="sxs-lookup"><span data-stu-id="e7203-113">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</span></span>](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)

  - [<span data-ttu-id="e7203-114">Modifica delle opzioni del database di archiviazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e7203-114">Changing Archiving database options in Lync Server 2013</span></span>](lync-server-2013-changing-archiving-database-options.md)

  - [<span data-ttu-id="e7203-115">Esportazione di dati archiviati da Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e7203-115">Exporting archived data from Lync Server 2013</span></span>](lync-server-2013-exporting-archived-data.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

