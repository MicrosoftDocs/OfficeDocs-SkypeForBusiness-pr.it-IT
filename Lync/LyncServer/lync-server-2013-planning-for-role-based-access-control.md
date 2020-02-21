---
title: 'Lync Server 2013: pianificazione del controllo di accesso basato sui ruoli'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for role-based access control (RBAC)
ms:assetid: 41204ba3-ce5b-41a8-a6c3-b444468fa328
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425917(v=OCS.15)
ms:contentKeyID: 48183962
ms.date: 01/28/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d88353019a266fbb094df8808faa4543e31bf562
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201892"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-role-based-access-control-in-lync-server-2013"></a>Pianificazione del controllo di accesso basato sui ruoli in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2015-01-27_

Per consentire di delegare le attività amministrative mantenendo gli standard elevati per la sicurezza, Lync Server 2013 offre il controllo di accesso basato sui ruoli (RBAC). Grazie a questa funzionalità, il privilegio amministrativo viene concesso assegnando gli utenti a ruoli amministrativi. Lync Server 2013 include un set completo di ruoli amministrativi incorporati e consente inoltre di creare nuovi ruoli e di specificare un elenco personalizzato di cmdlet per ogni nuovo ruolo. Rende inoltre possibile l'aggiunta di script di cmdlet alle attività consentite sia dei ruoli RBAC predefiniti che di quelli personalizzati.

<div>

## <a name="better-server-security-and-centralization"></a>Migliore sicurezza dei server e centralizzazione

Con RBAC, l'accesso e l'autorizzazione si basano proprio sul ruolo Lync Server di un utente. In questo modo si dispone di un più ampio margine per applicare il metodo di sicurezza basato sul principio dei privilegi minimi, che concede agli amministratori e agli utenti solo i diritti necessari per le attività che devono svolgere.

<div>


> [!IMPORTANT]  
> Le restrizioni RBAC funzionano solo per gli amministratori che operano in remoto, utilizzando il pannello di controllo di Lync Server o Lync Server Management Shell. Un utente che si trova in un server su cui è in esecuzione Lync Server non è limitato da RBAC. Pertanto, la sicurezza fisica del server Lync è importante per preservare le restrizioni RBAC.



</div>

</div>

<div>

## <a name="roles-and-scope"></a>Ruoli e ambito

Nel controllo di accesso basato sui ruoli un *ruolo* è abilitato all'uso di un elenco di cmdlet, progettati in modo da essere utilizzati da un determinato tipo di amministratore o tecnico. Un *ambito* è un insieme di oggetti sui cui possono operare i cmdlet definiti in un ruolo. Gli oggetti su cui ha effetto l'ambito possono essere account utente (raggruppati per unità organizzativa) o server (raggruppati per sito).

Nella tabella seguente sono elencati i ruoli predefiniti in Lync Server e viene fornita una panoramica generale dei tipi di attività che possono essere eseguite. La quarta colonna Visualizza il ruolo di Microsoft Exchange Server analogo per ogni ruolo di Lync Server, se disponibile.

### <a name="predefined-administrative-roles"></a>Ruoli amministrativi predefiniti

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Ruolo</th>
<th>Attività consentite</th>
<th>Gruppo Active Directory sottostante</th>
<th>Equivalente di Exchange</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CsAdministrator</p></td>
<td><p>Può eseguire tutte le attività amministrative e modificare tutte le impostazioni, tra cui la creazione di ruoli e l'assegnazione di utenti ai ruoli. Può espandere una distribuzione aggiungendo nuovi siti, pool e servizi.</p></td>
<td><p>CSAdministrator</p></td>
<td><p>Gestione dell'organizzazione</p></td>
</tr>
<tr class="even">
<td><p>CsUserAdministrator</p></td>
<td><p>Consente di abilitare e disabilitare gli utenti per Lync Server, spostare gli utenti e assegnare criteri esistenti agli utenti. Non può modificare i criteri.</p></td>
<td><p>CSUserAdministrator</p></td>
<td><p>Mail Recipients</p></td>
</tr>
<tr class="odd">
<td><p>CsVoiceAdministrator</p></td>
<td><p>Può creare, configurare e gestire le impostazioni e i criteri vocali.</p></td>
<td><p>CSVoiceAdministrator</p></td>
<td><p>Non applicabile</p></td>
</tr>
<tr class="even">
<td><p>CsServerAdministrator</p></td>
<td><p>Può gestire e monitorare server e servizi, nonché risolvere i relativi errori. Può impedire nuove connessioni ai server, arrestare e avviare servizi e applicare aggiornamenti software. Non può apportare modifiche con impatto sulla configurazione globale.</p></td>
<td><p>CSServerAdministrator</p></td>
<td><p>Server Management</p></td>
</tr>
<tr class="odd">
<td><p>CsViewOnlyAdministrator</p></td>
<td><p>Può visualizzare la distribuzione, incluse le informazioni su utenti e server, in modo da monitorare l'integrità della distribuzione.</p></td>
<td><p>CSViewOnlyAdministrator</p></td>
<td><p>Gestione organizzazione in sola visualizzazione</p></td>
</tr>
<tr class="even">
<td><p>CsHelpDesk</p></td>
<td><p>Può visualizzare la distribuzione, tra cui le proprietà e i criteri utente, e può eseguire specifiche attività di risoluzione dei problemi. Non può modificare le proprietà o i criteri utente, la configurazione dei server o i servizi.</p></td>
<td><p>CSHelpDesk</p></td>
<td><p>HelpDesk</p></td>
</tr>
<tr class="odd">
<td><p>CsArchivingAdministrator</p></td>
<td><p>Può modificare la configurazione e i criteri di archiviazione.</p></td>
<td><p>CSArchivingAdministrator</p></td>
<td><p>Gestione conservazione, Conservazione legale</p></td>
</tr>
<tr class="even">
<td><p>CsResponseGroupAdministrator</p></td>
<td><p>Può gestire la configurazione dell'applicazione Response Group in un sito.</p></td>
<td><p>CSResponseGroupAdministrator</p></td>
<td><p>Non applicabile</p></td>
</tr>
<tr class="odd">
<td><p>CsLocationAdministrator</p></td>
<td><p>Livello minimo di diritti per la gestione di Enhanced 9-1-1 (E9-1-1), incluse la creazione di posizioni E9-1-1 e di identificatori di rete e l'associazione tra questi elementi. Questo ruolo viene sempre assegnato con un ambito globale.</p></td>
<td><p>CSLocationAdministrator</p></td>
<td><p>Non applicabile</p></td>
</tr>
<tr class="even">
<td><p>CsResponseGroupManager</p></td>
<td><p>Può gestire Response Group specifici.</p></td>
<td><p>CSResponseGroupManager</p></td>
<td><p>Non applicabile</p></td>
</tr>
<tr class="odd">
<td><p>Ruolo CsPersistentChatAdministrator</p></td>
<td><p>Può gestire la funzionalità di chat persistente e specifiche chat Persistent Chat.</p></td>
<td><p>Ruolo CsPersistentChatAdministrator</p></td>
<td><p>Non applicabile</p></td>
</tr>
</tbody>
</table>


Tutti i ruoli predefiniti spediti in Lync Server hanno un ambito globale. Per applicare il principio dei privilegi minimi, è consigliabile non assegnare utenti a ruoli con ambito globale se amministreranno solo un insieme limitato di server o utenti. A tale scopo, è possibile creare ruoli basati su ruoli esistenti, ma con un ambito molto più limitato.

<div>

## <a name="creating-a-scoped-role"></a>Creazione di un ruolo con ambito

Quando si crea un ruolo con ambito limitato, ovvero un ruolo con ambito, si specifica l'ambito insieme al ruolo esistente sui cui si basa e al gruppo Active Directory a cui assegnare il ruolo. Il gruppo Active Directory specificato deve essere già creato. Il cmdlet seguente è un esempio di creazione di un ruolo che dispone dei privilegi di uno dei ruoli amministrativi, ma con ambito limitato. Viene creato un nuovo ruolo denominato `Site01 Server Administrators`. Il nuovo ruolo ha le capacità del ruolo CsServerAdministrator predefinito, ma solo per i server del sito Site01. Per il funzionamento di questo cmdlet, è necessario che il sito Site01 sia già stato definito e che sia `Site01 Server Administrators` già presente un gruppo di sicurezza universale denominato.

    New-CsAdminRole -Identity "Site01 Server Administrators" -Template CsServerAdministrator -ConfigScopes "site:Site01"

Dopo l'esecuzione di questo cmdlet, tutti gli utenti membri del `Site01 Server Administrators` gruppo disporranno dei privilegi di amministratore del server per i server di Site01. Inoltre, tutti gli utenti che successivamente sono stati aggiunti a questo gruppo di protezione universale ottengono anche i privilegi di questo ruolo. Si noti che sia il ruolo stesso che il gruppo di sicurezza universale a cui viene assegnato sono `Site01 Server Administrators`chiamati.

Nell'esempio seguente si applicano limiti all'ambito utente anziché all'ambito server. Consente di creare `Sales Users Administrator` un ruolo per amministrare gli account utente nell'unità organizzativa Sales. Per il funzionamento del cmdlet, è necessario che il gruppo di sicurezza universale di SalesUsersAdministrator sia già stato creato.

    New-CsAdminRole -Identity "Sales Users Administrator " -Template CsUserAdministrator -UserScopes "OU:OU=Sales, OU=Lync Tenants, DC=Domain, DC=com"

</div>

<div>

## <a name="creating-a-new-role"></a>Creazione di un nuovo ruolo

Per creare un ruolo che disponga di accesso a un insieme di cmdlet non inclusi in uno dei ruoli predefiniti oppure a un insieme di script o moduli, usare di nuovo uno dei ruoli predefiniti come modello. Si noti che gli script e i moduli che i ruoli sono in grado di eseguire devono essere memorizzati nei percorsi seguenti:

  - Il percorso del modulo di Lync, che per impostazione predefinita\\è C\\: Program\\files Common Files Microsoft\\Lync\\Server 2013 Modules Lync

  - Il percorso dello script utente, che per impostazione predefinita è\\C:\\Program Files\\Common Files Microsoft Lync\\Server 2013 AdminScripts

Per creare un nuovo ruolo, utilizzare il cmdlet **New-CsAdminRole**. Prima di eseguire **New-CsAdminRole**, è innanzitutto necessario creare il gruppo di protezione universale sottostante che verrà associato a questo ruolo.

I cmdlet seguenti possono essere usati come esempio di creazione di un nuovo ruolo. Si crea un nuovo tipo di ruolo `MyHelpDeskScriptRole`denominato. Il nuovo ruolo ha le capacità del ruolo CsHelpDesk predefinito e può anche eseguire le funzioni in uno script denominato "testscript".

    New-CsAdminRole -Identity "MyHelpDeskScriptRole" -Template CsHelpDesk -ScriptModules @{Add="testScript.ps1"}

Affinché questo cmdlet funzioni, è necessario che sia stato creato per la prima volta il gruppo di protezione universale MyHelpDeskScriptRole.

Dopo aver eseguito il cmdlet, è possibile assegnare gli utenti direttamente a questo ruolo (in tal caso avranno ambito globale) o creare un ruolo con ambito basato su questo ruolo, come spiegato nella sezione precedente del presente documento, intitolata Creazione di un ruolo con ambito.

</div>

<div>

## <a name="assigning-roles-to-users"></a>Assegnazione di ruoli agli utenti

Ogni ruolo di Lync Server è associato a un gruppo di protezione universale di Active Directory sottostante. Tutti gli utenti che vengono aggiunti al gruppo sottostante acquisiscono le capacità di tale ruolo.

Negli esempi nelle sezioni precedenti è stato creato un nuovo ruolo e assegnato un gruppo di sicurezza universale esistente al nuovo ruolo. Per assegnare un ruolo esistente a uno o più utenti, aggiungere gli utenti desiderati al gruppo associato al ruolo. È possibile aggiungere entrambi i singoli utenti e i gruppi di protezione universale a questi gruppi.

Ad esempio, il ruolo **CsAdministrator** viene concesso automaticamente al gruppo di protezione universale **Administrators di CS** in Active Directory. Questo gruppo di sicurezza universale viene creato in Active Directory quando si distribuisce Lync Server. Per concedere questo privilegio a un utente o a un gruppo, è sufficiente aggiungerlo al gruppo **CS Administrators**.

È possibile assegnare a un utente più ruoli di controllo di accesso basato sui ruoli aggiungendo l'utente ai gruppi Active Directory sottostanti che corrispondono a ogni ruolo.

Si noti che quando si crea un ruolo, gli utenti che vengono aggiunti successivamente al gruppo Active Directory sottostante acquisiscono le capacità di tale ruolo.

</div>

<div>

## <a name="modifying-the-abilities-of-a-role"></a>Modifica delle capacità di un ruolo

È possibile modificare l'elenco di cmdlet e script che un ruolo può eseguire, nonché modificare sia i cmdlet che gli script che i ruoli personalizzati possono eseguire, ma solo gli script dei ruoli predefiniti. Ogni cmdlet digitato può aggiungere, rimuovere o sostituire cmdlet o script.

Per modificare un ruolo, usare il cmdlet **Set-CsAdminRole**. Il cmdlet seguente consente di rimuovere uno script dal ruolo.

    Set-CsAdminRole -Identity "MyHelpDeskScriptRole" -ScriptModules @{Remove="testScript.ps1"}

</div>

</div>

<div>

## <a name="planning-for-rbac"></a>Pianificazione del controllo di accesso basato sui ruoli

Per ogni persona a cui deve essere assegnato qualsiasi tipo di diritti amministrativi per la distribuzione di Lync Server, prendere in considerazione le attività da eseguire, quindi assegnarle ai ruoli con i privilegi minimi e l'ambito necessari per il proprio lavoro. Se necessario, è possibile utilizzare il cmdlet **Set-CsAdminRole** per creare un nuovo ruolo con i soli cmdlet richiesti per le attività di questo utente.

Gli utenti con ruolo CsAdministrator possono creare tutti i tipi di ruoli, inclusi quelli basati su CsAdministrator, e assegnare utenti a tali ruoli. La procedura consigliata prevede l'assegnazione del ruolo CsAdministrator a un insieme limitato di utenti trusted.

</div>

</div>

<span> </span>

</div>

</div>

</div>

