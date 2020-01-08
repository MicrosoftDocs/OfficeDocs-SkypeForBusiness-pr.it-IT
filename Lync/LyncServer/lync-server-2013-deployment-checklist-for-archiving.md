---
title: "Lync Server 2013: Elenco di controllo di distribuzione per l'archiviazione"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment checklist for Archiving
ms:assetid: 7479734d-be01-40d9-ad82-320a09d19d04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205009(v=OCS.15)
ms:contentKeyID: 48184516
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 51c556dd288ff3539bbf2f4de816eab3a544b847
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981376"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-archiving-in-lync-server-2013"></a>Elenco di controllo di distribuzione per l'archiviazione in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-18_

L'archiviazione viene installata automaticamente in ogni server front-end nella distribuzione di Lync Server 2013, ma è comunque necessario configurarla prima di poterla usare. I passaggi necessari per configurarla, come riepilogati in questa sezione, costituiscono la distribuzione dell'archiviazione.

<div>

## <a name="deployment-sequence"></a>Sequenza di distribuzione

La modalità di configurazione dell'archiviazione dipende dall'opzione di archiviazione scelta:

  - Se si usa l'integrazione di Microsoft Exchange per tutti gli utenti della distribuzione, non è necessario configurare i criteri di archiviazione di Lync Server 2013 per gli utenti. Configurare invece i criteri di blocco sul posto di Exchange per supportare l'archiviazione per gli utenti ospitati in Exchange 2013, con le cassette postali inserite sul posto. Per informazioni dettagliate sulla configurazione di questi criteri, vedere la documentazione del prodotto Exchange 2013.

  - Se non si usa l'integrazione di Microsoft Exchange per tutti gli utenti della distribuzione, è necessario aggiungere i database di archiviazione di Lync Server (database di SQL Server) alla topologia e quindi pubblicarlo, nonché configurare i criteri e le impostazioni per gli utenti, prima di poter archiviare i dati per tali utenti. È possibile distribuire i database di archiviazione contemporaneamente alla distribuzione della topologia iniziale o dopo avere distribuito almeno un pool di front-end o un server Standard Edition. Questo documento descrive come distribuire i database di archiviazione aggiungendoli a una distribuzione esistente.

Se si Abilita l'archiviazione in un pool Front-end o in un server Standard Edition, è consigliabile abilitarlo per tutti gli altri pool Front end e i server Standard Edition nella distribuzione. Il motivo è che gli utenti le cui comunicazioni devono essere archiviati possono essere invitati a una conversazione di messaggistica istantanea di gruppo o a riunioni ospitate in un pool diverso. Se l'archiviazione non è abilitata nel pool in cui è ospitata la conversazione o la riunione, la sessione completa potrebbe non essere archiviata. In questi casi, è ancora possibile archiviare messaggi istantanei con utenti abilitati all'archiviazione, ma non per i file di contenuto di conferenza e gli eventi di conferenza o di uscita.

<div>


> [!IMPORTANT]  
> Se l'archiviazione è fondamentale per i motivi di conformità dell'organizzazione, assicurarsi di distribuire l'archiviazione, configurare i criteri e altre opzioni a livello appropriato e abilitarla per tutti gli utenti appropriati prima di abilitare gli utenti per Lync Server 2013.



</div>

</div>

<div>

## <a name="archiving-deployment-process"></a>Processo di distribuzione dell'archiviazione

La tabella seguente offre una panoramica dei passaggi necessari per distribuire l'archiviazione in una topologia esistente.


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
<th>Ruoli e appartenenze ai gruppi</th>
<th>Documentazione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Installare hardware e software prerequisiti</strong></p></td>
<td><ul>
<li><p>Per usare l'integrazione di Microsoft Exchange (usando Exchange 2013 per l'archiviazione dello spazio di archiviazione per alcuni o tutti gli utenti), è necessaria una distribuzione di Exchange 2013 esistente.</p></li>
<li><p>Per usare database di archiviazione distinti (tramite database di SQL Server) per l'archiviazione dello spazio di archiviazione per alcuni o tutti gli utenti, SQL Server nel server in cui verranno archiviati i dati di archiviazione.</p></li>
</ul>
<div>

> [!NOTE]  
> L'archiviazione viene eseguita nei server front-end di un pool Enterprise e di server Standard Edition. Non ha requisiti hardware o software aggiuntivi oltre a ciò che è necessario per installare tali server.


</div></td>
<td><p>Utente del dominio che è un membro del gruppo Administrators locale.</p></td>
<td><p><a href="lync-server-2013-supported-hardware.md">Hardware supportato per Lync Server 2013</a> nella documentazione relativa alla supportabilità.</p>
<p><a href="lync-server-2013-server-software-and-infrastructure-support.md">Supporto di software e infrastrutture server in Lync server 2013</a> nella documentazione relativa alla supportabilità.</p>
<p><a href="lync-server-2013-technical-requirements-for-archiving.md">Requisiti tecnici per l'archiviazione in Lync Server 2013</a> nella documentazione relativa alla pianificazione.</p>
<p><a href="lync-server-2013-setting-up-systems-and-infrastructure-for-archiving.md">Configurazione di sistemi e infrastrutture per l'archiviazione in Lync Server 2013</a> nella documentazione relativa alla distribuzione.</p>
<p><a href="lync-server-2013-exchange-and-sharepoint-integration-support.md">Supporto di Exchange Server e integrazione di SharePoint in Lync server 2013</a> nella documentazione relativa alla supportabilità.</p></td>
</tr>
<tr class="even">
<td><p><strong>Creare la topologia interna appropriata per supportare l'archiviazione (solo se non si usa l'integrazione di Microsoft Exchange per tutti gli utenti della distribuzione)</strong></p></td>
<td><p>Eseguire Generatore di topologia per aggiungere i database di archiviazione di Lync Server 2013 (database di SQL Server) alla topologia e quindi pubblicare la topologia.</p></td>
<td><p>Per definire una topologia per incorporare i database di archiviazione, un account membro del gruppo utenti locali.</p>
<p>Per pubblicare la topologia, un account che sia un membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins e che disponga delle autorizzazioni controllo completo (lettura/scrittura/modifica) nella condivisione file da usare per l'archivio di file di Lync Server 2013 (in modo che il generatore di topologia possa configurare gli elenchi DACL necessari).</p></td>
<td><p><a href="lync-server-2013-adding-archiving-databases-to-an-existing-lync-server-2013-deployment.md">Aggiunta di database di archiviazione a una distribuzione di Lync Server 2013 esistente</a> nella documentazione relativa alla distribuzione.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Configurare l'autenticazione da server a server (solo se si usa l'integrazione di Microsoft Exchange)</strong></p></td>
<td><p>Configurare i server per consentire l'autenticazione tra Lync Server 2013 ed Exchange 2013. È consigliabile eseguire <strong>test-CsExchangeStorageConnectivity testuser_sipUri-dumpster della cartella</strong> per convalidare la connettività di archiviazione dell'archiviazione di Exchange prima di abilitare l'archiviazione.</p></td>
<td><p>Un account con le autorizzazioni appropriate per la gestione dei certificati nei server.</p></td>
<td><p><a href="lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md">Gestione dell'autenticazione server-Server (OAuth) e delle applicazioni partner in Lync server 2013</a> nella documentazione relativa alla distribuzione o nella documentazione delle operazioni.</p></td>
</tr>
<tr class="even">
<td><p><strong>Configurare i criteri di archiviazione e le configurazioni</strong></p></td>
<td><p>Configurare l'archiviazione, ad esempio se usare l'integrazione di Microsoft Exchange, i criteri globali e tutti i criteri per i siti e gli utenti (quando non si usa l'integrazione di Microsoft Exchange per tutti gli archivi dati) e le opzioni di archiviazione specifiche, come la modalità critica e i dati esportare ed eliminare.</p>
<p>Se si usa l'integrazione di Microsoft Exchange, configurare i criteri di blocco sul posto di Exchange in base alle esigenze.</p></td>
<td><p>Gruppo RTCUniversalServerAdmins (solo Windows PowerShell) o assegna agli utenti il ruolo CSArchivingAdministrator o CSAdministrator.</p></td>
<td><p><a href="lync-server-2013-configuring-support-for-archiving.md">Configurazione del supporto per l'archiviazione in Lync Server 2013</a> nella documentazione relativa alla distribuzione.</p>
<p>Documentazione del prodotto Exchange (se si usa l'integrazione di Microsoft Exchange).</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="deploying-lync-server-and-microsoft-exchange-in-different-forests"></a>Distribuzione di Lync Server e Microsoft Exchange in foreste diverse

Se Microsoft Exchange Server non è distribuito nella stessa foresta di Lync Server, è necessario verificare che gli attributi di Exchange Active Directory seguenti siano sincronizzati con la foresta in cui è distribuito Lync Server:

1.  msExchUserHoldPolicies

2.  proxyAddresses

Questo è un attributo multivalore. Quando si sincronizza questo attributo, è necessario unire i valori, non sostituirli per evitare che i valori esistenti vengano persi.

</div>

</div>

<span> </span>

</div>

</div>

</div>

