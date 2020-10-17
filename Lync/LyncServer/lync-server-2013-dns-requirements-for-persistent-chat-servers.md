---
title: 'Lync Server 2013: requisiti DNS per i server Chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for Persistent Chat Servers
ms:assetid: f7531374-d7ed-4b63-ae81-02294cb4496a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205391(v=OCS.15)
ms:contentKeyID: 48185857
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 055a55498247cdde540ceca44cc33187e2b9baca
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501383"
---
# <a name="dns-requirements-for-persistent-chat-servers-in-lync-server-2013"></a><span data-ttu-id="fa3bd-102">Requisiti DNS per i server Chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fa3bd-102">DNS requirements for Persistent Chat Servers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fa3bd-103">_**Ultimo argomento modificato:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="fa3bd-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="fa3bd-104">In questa sezione vengono descritti i record DNS (Domain Name System) necessari per la distribuzione di server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="fa3bd-104">This section describes the Domain Name System (DNS) records that are required for deployment of Persistent Chat Servers.</span></span>

<div>

## <a name="dns-records-for-persistent-chat-servers"></a><span data-ttu-id="fa3bd-105">Record DNS per i server chat persistente</span><span class="sxs-lookup"><span data-stu-id="fa3bd-105">DNS Records for Persistent Chat Servers</span></span>

<span data-ttu-id="fa3bd-106">Nella tabella seguente vengono specificati i requisiti DNS per la distribuzione del server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="fa3bd-106">The following table specifies DNS requirements for Persistent Chat Server deployment.</span></span>

### <a name="dns-requirements-for-a-persistent-chat-server"></a><span data-ttu-id="fa3bd-107">Requisiti DNS per un server chat persistente</span><span class="sxs-lookup"><span data-stu-id="fa3bd-107">DNS Requirements for a Persistent Chat Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fa3bd-108">Scenario di distribuzione</span><span class="sxs-lookup"><span data-stu-id="fa3bd-108">Deployment scenario</span></span></th>
<th><span data-ttu-id="fa3bd-109">Requisito DNS</span><span class="sxs-lookup"><span data-stu-id="fa3bd-109">DNS requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fa3bd-110">Un server chat persistente</span><span class="sxs-lookup"><span data-stu-id="fa3bd-110">One Persistent Chat Server</span></span></p></td>
<td><p><span data-ttu-id="fa3bd-111">Un record A interno che risolve il nome di dominio completo (FQDN) del server nel relativo indirizzo IP.</span><span class="sxs-lookup"><span data-stu-id="fa3bd-111">An internal A record that resolves the fully qualified domain name (FQDN) of the server to its IP address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa3bd-112">Pool chat persistente</span><span class="sxs-lookup"><span data-stu-id="fa3bd-112">Persistent Chat pool</span></span></p></td>
<td><p><span data-ttu-id="fa3bd-113">Un record A interno che risolve il nome di dominio completo (FQDN) dei server nel relativo indirizzo IP.</span><span class="sxs-lookup"><span data-stu-id="fa3bd-113">An internal A record that resolves the fully qualified domain name (FQDN) of the servers to its IP address.</span></span></p>
<p><span data-ttu-id="fa3bd-114"><strong>Esempio</strong></span><span class="sxs-lookup"><span data-stu-id="fa3bd-114"><strong>Example</strong></span></span></p>
<p><span data-ttu-id="fa3bd-115">PersistentChatServer01.contoso.com 10.10.10.1</span><span class="sxs-lookup"><span data-stu-id="fa3bd-115">PersistentChatServer01.contoso.com     10.10.10.1</span></span></p>
<p><span data-ttu-id="fa3bd-116">PersistentChatServer02.contoso.com 10.10.10.2</span><span class="sxs-lookup"><span data-stu-id="fa3bd-116">PersistentChatServer02.contoso.com     10.10.10.2</span></span></p>
<p><span data-ttu-id="fa3bd-117">Un record A interno che risolve il nome di dominio completo (FQDN) dei server nel relativo indirizzo IP.</span><span class="sxs-lookup"><span data-stu-id="fa3bd-117">An internal A record that resolves the fully qualified domain name (FQDN) of the servers to its IP address.</span></span></p>
<p><span data-ttu-id="fa3bd-118"><strong>Esempio</strong></span><span class="sxs-lookup"><span data-stu-id="fa3bd-118"><strong>Example</strong></span></span></p>
<p><span data-ttu-id="fa3bd-119">PersistentChatPool.contoso.com 10.10.10.1</span><span class="sxs-lookup"><span data-stu-id="fa3bd-119">PersistentChatPool.contoso.com    10.10.10.1</span></span></p>
<p><span data-ttu-id="fa3bd-120">PersistentChatPool.contoso.com 10.10.10.2</span><span class="sxs-lookup"><span data-stu-id="fa3bd-120">PersistentChatPool.contoso.com    10.10.10.2</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

