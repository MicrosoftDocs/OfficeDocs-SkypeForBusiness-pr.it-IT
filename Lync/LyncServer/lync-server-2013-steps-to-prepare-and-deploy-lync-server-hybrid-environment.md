---
title: 'Lync Server 2013: Passaggi per la preparazione e la distribuzione di un ambiente ibrido di Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Steps to prepare and deploy Lync Server 2013 hybrid environment
ms:assetid: a50d4f7b-63f4-4663-af63-56ca87e4e3e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205157(v=OCS.15)
ms:contentKeyID: 48185060
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d239d7a57be1aa96dde1f9ccf30c2965de982017
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981040"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="steps-to-prepare-and-deploy-lync-server-2013-hybrid-environment"></a>Passaggi per la preparazione e la distribuzione di un ambiente ibrido di Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2016-12-08_

La tabella seguente elenca i passaggi necessari per preparare l'ambiente per una distribuzione ibrida con Skype for business online e Microsoft Office 365.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Completato?</th>
<th>Passaggio</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td></td>
<td><p>Creare un account del tenant per Office 365 e abilitare Lync Online</p></td>
<td><p>Informazioni su Office 365 e Lync online in <a href="https://go.microsoft.com/fwlink/p/?linkid=254980">office 365</a>.</p>
<p>Per verificare che l'ambiente sia pronto per Office 365, vedere requisiti di <a href="https://go.microsoft.com/fwlink/p/?linkid=401408">sistema</a>.</p>
<p>Per informazioni dettagliate sulla configurazione di Office 365, vedere <a href="https://go.microsoft.com/fwlink/p/?linkid=254982">Introduzione a office 365</a> e <a href="http://go.microsoft.com/fwlink/p/?linkid=254979">configurazione di Office 365</a>.</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Aggiungere il dominio e verificare la proprietà</p></td>
<td><p>Il dominio viene talvolta indicato anche come dominio di <em>vanità</em>. È necessario aggiungere il dominio al tenant di Office 365 e seguire la procedura per convalidare il dominio con Office 365. Questo per verificare di essere il proprietario del dominio.</p>
<p>Per aggiungere il dominio al tenant di Office 365, seguire la procedura descritta in <a href="https://go.microsoft.com/fwlink/p/?linkid=254983">aggiungere il proprio dominio a office 365</a>.</p>
<p>Completare tutti i passaggi di ogni sezione dell'argomento, inclusi &quot;i record DNS di modifica per i servizi di Office 365.&quot;</p></td>
</tr>
<tr class="odd">
<td></td>
<td><p>Verificare la disponibilità dell'ambiente</p></td>
<td><p>È possibile usare la configurazione guidata di Office 365 per distribuire Office 365. Per altre informazioni, vedere <a href="https://go.microsoft.com/fwlink/p/?linkid=254985">usare Setup Assistant per determinare la conformità di Office 365</a>.</p>
<p>Per informazioni dettagliate sull'uso dello strumento e sulla distribuzione di Office 365, vedere <a href="https://go.microsoft.com/fwlink/p/?linkid=257337">Guida alla distribuzione di office 365</a>.</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Preparare la sincronizzazione di Active Directory</p></td>
<td><p>La sincronizzazione di Active Directory consente di mantenere costantemente sincronizzata la Active Directory locale con Office 365. In questo modo è possibile creare versioni sincronizzate di ogni account utente e gruppo e consente inoltre la sincronizzazione dell'elenco indirizzi globale (GAL) dall'ambiente Microsoft Exchange Server locale a Microsoft Exchange Online.</p>
<div>

> [!IMPORTANT]  
> È necessario sincronizzare gli account degli annunci per tutti gli utenti di Lync dell'organizzazione tra le distribuzioni locale e online di Lync, anche se gli utenti non vengono spostati in Lync Online. Se non si sincronizzano tutti gli utenti, la comunicazione tra gli utenti locali e online dell'organizzazione potrebbe non funzionare come previsto.


</div>
<p>Per preparare l'ambiente per la sincronizzazione di Active Directory, seguire i passaggi descritti in <a href="https://go.microsoft.com/fwlink/p/?linkid=254988">Roadmap della sincronizzazione della directory</a>, inclusa la configurazione di Single Sign-on.</p></td>
</tr>
<tr class="odd">
<td></td>
<td><p>Creare certificati per Active Directory Federation Services (ADFS)</p></td>
<td><p>Sarà necessario creare i certificati usati per la Federazione delle identità con Office 365. Per altre informazioni, vedere la sezione "certificati del server federativo" del piano per e distribuire ADFS per l'uso con l'argomento Single Sign-on in <a href="https://go.microsoft.com/fwlink/p/?linkid=285376">elenco di controllo: usare ADFS per implementare e gestire Single Sign-on</a>.</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Assegnare certificati per ADFS</p></td>
<td><p>Dopo aver creato i certificati usati per la Federazione delle identità con Office 365, è necessario installarli e assegnarli.</p></td>
</tr>
<tr class="odd">
<td></td>
<td><p>Trasferire gli utenti pilota in Skype for business online</p></td>
<td><p>Dopo aver completato la procedura per preparare e configurare l'ambiente per Skype for business online, è possibile iniziare a spostare gli utenti pilota in Lync Online.</p>
<p>Vedere <a href="lync-server-2013-move-users-to-lync-online.md">trasferire utenti a Lync online in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Amministrazione degli utenti in una distribuzione ibrida</p></td>
<td><p>Per informazioni dettagliate sull'amministrazione degli utenti in una distribuzione ibrida, vedere <a href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">amministrazione degli utenti in una distribuzione ibrida di Lync Server 2013</a>.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

