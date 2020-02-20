---
title: 'Lync Server 2013: processo di distribuzione per il parcheggio di chiamata'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for Call Park
ms:assetid: 2000d672-a85f-4262-9d69-0bee9ae3709a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398283(v=OCS.15)
ms:contentKeyID: 48183586
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2ff40921e75eb9b2a48c591f3f5df2ba09891627
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137195"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-call-park-in-lync-server-2013"></a>Processo di distribuzione per il parcheggio di chiamata in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-25_

In questa sezione viene fornita una panoramica dei passaggi necessari per la distribuzione dell'applicazione Parcheggio di chiamata. Prima di configurare il parcheggio di chiamata, è necessario distribuire Enterprise Edition o Standard Edition con VoIP aziendale. I componenti richiesti dal parcheggio di chiamata vengono installati e abilitati quando si distribuisce VoIP aziendale.

### <a name="call-park-deployment-process"></a>Processo di distribuzione di Parcheggio di chiamata

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
<th>Gruppi e ruoli obbligatori</th>
<th>Documentazione sulla distribuzione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Configurare gli intervalli dei codici orbit di parcheggio di chiamata nella tabella dei codici orbit</p></td>
<td><p>Utilizzare il pannello di controllo di Lync Server o il cmdlet <strong>New-CsCallParkOrbit</strong> per creare gli intervalli di Orbit nella tabella orbit del parcheggio di chiamata e associarli al servizio dell'applicazione che ospita l'applicazione Parcheggio di chiamata.</p>
<div>

> [!NOTE]  
> Per l'integrazione completa con i dial plan esistenti, gli intervalli dei codici orbit in genere sono configurati come un blocco di estensioni virtuali. L'assegnazione di numeri Direct Inward Dialing (DID) come numeri di codici orbit nella tabella dei codici orbit di parcheggio di chiamata non è supportata.


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-create-or-modify-a-call-park-orbit-range.md">Creare o modificare un intervallo di codici orbit del parcheggio di chiamata in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Configurare le impostazioni del parcheggio di chiamata</p></td>
<td><p>Utilizzare il cmdlet <strong>Set-CsCpsConfiguration</strong> per configurare le impostazioni del parcheggio di chiamata. È consigliabile configurare almeno l'opzione <strong>OnTimeoutURI</strong> per configurare la destinazione di fallback da utilizzare quando si verifica il timeout di una chiamata parcheggiata. È inoltre possibile configurare le impostazioni seguenti:</p>
<ul>
<li><p>(Facoltativo) <strong>EnableMusicOnHold</strong> per abilitare o disabilitare la musica di attesa.</p></li>
<li><p>(Facoltativo) <strong>MaxCallPickupAttempts</strong> per determinare il numero di squilli sul telefono di destinazione di una chiamata parcheggiata prima dell'inoltro all'URI (Uniform Resource Identifier) di fallback.</p></li>
<li><p>(Facoltativo) <strong>CallPickupTimeoutThreshold</strong> per determinare quanto tempo deve trascorrere dopo che una chiamata è stata parcheggiata prima che squilli sul telefono da cui è stata effettuata la risposta.</p></li>
</ul></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-call-park-settings.md">Configurare le impostazioni del parcheggio di chiamata in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Se lo si desidera, personalizzare la musica di attesa</p></td>
<td><p>Utilizzare il cmdlet <strong>Set-CsCallParkServiceMusicOnHoldFile</strong> per personalizzare e caricare un file audio, se non si desidera utilizzare la musica di attesa predefinita.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-customize-call-park-music-on-hold.md">Personalizzare la musica del parcheggio di chiamata in attesa in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Configurare il criterio vocale per abilitare il parcheggio di chiamata per gli utenti</p></td>
<td><p>Utilizzare il pannello di controllo di Lync Server o il cmdlet <strong>Set-CsVoicePolicy</strong> con l'opzione <strong>EnableCallPark</strong> per abilitare il parcheggio di chiamata per gli utenti nel criterio vocale.</p>
<div>

> [!NOTE]  
> Per impostazione predefinita, il parcheggio di chiamata è disabilitato per tutti gli utenti.


</div>
<div>

> [!NOTE]  
> Se si dispone di più criteri vocali, verificare che la proprietà EnableCallPark sia impostata per ogni criterio vocale e non solo per quello predefinito.


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsUserAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-enable-call-park-for-users.md">Abilitare il parcheggio di chiamata per gli utenti in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Verificare le regole di normalizzazione per il parcheggio di chiamata</p></td>
<td><p>I codici orbit di Parcheggio di chiamata non devono essere normalizzati. Verificare che le regole di normalizzazione non includano alcun intervallo dei codici orbit. Se necessario, creare regole di normalizzazione aggiuntive per impedire che vengano normalizzati i codici orbit.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-verify-normalization-rules-for-call-park.md">Verificare le regole di normalizzazione per il parcheggio di chiamata in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Verificare la distribuzione del parcheggio di chiamata</p></td>
<td><p>Verifica del parcheggio e del recupero delle chiamate per verificare che la configurazione funzioni come previsto.</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-optional-verify-call-park-deployment.md">Optional Verificare la distribuzione del parcheggio di chiamata in Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

