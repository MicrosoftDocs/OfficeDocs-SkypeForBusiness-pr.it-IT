---
title: 'Lync Server 2013: Controllo delle chiamate remote e normalizzazione dei numeri di telefono'
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
ms.openlocfilehash: 6eff9fb48e9730549d67638c69d8655d8f04d710
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724376"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remote-call-control-and-phone-number-normalization-in-lync-server-2013"></a><span data-ttu-id="218f8-102">Controllo delle chiamate remote e normalizzazione dei numeri di telefono in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="218f8-102">Remote call control and phone number normalization in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="218f8-103">_**Argomento Ultima modifica:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="218f8-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="218f8-104">I client Lync scaricano le regole di normalizzazione dei numeri di telefono come parte del download di file in ABS (Address Book Service).</span><span class="sxs-lookup"><span data-stu-id="218f8-104">Lync clients download phone number normalization rules as part of the Address Book Service (ABS) file download.</span></span> <span data-ttu-id="218f8-105">Negli scenari di controllo delle chiamate remote, le regole di normalizzazione del numero di telefono del servizio Rubrica vengono applicate alle chiamate di controllo delle chiamate remote in entrata e in uscita.</span><span class="sxs-lookup"><span data-stu-id="218f8-105">In remote call control scenarios, Address Book Service phone number normalization rules are applied to both incoming and outgoing remote call control calls.</span></span> <span data-ttu-id="218f8-106">Per le chiamate in arrivo a un utente abilitato per il controllo delle chiamate remote, il numero di telefono del chiamante viene normalizzato per la prima volta in formato E. 164 tramite il gateway SIP/CSTA o il PBX (Private Branch Exchange).</span><span class="sxs-lookup"><span data-stu-id="218f8-106">For incoming calls to a remote call control-enabled user, the phone number of the caller is first normalized to E.164 format by either the SIP/CSTA gateway or private branch exchange (PBX).</span></span> <span data-ttu-id="218f8-107">Quando Lync Server 2013 riceve la chiamata dal gateway, esegue la ricerca di numeri inversa (RNL) sul numero di telefono del chiamante rispetto al numero normalizzato nell'elenco contatti di Microsoft Office Outlook o nell'elenco indirizzi globale archiviato in Servizio Rubrica.</span><span class="sxs-lookup"><span data-stu-id="218f8-107">When Lync Server 2013 receives the call from the gateway, it performs reverse number lookup (RNL) on the phone number of the caller against the normalized number in the callee’s Microsoft Office Outlook Contacts list or the global address list (GAL) that is stored in the Address Book Service.</span></span> <span data-ttu-id="218f8-108">Se la ricerca con numero inverso trova una corrispondenza, il chiamante viene identificato per nome nella notifica di chiamata in arrivo.</span><span class="sxs-lookup"><span data-stu-id="218f8-108">If reverse number lookup successfully finds a match, the caller is identified by name in the incoming call notification.</span></span>

<span data-ttu-id="218f8-109">Per le chiamate di controllo delle chiamate remote in uscita, Lync applica le regole di normalizzazione del numero di telefono del servizio Rubrica al numero composto prima di instradare la chiamata al gateway SIP/CSTA.</span><span class="sxs-lookup"><span data-stu-id="218f8-109">For outgoing remote call control calls, Lync applies the Address Book Service phone number normalization rules to the dialed number before routing the call to the SIP/CSTA gateway.</span></span>

<span data-ttu-id="218f8-110">Per informazioni dettagliate sulla creazione di regole di normalizzazione dei numeri di telefono per il controllo delle chiamate remote, vedere [dial plan e regole di normalizzazione in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="218f8-110">For details about creating phone number normalization rules for remote call control, see [Dial plans and normalization rules in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) in the Planning documentation.</span></span>

<div>

## <a name="migrating-phone-number-normalization-rules"></a><span data-ttu-id="218f8-111">Migrazione delle regole di normalizzazione dei numeri di telefono</span><span class="sxs-lookup"><span data-stu-id="218f8-111">Migrating Phone Number Normalization Rules</span></span>

<span data-ttu-id="218f8-112">Se si esegue la migrazione degli utenti abilitati in precedenza per il controllo delle chiamate remote, vedere gli argomenti seguenti nella documentazione relativa alla migrazione:</span><span class="sxs-lookup"><span data-stu-id="218f8-112">If you are migrating users previously enabled for remote call control, see the following topics in the Migration documentation:</span></span>

  - <span data-ttu-id="218f8-113">Per Lync Server 2010, vedere [eseguire la migrazione della rubrica](migrate-address-book.md) nella documentazione relativa alla migrazione.</span><span class="sxs-lookup"><span data-stu-id="218f8-113">For Lync Server 2010, see [Migrate Address Book](migrate-address-book.md) in the Migration documentation.</span></span>

  - <span data-ttu-id="218f8-114">Per Communications Server 2007 R2, vedere [eseguire la migrazione della rubrica](migrate-address-book_1.md) nella documentazione di migrazione.</span><span class="sxs-lookup"><span data-stu-id="218f8-114">For Communications Server 2007 R2, see [Migrate Address Book](migrate-address-book_1.md) in the Migration documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

