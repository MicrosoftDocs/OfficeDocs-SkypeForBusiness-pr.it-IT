---
title: 'Lync Server 2013: Requisiti di appartenenza ai gruppi'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Group membership requirements
ms:assetid: 01876843-8717-4e72-baf5-866ac8cceee6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204623(v=OCS.15)
ms:contentKeyID: 48183239
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6aed308674cc334cfb8f3d4f214ce7388ae89fea
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974546"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="group-membership-requirements-for-lync-server-2013"></a>Requisiti di appartenenza ai gruppi per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-05_

La tabella seguente riepiloga il gruppo o i gruppi a cui deve appartenere una persona per poter installare, gestire e risolvere i problemi di Lync Server 2013.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Eseguibile di Lync Server 2013</th>
<th>Appartenenza a gruppi obbligatoria</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Setup. exe</strong> : eseguibile che avvia l'installazione degli strumenti di amministrazione di Lync Server 2013.</p></td>
<td><p>Membro del gruppo Administrators locale nel computer da cui viene eseguito l'eseguibile. Membro del gruppo Domain Users per leggere le informazioni in servizi di dominio Active Directory. Questo livello di autorizzazione è necessario perché l'installazione automatica dei pacchetti MSI obbligatori nel computer locale richiede privilegi che consentono la lettura e la scrittura in risorse di computer locali protette, ad esempio directory dei file di programma, e protette Registro di sistema, ad esempio l'hive del computer locale.</p>
<div>

> [!TIP]  
> È anche possibile delegare le autorizzazioni di configurazione per gli utenti o i gruppi a cui non si vuole concedere l'appartenenza al gruppo Domain Admins. Per informazioni dettagliate, vedere <A href="lync-server-2013-granting-setup-permissions.md">concessione delle autorizzazioni di configurazione in Lync Server 2013</A> nella documentazione relativa alla distribuzione.


</div></td>
</tr>
<tr class="even">
<td><p><strong>Deploy. exe</strong> : chiamato da Setup. exe, deploy. exe è responsabile della distribuzione dei componenti software per i ruoli del server.</p></td>
<td><p>Membro del gruppo Administrators locale nel computer da cui viene eseguito l'eseguibile. Membro del gruppo Domain Users per leggere le informazioni in servizi di dominio Active Directory. Questo livello di autorizzazione è necessario perché l'installazione automatica dei pacchetti MSI obbligatori nel computer locale richiede privilegi che consentono la lettura e la scrittura in risorse di computer locali protette, ad esempio directory dei file di programma, e protette Registro di sistema, ad esempio l'hive del computer locale. L'appartenenza al gruppo RtcUniversalReadOnlyAdmins è necessaria per leggere l'Central Management store.</p>
<div>

> [!NOTE]  
> Se si esegue il sistema operativo Windows Vista o Windows 7, verrà richiesto dal controllo dell'account utente per procedere con l'installazione. Se è stato effettuato l'accesso con un account utente standard, sarà necessario disporre di un membro del gruppo Administrators locale per specificare le credenziali quando viene richiesto un account con le autorizzazioni necessarie per installare il software.


</div></td>
</tr>
<tr class="odd">
<td><p><strong>Bootstrapper. exe</strong> : chiamato da Setup. exe, Bootstrapper. exe è responsabile della distribuzione e della configurazione dei ruoli del server.</p></td>
<td><p>Membro del gruppo Administrators locale nel computer da cui viene eseguito l'eseguibile. Membro del gruppo RTCUniversalServerAdmins per l'esecuzione di Bootstrapper. exe. Membro del gruppo Domain Users per leggere le informazioni in servizi di dominio Active Directory. Questo livello di autorizzazione è necessario perché l'installazione automatica dei pacchetti MSI obbligatori nel computer locale richiede privilegi che consentono la lettura e la scrittura in risorse di computer locali protette, ad esempio directory dei file di programma, e protette Registro di sistema, ad esempio l'hive del computer locale.</p></td>
</tr>
<tr class="even">
<td><p><strong>TopologyBuilder</strong> -interfaccia utente guidata da Wizard per creare, visualizzare, modificare e convalidare le topologie di Lync Server 2013.</p></td>
<td><p>Membro del gruppo Administrators locale nel computer da cui viene eseguito l'eseguibile per visualizzare la topologia. Membro del gruppo RTCUniversalServerAdmins per modificare le impostazioni di configurazione. Membro del gruppo RTCUniversalServerAdmins e Domain Admins o membro del gruppo RTCUniversalServerAdmins (solo se al gruppo sono state concesse le autorizzazioni di configurazione del delegato) per pubblicare la topologia. Per informazioni dettagliate sulla delega delle autorizzazioni di configurazione per consentire ai membri del gruppo RTCUniversalServerAdmins di pubblicare la topologia senza essere membri del gruppo Domain Admins, vedere <a href="lync-server-2013-granting-setup-permissions.md">concessione delle autorizzazioni di configurazione in Lync Server 2013</a> nella documentazione relativa alla distribuzione.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AdminUIHost</strong> -interfaccia utente grafica basata sul Web per la gestione di Lync Server 2013.</p></td>
<td><p>Membro del gruppo CsAdministrator o membro di un altro ruolo di controllo di accesso basato sui ruoli (RBAC) a cui è assegnata l'attività amministrativa specifica. Il pannello di controllo di Lync Server 2013 implementa le modifiche alla configurazione eseguendo i cmdlet di Lync Server 2013 Management Shell. Per un elenco di ruoli predefiniti e i membri dei cmdlet sono consentiti per l'esecuzione, vedere <a href="lync-server-2013-planning-for-role-based-access-control.md">pianificazione per il controllo dell'accesso basato sui ruoli in Lync Server 2013</a> nella documentazione relativa alla pianificazione.</p></td>
</tr>
<tr class="even">
<td><p><strong>PowerShell. exe con il modulo Lync server 2013 caricato</strong> : strumento di amministrazione della riga di comando con cmdlet specifici per la gestione di lync Server 2013.</p></td>
<td><p>Membro del gruppo CsAdministrator o membro di un altro ruolo RBAC a cui è stato assegnato il cmdlet specifico. Per un elenco di ruoli predefiniti e i membri dei cmdlet sono consentiti per l'esecuzione, vedere <a href="lync-server-2013-planning-for-role-based-access-control.md">pianificazione per il controllo dell'accesso basato sui ruoli in Lync Server 2013</a> nella documentazione relativa alla pianificazione.</p>
<p>In alternativa, membro di uno o più dei gruppi seguenti, a seconda del cmdlet:</p>
<ul>
<li><p>RTCUniversalServerAdmins</p></li>
<li><p>RTCUniversalUserAdmins</p></li>
<li><p>RTCUniversalReadOnlyAdmins</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

