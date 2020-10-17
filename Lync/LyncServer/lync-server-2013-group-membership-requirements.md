---
title: 'Lync Server 2013: requisiti di appartenenza ai gruppi'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Group membership requirements
ms:assetid: 01876843-8717-4e72-baf5-866ac8cceee6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204623(v=OCS.15)
ms:contentKeyID: 48183239
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 041bba31a4c8225a4326e3409475210a46261a70
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498773"
---
# <a name="group-membership-requirements-for-lync-server-2013"></a>Requisiti di appartenenza ai gruppi per Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-05_

Nella tabella seguente viene riepilogato il gruppo o i gruppi a cui appartiene una persona per poter eseguire correttamente l'installazione, la gestione e la risoluzione dei problemi di Lync Server 2013.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>File eseguibile di Lync Server 2013</th>
<th>Appartenenze ai gruppi richieste</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Setup.exe</strong> : eseguibile che avvia l'installazione degli strumenti di amministrazione di Lync Server 2013.</p></td>
<td><p>Membro del gruppo Administrators locale nel computer da cui viene eseguito il file. Membro del gruppo Domain Users per leggere le informazioni in servizi di dominio Active Directory. Questo livello di autorizzazione è necessario perché l'installazione automatica dei pacchetti MSI richiesti nel computer locale richiede privilegi che consentano la lettura e scrittura di risorse del computer locale protette, come le directory Programmi e l'hive Local Machine del Registro di sistema.</p>
<div>

> [!TIP]  
> È inoltre possibile delegare le autorizzazioni per l'installazione a utenti o gruppi a cui non si desidera concedere l'appartenenza al gruppo Domain Admins. Per informazioni dettagliate, vedere <A href="lync-server-2013-granting-setup-permissions.md">concessione di autorizzazioni di installazione in Lync Server 2013</A> nella documentazione relativa alla distribuzione.


</div></td>
</tr>
<tr class="even">
<td><p><strong>Deploy.exe</strong> – Chiamato da setup.exe, deploy.exe è responsabile per la distribuzione dei componenti software per i ruoli del server.</p></td>
<td><p>Membro del gruppo Administrators locale nel computer da cui viene eseguito il file. Membro del gruppo Domain Users per la lettura delle informazioni in Servizi di dominio Active Directory. Questo livello di autorizzazione è necessario perché l'installazione automatica dei pacchetti MSI richiesti nel computer locale richiede privilegi che consentano la lettura e scrittura di risorse del computer locale protette, come le directory Programmi e l'hive Local Machine del Registro di sistema. L'appartenenza al gruppo di RtcUniversalReadOnlyAdmins è necessaria per leggere l'archivio di gestione centrale.</p>
<div>

> [!NOTE]  
> Se si esegue il sistema operativo Windows Vista o Windows 7, viene richiesto dal controllo dell'account utente di procedere con l'installazione. Se si è connessi con un account utente standard, sarà necessario che qualcuno membro del gruppo Administrators locale fornisca le credenziali quando viene richiesto di specificare un account che dispone delle autorizzazioni per l'installazione del software.


</div></td>
</tr>
<tr class="odd">
<td><p><strong>Bootstrapper.exe</strong> – Chiamato da setup.exe, bootstrapper.exe è responsabile della distribuzione e configurazione dei ruoli del server.</p></td>
<td><p>Membro del gruppo Administrators locale nel computer da cui viene eseguito il file. Membro del gruppo RTCUniversalServerAdmins per l'esecuzione di Bootstrapper.exe. Membro del gruppo Utenti di dominio per la lettura di informazioni in AD DS. Questo livello di autorizzazione è necessario perché l'installazione automatica dei pacchetti MSI richiesti nel computer locale richiede privilegi che consentano la lettura e scrittura di risorse del computer locale protette, come le directory Programmi e l'hive Local Machine del Registro di sistema.</p></td>
</tr>
<tr class="even">
<td><p><strong>TopologyBuilder</strong> : interfaccia utente basata su procedura guidata per creare, visualizzare, modificare e convalidare le topologie di Lync Server 2013.</p></td>
<td><p>Membro del gruppo Administrators locale nel computer da cui viene eseguito il file per visualizzare la topologia. Membro del gruppo RTCUniversalServerAdmins per modificare le impostazioni di configurazione. Membro del gruppo RTCUniversalServerAdmins e del gruppo Domain Admins oppure membro del gruppo RTCUniversalServerAdmins (solo se al gruppo sono state concesse le autorizzazioni per la delega dell'installazione) per pubblicare la topologia. Per informazioni dettagliate sulla delega delle autorizzazioni di installazione per consentire ai membri del gruppo RTCUniversalServerAdmins di pubblicare la topologia senza essere membri del gruppo Domain Admins, vedere <a href="lync-server-2013-granting-setup-permissions.md">concessione di autorizzazioni di installazione in Lync Server 2013</a> nella documentazione relativa alla distribuzione.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AdminUIHost</strong> -interfaccia utente grafica basata sul Web per la gestione di Lync Server 2013.</p></td>
<td><p>Membro del gruppo CsAdministrator o di un altro ruolo di controllo di accesso basato sui ruoli a cui viene assegnata la specifica attività amministrativa. Il pannello di controllo di Lync Server 2013 implementa le modifiche di configurazione eseguendo i cmdlet di Lync Server 2013 Management Shell. Per un elenco di ruoli predefiniti e per i quali è consentito l'esecuzione dei membri cmdlet, vedere <a href="lync-server-2013-planning-for-role-based-access-control.md">Planning for Role-Based Access Control in Lync Server 2013</a> nella documentazione relativa alla pianificazione.</p></td>
</tr>
<tr class="even">
<td><p><strong>PowerShell.exe con lo</strong> strumento di amministrazione della riga di comando di lync Server 2013, con cmdlet specifici per la gestione di lync Server 2013.</p></td>
<td><p>Membro del gruppo CsAdministrator o di un altro ruolo di controllo di accesso basato sui ruoli a cui viene assegnato il cmdlet specifico. Per un elenco di ruoli predefiniti e per i quali è consentito l'esecuzione dei membri cmdlet, vedere <a href="lync-server-2013-planning-for-role-based-access-control.md">Planning for Role-Based Access Control in Lync Server 2013</a> nella documentazione relativa alla pianificazione.</p>
<p>Oppure membro di uno o più dei gruppi seguenti, a seconda del cmdlet:</p>
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

