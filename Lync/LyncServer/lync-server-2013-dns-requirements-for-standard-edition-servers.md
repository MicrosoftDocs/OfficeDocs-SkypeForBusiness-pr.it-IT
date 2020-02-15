---
title: 'Lync Server 2013: requisiti DNS per i server Standard Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for Standard Edition servers
ms:assetid: 3d6bbe65-e7ce-491b-a0bd-d2f7197f240d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425900(v=OCS.15)
ms:contentKeyID: 48183920
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2064181a7c4d60015905d5974ac01378b7d025e2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029597"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-standard-edition-servers-in-lync-server-2013"></a><span data-ttu-id="2de6d-102">Requisiti DNS per i server Standard Edition in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2de6d-102">DNS requirements for Standard Edition servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2de6d-103">_**Ultimo argomento modificato:** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="2de6d-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="2de6d-104">In questa sezione vengono descritti i record DNS (Domain Name System) necessari per la distribuzione di server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="2de6d-104">This section describes the Domain Name System (DNS) records that are required for deployment of Standard Edition servers.</span></span>

<div>

## <a name="dns-records-for-standard-edition-servers"></a><span data-ttu-id="2de6d-105">Record DNS per server Standard Edition</span><span class="sxs-lookup"><span data-stu-id="2de6d-105">DNS Records for Standard Edition Servers</span></span>

<span data-ttu-id="2de6d-106">Nella tabella seguente vengono specificati i requisiti DNS per la distribuzione del server di Lync Server 2013 Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="2de6d-106">The following table specifies DNS requirements for Lync Server 2013 Standard Edition server deployment.</span></span>

### <a name="dns-requirements-for-a-standard-edition-server"></a><span data-ttu-id="2de6d-107">Requisiti DNS per un server Standard Edition</span><span class="sxs-lookup"><span data-stu-id="2de6d-107">DNS Requirements for a Standard Edition Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2de6d-108">Scenario di distribuzione</span><span class="sxs-lookup"><span data-stu-id="2de6d-108">Deployment scenario</span></span></th>
<th><span data-ttu-id="2de6d-109">Requisito DNS</span><span class="sxs-lookup"><span data-stu-id="2de6d-109">DNS requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2de6d-110">Server Standard Edition</span><span class="sxs-lookup"><span data-stu-id="2de6d-110">Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="2de6d-111">Un record A interno che risolve il nome di dominio completo (FQDN) del server nel relativo indirizzo IP.</span><span class="sxs-lookup"><span data-stu-id="2de6d-111">An internal A record that resolves the fully qualified domain name (FQDN) of the server to its IP address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2de6d-112">Accesso client automatico</span><span class="sxs-lookup"><span data-stu-id="2de6d-112">Automatic client sign-in</span></span></p></td>
<td><p><span data-ttu-id="2de6d-113">Per ogni dominio SIP supportato, un record SRV per _sipinternaltls. _tcp. &lt;domain&gt; over Port 5061 che corrisponde al nome di dominio completo del server Standard Edition che consente di autenticare e reindirizzare le richieste client per l'accesso.</span><span class="sxs-lookup"><span data-stu-id="2de6d-113">For each supported SIP domain, an SRV record for _sipinternaltls._tcp.&lt;domain&gt; over port 5061 that maps to the FQDN of the Standard Edition server that authenticates and redirects client requests for sign-in.</span></span> <span data-ttu-id="2de6d-114">Per informazioni dettagliate, vedere <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">DNS requirements for Automatic client Sign-in in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="2de6d-114">For details, see <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">DNS requirements for automatic client sign-in in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2de6d-115">Individuazione del servizio Web Aggiornamento dispositivi da parte di dispositivi per comunicazioni unificate</span><span class="sxs-lookup"><span data-stu-id="2de6d-115">Device Update Web service discovery by unified communications (UC) devices</span></span></p></td>
<td><p><span data-ttu-id="2de6d-116">Un record interno con il nome ucupdates-R2. &lt;Dominio&gt; SIP che viene risolto nell'indirizzo IP del servizio Web aggiornamento dispositivi di hosting del server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="2de6d-116">An internal A record with the name ucupdates-r2.&lt;SIP domain&gt; that resolves to the IP address of the Standard Edition server hosting Device Update Web service.</span></span> <span data-ttu-id="2de6d-117">Se viene attivato un dispositivo per comunicazioni unificate, ma un utente non ha mai effettuato l'accesso al dispositivo, il record A consente al dispositivo di individuare il server che ospita il servizio Web Aggiornamento dispositivi e ottenere gli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="2de6d-117">In the situation where a UC device is turned on, but a user has never logged into the device, the A record allows the device to discover the server hosting Device Update Web service and obtain updates.</span></span> <span data-ttu-id="2de6d-118">In caso contrario, i dispositivi ottengono le informazioni del server tramite provisioning di tipo in-band al primo accesso di un utente.</span><span class="sxs-lookup"><span data-stu-id="2de6d-118">Otherwise, devices obtain the server information though in-band provisioning the first time a user logs in.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2de6d-119">Proxy inverso per il supporto del traffico HTTP</span><span class="sxs-lookup"><span data-stu-id="2de6d-119">A reverse proxy to support HTTP traffic</span></span></p></td>
<td><p><span data-ttu-id="2de6d-120">Un record A esterno che risolve l'FQDN della Web farm esterna nell'indirizzo IP esterno del proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="2de6d-120">An external A record that resolves the external web farm FQDN to the external IP address of the reverse proxy.</span></span> <span data-ttu-id="2de6d-121">I client e i dispositivi per comunicazioni unificate utilizzano questo record per la connessione al proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="2de6d-121">Clients and UC devices use this record to connect to the reverse proxy.</span></span> <span data-ttu-id="2de6d-122">Per informazioni dettagliate, vedere <a href="lync-server-2013-determine-dns-requirements.md">determine DNS requirements for Lync Server 2013</a> nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="2de6d-122">For details, see <a href="lync-server-2013-determine-dns-requirements.md">Determine DNS requirements for Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

