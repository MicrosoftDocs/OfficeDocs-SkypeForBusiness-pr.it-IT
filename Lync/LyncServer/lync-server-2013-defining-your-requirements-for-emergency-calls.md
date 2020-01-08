---
title: 'Lync Server 2013: Definizione dei requisiti per le chiamate di emergenza'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining your requirements for emergency calls
ms:assetid: 5c12b517-9be6-41d0-83e2-11c78793620c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398404(v=OCS.15)
ms:contentKeyID: 48184276
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 53543d815519dc440ba038999e5fc531173551f3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981475"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-emergency-calls-in-lync-server-2013"></a>Definizione dei requisiti per le chiamate di emergenza in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-06-06_

Prima di iniziare una distribuzione E9-1-1 di Microsoft Lync Server 2013, è necessario prima di tutto rispondere alle domande descritte nelle sezioni seguenti. La pianificazione che devi eseguire dipende dal tipo di soluzione E9-1-1 che scegli di distribuire: un provider di servizi E9-1-1 trunk SIP o un gateway ELIN (Emergency Location Identification Number). La tabella seguente identifica le sezioni della cartella di lavoro per la pianificazione che è necessario rivedere per ognuna di queste soluzioni.

### <a name="planning-steps-by-type-of-e9-1-1-solution"></a>Passaggi per la pianificazione per tipo di soluzione E9-1-1

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Provider di servizi trunk SIP</th>
<th>Gateway ELIN</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">Definizione dell'ambito della distribuzione di E9-1-1 in Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">Definizione dell'ambito della distribuzione di E9-1-1 in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">Definizione degli elementi di rete usati per determinare la posizione in Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">Definizione degli elementi di rete usati per determinare la posizione in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-enabling-users-for-e9-1-1.md">Abilitazione degli utenti per E9-1-1 in Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-enabling-users-for-e9-1-1.md">Abilitazione degli utenti per E9-1-1 in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-managing-locations-for-sip-trunk-service-providers.md">Gestione delle posizioni per i provider di servizi trunk SIP in Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-managing-locations-for-elin-gateways.md">Gestione delle posizioni per i gateway ELIN in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">Definizione dell'esperienza utente per l'acquisizione manuale di una posizione in Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">Definizione dell'esperienza utente per l'acquisizione manuale di una posizione in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-designing-the-sip-trunk-for-e9-1-1.md">Progettazione del trunk SIP per E9-1-1 in Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-including-the-security-desk.md">Incluso il servizio di sicurezza in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-including-the-security-desk.md">Incluso il servizio di sicurezza in Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-defining-the-location-policy.md">Definizione dei criteri di posizione per Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-choosing-an-e9-1-1-service-provider.md">Scelta di un provider di servizi E9-1-1 per Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-assigning-location-policy-scope.md">Assegnazione dell'ambito dei criteri di posizione in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-defining-the-location-policy.md">Definizione dei criteri di posizione per Lync Server 2013</a></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-assigning-location-policy-scope.md">Assegnazione dell'ambito dei criteri di posizione in Lync Server 2013</a></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a>Contenuto della sezione

  - [Definizione dell'ambito della distribuzione di E9-1-1 in Lync Server 2013](lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md)

  - [Definizione degli elementi di rete usati per determinare la posizione in Lync Server 2013](lync-server-2013-defining-the-network-elements-used-to-determine-location.md)

  - [Abilitazione degli utenti per E9-1-1 in Lync Server 2013](lync-server-2013-enabling-users-for-e9-1-1.md)

  - [Gestione delle posizioni per i provider di servizi trunk SIP in Lync Server 2013](lync-server-2013-managing-locations-for-sip-trunk-service-providers.md)

  - [Gestione delle posizioni per i gateway ELIN in Lync Server 2013](lync-server-2013-managing-locations-for-elin-gateways.md)

  - [Definizione dell'esperienza utente per l'acquisizione manuale di una posizione in Lync Server 2013](lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md)

  - [Progettazione del trunk SIP per E9-1-1 in Lync Server 2013](lync-server-2013-designing-the-sip-trunk-for-e9-1-1.md)

  - [Incluso il servizio di sicurezza in Lync Server 2013](lync-server-2013-including-the-security-desk.md)

  - [Scelta di un provider di servizi E9-1-1 per Lync Server 2013](lync-server-2013-choosing-an-e9-1-1-service-provider.md)

  - [Definizione dei criteri di posizione per Lync Server 2013](lync-server-2013-defining-the-location-policy.md)

  - [Assegnazione dell'ambito dei criteri di posizione in Lync Server 2013](lync-server-2013-assigning-location-policy-scope.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

