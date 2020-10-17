---
title: 'Lync Server 2013: passaggi per la preparazione e la distribuzione di un ambiente ibrido di Lync Server'
description: "Lync Server 2013: passaggi per la preparazione e la distribuzione dell'ambiente ibrido di Lync Server."
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Steps to prepare and deploy Lync Server 2013 hybrid environment
ms:assetid: a50d4f7b-63f4-4663-af63-56ca87e4e3e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205157(v=OCS.15)
ms:contentKeyID: 48185060
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ffb791a8a45b2220d8987c8d688f346447747c00
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546332"
---
# <a name="steps-to-prepare-and-deploy-lync-server-2013-hybrid-environment"></a>Passaggi per la preparazione e la distribuzione dell'ambiente ibrido di Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2016-12-08_

Nella tabella seguente sono elencati i passaggi necessari per preparare l'ambiente per una distribuzione ibrida con Skype for business online e Microsoft Office 365.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Operazione completata?</th>
<th>Passaggio</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td></td>
<td><p>Creare un account tenant per Office 365 e abilitare Lync Online</p></td>
<td><p>Informazioni su Office 365 e Lync online in <a href="https://go.microsoft.com/fwlink/p/?linkid=254980">office 365</a>.</p>
<p>Per assicurarsi che l'ambiente sia pronto per Office 365, vedere i <a href="https://go.microsoft.com/fwlink/p/?linkid=401408">requisiti di sistema</a>.</p>
<p>Per informazioni dettagliate sulla configurazione di Office 365, vedere <a href="https://go.microsoft.com/fwlink/p/?linkid=254982">Guida introduttiva a office 365</a> e <a href="https://go.microsoft.com/fwlink/p/?linkid=254979">configurazione di Office 365</a>.</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Aggiungere il dominio e verificare la proprietà</p></td>
<td><p>Il dominio è talvolta denominato anche <em>dominio Vanity</em>. È necessario aggiungere il proprio dominio all'organizzazione di Office 365, quindi seguire la procedura per convalidare il dominio con Office 365. In questo modo si conferma che si è il proprietario del dominio.</p>
<p>Per aggiungere il dominio alla propria organizzazione di Office 365, attenersi alla procedura descritta in <a href="https://go.microsoft.com/fwlink/p/?linkid=254983">aggiungere il proprio dominio a office 365</a>.</p>
<p>Completare tutti i passaggi di ogni sezione dell'argomento, tra cui la &quot; modifica dei record DNS per i servizi di Office 365.&quot;</p></td>
</tr>
<tr class="odd">
<td></td>
<td><p>Verificare la conformità dell'ambiente</p></td>
<td><p>È possibile utilizzare l'assistente per l'installazione di Office 365 per la distribuzione di Office 365. Per ulteriori informazioni, vedere <a href="https://go.microsoft.com/fwlink/p/?linkid=254985">utilizzo di Setup Assistant per determinare la conformità di Office 365</a>.</p>
<p>Per informazioni dettagliate sull'utilizzo dello strumento e sulla distribuzione di Office 365, vedere <a href="https://go.microsoft.com/fwlink/p/?linkid=257337">Guida alla distribuzione di office 365</a>.</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Preparare la sincronizzazione con Active Directory</p></td>
<td><p>La sincronizzazione di Active Directory mantiene continuamente sincronizzata la propria Active Directory locale con Office 365. In questo modo è possibile creare versioni sincronizzate di ogni account utente e gruppo, nonché abilitare la sincronizzazione dell'elenco indirizzi globale (GAL) dall'ambiente Microsoft Exchange Server locale a Microsoft Exchange Online.</p>
<div>

> [!IMPORTANT]  
> È necessario sincronizzare gli account di Active Directory per tutti gli utenti di Lync nell'organizzazione tra le distribuzioni di Lync locali e online, anche se gli utenti non vengono spostati in Lync Online. Se non si sincronizzano tutti gli utenti, la comunicazione tra gli utenti locali e quelli online nell'organizzazione potrebbe non funzionare come previsto.


</div>
<p>Per preparare l'ambiente per la sincronizzazione di Active Directory, eseguire i passaggi descritti in <a href="https://go.microsoft.com/fwlink/p/?linkid=254988">Roadmap della sincronizzazione della directory</a>, inclusa la configurazione di Single Sign-on.</p></td>
</tr>
<tr class="odd">
<td></td>
<td><p>Creare certificati per Active Directory Federation Services (AD FS)</p></td>
<td><p>Sarà necessario creare i certificati utilizzati per la Federazione delle identità con Office 365. Per ulteriori informazioni, vedere la sezione "certificati del server federativo" dell'argomento piano per e deploy AD FS per l'utilizzo con Single Sign-on in <a href="https://go.microsoft.com/fwlink/p/?linkid=285376">elenco di controllo: utilizzare ADFS per implementare e gestire l'accesso Single Sign-on</a>.</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Assegnare certificati per ADFS</p></td>
<td><p>Dopo aver creato i certificati utilizzati per la Federazione delle identità con Office 365, è necessario installarli e assegnarli.</p></td>
</tr>
<tr class="odd">
<td></td>
<td><p>Spostare gli utenti pilota in Skype for business online</p></td>
<td><p>Dopo aver completato la procedura per preparare e configurare l'ambiente per Skype for business online, è possibile iniziare a spostare gli utenti pilota in Lync Online.</p>
<p>Vedere <a href="lync-server-2013-move-users-to-lync-online.md">Move users to Lync online in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Amministrazione degli utenti in una distribuzione ibrida</p></td>
<td><p>Per informazioni dettagliate su come amministrare gli utenti in una distribuzione ibrida, vedere <a href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">amministrazione degli utenti in una distribuzione ibrida di Lync Server 2013</a>.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

