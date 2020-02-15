---
title: Introduzione
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Introduction
ms:assetid: 276395be-93df-4a16-97e2-cb468cd0f2e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945588(v=OCS.15)
ms:contentKeyID: 51541414
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8a3674742cedbdfb267326e0170703f3fbc3ba3b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044268"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="introduction"></a>Introduzione

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-24_

Lo strumento di stress e prestazioni di Lync Server 2013 (denominato LyncPerfTool) può simulare il carico degli utenti dei tipi seguenti:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Servizi di messaggistica istantanea e presenza</p></td>
<td><p>Servizi di audioconferenza</p></td>
</tr>
<tr class="even">
<td><p>Condivisione applicazioni</p></td>
<td><p>VoIP (Voice over IP), inclusa la simulazione PSTN (Public Switched Telephone Network)</p></td>
</tr>
<tr class="odd">
<td><p>Servizi di conferenza client di accesso Web</p></td>
<td><p>Operatore Microsoft Lync 2013</p></td>
</tr>
<tr class="even">
<td><p>Response Group</p></td>
<td><p>Espansione della lista di distribuzione</p></td>
</tr>
<tr class="odd">
<td><p>Download della Rubrica e query della Rubrica</p></td>
<td><p>Chiamate e profili delle posizioni migliorati di 9-1-1 (E9-1-1) (dial plan)</p></td>
</tr>
<tr class="even">
<td><p>MultiView</p></td>
<td><p>Visualizzazione di più flussi da una conferenza</p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
</tr>
</tbody>
</table>


Lo strumento Lync Server 2013 stress and performance supporta la generazione e la Federazione dei carichi tra pool solo tramite la configurazione avanzata.

Nello strumento non è inoltre possibile simulare il carico utente per i client seguenti:

  - Office Live Meeting 2007

  - Lync 2013 Persistent Chat

Di conseguenza, lo strumento di analisi dello stress e delle prestazioni di Lync Server 2013 non supporterà i test dei componenti seguenti:

  - Lync 2013 Persistent Chat

  - Scenari di integrazione di Exchange

<div>

## <a name="applications-and-files-included-with-the-lync-server-2013-stress-and-performance-tool"></a>Applicazioni e file inclusi nello strumento di stress e prestazioni di Lync Server 2013

Nello strumento di stress e prestazioni di Lync Server 2013 sono incluse le applicazioni seguenti:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Strumento</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>UserProvisioningTool. exe</p></td>
<td><p>Lo strumento di provisioning degli utenti di Lync Server 2013. Questo strumento viene utilizzato per creare utenti e contatti.</p></td>
</tr>
<tr class="even">
<td><p>UserProfileGenerator. exe</p></td>
<td><p>Strumento di configurazione del caricamento di Lync Server 2013. Questo strumento viene utilizzato per configurare le caratteristiche del carico utente da simulare.</p></td>
</tr>
<tr class="odd">
<td><p>LyncPerfTool. exe</p></td>
<td><p>Strumento di stress e prestazioni di Lync Server 2013. LyncPerfTool è lo strumento che simula il caricamento dell'utente.</p></td>
</tr>
<tr class="even">
<td><p>Default. TMX</p></td>
<td><p>Default. TMX è necessario per utilizzare lo strumento di registrazione di Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p>Script di provisioning di esempio</p></td>
<td><p>Questi esempi vengono utilizzati per configurare la topologia per l'esecuzione di test di carico, in base a scenari specifici</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

