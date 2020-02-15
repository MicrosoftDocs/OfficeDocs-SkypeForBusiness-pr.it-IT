---
title: "Lync Server 2013: processo di distribuzione per l'applicazione annuncio"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for the Announcement application
ms:assetid: 72c66249-c4ce-48ce-b1b9-90ebf77d7805
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398545(v=OCS.15)
ms:contentKeyID: 48184500
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 55e0c65bfbbed55a8d7f9c3be4f7a586581c2307
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042253"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-the-announcement-application-in-lync-server-2013"></a>Processo di distribuzione per l'applicazione annuncio in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-12_

In questa sezione viene fornita una panoramica dei passaggi necessari per la distribuzione dell'applicazione annuncio. Prima di configurare gli annunci, è necessario distribuire VoIP aziendale. I componenti richiesti dall'applicazione annuncio sono installati e abilitati quando si distribuisce VoIP aziendale.

### <a name="announcement-deployment-process"></a>Processo di distribuzione degli annunci

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Fase</th>
<th>Passaggi</th>
<th>Ruoli</th>
<th>Documentazione relativa alla distribuzione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Configurazione delle impostazioni degli annunci</p></td>
<td><ul>
<li><p>Creare l'annuncio registrando e caricando file audio o tramite sintesi vocale.</p></li>
<li><p>Configurare gli intervalli di numeri non assegnati nella tabella dei numeri non assegnati e associarli all'annuncio appropriato.</p></li>
</ul></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p>
<p>CsViewOnlyAdministrator</p></td>
<td><p><a href="lync-server-2013-create-an-announcement.md">Creare un annuncio in Lync Server 2013</a></p>
<p><a href="lync-server-2013-configure-the-unassigned-number-table.md">Configurare la tabella dei numeri non assegnati in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Verifica della distribuzione degli annunci</p></td>
<td><p>Testare ascoltando annunci per verificare che la configurazione funzioni nel modo previsto.</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-optional-verify-announcement-deployment.md">Optional Verificare la distribuzione degli annunci in Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

