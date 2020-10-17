---
title: 'Lync Server 2013: modifiche allo schema in Lync Server 2013'
description: 'Lync Server 2013: modifiche allo schema in Lync Server 2013.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Schema changes in Lync Server 2013
ms:assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398944(v=OCS.15)
ms:contentKeyID: 48185575
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e914de48ace80fd2611f2d05b092894b11c534a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557152"
---
# <a name="schema-changes-in-lync-server-2013"></a>Modifiche dello schema in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-18_

Prima di distribuire e utilizzare Lync Server 2013, è necessario preparare i servizi di dominio Active Directory estendendo lo schema. Le estensioni dello schema aggiungono le classi e gli attributi richiesti da Lync Server 2013.

Lync Server 2013 richiede diverse nuove classi e attributi e modifica alcune classi e attributi esistenti. Inoltre, molte informazioni di configurazione per Lync Server 2013 sono archiviate nell'archivio di gestione centrale invece che in servizi di dominio Active Directory come nelle versioni precedenti. Le informazioni seguenti sono ancora memorizzate in servizi di dominio Active Directory in Lync Server 2013:

  - **Estensioni dello schema**:
    
      - Estensioni degli oggetti utente
    
      - Estensioni per le classi di Office Communications Server 2007 e Office Communications Server 2007 R2 per mantenere la compatibilità con le versioni precedenti supportate

<!-- end list -->

  - **Dati** (memorizzati nello schema esteso di Lync Server e nelle classi dello schema esistenti):
    
      - URI (Uniform Resource Identifier) SIP dell'utente e altre impostazioni utente
    
      - Oggetti contatto per applicazioni quali Response Group e Operatore Conferenza
    
      - Puntatore all'archivio di gestione centrale
    
      - Account di autenticazione Kerberos (un oggetto computer facoltativo)

In questo argomento vengono descritte le modifiche allo schema di Active Directory richieste da Lync Server 2013. Non vengono descritte le modifiche allo schema introdotte dalle versioni precedenti di Office Communications Server. Per un elenco delle classi e delle relative descrizioni, vedere [classi e descrizioni di schemi in Lync Server 2013](lync-server-2013-schema-classes-and-descriptions.md). Per un elenco degli attributi e delle relative descrizioni, vedere [attributi e descrizioni dello schema in Lync Server 2013](lync-server-2013-schema-attributes-and-descriptions.md). Per un elenco di classi con gli attributi che possono contenere, vedere [schema Attributes by Class in Lync Server 2013](lync-server-2013-schema-attributes-by-class.md).

Il prefisso msRTCSIP identifica le classi e gli attributi specifici di Lync Server.

<div>

## <a name="new-active-directory-attributes"></a>Nuovi attributi di Active Directory

Nella tabella seguente vengono descritti gli attributi di Active Directory aggiunti da Lync Server 2013.

### <a name="attributes-added-by-lync-server-2013"></a>Attributi aggiunti da Lync Server 2013

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Attributo</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>msExchUserHoldPolicies</p></td>
<td><p>Questo attributo multivalore contiene gli identificatori per i criteri di blocco che si applicano all'utente. I criteri di conservazione conservano gli elementi della cassetta postale per l'utente per tutta la durata del blocco. Questo attributo è condiviso con Exchange 2013.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UserRoutingGroupId</p></td>
<td><p>Questo è l'ID del gruppo di routing SIP. Gli utenti dello stesso gruppo registreranno lo stesso front end server.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MirrorBackEndServer</p></td>
<td><p>Questo attributo viene utilizzato per archiviare il backend di SQL Server con mirroring utilizzato dal pool Front end.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="modified-active-directory-classes"></a>Classi di Active Directory modificate

Nella tabella seguente vengono descritte le classi di Active Directory modificate da Lync Server 2013.

### <a name="classes-modified-by-lync-server-2013"></a>Classi modificate da Lync Server 2013

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Classe</th>
<th>Modifica</th>
<th>Classe o attributo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Utente</p></td>
<td><p>add: mayContain</p>
<p>add: mayContain</p></td>
<td><p>ProxyAddresses</p>
<p>msRTCSIP-UserRoutingGroupId</p></td>
</tr>
<tr class="even">
<td><p>Contatto</p></td>
<td><p>add: mayContain</p>
<p>add: mayContain</p></td>
<td><p>ProxyAddresses</p>
<p>msRTCSIP-UserRoutingGroupId</p></td>
</tr>
<tr class="odd">
<td><p>Mail-Recipient</p></td>
<td><p>add: mayContain</p></td>
<td><p>msExchUserHoldPolicies</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-GlobalTopologySetting</p></td>
<td><p>add: mayContain</p></td>
<td><p>msRTCSIP-MirrorBackEndServer</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

