---
title: 'Lync Server 2013: pianificazione e configurazione di IPv6'
description: 'Lync Server 2013: pianificazione e configurazione di IPv6.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for and configuring IPv6
ms:assetid: 01f77196-38f4-4292-9480-2e2fbd57eabe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204624(v=OCS.15)
ms:contentKeyID: 48183236
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2c63268bd92fc9d3b683cfa05ab49f01ea56d6ba
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554362"
---
# <a name="planning-for-and-configuring-ipv6-in-lync-server-2013"></a><span data-ttu-id="84191-103">Pianificazione e configurazione di IPv6 in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="84191-103">Planning for and configuring IPv6 in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="84191-104">_**Ultimo argomento modificato:** 2012-06-14_</span><span class="sxs-lookup"><span data-stu-id="84191-104">_**Topic Last Modified:** 2012-06-14_</span></span>

<span data-ttu-id="84191-105">Lync Server 2013 include il supporto per gli indirizzi IP versione 6 (IPv6), insieme al supporto continuativo degli indirizzi IP versione 4 (IPv4).</span><span class="sxs-lookup"><span data-stu-id="84191-105">Lync Server 2013 includes support for IP version 6 (IPv6) addresses, along with continued support of IP version 4 (IPv4) addresses.</span></span> <span data-ttu-id="84191-106">Gli indirizzi IPv4 sono indirizzi a 32 bit che consentono a un computer di comunicare tramite Internet.</span><span class="sxs-lookup"><span data-stu-id="84191-106">IPv4 addresses are 32-bit addresses that allow a computer to communicate over the Internet.</span></span> <span data-ttu-id="84191-107">A causa del numero crescente di dispositivi in tutto il mondo, gli indirizzi IPv4 disponibili sono esauriti. Per questo motivo, molti nuovi dispositivi si stanno spostando nell'utilizzo degli indirizzi IPv6.</span><span class="sxs-lookup"><span data-stu-id="84191-107">Due to the increasing number of devices worldwide, the available IPv4 addresses have run out. Because of this, many new devices are moving to using IPv6 addresses.</span></span> <span data-ttu-id="84191-108">Gli indirizzi IPv6 eseguono la stessa funzione degli indirizzi IPv4 (con alcune funzionalità aggiuntive), ma invece di utilizzare solo 32 bit, gli indirizzi IPv6 utilizzano 128 bit.</span><span class="sxs-lookup"><span data-stu-id="84191-108">IPv6 addresses perform the same function as IPv4 addresses (with some additional features), but instead of using only 32-bits, IPv6 addresses use 128-bits.</span></span> <span data-ttu-id="84191-109">Questo fornisce non solo un nuovo set di indirizzi, ma anche un numero molto più grande.</span><span class="sxs-lookup"><span data-stu-id="84191-109">This provides not only a new set of addresses, but also a much larger number of them.</span></span> <span data-ttu-id="84191-110">Un indirizzo IPv4 tipico ha un aspetto simile al seguente: 192.0.2.235, mentre un indirizzo IPv6 è simile al seguente: 2001:0DB8:85a3:0000:0000:8a2e: 0370:7334.</span><span class="sxs-lookup"><span data-stu-id="84191-110">A typical IPv4 address looks something like this: 192.0.2.235, whereas an IPv6 address looks like this: 2001:0db8:85a3:0000:0000:8a2e:0370:7334.</span></span> <span data-ttu-id="84191-111">La modifica della formattazione e della funzionalità per i dispositivi che utilizzano gli indirizzi IPv6 richiede diverse considerazioni sulla distribuzione e la configurazione nell'installazione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="84191-111">The change in formatting and functionality for devices that use IPv6 addresses requires several deployment and configuration considerations in your Lync Server 2013 installation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="84191-112">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="84191-112">In This Section</span></span>

  - [<span data-ttu-id="84191-113">Panoramica dei tipi di indirizzi IP per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="84191-113">Overview of IP address types for Lync Server 2013</span></span>](lync-server-2013-overview-of-ip-address-types.md)

  - [<span data-ttu-id="84191-114">Requisiti tecnici per IPv6 in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="84191-114">Technical requirements for IPv6 in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-ipv6.md)

  - [<span data-ttu-id="84191-115">Considerazioni sulla migrazione e la coesistenza per IPv6 in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="84191-115">Migration and coexistence considerations for IPv6 in Lync Server 2013</span></span>](lync-server-2013-migration-and-coexistence-considerations-for-ipv6.md)

  - [<span data-ttu-id="84191-116">Configurare i tipi di indirizzi IP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="84191-116">Configure IP address types in Lync Server 2013</span></span>](lync-server-2013-configure-ip-address-types.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

