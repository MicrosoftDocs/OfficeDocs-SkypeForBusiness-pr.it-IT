---
title: 'Lync Server 2013: requisiti DNS per un server Standard Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for a Standard Edition server
ms:assetid: 5d1daf54-6e60-4ce0-9254-7d57a0835fa4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204936(v=OCS.15)
ms:contentKeyID: 48184259
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe05133865c0aecdb522e203c1ec2d39ff7b824d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034798"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-a-standard-edition-server-in-lync-server-2013"></a>Requisiti DNS per un server Standard Edition in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-22_

In questa sezione vengono descritti i record DNS (Domain Name System) necessari per la distribuzione di server Standard Edition.

<div>

## <a name="dns-records-for-standard-edition-servers"></a>Record DNS per server Standard Edition

Nella tabella seguente vengono specificati i requisiti DNS per la distribuzione del server di Lync Server 2013 Standard Edition.


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
<td><p>Un record A interno che risolve il nome di dominio completo (FQDN) del server nel relativo indirizzo IP.</p></td>
</tr>
<tr class="even">
<td><p>Accesso client automatico</p></td>
<td><p>Per ogni dominio SIP supportato, un record SRV per _sipinternaltls. _tcp. &lt;domain&gt; over Port 5061 che corrisponde al nome di dominio completo del server Standard Edition che consente di autenticare e reindirizzare le richieste client per l'accesso. Per informazioni dettagliate, vedere <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">DNS requirements for Automatic client Sign-in in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>Individuazione del servizio Web Aggiornamento dispositivi da parte di dispositivi per comunicazioni unificate</p></td>
<td><p>Un record interno con il nome ucupdates-R2. &lt;Dominio&gt; SIP che viene risolto nell'indirizzo IP del servizio Web aggiornamento dispositivi di hosting del server Standard Edition. Se viene attivato un dispositivo per comunicazioni unificate, ma un utente non ha mai effettuato l'accesso al dispositivo, il record A consente al dispositivo di individuare il server che ospita il servizio Web Aggiornamento dispositivi e ottenere gli aggiornamenti. In caso contrario, i dispositivi ottengono le informazioni del server tramite provisioning di tipo in-band al primo accesso di un utente. Per ulteriori informazioni, vedere <a href="lync-server-2013-device-update-web-service.md">servizio Web aggiornamento dispositivi in Lync Server 2013</a> nella documentazione relativa alle operazioni.</p></td>
</tr>
<tr class="even">
<td><p>Proxy inverso per il supporto del traffico HTTP</p></td>
<td><p>Un record A esterno che risolve l'FQDN della Web farm esterna nell'indirizzo IP esterno del proxy inverso. I client e i dispositivi per comunicazioni unificate utilizzano questo record per la connessione al proxy inverso. Per informazioni dettagliate, vedere <a href="lync-server-2013-determine-dns-requirements.md">determine DNS requirements for Lync Server 2013</a> nella documentazione relativa alla pianificazione.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>Vedere anche


[Requisiti DNS per l'accesso automatico dei client in Lync Server 2013](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md)  
[Determinare i requisiti DNS per Lync Server 2013](lync-server-2013-determine-dns-requirements.md)  


[Servizio Web aggiornamento dispositivi in Lync Server 2013](lync-server-2013-device-update-web-service.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

