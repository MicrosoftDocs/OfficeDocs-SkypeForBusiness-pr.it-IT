---
title: "Lync Server 2013: processo di distribuzione per l'applicazione di annunci"
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
ms.openlocfilehash: dcb56f197a32403d1207cf0a15d47e0459fc41bf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762574"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-the-announcement-application-in-lync-server-2013"></a>Processo di distribuzione per l'applicazione di annuncio in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-12_

Questa sezione fornisce una panoramica dei passaggi necessari per la distribuzione dell'applicazione di annunci. È necessario distribuire Enterprise Voice prima di configurare gli annunci. I componenti necessari per l'applicazione di annuncio vengono installati e abilitati quando si distribuisce VoIP aziendale.

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
<th>Documentazione di distribuzione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Configurare le impostazioni degli annunci</p></td>
<td><ul>
<li><p>Creare l'annuncio registrando e caricando i file audio o tramite sintesi vocale.</p></li>
<li><p>Configurare gli intervalli di numeri non assegnati nella tabella dei numeri non assegnati e associarli con l'annuncio appropriato.</p></li>
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
<td><p>Verificare la distribuzione degli annunci</p></td>
<td><p>Eseguire il test ascoltando gli annunci per verificare che la configurazione funzioni come previsto.</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-optional-verify-announcement-deployment.md">Opzionale Verificare la distribuzione degli annunci in Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

