---
title: 'Lync Server 2013: processo di distribuzione per Call Park'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment process for Call Park
ms:assetid: 2000d672-a85f-4262-9d69-0bee9ae3709a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398283(v=OCS.15)
ms:contentKeyID: 48183586
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bab02c8cfbf0f1ca71aff85c8a71a2bcb20ee3fd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982121"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-call-park-in-lync-server-2013"></a>Processo di distribuzione per Call Park in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-25_

Questa sezione fornisce una panoramica dei passaggi necessari per la distribuzione dell'applicazione Call Park. È necessario distribuire Enterprise Edition o Standard Edition con Enterprise Voice prima di configurare Call Park. I componenti necessari per il parcheggio delle chiamate vengono installati e abilitati quando si distribuisce VoIP aziendale.

### <a name="call-park-deployment-process"></a>Processo di distribuzione di Call Park

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
<th>Documentazione di distribuzione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Configurare gli intervalli di orbit del parcheggio delle chiamate nella tabella Orbit</p></td>
<td><p>Usa il pannello di controllo di Lync Server o il cmdlet <strong>New-CsCallParkOrbit</strong> per creare gli intervalli di Orbit nella tabella Orbit di Call Park e associarli al servizio applicazione che ospita l'applicazione Parcheggio di chiamata.</p>
<div>

> [!NOTE]  
> Per una perfetta integrazione con i dial plan esistenti, gli intervalli orbit sono in genere configurati come blocco di estensioni virtuali. L'assegnazione di numeri DID (Direct Inward Dialing) come numeri di orbita nella tabella Orbit di parcheggio delle chiamate non è supportata.


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-create-or-modify-a-call-park-orbit-range.md">Creare o modificare un intervallo orbit di Call Park in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Configurare le impostazioni di Parcheggio di chiamata</p></td>
<td><p>Usa il cmdlet <strong>Set-CsCpsConfiguration</strong> per configurare le impostazioni di Call Park. Come minimo, ti consigliamo di configurare l'opzione <strong>OnTimeoutURI</strong> per configurare la destinazione di fallback da usare in caso di timeout di una chiamata parcheggiata. È anche possibile configurare le impostazioni seguenti:</p>
<ul>
<li><p>Opzionale <strong>EnableMusicOnHold</strong> per abilitare o disabilitare la musica in attesa.</p></li>
<li><p>Opzionale <strong>MaxCallPickupAttempts</strong> per determinare il numero di squilli di una chiamata parcheggiata di nuovo al telefono che risponde prima di inoltrare la chiamata all'URI (Uniform Resource Identifier) di fallback.</p></li>
<li><p>Opzionale <strong>CallPickupTimeoutThreshold</strong> per determinare la quantità di tempo che trascorre dopo il parcheggio di una chiamata prima che ritorni al telefono in cui è stata risolta la chiamata.</p></li>
</ul></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-call-park-settings.md">Configurare le impostazioni di Call Park in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Facoltativamente, personalizzare la musica in attesa</p></td>
<td><p>Usare il cmdlet <strong>Set-CsCallParkServiceMusicOnHoldFile</strong> per personalizzare e caricare un file audio, se non si vuole usare la musica predefinita in attesa.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-customize-call-park-music-on-hold.md">Personalizzare la musica di Call Park in attesa in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Configurare i criteri vocali per abilitare il parcheggio delle chiamate per gli utenti</p></td>
<td><p>Utilizzare il pannello di controllo di Lync Server o il cmdlet <strong>Set-CsVoicePolicy</strong> con l'opzione <strong>EnableCallPark</strong> per abilitare il parcheggio di chiamata per gli utenti nel criterio vocale.</p>
<div>

> [!NOTE]  
> Per impostazione predefinita, il parcheggio delle chiamate è disabilitato per tutti gli utenti.


</div>
<div>

> [!NOTE]  
> Se si hanno più criteri vocali, verificare che la proprietà EnableCallPark sia impostata per ogni criterio vocale, non solo per i criteri predefiniti.


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsUserAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-enable-call-park-for-users.md">Abilitare il parcheggio delle chiamate per gli utenti in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Verificare le regole di normalizzazione per il parcheggio di chiamata</p></td>
<td><p>Le orbite del parcheggio delle chiamate non devono essere normalizzate. Verificare che le regole di normalizzazione non includano alcuno degli intervalli di orbita. Se necessario, creare regole di normalizzazione aggiuntive per impedire la normalizzazione delle orbite.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-verify-normalization-rules-for-call-park.md">Verificare le regole di normalizzazione per Call Park in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Verificare la distribuzione di Call Park</p></td>
<td><p>Verificare il parcheggio e il recupero delle chiamate per verificare che la configurazione funzioni come previsto.</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-optional-verify-call-park-deployment.md">Opzionale Verificare la distribuzione di Call Park in Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

