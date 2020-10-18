---
title: 'Lync Server 2013: configurazione del prelievo delle chiamate di gruppo'
description: 'Lync Server 2013: configurazione del prelievo delle chiamate di gruppo.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Group Call Pickup
ms:assetid: b4b0a9a0-91c6-43a5-9e2b-a086caeb3f94
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945645(v=OCS.15)
ms:contentKeyID: 51541505
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ff6be1ea20a98cfaf2addf32c7767940b420c5c8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575912"
---
# <a name="configuring-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="20e8b-103">Configurazione del prelievo delle chiamate di gruppo in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="20e8b-103">Configuring Group Call Pickup in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="20e8b-104">_**Ultimo argomento modificato:** 2013-02-01_</span><span class="sxs-lookup"><span data-stu-id="20e8b-104">_**Topic Last Modified:** 2013-02-01_</span></span>

<span data-ttu-id="20e8b-105">Aggiornamento cumulativo per Lync Server 2013: febbraio 2013 introduce il prelievo delle chiamate di gruppo come nuova funzionalità VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="20e8b-105">Cumulative update for Lync Server 2013: February 2013 introduces Group Call Pickup as a new Enterprise Voice feature.</span></span> <span data-ttu-id="20e8b-106">Raccolta chiamata di gruppo consente agli utenti di raccogliere le chiamate che squillano per un altro utente componendo un numero di gruppo di prelievo di chiamata.</span><span class="sxs-lookup"><span data-stu-id="20e8b-106">Group Call Pickup lets users pick up calls that are ringing for another user by dialing a call pickup group number.</span></span>

<span data-ttu-id="20e8b-107">Quando si distribuisce VoIP aziendale, i componenti utilizzati dal prelievo di chiamata di gruppo vengono installati e abilitati automaticamente nel front end server o nel server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="20e8b-107">The components that Group Call Pickup uses are automatically installed and enabled on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="20e8b-108">Tuttavia, è necessario configurare il prelievo delle chiamate di gruppo prima che sia disponibile per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="20e8b-108">However, you must configure Group Call Pickup before it is available to users.</span></span>

<span data-ttu-id="20e8b-109">In questa sezione viene illustrata la configurazione del prelievo delle chiamate di gruppo.</span><span class="sxs-lookup"><span data-stu-id="20e8b-109">This section guides you through the configuration of Group Call Pickup.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="20e8b-110">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="20e8b-110">In This Section</span></span>

[<span data-ttu-id="20e8b-111">Prerequisiti di configurazione del prelievo delle chiamate di gruppo e diritti utente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="20e8b-111">Group Call Pickup configuration prerequisites and user rights in Lync Server 2013</span></span>](lync-server-2013-group-call-pickup-configuration-prerequisites-and-user-rights.md)

[<span data-ttu-id="20e8b-112">Processo di distribuzione per il ritiro delle chiamate di gruppo in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="20e8b-112">Deployment process for Group Call Pickup in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-group-call-pickup.md)

[<span data-ttu-id="20e8b-113">Distribuire lo strumento SEFAUtil in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="20e8b-113">Deploy the SEFAUtil tool in Lync Server 2013</span></span>](lync-server-2013-deploy-the-sefautil-tool.md)

[<span data-ttu-id="20e8b-114">Configurare i numeri del gruppo di prelievo delle chiamate in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="20e8b-114">Configure call pickup group numbers in Lync Server 2013</span></span>](lync-server-2013-configure-call-pickup-group-numbers.md)

[<span data-ttu-id="20e8b-115">Abilitazione del prelievo delle chiamate di gruppo per gli utenti in Lync Server 2013 e assegnazione di un numero di gruppo</span><span class="sxs-lookup"><span data-stu-id="20e8b-115">Enable Group Call Pickup for users in Lync Server 2013 and assign a group number</span></span>](lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md)

[<span data-ttu-id="20e8b-116">Comunicare le assegnazioni di prelievo delle chiamate di gruppo agli utenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="20e8b-116">Communicate Group Call Pickup assignments to users in Lync Server 2013</span></span>](lync-server-2013-communicate-group-call-pickup-assignment-to-users.md)

[<span data-ttu-id="20e8b-117">Optional Verificare la distribuzione del prelievo delle chiamate di gruppo in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="20e8b-117">(Optional) Verify the Group Call Pickup deployment in Lync Server 2013</span></span>](lync-server-2013-optional-verify-the-group-call-pickup-deployment.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

