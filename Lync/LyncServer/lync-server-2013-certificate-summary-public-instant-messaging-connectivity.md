---
title: 'Lync Server 2013: riepilogo dei certificati-connettività per la messaggistica istantanea pubblica'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Public instant messaging connectivity
ms:assetid: 2b3687ee-50c2-4c1c-880e-8dcf8bd4f309
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618370(v=OCS.15)
ms:contentKeyID: 49105657
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bdc4bba8064332d7fa3f90d0d6a3d4b9f6cef9e6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512783"
---
# <a name="certificate-summary---public-instant-messaging-connectivity-in-lync-server-2013"></a>Riepilogo dei certificati-connettività per la messaggistica istantanea pubblica in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-19_

Per configurare i certificati per la connettività per la messaggistica istantanea pubblica, è necessario prima di tutto notare che non vi è nulla di diverso da altri tipi di federazione SIP o persino certificati standard del server perimetrale, tranne per il fatto che America Online (AOL) richiede una configurazione del certificato univoca. Oltre al consueto utilizzo della chiave avanzata del server (EKU), in America Online è necessario che il certificato o i certificati (nel caso di un pool perimetrale) contengano anche l'EKU client. L'EKU client è un'aggiunta al certificato e fa parte del certificato pubblico esterno assegnato al server perimetrale.

<div>

## <a name="certificate-summary--public-instant-messaging-connectivity"></a>Riepilogo dei certificati - Connettività per messaggistica istantanea pubblica


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Componente</th>
<th>Nome soggetto</th>
<th>Ordine/voci nomi alternativi del soggetto (SAN)</th>
<th>Commenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Perimetro esterno/Access Edge</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>sip.contoso.com</p>
<p>webcon.contoso.com</p>
<p>sip.fabrikam.com</p></td>
<td><p>Il certificato deve provenire da un'autorità di certificazione pubblica e deve disporre del server EKU e del client EKU se è necessario distribuire la connettività di messaggistica istantanea pubblica con AOL. Il certificato viene assegnato alle interfacce del server perimetrale esterno per:</p>
<ul>
<li><p>Servizio Access Edge</p></li>
<li><p>Servizio Web Conferencing Edge</p></li>
<li><p>Servizio A/V Edge</p></li>
</ul>
<p>Si noti che i SAN vengono aggiunti automaticamente al certificato in base alle definizioni fornite nel Generatore di topologie. Le voci SAN vengono aggiunte in base alle esigenze per i domini SIP aggiuntivi e per altre voci di cui è richiesto il supporto. Il nome soggetto viene replicato nel SAN e deve essere presente per il funzionamento corretto.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>Vedere anche


[Scenari per l'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

