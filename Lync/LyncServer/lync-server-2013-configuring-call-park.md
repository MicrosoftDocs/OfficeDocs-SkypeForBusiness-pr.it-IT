---
title: 'Lync Server 2013: Configurazione del parcheggio di chiamata'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Call Park
ms:assetid: e4c5da53-7f6c-4535-bc9b-9da2026caec8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399014(v=OCS.15)
ms:contentKeyID: 48185732
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69e2a1c6ef9da447688ea1ca7d0308afc0b4ab9c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976625"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-call-park-in-lync-server-2013"></a><span data-ttu-id="3bdc0-102">Configurazione del parcheggio di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3bdc0-102">Configuring Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3bdc0-103">_**Argomento Ultima modifica:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="3bdc0-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="3bdc0-104">Call Park consente a un utente di VoIP aziendale di mettere una chiamata in attesa da un telefono e quindi recuperare la chiamata in un secondo momento componendo un numero interno (noto come *orbita*di Call Park) da qualsiasi telefono.</span><span class="sxs-lookup"><span data-stu-id="3bdc0-104">Call Park enables an Enterprise Voice user to put a call on hold from one telephone and then retrieve the call later by dialing an internal number (known as a Call Park *orbit*) from any telephone.</span></span>

<span data-ttu-id="3bdc0-105">I componenti usati da Park chiamata vengono installati e abilitati automaticamente nel server front-end o Standard Edition quando si distribuisce VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="3bdc0-105">The components that Call Park uses are automatically installed and enabled on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="3bdc0-106">Tuttavia, devi configurare Call Park prima che sia disponibile per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="3bdc0-106">However, you must configure Call Park before it is available to users.</span></span>

<span data-ttu-id="3bdc0-107">Questa sezione guida la configurazione di Call Park.</span><span class="sxs-lookup"><span data-stu-id="3bdc0-107">This section guides you through the configuration of Call Park.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="3bdc0-108">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="3bdc0-108">In This Section</span></span>

  - [<span data-ttu-id="3bdc0-109">Diritti utente e prerequisiti per la configurazione del parcheggio di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3bdc0-109">Call Park configuration prerequisites and user rights in Lync Server 2013</span></span>](lync-server-2013-call-park-configuration-prerequisites-and-user-rights.md)

  - [<span data-ttu-id="3bdc0-110">Processo di distribuzione per Call Park in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3bdc0-110">Deployment process for Call Park in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-call-park.md)

  - [<span data-ttu-id="3bdc0-111">Configurare la tabella di codici orbit del parcheggio di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3bdc0-111">Configure the Call Park orbit table in Lync Server 2013</span></span>](lync-server-2013-configure-the-call-park-orbit-table.md)

  - [<span data-ttu-id="3bdc0-112">Configurare le impostazioni di Call Park in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3bdc0-112">Configure Call Park settings in Lync Server 2013</span></span>](lync-server-2013-configure-call-park-settings.md)

  - [<span data-ttu-id="3bdc0-113">Personalizzare la musica di Call Park in attesa in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3bdc0-113">Customize Call Park music on hold in Lync Server 2013</span></span>](lync-server-2013-customize-call-park-music-on-hold.md)

  - [<span data-ttu-id="3bdc0-114">Abilitare il parcheggio delle chiamate per gli utenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3bdc0-114">Enable Call Park for users in Lync Server 2013</span></span>](lync-server-2013-enable-call-park-for-users.md)

  - [<span data-ttu-id="3bdc0-115">Verificare le regole di normalizzazione per Call Park in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3bdc0-115">Verify normalization rules for Call Park in Lync Server 2013</span></span>](lync-server-2013-verify-normalization-rules-for-call-park.md)

  - [<span data-ttu-id="3bdc0-116">Opzionale Verificare la distribuzione di Call Park in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3bdc0-116">(Optional) Verify Call Park deployment in Lync Server 2013</span></span>](lync-server-2013-optional-verify-call-park-deployment.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

