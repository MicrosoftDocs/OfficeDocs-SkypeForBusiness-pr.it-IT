---
title: "Lync Server 2013: elenco di controllo di distribuzione per l'archiviazione"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for Archiving
ms:assetid: 7479734d-be01-40d9-ad82-320a09d19d04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205009(v=OCS.15)
ms:contentKeyID: 48184516
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ccec3917e892d1ba6c3e1841773c77e8c2d015d0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514529"
---
# <a name="deployment-checklist-for-archiving-in-lync-server-2013"></a>Elenco di controllo di distribuzione per l'archiviazione in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-18_

L'archiviazione viene automaticamente installata su ogni Front End Server nella distribuzione di Lync Server 2013, ma è comunque necessario configurarla prima di poterla utilizzare. I passaggi necessari per la configurazione, riepilogati in questa sezione, costituiscono la distribuzione dell'archiviazione.

<div>

## <a name="deployment-sequence"></a>Sequenza di distribuzione

La modalità di configurazione dell'archiviazione dipende dall'opzione di archiviazione che si seleziona:

  - Se si utilizza l'integrazione di Microsoft Exchange per tutti gli utenti nella distribuzione, non è necessario configurare i criteri di archiviazione di Lync Server 2013 per gli utenti. Invece, configurare i criteri di Exchange In-Place Hold per supportare l'archiviazione per gli utenti ospitati in Exchange 2013, con le loro cassette postali inserite In-Place blocco. Per informazioni dettagliate sulla configurazione di questi criteri, vedere la documentazione del prodotto Exchange 2013.

  - Se non si utilizza l'integrazione di Microsoft Exchange per tutti gli utenti nella distribuzione, è necessario aggiungere i database di archiviazione di Lync Server (database di SQL Server) alla topologia e quindi pubblicarli, nonché configurare i criteri e le impostazioni per gli utenti, prima di poter archiviare i dati per tali utenti. È possibile distribuire i database di archiviazione mentre si distribuisce la topologia iniziale o dopo avere distribuito almeno un pool Front End o un server Standard Edition. In questo documento viene illustrato come distribuire database di archiviazione aggiungendoli a una distribuzione esistente.

Se si abilita l'archiviazione in un pool Front End o in un server Standard Edition, sarà necessario abilitarla per tutti gli altri pool Front End e server Standard Edition nella distribuzione. Questo è dovuto al fatto che gli utenti di cui devono essere archiviate le comunicazioni possono essere invitati a una conversazione di messaggistica istantanea di gruppo oppure a riunioni ospitate in un altro pool. Se l'archiviazione non è abilitata nel pool in cui viene ospitata la conversazione o la riunione, potrebbe non essere possibile archiviare l'intera sessione. In questi casi, è possibile archiviare la messaggistica istantanea con utenti abilitati per l'archiviazione, ma non per file di contenuto delle conferenze e eventi di accesso o abbandono della conferenza.

<div>


> [!IMPORTANT]  
> Se l'archiviazione è critica nell'organizzazione per motivi di conformità, assicurarsi di distribuire l'archiviazione, configurare i criteri e altre opzioni al livello appropriato e abilitarla per tutti gli utenti idonei, prima di abilitare tali utenti per Lync Server 2013.



</div>

</div>

<div>

## <a name="archiving-deployment-process"></a>Processo di distribuzione dell'archiviazione

Nella tabella seguente viene fornita una panoramica dei passaggi da eseguire per distribuire l'archiviazione in una topologia esistente.


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
<th>Ruoli e gruppi a cui è necessario appartenere</th>
<th>Documentazione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Installare l'hardware e il software prerequisiti</strong></p></td>
<td><ul>
<li><p>Per utilizzare l'integrazione di Microsoft Exchange (utilizzando Exchange 2013 per l'archiviazione di alcuni o tutti gli utenti), è necessaria una distribuzione di Exchange 2013 esistente.</p></li>
<li><p>Per utilizzare database di archiviazione separati (utilizzando database SQL Server) per l'archiviazione di alcuni o tutti gli utenti, è necessario SQL Server sul server che memorizzerà i dati di archiviazione.</p></li>
</ul>
<div>

> [!NOTE]  
> L'archiviazione è eseguita sui server Front End di un pool Enterprise e server Standard Edition. Non esistono ulteriori requisiti di hardware o software oltre a quelli necessari per l'installazione di questi server.


</div></td>
<td><p>Utente del dominio membro del gruppo Administrators locale</p></td>
<td><p><a href="lync-server-2013-supported-hardware.md">Hardware supportato per Lync Server 2013</a> nella documentazione relativa alla supportabilità.</p>
<p><a href="lync-server-2013-server-software-and-infrastructure-support.md">Supporto dell'infrastruttura e del software server in Lync server 2013</a> nella documentazione relativa alla supportabilità.</p>
<p><a href="lync-server-2013-technical-requirements-for-archiving.md">Requisiti tecnici per l'archiviazione in Lync Server 2013</a> nella documentazione relativa alla pianificazione.</p>
<p><a href="lync-server-2013-setting-up-systems-and-infrastructure-for-archiving.md">Configurazione dei sistemi e dell'infrastruttura per l'archiviazione in Lync Server 2013</a> nella documentazione relativa alla distribuzione.</p>
<p><a href="lync-server-2013-exchange-and-sharepoint-integration-support.md">Supporto per l'integrazione di Exchange Server e SharePoint in Lync server 2013</a> nella documentazione relativa alla supportabilità.</p></td>
</tr>
<tr class="even">
<td><p><strong>Creare la topologia interna appropriata per supportare l'archiviazione (solo se non si utilizza l'integrazione di Microsoft Exchange per tutti gli utenti nella distribuzione)</strong></p></td>
<td><p>Eseguire Generatore di topologie per aggiungere database di archiviazione di Lync Server 2013 (database di SQL Server) alla topologia e quindi pubblicare la topologia.</p></td>
<td><p>Per definire una topologia che incorpori database di archiviazione, un account membro del gruppo Users locale.</p>
<p>Per pubblicare la topologia, un account che sia membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins e che disponga di autorizzazioni di controllo completo (lettura/scrittura/modifica) sulla condivisione file da utilizzare per l'archivio file di Lync Server 2013 (in modo che il generatore di topologie possa configurare gli elenchi DACL necessari).</p></td>
<td><p><a href="lync-server-2013-adding-archiving-databases-to-an-existing-lync-server-2013-deployment.md">Aggiunta dei database di archiviazione a una distribuzione di Lync Server 2013 esistente</a> nella documentazione relativa alla distribuzione.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Configurare l'autenticazione da server a server (solo se si utilizza l'integrazione di Microsoft Exchange)</strong></p></td>
<td><p>Configurare i server per l'abilitazione dell'autenticazione tra Lync Server 2013 ed Exchange 2013. Per convalidare la connettività dello spazio di archiviazione di Exchange prima di abilitare l'archiviazione, è consigliabile eseguire il <strong>dumpster test-CsExchangeStorageConnectivity testuser_sipUri – Folder</strong> .</p></td>
<td><p>Un account con le autorizzazioni appropriate per la gestione dei certificati sul server.</p></td>
<td><p><a href="lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md">Gestione dell'autenticazione da server a server (OAuth) e delle applicazioni partner in Lync server 2013</a> nella documentazione relativa alla distribuzione o nella documentazione relativa alle operazioni.</p></td>
</tr>
<tr class="even">
<td><p><strong>Configurare i criteri e le configurazioni per l'archiviazione</strong></p></td>
<td><p>Configurare l'archiviazione, tra cui l'integrazione di Microsoft Exchange, il criterio globale e tutti i criteri per i siti e gli utenti (quando non si utilizza l'integrazione di Microsoft Exchange per tutti gli archivi dati) e le opzioni di archiviazione specifiche, ad esempio la modalità critica e l'esportazione ed eliminazione dei dati.</p>
<p>Se si utilizza l'integrazione di Microsoft Exchange, configurare i criteri di blocco In-Place di Exchange in base alle esigenze.</p></td>
<td><p>Gruppo RTCUniversalServerAdmins (solo Windows PowerShell) oppure assegnare gli utenti al ruolo CSArchivingAdministrator o CSAdministrator</p></td>
<td><p><a href="lync-server-2013-configuring-support-for-archiving.md">Configurazione del supporto per l'archiviazione in Lync Server 2013</a> nella documentazione relativa alla distribuzione.</p>
<p>Documentazione del prodotto Exchange (se si utilizza l'integrazione di Microsoft Exchange).</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="deploying-lync-server-and-microsoft-exchange-in-different-forests"></a>Distribuzione di Lync Server e di Microsoft Exchange in foreste diverse

Se Microsoft Exchange Server non è distribuito nella stessa foresta di Lync Server, è necessario verificare che i seguenti attributi di Active Directory di Exchange siano sincronizzati con la foresta in cui è distribuito Lync Server:

1.  msExchUserHoldPolicies

2.  proxyAddresses

Si tratta di un attributo a valore multiplo. Quando si sincronizza questo attributo, è necessario unire i valori, e non sostituirli, per evitare che i valori esistenti vengano persi.

</div>

</div>

<span> </span>

</div>

</div>

</div>

