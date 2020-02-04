---
title: 'Lync Server 2013: Pianificazione del controllo di accesso basato sui ruoli'
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
ms.openlocfilehash: b89e4bdc075783d33bebcfb85398b1b627e1bf1c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41750476"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-role-based-access-control-in-lync-server-2013"></a>Pianificazione del controllo di accesso basato sui ruoli in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2015-01-27_

Per consentire di delegare le attività amministrative mantenendo standard elevati per la sicurezza, Lync Server 2013 offre il controllo di accesso basato sui ruoli (RBAC). Con RBAC, il privilegio amministrativo viene concesso assegnando agli utenti ruoli amministrativi. Lync Server 2013 include un set completo di ruoli amministrativi predefiniti e consente inoltre di creare nuovi ruoli e specificare un elenco personalizzato di cmdlet per ogni nuovo ruolo. È inoltre possibile aggiungere script di cmdlet alle attività consentite sia dei ruoli predefiniti che di quelli RBAC.

<div>

## <a name="better-server-security-and-centralization"></a>Migliorare la sicurezza e la centralizzazione del server

Con RBAC, Access e Authorization si basano proprio sul ruolo del server Lync dell'utente. In questo modo, è possibile usare la procedura di sicurezza "privilegi minimi", concedendo solo agli amministratori e agli utenti i diritti necessari per il lavoro.

<div>


> [!IMPORTANT]  
> Le restrizioni RBAC funzionano solo per gli amministratori che lavorano in remoto, usando il pannello di controllo di Lync Server o Lync Server Management Shell. Un utente che si siede in un server su cui è in uso Lync Server non è limitato da RBAC. Di conseguenza, la sicurezza fisica del server Lync è importante per preservare le restrizioni RBAC.



</div>

</div>

<div>

## <a name="roles-and-scope"></a>Ruoli e ambito

In RBAC viene abilitato un *ruolo* per l'uso di un elenco di cmdlet, progettato per essere utile per un determinato tipo di amministratore o tecnico. Un *ambito* è il set di oggetti su cui possono operare i cmdlet definiti in un ruolo. Gli oggetti a cui viene applicato l'ambito possono essere account utente (raggruppati per unità organizzativa) o server (raggruppati per sito).

La tabella seguente elenca i ruoli predefiniti in Lync Server e offre una panoramica generale dei tipi di attività che ognuno può eseguire. La quarta colonna Mostra il ruolo di Microsoft Exchange Server simile per ogni ruolo di Lync Server, se disponibile.

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
<td><p>Può abilitare e disabilitare gli utenti per Lync Server, trasferire gli utenti e assegnare i criteri esistenti agli utenti. Non è possibile modificare i criteri.</p></td>
<td><p>CSUserAdministrator</p></td>
<td><p>Destinatari della posta elettronica</p></td>
</tr>
<tr class="odd">
<td><p>CsVoiceAdministrator</p></td>
<td><p>Può creare, configurare e gestire le impostazioni e i criteri relativi alla voce.</p></td>
<td><p>CSVoiceAdministrator</p></td>
<td><p>Non applicabile</p></td>
</tr>
<tr class="even">
<td><p>CsServerAdministrator</p></td>
<td><p>Può gestire, monitorare e risolvere i problemi di server e servizi. Può impedire le nuove connessioni ai server, arrestare e avviare i servizi e applicare gli aggiornamenti software. Non è possibile apportare modifiche con l'impatto della configurazione globale.</p></td>
<td><p>CSServerAdministrator</p></td>
<td><p>Gestione server</p></td>
</tr>
<tr class="odd">
<td><p>CsViewOnlyAdministrator</p></td>
<td><p>Può visualizzare la distribuzione, incluse le informazioni sull'utente e sul server, per monitorare l'integrità della distribuzione.</p></td>
<td><p>CSViewOnlyAdministrator</p></td>
<td><p>Gestione dell'organizzazione di sola visualizzazione</p></td>
</tr>
<tr class="even">
<td><p>CsHelpDesk</p></td>
<td><p>Può visualizzare la distribuzione, incluse le proprietà e i criteri dell'utente. Può eseguire attività specifiche per la risoluzione dei problemi. Non è possibile modificare le proprietà o i criteri degli utenti, la configurazione del server o i servizi.</p></td>
<td><p>CSHelpDesk</p></td>
<td><p>Help desk</p></td>
</tr>
<tr class="odd">
<td><p>CsArchivingAdministrator</p></td>
<td><p>Può modificare la configurazione e i criteri di archiviazione.</p></td>
<td><p>CSArchivingAdministrator</p></td>
<td><p>Gestione della conservazione, blocco legale</p></td>
</tr>
<tr class="even">
<td><p>CsResponseGroupAdministrator</p></td>
<td><p>Può gestire la configurazione dell'applicazione Response Group all'interno di un sito.</p></td>
<td><p>CSResponseGroupAdministrator</p></td>
<td><p>Non applicabile</p></td>
</tr>
<tr class="odd">
<td><p>CsLocationAdministrator</p></td>
<td><p>Livello di diritti più basso per la gestione avanzata di 9-1-1 (E9-1-1), tra cui la creazione di percorsi E9-1-1 e gli identificatori di rete e l'associazione tra loro. Questo ruolo viene sempre assegnato con un ambito globale.</p></td>
<td><p>CSLocationAdministrator</p></td>
<td><p>Non applicabile</p></td>
</tr>
<tr class="even">
<td><p>CsResponseGroupManager</p></td>
<td><p>Può gestire gruppi di risposta specifici.</p></td>
<td><p>CSResponseGroupManager</p></td>
<td><p>Non applicabile</p></td>
</tr>
<tr class="odd">
<td><p>CsPersistentChatAdministrator</p></td>
<td><p>Può gestire la funzionalità chat persistente e le chat room persistenti specifiche.</p></td>
<td><p>CSPersistentChatAdministrator</p></td>
<td><p>Non applicabile</p></td>
</tr>
</tbody>
</table>


Tutti i ruoli predefiniti spediti in Lync Server hanno un ambito globale. Per seguire le procedure per i privilegi minimi, non è consigliabile assegnare utenti ai ruoli con ambito globale se si vuole amministrare solo un set limitato di server o utenti. A questo scopo, puoi creare ruoli basati su un ruolo esistente, ma con un ambito più limitato.

<div>

## <a name="creating-a-scoped-role"></a>Creazione di un ruolo con ambito

Quando si crea un ruolo con un ambito limitato (un ruolo con ambito), si specifica l'ambito, insieme al ruolo esistente su cui è basato e al gruppo Active Directory a cui assegnare il ruolo. Il gruppo di Active Directory specificato deve essere già creato. Il cmdlet seguente è un esempio di creazione di un ruolo che ha i privilegi di uno dei ruoli amministrativi predefiniti, ma con un ambito limitato. Viene creato un nuovo ruolo denominato `Site01 Server Administrators`. Il ruolo ha le capacità del ruolo di CsServerAdministrator predefinito, ma solo per i server presenti nel sito di Site01. Affinché questo cmdlet funzioni, il sito di Site01 deve essere già definito e un gruppo di sicurezza universale denominato `Site01 Server Administrators` deve esistere già.

    New-CsAdminRole -Identity "Site01 Server Administrators" -Template CsServerAdministrator -ConfigScopes "site:Site01"

Dopo l'esecuzione di questo cmdlet, tutti gli utenti membri del `Site01 Server Administrators` gruppo avranno i privilegi di amministratore del server per i server in Site01. Inoltre, gli eventuali utenti aggiunti in seguito a questo gruppo di sicurezza universale acquisiscono anche i privilegi di questo ruolo. Tieni presente che viene chiamato `Site01 Server Administrators`sia il ruolo stesso che il gruppo di sicurezza universale a cui viene assegnato.

L'esempio seguente limita l'ambito utente anziché l'ambito server. Crea un `Sales Users Administrator` ruolo per amministrare gli account utente nell'unità organizzativa Sales. Il gruppo di sicurezza universale SalesUsersAdministrator deve essere già creato per il funzionamento del cmdlet.

    New-CsAdminRole -Identity "Sales Users Administrator " -Template CsUserAdministrator -UserScopes "OU:OU=Sales, OU=Lync Tenants, DC=Domain, DC=com"

</div>

<div>

## <a name="creating-a-new-role"></a>Creazione di un nuovo ruolo

Per creare un ruolo che abbia accesso a un set di cmdlet non in uno dei ruoli predefiniti oppure a un set di script o moduli, è possibile iniziare a usare uno dei ruoli predefiniti come modello. Tieni presente che gli script e i moduli che i ruoli possono eseguire devono essere archiviati nei percorsi seguenti:

  - Percorso modulo di Lync, che è per impostazione predefinita C\\: programmi\\file comuni\\Microsoft Lync Server 2013\\modules\\Lync

  - Il percorso di script utente, che è per impostazione predefinita\\C:\\programmi file\\comuni di Microsoft Lync\\Server 2013 AdminScripts

Per creare un nuovo ruolo, puoi usare il cmdlet **New-CsAdminRole** . Prima di eseguire **New-CsAdminRole**, è necessario prima di tutto creare il gruppo di sicurezza universale sottostante che verrà associato a questo ruolo.

I cmdlet seguenti fungono da esempio di creazione di un nuovo ruolo. Crea un nuovo tipo di ruolo denominato `MyHelpDeskScriptRole`. Il nuovo ruolo ha le capacità del ruolo CsHelpDesk predefinito e può inoltre eseguire le funzioni in uno script denominato "TestScript".

    New-CsAdminRole -Identity "MyHelpDeskScriptRole" -Template CsHelpDesk -ScriptModules @{Add="testScript.ps1"}

Per il funzionamento di questo cmdlet, è necessario aver creato prima il gruppo di sicurezza universale MyHelpDeskScriptRole.

Dopo l'esecuzione di questo cmdlet, è possibile assegnare gli utenti direttamente a questo ruolo (nel qual caso hanno ambito globale) oppure creare un ruolo con ambito basato su questo ruolo, come spiegato in creare un ruolo con ambito, in precedenza in questo documento.

</div>

<div>

## <a name="assigning-roles-to-users"></a>Assegnazione di ruoli agli utenti

Ogni ruolo di Lync Server è associato a un gruppo di sicurezza universale di Active Directory sottostante. Gli utenti aggiunti al gruppo sottostante acquisiscono le capacità di tale ruolo.

Gli esempi nelle sezioni precedenti hanno creato un nuovo ruolo e assegnato un gruppo di sicurezza universale esistente al nuovo ruolo. Per assegnare un ruolo esistente a uno o più utenti, aggiungere gli utenti al gruppo associato al ruolo. È possibile aggiungere entrambi i singoli utenti e i gruppi di sicurezza universale a questi gruppi.

Ad esempio, il ruolo **CsAdministrator** viene concesso automaticamente al gruppo **amministratori** di sicurezza universale di CS in Active Directory. Questo gruppo di sicurezza universale viene creato in Active Directory quando si distribuisce Lync Server. Per concedere a un utente o a un gruppo questo privilegio, è possibile aggiungerli semplicemente al gruppo **amministratori di CS** .

A un utente possono essere assegnati più ruoli RBAC per essere aggiunti ai gruppi di Active Directory sottostanti che corrispondono a ogni ruolo.

Tieni presente che quando crei un ruolo, gli utenti che vengono aggiunti in seguito al gruppo Active Directory sottostante acquisiscono le capacità di tale ruolo.

</div>

<div>

## <a name="modifying-the-abilities-of-a-role"></a>Modifica delle capacità di un ruolo

È possibile modificare l'elenco di cmdlet e script che possono essere eseguiti da un ruolo. È possibile modificare sia i cmdlet che gli script che i ruoli personalizzati possono eseguire, ma è possibile modificare solo gli script per i ruoli predefiniti. Ogni cmdlet digitato può aggiungere, rimuovere o sostituire cmdlet o script.

Per modificare un ruolo, usare il cmdlet **Set-CsAdminRole** . Il cmdlet seguente consente di rimuovere uno script dal ruolo.

    Set-CsAdminRole -Identity "MyHelpDeskScriptRole" -ScriptModules @{Remove="testScript.ps1"}

</div>

</div>

<div>

## <a name="planning-for-rbac"></a>Pianificazione per RBAC

Per ogni persona a cui deve essere assegnato qualsiasi tipo di diritti amministrativi per la distribuzione di Lync Server, valutare le attività che devono eseguire, quindi assegnarle ai ruoli con i privilegi minimi e l'ambito necessari per il lavoro. Se necessario, puoi usare il cmdlet **Set-CsAdminRole** per creare un nuovo ruolo con solo i cmdlet necessari per le attività di questa persona.

Gli utenti che hanno il ruolo CsAdministrator possono creare tutti i tipi di ruoli, inclusi i ruoli basati su CsAdministrator, e assegnarli agli utenti. La procedura consigliata consiste nell'assegnare il ruolo CsAdministrator a un set molto piccolo di utenti attendibili.

</div>

</div>

<span> </span>

</div>

</div>

</div>

