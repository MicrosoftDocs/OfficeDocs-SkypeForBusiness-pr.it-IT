---
title: 'Lync Server 2013: configurazione del parcheggio di chiamata'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Call Park
ms:assetid: e4c5da53-7f6c-4535-bc9b-9da2026caec8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399014(v=OCS.15)
ms:contentKeyID: 48185732
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2932053e8224b751c124c80152c097d9da82e517
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043888"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-call-park-in-lync-server-2013"></a><span data-ttu-id="81227-102">Configurazione del parcheggio di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="81227-102">Configuring Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="81227-103">_**Ultimo argomento modificato:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="81227-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="81227-104">Parcheggio di chiamata consente a un utente di VoIP aziendale di inserire una chiamata in attesa da un telefono e quindi di recuperare la chiamata in un secondo momento componendo un numero interno (noto come *orbita*del parcheggio di chiamata) da qualsiasi telefono.</span><span class="sxs-lookup"><span data-stu-id="81227-104">Call Park enables an Enterprise Voice user to put a call on hold from one telephone and then retrieve the call later by dialing an internal number (known as a Call Park *orbit*) from any telephone.</span></span>

<span data-ttu-id="81227-105">I componenti utilizzati dal parcheggio di chiamata vengono installati e abilitati automaticamente nel front end server o nel server Standard Edition quando si distribuisce VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="81227-105">The components that Call Park uses are automatically installed and enabled on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="81227-106">Tuttavia, è necessario configurare il parcheggio di chiamata prima che sia disponibile per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="81227-106">However, you must configure Call Park before it is available to users.</span></span>

<span data-ttu-id="81227-107">In questa sezione viene illustrata la configurazione del parcheggio di chiamata.</span><span class="sxs-lookup"><span data-stu-id="81227-107">This section guides you through the configuration of Call Park.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="81227-108">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="81227-108">In This Section</span></span>

  - [<span data-ttu-id="81227-109">Requisiti di configurazione del parcheggio di chiamata e diritti utente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="81227-109">Call Park configuration prerequisites and user rights in Lync Server 2013</span></span>](lync-server-2013-call-park-configuration-prerequisites-and-user-rights.md)

  - [<span data-ttu-id="81227-110">Processo di distribuzione per il parcheggio di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="81227-110">Deployment process for Call Park in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-call-park.md)

  - [<span data-ttu-id="81227-111">Configurare la tabella di orbit del parcheggio di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="81227-111">Configure the Call Park orbit table in Lync Server 2013</span></span>](lync-server-2013-configure-the-call-park-orbit-table.md)

  - [<span data-ttu-id="81227-112">Configurare le impostazioni del parcheggio di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="81227-112">Configure Call Park settings in Lync Server 2013</span></span>](lync-server-2013-configure-call-park-settings.md)

  - [<span data-ttu-id="81227-113">Personalizzare la musica del parcheggio di chiamata in attesa in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="81227-113">Customize Call Park music on hold in Lync Server 2013</span></span>](lync-server-2013-customize-call-park-music-on-hold.md)

  - [<span data-ttu-id="81227-114">Abilitare il parcheggio di chiamata per gli utenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="81227-114">Enable Call Park for users in Lync Server 2013</span></span>](lync-server-2013-enable-call-park-for-users.md)

  - [<span data-ttu-id="81227-115">Verificare le regole di normalizzazione per il parcheggio di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="81227-115">Verify normalization rules for Call Park in Lync Server 2013</span></span>](lync-server-2013-verify-normalization-rules-for-call-park.md)

  - [<span data-ttu-id="81227-116">Optional Verificare la distribuzione del parcheggio di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="81227-116">(Optional) Verify Call Park deployment in Lync Server 2013</span></span>](lync-server-2013-optional-verify-call-park-deployment.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

