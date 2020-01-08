---
title: 'Lync Server 2013: requisiti DNS per i server Standard Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS requirements for Standard Edition servers
ms:assetid: 3d6bbe65-e7ce-491b-a0bd-d2f7197f240d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425900(v=OCS.15)
ms:contentKeyID: 48183920
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 19c5e04f23428b073e544b040ed07dc852f1da4c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985040"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-standard-edition-servers-in-lync-server-2013"></a><span data-ttu-id="67689-102">Requisiti DNS per i server Standard Edition in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="67689-102">DNS requirements for Standard Edition servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="67689-103">_**Argomento Ultima modifica:** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="67689-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="67689-104">Questa sezione descrive i record DNS (Domain Name System) necessari per la distribuzione di server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="67689-104">This section describes the Domain Name System (DNS) records that are required for deployment of Standard Edition servers.</span></span>

<div>

## <a name="dns-records-for-standard-edition-servers"></a><span data-ttu-id="67689-105">Record DNS per server Standard Edition</span><span class="sxs-lookup"><span data-stu-id="67689-105">DNS Records for Standard Edition Servers</span></span>

<span data-ttu-id="67689-106">Nella tabella seguente sono specificati i requisiti DNS per la distribuzione del server standard di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="67689-106">The following table specifies DNS requirements for Lync Server 2013 Standard Edition server deployment.</span></span>

### <a name="dns-requirements-for-a-standard-edition-server"></a><span data-ttu-id="67689-107">Requisiti DNS per un server Standard Edition</span><span class="sxs-lookup"><span data-stu-id="67689-107">DNS Requirements for a Standard Edition Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="67689-108">Scenario di distribuzione</span><span class="sxs-lookup"><span data-stu-id="67689-108">Deployment scenario</span></span></th>
<th><span data-ttu-id="67689-109">Requisito DNS</span><span class="sxs-lookup"><span data-stu-id="67689-109">DNS requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="67689-110">Server Standard Edition</span><span class="sxs-lookup"><span data-stu-id="67689-110">Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="67689-111">Un record interno che risolve il nome di dominio completo (FQDN) del server nel relativo indirizzo IP.</span><span class="sxs-lookup"><span data-stu-id="67689-111">An internal A record that resolves the fully qualified domain name (FQDN) of the server to its IP address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67689-112">Accesso automatico client</span><span class="sxs-lookup"><span data-stu-id="67689-112">Automatic client sign-in</span></span></p></td>
<td><p><span data-ttu-id="67689-113">Per ogni dominio SIP supportato, un record SRV per _sipinternaltls. _tcp. &lt;dominio&gt; sulla porta 5061 che esegue il mapping con il nome di dominio completo del server Standard Edition che autentica e reindirizza le richieste client per l'accesso.</span><span class="sxs-lookup"><span data-stu-id="67689-113">For each supported SIP domain, an SRV record for _sipinternaltls._tcp.&lt;domain&gt; over port 5061 that maps to the FQDN of the Standard Edition server that authenticates and redirects client requests for sign-in.</span></span> <span data-ttu-id="67689-114">Per informazioni dettagliate, vedere <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">requisiti DNS per l'accesso automatico al client in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="67689-114">For details, see <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">DNS requirements for automatic client sign-in in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67689-115">Individuazione del servizio Web di aggiornamento dispositivi da dispositivi Unified Communications (UC)</span><span class="sxs-lookup"><span data-stu-id="67689-115">Device Update Web service discovery by unified communications (UC) devices</span></span></p></td>
<td><p><span data-ttu-id="67689-116">Un record interno con il nome ucupdates-R2. &lt;Dominio&gt; SIP che viene risolto nell'indirizzo IP del servizio Web di aggiornamento del server di hosting del dispositivo Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="67689-116">An internal A record with the name ucupdates-r2.&lt;SIP domain&gt; that resolves to the IP address of the Standard Edition server hosting Device Update Web service.</span></span> <span data-ttu-id="67689-117">Nella situazione in cui è attivato un dispositivo UC, ma un utente non ha mai effettuato l'accesso al dispositivo, il record A consente al dispositivo di individuare il servizio Web di aggiornamento del dispositivo che ospita il server e di ottenere gli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="67689-117">In the situation where a UC device is turned on, but a user has never logged into the device, the A record allows the device to discover the server hosting Device Update Web service and obtain updates.</span></span> <span data-ttu-id="67689-118">In caso contrario, i dispositivi ottengono le informazioni sul server anche se il provisioning in banda è la prima volta che si accede a un utente.</span><span class="sxs-lookup"><span data-stu-id="67689-118">Otherwise, devices obtain the server information though in-band provisioning the first time a user logs in.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67689-119">Proxy inverso per supportare il traffico HTTP</span><span class="sxs-lookup"><span data-stu-id="67689-119">A reverse proxy to support HTTP traffic</span></span></p></td>
<td><p><span data-ttu-id="67689-120">Un record esterno che risolve il nome di dominio completo della Web farm esterna nell'indirizzo IP esterno del proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="67689-120">An external A record that resolves the external web farm FQDN to the external IP address of the reverse proxy.</span></span> <span data-ttu-id="67689-121">I client e i dispositivi UC usano questo record per connettersi al proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="67689-121">Clients and UC devices use this record to connect to the reverse proxy.</span></span> <span data-ttu-id="67689-122">Per informazioni dettagliate, vedere <a href="lync-server-2013-determine-dns-requirements.md">determinare i requisiti DNS per Lync Server 2013</a> nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="67689-122">For details, see <a href="lync-server-2013-determine-dns-requirements.md">Determine DNS requirements for Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

