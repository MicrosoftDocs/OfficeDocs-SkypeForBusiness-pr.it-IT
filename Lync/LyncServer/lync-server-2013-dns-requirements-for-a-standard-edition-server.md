---
title: 'Lync Server 2013: Requisiti DNS per un server Standard Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS requirements for a Standard Edition server
ms:assetid: 5d1daf54-6e60-4ce0-9254-7d57a0835fa4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204936(v=OCS.15)
ms:contentKeyID: 48184259
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7508fea0fa6640546bda4f1ecb559821d468803d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984233"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-a-standard-edition-server-in-lync-server-2013"></a>Requisiti DNS per un server Standard Edition in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-22_

Questa sezione descrive i record DNS (Domain Name System) necessari per la distribuzione di server Standard Edition.

<div>

## <a name="dns-records-for-standard-edition-servers"></a>Record DNS per server Standard Edition

Nella tabella seguente sono specificati i requisiti DNS per la distribuzione del server standard di Lync Server 2013.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Scenario di distribuzione</th>
<th>Requisito DNS</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Server Standard Edition</p></td>
<td><p>Un record interno che risolve il nome di dominio completo (FQDN) del server nel relativo indirizzo IP.</p></td>
</tr>
<tr class="even">
<td><p>Accesso automatico client</p></td>
<td><p>Per ogni dominio SIP supportato, un record SRV per _sipinternaltls. _tcp. &lt;dominio&gt; sulla porta 5061 che esegue il mapping con il nome di dominio completo del server Standard Edition che autentica e reindirizza le richieste client per l'accesso. Per informazioni dettagliate, vedere <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">requisiti DNS per l'accesso automatico al client in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>Individuazione del servizio Web di aggiornamento dispositivi da dispositivi Unified Communications (UC)</p></td>
<td><p>Un record interno con il nome ucupdates-R2. &lt;Dominio&gt; SIP che viene risolto nell'indirizzo IP del servizio Web di aggiornamento del server di hosting del dispositivo Standard Edition. Nella situazione in cui è attivato un dispositivo UC, ma un utente non ha mai effettuato l'accesso al dispositivo, il record A consente al dispositivo di individuare il servizio Web di aggiornamento del dispositivo che ospita il server e di ottenere gli aggiornamenti. In caso contrario, i dispositivi ottengono le informazioni sul server anche se il provisioning in banda è la prima volta che si accede a un utente. Per informazioni dettagliate, vedere <a href="lync-server-2013-device-update-web-service.md">servizio Web Update per dispositivi in Lync Server 2013</a> nella documentazione Operations.</p></td>
</tr>
<tr class="even">
<td><p>Proxy inverso per supportare il traffico HTTP</p></td>
<td><p>Un record esterno che risolve il nome di dominio completo della Web farm esterna nell'indirizzo IP esterno del proxy inverso. I client e i dispositivi UC usano questo record per connettersi al proxy inverso. Per informazioni dettagliate, vedere <a href="lync-server-2013-determine-dns-requirements.md">determinare i requisiti DNS per Lync Server 2013</a> nella documentazione relativa alla pianificazione.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>Vedere anche


[Requisiti DNS per l'accesso automatico client in Lync Server 2013](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md)  
[Determinare i requisiti di DNS per Lync Server 2013](lync-server-2013-determine-dns-requirements.md)  


[Servizio Web aggiornamento dispositivi in Lync Server 2013](lync-server-2013-device-update-web-service.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

