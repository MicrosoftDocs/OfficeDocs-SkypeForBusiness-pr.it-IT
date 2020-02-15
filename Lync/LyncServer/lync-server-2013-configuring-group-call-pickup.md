---
title: 'Lync Server 2013: configurazione del prelievo delle chiamate di gruppo'
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
ms.openlocfilehash: cbd4c7fc1d0e2c052910b6ddcc9027b9c3db4f72
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030580"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="a7bba-102">Configurazione del prelievo delle chiamate di gruppo in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a7bba-102">Configuring Group Call Pickup in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a7bba-103">_**Ultimo argomento modificato:** 2013-02-01_</span><span class="sxs-lookup"><span data-stu-id="a7bba-103">_**Topic Last Modified:** 2013-02-01_</span></span>

<span data-ttu-id="a7bba-104">Aggiornamento cumulativo per Lync Server 2013: febbraio 2013 introduce il prelievo delle chiamate di gruppo come nuova funzionalità VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="a7bba-104">Cumulative update for Lync Server 2013: February 2013 introduces Group Call Pickup as a new Enterprise Voice feature.</span></span> <span data-ttu-id="a7bba-105">Raccolta chiamata di gruppo consente agli utenti di raccogliere le chiamate che squillano per un altro utente componendo un numero di gruppo di prelievo di chiamata.</span><span class="sxs-lookup"><span data-stu-id="a7bba-105">Group Call Pickup lets users pick up calls that are ringing for another user by dialing a call pickup group number.</span></span>

<span data-ttu-id="a7bba-106">Quando si distribuisce VoIP aziendale, i componenti utilizzati dal prelievo di chiamata di gruppo vengono installati e abilitati automaticamente nel front end server o nel server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="a7bba-106">The components that Group Call Pickup uses are automatically installed and enabled on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="a7bba-107">Tuttavia, è necessario configurare il prelievo delle chiamate di gruppo prima che sia disponibile per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="a7bba-107">However, you must configure Group Call Pickup before it is available to users.</span></span>

<span data-ttu-id="a7bba-108">In questa sezione viene illustrata la configurazione del prelievo delle chiamate di gruppo.</span><span class="sxs-lookup"><span data-stu-id="a7bba-108">This section guides you through the configuration of Group Call Pickup.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a7bba-109">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="a7bba-109">In This Section</span></span>

[<span data-ttu-id="a7bba-110">Prerequisiti di configurazione del prelievo delle chiamate di gruppo e diritti utente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a7bba-110">Group Call Pickup configuration prerequisites and user rights in Lync Server 2013</span></span>](lync-server-2013-group-call-pickup-configuration-prerequisites-and-user-rights.md)

[<span data-ttu-id="a7bba-111">Processo di distribuzione per il ritiro delle chiamate di gruppo in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a7bba-111">Deployment process for Group Call Pickup in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-group-call-pickup.md)

[<span data-ttu-id="a7bba-112">Distribuire lo strumento SEFAUtil in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a7bba-112">Deploy the SEFAUtil tool in Lync Server 2013</span></span>](lync-server-2013-deploy-the-sefautil-tool.md)

[<span data-ttu-id="a7bba-113">Configurare i numeri del gruppo di prelievo delle chiamate in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a7bba-113">Configure call pickup group numbers in Lync Server 2013</span></span>](lync-server-2013-configure-call-pickup-group-numbers.md)

[<span data-ttu-id="a7bba-114">Abilitazione del prelievo delle chiamate di gruppo per gli utenti in Lync Server 2013 e assegnazione di un numero di gruppo</span><span class="sxs-lookup"><span data-stu-id="a7bba-114">Enable Group Call Pickup for users in Lync Server 2013 and assign a group number</span></span>](lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md)

[<span data-ttu-id="a7bba-115">Comunicare le assegnazioni di prelievo delle chiamate di gruppo agli utenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a7bba-115">Communicate Group Call Pickup assignments to users in Lync Server 2013</span></span>](lync-server-2013-communicate-group-call-pickup-assignment-to-users.md)

[<span data-ttu-id="a7bba-116">Optional Verificare la distribuzione del prelievo delle chiamate di gruppo in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a7bba-116">(Optional) Verify the Group Call Pickup deployment in Lync Server 2013</span></span>](lync-server-2013-optional-verify-the-group-call-pickup-deployment.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

