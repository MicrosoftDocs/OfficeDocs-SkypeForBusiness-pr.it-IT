---
title: 'Lync Server 2013: requisiti DNS per i server di chat persistenti'
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
ms.openlocfilehash: b97d3238c64173cb5f9bfcfc12dce40f987da123
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737396"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-persistent-chat-servers-in-lync-server-2013"></a><span data-ttu-id="aae84-102">Requisiti DNS per i server di chat persistenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aae84-102">DNS requirements for Persistent Chat Servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aae84-103">_**Argomento Ultima modifica:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="aae84-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="aae84-104">Questa sezione descrive i record DNS (Domain Name System) necessari per la distribuzione di server di chat permanenti.</span><span class="sxs-lookup"><span data-stu-id="aae84-104">This section describes the Domain Name System (DNS) records that are required for deployment of Persistent Chat Servers.</span></span>

<div>

## <a name="dns-records-for-persistent-chat-servers"></a><span data-ttu-id="aae84-105">Record DNS per server di chat persistenti</span><span class="sxs-lookup"><span data-stu-id="aae84-105">DNS Records for Persistent Chat Servers</span></span>

<span data-ttu-id="aae84-106">Nella tabella seguente sono specificati i requisiti DNS per la distribuzione del server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="aae84-106">The following table specifies DNS requirements for Persistent Chat Server deployment.</span></span>

### <a name="dns-requirements-for-a-persistent-chat-server"></a><span data-ttu-id="aae84-107">Requisiti DNS per un server di chat persistente</span><span class="sxs-lookup"><span data-stu-id="aae84-107">DNS Requirements for a Persistent Chat Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="aae84-108">Scenario di distribuzione</span><span class="sxs-lookup"><span data-stu-id="aae84-108">Deployment scenario</span></span></th>
<th><span data-ttu-id="aae84-109">Requisito DNS</span><span class="sxs-lookup"><span data-stu-id="aae84-109">DNS requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aae84-110">Un server di chat persistente</span><span class="sxs-lookup"><span data-stu-id="aae84-110">One Persistent Chat Server</span></span></p></td>
<td><p><span data-ttu-id="aae84-111">Un record interno che risolve il nome di dominio completo (FQDN) del server nel relativo indirizzo IP.</span><span class="sxs-lookup"><span data-stu-id="aae84-111">An internal A record that resolves the fully qualified domain name (FQDN) of the server to its IP address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aae84-112">Pool di chat persistente</span><span class="sxs-lookup"><span data-stu-id="aae84-112">Persistent Chat pool</span></span></p></td>
<td><p><span data-ttu-id="aae84-113">Un record interno che risolve il nome di dominio completo (FQDN) dei server nel relativo indirizzo IP.</span><span class="sxs-lookup"><span data-stu-id="aae84-113">An internal A record that resolves the fully qualified domain name (FQDN) of the servers to its IP address.</span></span></p>
<p><span data-ttu-id="aae84-114"><strong>Esempio</strong></span><span class="sxs-lookup"><span data-stu-id="aae84-114"><strong>Example</strong></span></span></p>
<p><span data-ttu-id="aae84-115">PersistentChatServer01.contoso.com 10.10.10.1</span><span class="sxs-lookup"><span data-stu-id="aae84-115">PersistentChatServer01.contoso.com     10.10.10.1</span></span></p>
<p><span data-ttu-id="aae84-116">PersistentChatServer02.contoso.com 10.10.10.2</span><span class="sxs-lookup"><span data-stu-id="aae84-116">PersistentChatServer02.contoso.com     10.10.10.2</span></span></p>
<p><span data-ttu-id="aae84-117">Un record interno che risolve il nome di dominio completo (FQDN) dei server nel relativo indirizzo IP.</span><span class="sxs-lookup"><span data-stu-id="aae84-117">An internal A record that resolves the fully qualified domain name (FQDN) of the servers to its IP address.</span></span></p>
<p><span data-ttu-id="aae84-118"><strong>Esempio</strong></span><span class="sxs-lookup"><span data-stu-id="aae84-118"><strong>Example</strong></span></span></p>
<p><span data-ttu-id="aae84-119">PersistentChatPool.contoso.com 10.10.10.1</span><span class="sxs-lookup"><span data-stu-id="aae84-119">PersistentChatPool.contoso.com    10.10.10.1</span></span></p>
<p><span data-ttu-id="aae84-120">PersistentChatPool.contoso.com 10.10.10.2</span><span class="sxs-lookup"><span data-stu-id="aae84-120">PersistentChatPool.contoso.com    10.10.10.2</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

