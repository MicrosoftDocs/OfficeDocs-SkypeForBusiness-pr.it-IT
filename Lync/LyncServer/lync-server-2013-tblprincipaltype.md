---
title: 'Lync Server 2013: tblPrincipalType'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblPrincipalType
ms:assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558633(v=OCS.15)
ms:contentKeyID: 48183787
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 725d097e1e2e75b6430974a4f133cb5fa4130346
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976567"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipaltype-in-lync-server-2013"></a>tblPrincipalType in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-12_

tblPrincipalType contiene i tipi Principal per categorizzare il contenuto della tabella tblPrincipal.

### <a name="columns"></a>Colonne

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Colonna</th>
<th>Tipo</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ptypeID</p></td>
<td><p>smallint e non null</p></td>
<td><p>ID tipo di entità.</p></td>
</tr>
<tr class="even">
<td><p>ptypeDesc</p></td>
<td><p>nvarchar (256), not null</p></td>
<td><p>Descrizione del tipo.</p></td>
</tr>
<tr class="odd">
<td><p>ptypeIsSystemUser</p></td>
<td><p>bit, not null</p></td>
<td><p>True se il tipo corrisponde alle entità usate per scopi interni.</p></td>
</tr>
<tr class="even">
<td><p>ptypeIsUser</p></td>
<td><p>bit, not null</p></td>
<td><p>True se il tipo è un tipo di utente.</p></td>
</tr>
</tbody>
</table>


### <a name="key"></a>Chiave

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Colonna</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ptypeID</p></td>
<td><p>Chiave primaria.</p></td>
</tr>
</tbody>
</table>


### <a name="principal-values"></a>Valori principali

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>ID</th>
<th>Ruolo</th>
<th>Descrizione</th>
<th>Utente</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1</p></td>
<td><p>Qualsiasi</p></td>
<td><p>Entità generica con nessun tipo noto. Non usato nella tabella tblPrincipal.</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>2</p></td>
<td><p>AnyUser</p></td>
<td><p>Oggetto Principal generico di tipo utente. Non usato nella tabella tblPrincipal.</p></td>
<td><p>Sì</p></td>
</tr>
<tr class="odd">
<td><p>3</p></td>
<td><p>AnyGroup</p></td>
<td><p>Entità generica con semantica di gruppo. Non usato nella tabella tblPrincipal.</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>4</p></td>
<td><p>SystemUser</p></td>
<td><p>Principal usato internamente dal server di chat persistente.</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>5</p></td>
<td><p>Utente</p></td>
<td><p>Utente normale.</p></td>
<td><p>Sì</p></td>
</tr>
<tr class="even">
<td><p>8</p></td>
<td><p>DC</p></td>
<td><p>Controller di dominio Active Directory Domain Services.</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>9</p></td>
<td><p>Gruppo</p></td>
<td><p>Gruppo di sicurezza di Active Directory.</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>10</p></td>
<td><p>Cartella</p></td>
<td><p>Contenitore o unità organizzativa di Active Directory.</p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a>Vedere anche


[tblPrincipal in Lync Server 2013](lync-server-2013-tblprincipal.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

