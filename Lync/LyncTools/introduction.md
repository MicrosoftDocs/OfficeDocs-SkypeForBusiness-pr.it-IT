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
ms.openlocfilehash: 893205127b6b1ccba958a0882c3aa0d1360a7c06
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730566"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="introduction"></a>Introduzione

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-24_

Lo strumento di stress e prestazioni di Lync Server 2013 (denominato LyncPerfTool) può simulare il caricamento degli utenti dei tipi seguenti:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Messaggistica istantanea (IM) e presenza</p></td>
<td><p>Audioconferenza</p></td>
</tr>
<tr class="even">
<td><p>Condivisione applicazioni</p></td>
<td><p>Voice over IP (VoIP), inclusa la simulazione PSTN (Public Switched Telephone Network)</p></td>
</tr>
<tr class="odd">
<td><p>Servizi di conferenza client di Web Access</p></td>
<td><p>Assistente di Microsoft Lync 2013</p></td>
</tr>
<tr class="even">
<td><p>Response Group</p></td>
<td><p>Espansione della lista di distribuzione</p></td>
</tr>
<tr class="odd">
<td><p>Query di download e Rubrica per la Rubrica</p></td>
<td><p>Chiamate e profilo della posizione avanzati di 9-1-1 (E9-1-1) (dial plan)</p></td>
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


Lo strumento per lo stress e le prestazioni di Lync Server 2013 supporta la generazione di carichi tra pool e la Federazione tramite la configurazione avanzata.

Lo strumento non simula inoltre il caricamento degli utenti per i client seguenti:

  - Office Live Meeting 2007

  - Chat persistente di Lync 2013

Di conseguenza, lo strumento di analisi dello stress e delle prestazioni di Lync Server 2013 non supporta i test dei componenti seguenti:

  - Chat persistente di Lync 2013

  - Scenari di integrazione di Exchange

<div>

## <a name="applications-and-files-included-with-the-lync-server-2013-stress-and-performance-tool"></a>Applicazioni e file inclusi nello strumento per lo stress e le prestazioni di Lync Server 2013

Le applicazioni seguenti sono incluse nello strumento per lo stress e le prestazioni di Lync Server 2013:


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
<td><p>Strumento di provisioning degli utenti di Lync Server 2013. Questo strumento viene usato per creare utenti e contatti.</p></td>
</tr>
<tr class="even">
<td><p>UserProfileGenerator. exe</p></td>
<td><p>Strumento di configurazione del caricamento di Lync Server 2013. Questo strumento viene usato per configurare le caratteristiche del carico utente da simulare.</p></td>
</tr>
<tr class="odd">
<td><p>LyncPerfTool. exe</p></td>
<td><p>Strumento di stress e prestazioni di Lync Server 2013. LyncPerfTool è lo strumento che simula il caricamento dell'utente.</p></td>
</tr>
<tr class="even">
<td><p>Default. TMX</p></td>
<td><p>Per usare lo strumento di registrazione di Lync Server 2013 è necessario default. TMX.</p></td>
</tr>
<tr class="odd">
<td><p>Esempio di provisioning di script</p></td>
<td><p>Questi esempi vengono usati per configurare la topologia per l'eseguire test di carico, in base a scenari specifici</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

