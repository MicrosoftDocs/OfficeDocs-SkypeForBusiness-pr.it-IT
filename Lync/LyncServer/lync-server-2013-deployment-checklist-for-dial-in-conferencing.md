---
title: Elenco di controllo di distribuzione di Lync Server 2013 per le conferenze telefoniche con accesso esterno
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for dial-in conferencing
ms:assetid: 9c8d3ebe-0d70-4a61-9bd0-522286cddd9a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412726(v=OCS.15)
ms:contentKeyID: 48184987
ms.date: 10/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dc1cbf5d732cbd30ac7d59e3bcedafadb0759ce2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135923"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-dial-in-conferencing-in-lync-server-2013"></a>Elenco di controllo di distribuzione per le conferenze telefoniche con accesso esterno in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-10-03_

I componenti necessari per le conferenze telefoniche con accesso esterno vengono distribuiti quando si distribuisce il carico di lavoro per le conferenze. Prima di poter configurare le conferenze telefoniche con accesso esterno, è necessario distribuire VoIP aziendale o Mediation Server e un gateway PSTN (Public Switched Telephone Network).

Tutti i passaggi descritti nella tabella seguente devono essere eseguiti prima che gli utenti possano comporre dalla rete PSTN per partecipare a una conferenza audio/video.

<div>


> [!NOTE]  
> Se si esegue la migrazione da Office Communications Server 2007 R2, è necessario applicare gli aggiornamenti più recenti all'ambiente Office Communications Server 2007 R2 prima di distribuire le conferenze telefoniche con accesso esterno.



</div>

### <a name="dial-in-conferencing-deployment-process"></a>Processo di distribuzione delle conferenze telefoniche con accesso esterno

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
<th>Autorizzazioni</th>
<th>Documentazione relativa alla distribuzione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Creare una topologia che includa il carico di lavoro per le conferenze, tra cui un Mediation Server e un gateway PSTN, e distribuire il pool Front end o il server Standard Edition</strong></p></td>
<td><ol>
<li><p>Eseguire Generatore di topologie per configurare la topologia. Durante la configurazione della topologia, selezionare l'opzione per le conferenze telefoniche con accesso esterno.</p></li>
<li><p>Pubblicare la topologia e distribuire il pool Front end o il server Standard Edition.</p></li>
<li><p>Se necessario, creare un Mediation Server autonomo e associarlo a un gateway PSTN.</p>
<div>

> [!NOTE]  
> Questo passaggio è obbligatorio solo se non si distribuisce VoIP aziendale e non si colloca il Mediation Server con l'Enterprise EditionFront End Server o il server Standard Edition. Se si distribuisce VoIP aziendale, vengono installati e configurati Mediation Server e gateway PSTN come parte della distribuzione di VoIP aziendale. Se si colloca il Mediation Server, è necessario installare e configurare il Mediation Server come parte della distribuzione del pool Front end o del server Standard Edition.


</div></li>
</ol></td>
<td><p>Domain Admins</p>
<p>RTCUniversalServerAdmins</p>
<p>Amministratore</p></td>
<td><ul>
<li><p><a href="lync-server-2013-deploying-lync-server.md">Distribuzione di Lync Server 2013</a></p></li>
<li><p>Per creare un pool di Mediation Server autonomo: <a href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">distribuzione di Mediation Server e definizione di peer in Lync Server 2013</a></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Configurare i dial plan</strong></p></td>
<td><p>Un dial plan è un insieme di regole di normalizzazione dei numeri di telefono che trasportano il numero di telefono composto da una posizione specifica a un singolo formato standard (E. 164) ai fini dell'autorizzazione del telefono e del routing delle chiamate. Lo stesso numero di telefono composto da diverse posizioni può, in base ai rispettivi dial plan, risolvere i diversi numeri E. 164, a seconda dei casi. Se si distribuisce VoIP aziendale, si configurano i dial plan nell'ambito della distribuzione ed è necessario assicurarsi che i dial plan siano anche in grado di ospitare le conferenze telefoniche con accesso esterno. Se non si esegue la distribuzione di VoIP aziendale, è necessario configurare i dial plan per le conferenze telefoniche con accesso esterno.</p>
<p>Utilizzare il pannello di controllo di Lync Server 2013 o Lync Server Management Shell per configurare i dial plan come indicato di seguito:</p>
<ol>
<li><p>Creare uno o più dial plan per instradare i numeri di telefono di accesso esterno.</p></li>
<li><p>Assegnare un dial plan predefinito per ogni pool. Impostare l' <strong>area di conferenza telefonica con accesso esterno</strong> sulla posizione geografica a cui si applica il dial plan. L'area associa il dial plan ai numeri di accesso esterno.</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md">Configurare i dial plan per le conferenze telefoniche con accesso esterno in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>Verificare che i dial plan siano aree assegnate</strong></p></td>
<td><p>Eseguire i cmdlet <strong>Get-CsDialPlan</strong> e <strong>Set-CsDialPlan</strong> per assicurarsi che tutti i dial plan dispongano di un'area geografica assegnata.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-make-sure-dial-plans-have-assigned-regions.md">Assicurarsi che i dial plan Lync Server 2013 abbiano assegnato aree geografiche</a></p></td>
</tr>
<tr class="even">
<td><p><strong>Optional Verificare o modificare i requisiti del PIN (User Personal Identification Number)</strong></p></td>
<td><p>Utilizzare il pannello di controllo di Lync Server 2013 o Lync Server Management Shell per visualizzare o modificare il <strong>criterio PIN</strong>per le conferenze. È possibile specificare la lunghezza minima del PIN, il numero massimo di tentativi di accesso, la scadenza del PIN e la possibilità che i modelli comuni siano consentiti.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-optional-verify-pin-policy-settings.md">Optional Verificare le impostazioni del criterio PIN in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>Configurare i criteri di conferenza per il supporto delle conferenze telefoniche con accesso esterno</strong></p></td>
<td><p>Utilizzare il pannello di controllo di Lync Server 2013 o Lync Server Management Shell per configurare le impostazioni dei <strong>criteri di conferenza</strong> . Specificare se:</p>
<ul>
<li><p>L'accesso esterno alle conferenze PSTN è abilitato.</p></li>
<li><p>Gli utenti possono invitare partecipanti anonimi.</p></li>
<li><p>Gli utenti non autenticati possono partecipare a una conferenza utilizzando la chiamata in uscita. Con le chiamate in uscita, il server per conferenze chiama l'utente, il quale accede alla conferenza rispondendo al telefono.</p></li>
</ul></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-conferencing-policy-for-dial-in.md">Configurare i criteri di conferenza per l'accesso esterno in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p><strong>Configurare i numeri di accesso esterno</strong></p></td>
<td><p>Utilizzare il pannello di controllo di Lync Server 2013 o Lync Server Management Shell per configurare i numeri di accesso esterno che gli utenti chiamano per effettuare la chiamata in ingresso a una conferenza e specificare le aree che associano il numero di accesso ai dial plan corretti. I primi tre numeri di accesso per l'area specificata dal dial plan dell'organizzatore sono inclusi nell'invito a una conferenza. Tutti i numeri di accesso sono disponibili nella pagina delle impostazioni per le conferenze telefoniche con chiamata in ingresso.</p>
<div>

> [!NOTE]  
> Dopo aver creato i numeri di accesso esterno, è possibile utilizzare il cmdlet <STRONG>Set-CsDialInConferencingAccessNumber</STRONG> per modificare il nome visualizzato degli oggetti contatto di Active Directory in modo che gli utenti possano identificare più facilmente il numero di accesso corretto.


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-dial-in-conferencing-access-numbers.md">Configurare i numeri di accesso per le conferenze telefoniche con chiamata in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>Optional Verificare le impostazioni delle conferenze telefoniche con accesso esterno</strong></p></td>
<td><p>Utilizzare il cmdlet <strong>Get-CsDialInConferencingAccessNumber</strong> per cercare i dial plan con un'area di conferenza telefonica con accesso esterno non utilizzata da alcun numero di Access e per i numeri di accesso privi di aree assegnate.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p>
<p>CsViewOnlyAdministrator</p>
<p>CsHelpDesk</p></td>
<td><p><a href="lync-server-2013-optional-verify-dial-in-conferencing-settings.md">Optional Verificare le impostazioni delle conferenze telefoniche con accesso esterno in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p><strong>Optional Modificare il mapping dei tasti per i comandi DTMF</strong></p></td>
<td><p>Utilizzare il cmdlet <strong>Set-CsDialInConferencingDtmfConfiguration</strong> per modificare le chiavi utilizzate per i comandi DTMF (Dual-Tone Multifrequency), che possono essere utilizzati dai partecipanti per controllare le impostazioni di conferenza (ad esempio, disattivare e riattivare o bloccare e sbloccare).</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-optional-modify-key-mapping-for-dtmf-commands.md">Optional Modificare il mapping dei tasti per i comandi DTMF in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>Optional Modificare la modalità di partecipazione alle conferenze e lasciare l'annuncio</strong></p></td>
<td><p>Utilizzare il <strong>Set-CsDialInConferencingConfiguration</strong> per modificare il modo in cui gli annunci interagiscono quando i partecipanti partecipano e lasciano conferenze.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-optional-enable-and-disable-conference-join-and-leave-announcements.md">Optional Abilitare e disabilitare gli annunci di partecipazione alla conferenza e di uscita in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p><strong>Optional Verificare le conferenze telefoniche con accesso esterno</strong></p></td>
<td><p>Utilizzare il cmdlet <strong>Test-CsDialInConferencing</strong> per verificare che i numeri di accesso per il pool specificato funzionino correttamente.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-optional-verify-dial-in-conferencing.md">Optional Verificare le conferenze telefoniche con accesso esterno in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>Distribuire il componente aggiuntivo per riunioni online per Lync 2013</strong></p></td>
<td><p>Distribuire il componente aggiuntivo per riunioni online per Lync 2013 in modo che gli utenti possano pianificare conferenze per il supporto delle conferenze telefoniche con accesso esterno. Il componente aggiuntivo per riunioni online per Lync 2013 viene installato automaticamente quando si installa Lync 2013.</p></td>
<td><p>Amministratori</p></td>
<td><p><a href="lync-server-2013-deploy-the-online-meeting-add-in-for-lync-2013.md">Distribuire il componente aggiuntivo per riunioni online per Lync 2013</a></p></td>
</tr>
<tr class="even">
<td><p><strong>Configurare le impostazioni degli account utente</strong></p></td>
<td><p>Utilizzare il pannello di controllo di Lync Server 2013 o Lync Server Management Shell per configurare l' <strong>URI della linea</strong> di telefonia come un numero di telefono normalizzato univoco, ad esempio Tel: + 14255550200.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsAdministrator</p>
<p>CsUserAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-user-account-settings.md">Configurare le impostazioni degli account utente in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Consigliato Configurare le directory conferenze</p></td>
<td><p>Utilizzare il cmdlet <strong>New-CsConferenceDirectory</strong> per creare una directory conferenze per ogni 999 utenti nel pool.</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p>Requisiti per le conferenze telefoniche <a href="lync-server-2013-dial-in-conferencing-requirements.md">con accesso esterno in Lync Server 2013</a> <a href="recommended-create-conference-directories.md">(scelta consigliata) creare directory conferenze</a></p></td>
</tr>
<tr class="even">
<td><p><strong>Optional Accogliere gli utenti per le conferenze telefoniche con accesso esterno e impostare il PIN iniziale</strong></p></td>
<td><p>Utilizzare lo script <strong>Set-CsPinSendCAWelcomeMail</strong> per impostare i pin iniziali degli utenti e inviare un messaggio di posta elettronica di benvenuto che contiene il PIN iniziale e un collegamento alla pagina delle impostazioni per le conferenze telefoniche con accesso esterno.</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-optional-welcome-users-to-dial-in-conferencing.md">Optional Accogliere gli utenti per le conferenze telefoniche con accesso esterno in Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

