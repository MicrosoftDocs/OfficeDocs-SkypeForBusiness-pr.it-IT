---
title: 'Lync Server 2013: controllo delle chiamate remote e normalizzazione del numero di telefono'
description: 'Lync Server 2013: controllo delle chiamate remote e normalizzazione del numero di telefono.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remote call control and phone number normalization
ms:assetid: 291d9e87-4c65-4ea2-888f-517741391de5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558630(v=OCS.15)
ms:contentKeyID: 48183696
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: edcb50678da7111aba066745bce5e356dd1ac7f3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555812"
---
# <a name="remote-call-control-and-phone-number-normalization-in-lync-server-2013"></a><span data-ttu-id="b9f0c-103">Controllo delle chiamate remote e normalizzazione del numero di telefono in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b9f0c-103">Remote call control and phone number normalization in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b9f0c-104">_**Ultimo argomento modificato:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="b9f0c-104">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="b9f0c-105">I client Lync scaricano le regole di normalizzazione dei numeri di telefono come parte del download di file del servizio Rubrica (ABS).</span><span class="sxs-lookup"><span data-stu-id="b9f0c-105">Lync clients download phone number normalization rules as part of the Address Book Service (ABS) file download.</span></span> <span data-ttu-id="b9f0c-106">Negli scenari con controllo delle chiamate remote le regole di normalizzazione dei numeri di telefono del servizio Rubrica vengono applicate sia alle chiamate in arrivo che alle chiamate in uscita con tale controllo abilitato.</span><span class="sxs-lookup"><span data-stu-id="b9f0c-106">In remote call control scenarios, Address Book Service phone number normalization rules are applied to both incoming and outgoing remote call control calls.</span></span> <span data-ttu-id="b9f0c-107">Per le chiamate in arrivo dirette a un utente abilitato per l'utilizzo del controllo delle chiamate remote, il numero di telefono del chiamate viene innanzitutto normalizzato nel formato E.164 dal gateway SIP/CSTA o dal centralino (PBX).</span><span class="sxs-lookup"><span data-stu-id="b9f0c-107">For incoming calls to a remote call control-enabled user, the phone number of the caller is first normalized to E.164 format by either the SIP/CSTA gateway or private branch exchange (PBX).</span></span> <span data-ttu-id="b9f0c-108">Quando Lync Server 2013 riceve la chiamata dal gateway, esegue la ricerca di numeri inversi (inversa) sul numero di telefono del chiamante rispetto al numero normalizzato nell'elenco contatti di Microsoft Office Outlook del destinatario della chiamata o nell'elenco indirizzi globale memorizzato nel servizio Rubrica.</span><span class="sxs-lookup"><span data-stu-id="b9f0c-108">When Lync Server 2013 receives the call from the gateway, it performs reverse number lookup (RNL) on the phone number of the caller against the normalized number in the callee’s Microsoft Office Outlook Contacts list or the global address list (GAL) that is stored in the Address Book Service.</span></span> <span data-ttu-id="b9f0c-109">Se tale ricerca trova una corrispondenza, il chiamante viene identificato in base al nome nella notifica della chiamata in arrivo.</span><span class="sxs-lookup"><span data-stu-id="b9f0c-109">If reverse number lookup successfully finds a match, the caller is identified by name in the incoming call notification.</span></span>

<span data-ttu-id="b9f0c-110">Per le chiamate di controllo delle chiamate remote in uscita, Lync applica le regole di normalizzazione dei numeri di telefono del servizio Rubrica al numero composto prima di instradare la chiamata al gateway SIP/CSTA.</span><span class="sxs-lookup"><span data-stu-id="b9f0c-110">For outgoing remote call control calls, Lync applies the Address Book Service phone number normalization rules to the dialed number before routing the call to the SIP/CSTA gateway.</span></span>

<span data-ttu-id="b9f0c-111">Per informazioni dettagliate sulla creazione di regole di normalizzazione dei numeri di telefono per il controllo delle chiamate remote, vedere [dial plans and normalizzation Rules in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="b9f0c-111">For details about creating phone number normalization rules for remote call control, see [Dial plans and normalization rules in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) in the Planning documentation.</span></span>

<div>

## <a name="migrating-phone-number-normalization-rules"></a><span data-ttu-id="b9f0c-112">Migrazione delle regole di normalizzazione dei numeri di telefono</span><span class="sxs-lookup"><span data-stu-id="b9f0c-112">Migrating Phone Number Normalization Rules</span></span>

<span data-ttu-id="b9f0c-113">Se si esegue la migrazione di utenti precedentemente abilitati per il controllo delle chiamate remote, vedere gli argomenti seguenti nella documentazione relativa alla migrazione:</span><span class="sxs-lookup"><span data-stu-id="b9f0c-113">If you are migrating users previously enabled for remote call control, see the following topics in the Migration documentation:</span></span>

  - <span data-ttu-id="b9f0c-114">Per Lync Server 2010, vedere [migrate Address Book](migrate-address-book.md) nella documentazione relativa alla migrazione.</span><span class="sxs-lookup"><span data-stu-id="b9f0c-114">For Lync Server 2010, see [Migrate Address Book](migrate-address-book.md) in the Migration documentation.</span></span>

  - <span data-ttu-id="b9f0c-115">Per Communications Server 2007 R2, vedere [migrate Address Book](migrate-address-book.md) nella documentazione relativa alla migrazione.</span><span class="sxs-lookup"><span data-stu-id="b9f0c-115">For Communications Server 2007 R2, see [Migrate Address Book](migrate-address-book.md) in the Migration documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

