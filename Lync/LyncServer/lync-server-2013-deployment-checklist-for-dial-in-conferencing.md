---
title: 'Lync Server 2013: Elenco di controllo di distribuzione per le conferenze telefoniche con accesso esterno'
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
ms.openlocfilehash: edf496dcb24c021246bfbb6e7a5ef7b3a3a5acc1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740716"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-dial-in-conferencing-in-lync-server-2013"></a>Elenco di controllo di distribuzione per le conferenze telefoniche con accesso esterno in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-10-03_

I componenti necessari per i servizi di conferenza telefonica con accesso esterno vengono distribuiti quando si distribuisce il carico di lavoro di conferenza. Prima di poter configurare i servizi di conferenza telefonica con accesso esterno, è necessario distribuire VoIP aziendale o Mediation Server e un gateway PSTN (Public Switched Telephone Network).

Tutti i passaggi descritti nella tabella seguente devono essere eseguiti prima che gli utenti possano effettuare la chiamata dalla rete PSTN per partecipare a una conferenza audio/video.

<div>


> [!NOTE]  
> Se si esegue la migrazione da Office Communications Server 2007 R2, è necessario applicare gli aggiornamenti più recenti all'ambiente Office Communications Server 2007 R2 prima di distribuire i servizi di conferenza telefonica con accesso esterno.



</div>

### <a name="dial-in-conferencing-deployment-process"></a>Processo di distribuzione di servizi di conferenza telefonica con accesso esterno

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
<th>Documentazione di distribuzione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Creare una topologia che includa il carico di lavoro per le conferenze, incluso un Mediation Server e un gateway PSTN, e distribuire il pool Front end o il server Standard Edition</strong></p></td>
<td><ol>
<li><p>Eseguire Generatore di topologie per configurare la topologia. Durante la configurazione della topologia, selezionare l'opzione per i servizi di conferenza telefonica con accesso esterno.</p></li>
<li><p>Pubblicare la topologia e distribuire il pool Front-end o il server Standard Edition.</p></li>
<li><p>Se necessario, creare un Mediation Server autonomo e associarlo a un gateway PSTN.</p>
<div>

> [!NOTE]  
> Questo passaggio è obbligatorio solo se non si distribuisce VoIP aziendale e non si colloca il Mediation Server con l'Enterprise EditionFront End Server o Standard Edition Server. Se si distribuisce VoIP aziendale, si installano e si configurano i server di mediazione e i gateway PSTN come parte della distribuzione di VoIP aziendale. Se si colloca il Mediation Server, si installa e si configura il server Mediation come parte del pool Front-end o del server Standard Edition.


</div></li>
</ol></td>
<td><p>Amministratori di dominio</p>
<p>RTCUniversalServerAdmins</p>
<p>Amministratore</p></td>
<td><ul>
<li><p><a href="lync-server-2013-deploying-lync-server.md">Distribuzione di Lync Server 2013</a></p></li>
<li><p>Per creare un pool di Mediation Server autonomo: <a href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">distribuzione di Mediation Server e definizione di peer in Lync Server 2013</a></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Configurare i dial plan</strong></p></td>
<td><p>Un dial plan è un set di regole di normalizzazione per i numeri di telefono che traducono il numero di telefono composto da una posizione specifica a un singolo formato standard (E. 164) per scopi di autorizzazione del telefono e routing delle chiamate. Lo stesso numero di telefono composto da posizioni diverse può, in base ai rispettivi piani di chiamata, risolvere i diversi numeri E. 164, come appropriato per ogni posizione. Se si distribuisce VoIP aziendale, si configurano i dial plan come parte di tale distribuzione ed è necessario assicurarsi che i dial plan siano anche in grado di ospitare i servizi di conferenza telefonica con accesso esterno. Se non si distribuisce VoIP aziendale, è necessario configurare i dial plan per i servizi di conferenza telefonica con accesso esterno.</p>
<p>Usare il pannello di controllo di Lync Server 2013 o Lync Server Management Shell per configurare i piani di chiamata come segue:</p>
<ol>
<li><p>Creare uno o più piani di chiamata per il routing dei numeri di telefono di accesso esterno.</p></li>
<li><p>Assegnare un dial plan predefinito a ogni pool. Impostare l'area dei servizi di <strong>conferenza telefonica con accesso esterno</strong> nella posizione geografica in cui si applica il dial plan. L'area associa il dial plan con i numeri di accesso esterno.</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md">Configurare dial plan per le conferenze telefoniche con accesso esterno in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>Assicurarsi che i dial plan siano assegnati alle aree geografiche</strong></p></td>
<td><p>Eseguire i cmdlet <strong>Get-CsDialPlan</strong> e <strong>Set-CsDialPlan</strong> per assicurarsi che tutti i dial plan abbiano un'area geografica assegnata.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-make-sure-dial-plans-have-assigned-regions.md">Assicurarsi che i dial plan di Lync Server 2013 abbiano assegnato aree geografiche</a></p></td>
</tr>
<tr class="even">
<td><p><strong>Opzionale Verificare o modificare i requisiti del PIN (User Personal Identification Number)</strong></p></td>
<td><p>Usare il pannello di controllo di Lync Server 2013 o Lync Server Management Shell per visualizzare o modificare i <strong>criteri PIN</strong>per i servizi di conferenza. Puoi specificare la lunghezza minima del PIN, il numero massimo di tentativi di accesso, la scadenza del PIN e se i modelli comuni sono consentiti.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-optional-verify-pin-policy-settings.md">(Facoltativo) Verificare le impostazioni dei criteri per il PIN in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>Configurare i criteri di conferenza per supportare i servizi di conferenza telefonica con accesso esterno</strong></p></td>
<td><p>Usare il pannello di controllo di Lync Server 2013 o Lync Server Management Shell per configurare le impostazioni dei <strong>criteri di conferenza</strong> . Specificare se:</p>
<ul>
<li><p>L'accesso esterno a conferenza PSTN è abilitato.</p></li>
<li><p>Gli utenti possono invitare partecipanti anonimi.</p></li>
<li><p>Gli utenti non autenticati possono partecipare a una conferenza tramite chiamata in uscita. Con le chiamate in uscita, il server per conferenze chiama l'utente, il quale accede alla conferenza rispondendo al telefono.</p></li>
</ul></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-conferencing-policy-for-dial-in.md">Configurare i criteri di conferenza per l'accesso esterno in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p><strong>Configurare i numeri di accesso per la chiamata in ingresso</strong></p></td>
<td><p>Usare il pannello di controllo di Lync Server 2013 o Lync Server Management Shell per configurare i numeri di accesso esterno che gli utenti chiamano per connettersi a una conferenza e specificare le aree geografiche che associano il numero di accesso con i dial plan appropriati. I primi tre numeri di accesso per l'area specificata dal dial plan dell'organizzatore sono inclusi nell'invito alla conferenza. Tutti i numeri di accesso sono disponibili nella pagina delle impostazioni dei servizi di conferenza telefonica con accesso esterno.</p>
<div>

> [!NOTE]  
> Dopo aver creato i numeri di accesso esterno, è possibile usare il cmdlet <STRONG>Set-CsDialInConferencingAccessNumber</STRONG> per modificare il nome visualizzato degli oggetti contatto di Active Directory in modo che gli utenti possano identificare più facilmente il numero di accesso corretto.


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-dial-in-conferencing-access-numbers.md">Configurare i numeri di accesso per le conferenze telefoniche con accesso esterno in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>(Facoltativo) Verificare le impostazioni delle conferenze telefoniche con accesso esterno</strong></p></td>
<td><p>Utilizzare il cmdlet <strong>Get-CsDialInConferencingAccessNumber</strong> per cercare piani di chiamata con un'area dei servizi di conferenza telefonica con accesso esterno che non viene usata da alcun numero di Access e per i numeri di accesso a cui non è assegnata alcuna area geografica.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p>
<p>CsViewOnlyAdministrator</p>
<p>CsHelpDesk</p></td>
<td><p><a href="lync-server-2013-optional-verify-dial-in-conferencing-settings.md">(Facoltativo) Verificare le impostazioni delle conferenze telefoniche con accesso esterno in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p><strong>Opzionale Modificare il mapping delle chiavi dei comandi DTMF</strong></p></td>
<td><p>Usare il cmdlet <strong>Set-CsDialInConferencingDtmfConfiguration</strong> per modificare le chiavi usate per i comandi DTMF (Dual-Tone Multifrequency), che i partecipanti possono usare per controllare le impostazioni della conferenza, ad esempio per disattivare e riattivare l'audio o bloccare e sbloccare.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-optional-modify-key-mapping-for-dtmf-commands.md">(Facoltativo) Modificare il mapping dei tasti per i comandi DTMF in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>Opzionale Modificare il comportamento degli annunci di conferenza e di uscita</strong></p></td>
<td><p>Usare il <strong>Set-CsDialInConferencingConfiguration</strong> per modificare la modalità di funzionamento degli annunci quando i partecipanti partecipano e lasciano conferenze.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-optional-enable-and-disable-conference-join-and-leave-announcements.md">(Facoltativo) Abilitare e disabilitare gli annunci di partecipazione e abbandono delle conferenze in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p><strong>(Facoltativo) Verificare le conferenze telefoniche con accesso esterno</strong></p></td>
<td><p>Usa il cmdlet <strong>Test-CsDialInConferencing</strong> per verificare che i numeri di accesso per il pool specificato funzionino correttamente.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-optional-verify-dial-in-conferencing.md">(Facoltativo) Verificare le conferenze telefoniche con accesso esterno in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>Distribuire il componente aggiuntivo per riunioni online per Lync 2013</strong></p></td>
<td><p>Distribuire il componente aggiuntivo riunione online per Lync 2013 in modo che gli utenti possano pianificare conferenze che supportano i servizi di conferenza telefonica con accesso esterno. Il componente aggiuntivo riunione online per Lync 2013 viene installato automaticamente durante l'installazione di Lync 2013.</p></td>
<td><p>Gli amministratori</p></td>
<td><p><a href="lync-server-2013-deploy-the-online-meeting-add-in-for-lync-2013.md">Distribuire il componente aggiuntivo per riunioni online per Lync 2013</a></p></td>
</tr>
<tr class="even">
<td><p><strong>Configurare le impostazioni degli account utente</strong></p></td>
<td><p>Usare il pannello di controllo di Lync Server 2013 o Lync Server Management Shell per configurare l' <strong>URI della linea</strong> di telefonia come numero di telefono normalizzato univoco, ad esempio Tel: + 14255550200.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsAdministrator</p>
<p>CsUserAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-user-account-settings.md">Configurare le impostazioni degli account utente in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Consigliato Configurare le directory conferenza</p></td>
<td><p>Usa il cmdlet <strong>New-CsConferenceDirectory</strong> per creare una directory conferenza per ogni utente di 999 nel pool.</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p>Requisiti per i servizi <a href="lync-server-2013-dial-in-conferencing-requirements.md">di conferenza telefonica con accesso esterno in Lync Server 2013</a> <a href="recommended-create-conference-directories.md">(scelta consigliata) creare directory conferenza</a></p></td>
</tr>
<tr class="even">
<td><p><strong>Opzionale Accogliere gli utenti nei servizi di conferenza telefonica con accesso esterno e impostare il PIN iniziale</strong></p></td>
<td><p>Usare lo script <strong>Set-CsPinSendCAWelcomeMail</strong> per impostare i pin iniziali degli utenti e inviare un messaggio di benvenuto contenente il PIN iniziale e un collegamento alla pagina delle impostazioni dei servizi di conferenza telefonica con accesso esterno.</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-optional-welcome-users-to-dial-in-conferencing.md">(Facoltativo) Presentazione della funzionalità di conferenza telefonica con accesso esterno agli utenti in Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

