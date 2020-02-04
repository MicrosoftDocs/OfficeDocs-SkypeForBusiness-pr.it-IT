---
title: 'Lync Server 2013: Servizi di dominio Active Directory per Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory Domain Services for Lync Server 2013
ms:assetid: 5483afd5-d8af-4825-ae95-a82dbe941dbf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481129(v=OCS.15)
ms:contentKeyID: 59893871
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ac4b4da954fd792559d2160ce457aec91cb0ac6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730496"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="active-directory-domain-services-for-lync-server-2013"></a>Servizi di dominio Active Directory per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-11-13_

Active Directory Domain Services funziona come servizio directory per le reti Windows Server 2003, Windows Server 2008, Windows Server 2012 e Windows Server 2012 R2. Servizi di dominio Active Directory funge anche da fondamento per cui è stata creata l'infrastruttura di sicurezza di Microsoft Lync Server 2013. Lo scopo di questa sezione è descrivere in che modo Lync Server 2013 USA i servizi di dominio Active Directory per creare un ambiente affidabile per la messaggistica istantanea, le conferenze Web, i contenuti multimediali e la voce. Per informazioni dettagliate sulle estensioni di Lync Server per i servizi di dominio Active Directory e sulla preparazione dell'ambiente per i servizi di dominio Active Directory, vedere [preparazione di servizi di dominio Active Directory per Lync server 2013](lync-server-2013-preparing-active-directory-domain-services.md) nella documentazione relativa alla distribuzione. Per informazioni dettagliate sul ruolo dei servizi di dominio Active Directory nelle reti Windows Server, vedere la documentazione relativa alla versione del sistema operativo in uso.

Lync Server 2013 USA i servizi di dominio Active Directory per archiviare:

  - Impostazioni globali che richiedono tutti i server in cui è in uso Lync Server 2013 in una foresta.

  - Informazioni sul servizio che identificano i ruoli di tutti i server in cui è in uso Lync Server 2013 in una foresta.

  - Alcune impostazioni utente.

<div>

## <a name="active-directory-infrastructure"></a>Infrastruttura di Active Directory

I requisiti di infrastruttura per Active Directory includono i seguenti:

  - Requisiti del sistema operativo per i controller di dominio

  - Requisiti del livello di funzionalità Domain e Forest

  - Requisiti del dominio catalogo globale

Per informazioni dettagliate, vedere [requisiti per l'infrastruttura di Active Directory per Lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md) nella documentazione relativa alla distribuzione.

</div>

<div>

## <a name="active-directory-domain-services-preparation"></a>Preparazione dei servizi di dominio Active Directory

<div>


> [!NOTE]  
> È consigliabile distribuire le impostazioni globali nel contenitore di configurazione anziché nel contenitore di sistema. Questo non migliora la sicurezza, ma può determinare miglioramenti della scalabilità per alcune topologie di servizi di dominio Active Directory. Se si esegue la migrazione da Microsoft Office Communications Server 2007 e si usa il contenitore di sistema ma si prevede di usare il contenitore di configurazione, è necessario trasferire le impostazioni nel contenitore di sistema prima di eseguire qualsiasi preparazione per l'aggiornamento. Per eseguire la migrazione delle impostazioni del contenitore di sistema nel contenitore di configurazione, vedere lo strumento di migrazione delle <A href="http://go.microsoft.com/fwlink/p/?linkid=145236">http://go.microsoft.com/fwlink/p/?LinkId=145236</A>impostazioni globali di Office Communications Server 2007.



</div>

Quando si distribuisce Lync Server 2013, il primo passaggio consiste nel preparare i servizi di dominio Active Directory. La preparazione dei servizi di dominio Active Directory per Lync Server 2013 è costituita dai tre passaggi seguenti:

  - **Preparare lo schema**. Questa attività estende lo schema in servizi di dominio Active Directory per includere classi e attributi specifici di Lync Server 2013. Per informazioni dettagliate sulla preparazione dello schema, vedere [eseguire la preparazione dello schema di Active Directory in Lync Server 2013](lync-server-2013-running-schema-preparation.md) nella documentazione relativa alla distribuzione. Per altre informazioni, vedere [migrazione da Office Communications Server 2007 R2 a Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md).

  - **Preparare Forest**. Questa attività crea impostazioni globali e oggetti nel dominio radice della foresta, insieme al servizio universale e ai gruppi amministrativi che regolano l'accesso a queste impostazioni e agli oggetti. Per informazioni dettagliate sulla preparazione della foresta, vedere [eseguire la preparazione della foresta per Lync Server 2013](lync-server-2013-running-forest-preparation.md) nella documentazione relativa alla distribuzione.

  - **Preparare il dominio**. Questa attività aggiunge le necessarie voci di controllo di accesso (ACE) ai gruppi universali che assegnano le autorizzazioni per ospitare e gestire gli utenti all'interno del dominio. Questa attività deve essere completata in tutti i domini in cui si vogliono distribuire server che utilizzano Lync Server 2013 e tutti i domini in cui risiedono gli utenti di Lync Server. Per informazioni dettagliate sulla preparazione del dominio, vedere [eseguire la preparazione del dominio per Lync Server 2013](lync-server-2013-running-domain-preparation.md) nella documentazione relativa alla distribuzione.

Per una panoramica del processo completo per la preparazione di Active Directory e i diritti e le autorizzazioni necessarie per eseguire ogni passaggio, vedere [requisiti dell'infrastruttura Active Directory per Lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md) nella documentazione relativa alla distribuzione.

</div>

<div>

## <a name="universal-groups"></a>Gruppi universali

Durante la preparazione della foresta, Lync Server 2013 crea diversi gruppi universali all'interno di servizi di dominio Active Directory con l'autorizzazione per accedere e gestire le impostazioni e i servizi globali. Questi gruppi universali includono:

  - **Gruppi amministrativi**. Questi gruppi definiscono i ruoli di amministratore fondamentali per una rete Lync Server. Durante la preparazione della foresta, questi gruppi di amministratori vengono aggiunti ai gruppi di infrastruttura di Lync Server.

  - **Gruppi di servizi**. Questi gruppi sono account di servizio necessari per accedere a vari servizi forniti da Lync Server.

  - **Gruppi di infrastrutture**. Questi gruppi consentono di accedere ad aree specifiche dell'infrastruttura di Lync Server. Funzionano come componenti di gruppi amministrativi e non devono essere modificati o aggiunti direttamente agli utenti. Durante la preparazione della foresta, i gruppi di servizi e di amministrazione specifici vengono aggiunti ai gruppi di infrastruttura appropriati.

Per informazioni dettagliate sui gruppi universali specifici creati durante la preparazione di Active Directory per Lync Server, nonché i gruppi di servizi e di amministrazione aggiunti ai gruppi di infrastruttura, vedere [modifiche apportate dalla preparazione della foresta in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) nella documentazione relativa alla distribuzione.

<div>


> [!NOTE]  
> Lync Server 2013 supporta i gruppi universali di Windows Server 2012 per i server che utilizzano Lync Server 2013 e i sistemi operativi Windows Server 2003 per i controller di dominio. I membri dei gruppi universali possono includere altri gruppi e account da qualsiasi dominio nell'albero di dominio o nella foresta e possono essere assegnate autorizzazioni in qualsiasi dominio nell'albero o nella foresta del dominio. Il supporto del gruppo universale, combinato con la delega dell'amministratore, semplifica la gestione di una distribuzione di Lync Server. Ad esempio, non è necessario aggiungere un dominio a un altro per consentire a un amministratore di gestire entrambe le proprie esigenze.



</div>

</div>

<div>

## <a name="role-based-access-control"></a>Controllo dell'accesso basato sui ruoli

Oltre a creare gruppi di servizi e di amministrazione universali e ad aggiungere gruppi di servizi e di amministrazione ai gruppi universali appropriati, la preparazione della foresta crea anche gruppi di controllo di accesso basati sui ruoli. Per informazioni dettagliate sui gruppi RBAC specifici creati dalla preparazione della foresta, vedere le [modifiche apportate dalla preparazione della foresta in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) nella documentazione relativa alla distribuzione. Per altre informazioni sui gruppi RBAC, vedere [controllo di accesso basato sui ruoli (RBAC) per Lync Server 2013](lync-server-2013-role-based-access-control-rbac.md).

</div>

<div>

## <a name="access-control-entries-aces-and-inheritance"></a>Voci di controllo di accesso (ACE) ed ereditarietà

La preparazione della foresta crea sia gli assi privati che quelli pubblici e, aggiungendo le voci ACE per i gruppi universali creati. Crea Ace private specifiche nel contenitore di impostazioni globali usato da Lync Server. Questo contenitore viene usato solo da Lync Server e si trova nel contenitore di configurazione o nel contenitore di sistema nel dominio radice, a seconda di dove si archiviano le impostazioni globali.

Il passaggio preparazione del dominio aggiunge le voci di controllo di accesso (ACE) necessarie ai gruppi universali che assegnano le autorizzazioni per ospitare e gestire gli utenti all'interno del dominio. La preparazione del dominio crea ACE nella radice del dominio e tre contenitori predefiniti: User, computer e Domain controller.

Per informazioni dettagliate sulle voci ACE pubbliche create e aggiunte dalla preparazione della foresta e dalla preparazione del dominio, vedere [modifiche apportate dalla preparazione della foresta in Lync server 2013](lync-server-2013-changes-made-by-forest-preparation.md) e [modifiche apportate dalla preparazione del dominio in Lync Server 2013](lync-server-2013-changes-made-by-domain-preparation.md) nella documentazione relativa alla distribuzione.

Le organizzazioni spesso bloccano i servizi di dominio Active Directory (AD DS) per ridurre i rischi per la sicurezza. Tuttavia, un ambiente Active Directory bloccato può limitare le autorizzazioni necessarie per Lync Server 2013. Questa operazione può includere la rimozione di Ace da contenitori e unità organizzative e la disabilitazione dell'ereditarietà delle autorizzazioni per gli oggetti utente, contatto, InetOrgPerson o computer. In un ambiente Active Directory bloccato è necessario impostare manualmente le autorizzazioni sui contenitori e le UO che le richiedono. Per informazioni dettagliate, vedere [preparazione di servizi di dominio Active Directory bloccati in Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md) nella documentazione relativa alla distribuzione.

</div>

<div>

## <a name="server-information"></a>Informazioni sul server

Durante l'attivazione, Lync Server 2013 pubblica le informazioni sul server nei tre percorsi seguenti in servizi di dominio Active Directory:

  - Un punto di connessione del servizio (SCP) in ogni oggetto computer di Active Directory corrispondente a un computer fisico in cui è installato Lync Server 2013.

  - Oggetti server creati nel contenitore della classe **msRTCSIP-Pools** .

  - Server attendibili specificati in Generatore di topologia.

</div>

<div>

## <a name="service-connection-points"></a>Punti di connessione del servizio

Ogni oggetto Lync Server 2013 in servizi di dominio Active Directory include un SCP denominato RTC Services, che a sua volta contiene un numero di attributi che identificano ogni computer e specificano i servizi forniti. Tra gli attributi SCP più importanti ci sono *serviceDNSName*, *serviceDNSNameType*, *serviceClassName*e *serviceBindingInformation*. Le applicazioni di Asset Management di terze parti possono recuperare le informazioni sul server in una distribuzione eseguendo una query su questi e altri attributi SCP.

</div>

<div>

## <a name="active-directory-server-objects"></a>Oggetti server di Active Directory

Ogni ruolo del server di Lync Server 2013 include un oggetto Active Directory corrispondente i cui attributi definiscono i servizi forniti da tale ruolo. Inoltre, quando viene attivato un server Standard Edition o quando viene creato un pool Enterprise Edition, Lync Server 2013 crea un nuovo oggetto **msRTCSIP-Pool** nel contenitore **msRTCSIP-** pools. La classe **msRTCSIP-Pool** specifica il nome di dominio completo (FQDN) del pool, insieme all'associazione tra i componenti front-end e back-end del pool. Un server Standard Edition viene considerato come un pool logico di cui le estremità anteriore e posteriore sono collocate in un singolo computer.

</div>

<div>

## <a name="trusted-servers"></a>Server attendibili

In Lync Server 2013 i server attendibili sono quelli specificati quando si esegue Generatore di topologie e si pubblica la topologia. La topologia pubblicata, incluse tutte le informazioni sul server, è archiviata in Central Management store. Solo i server definiti nell'Central Management store sono attendibili. In Lync Server 2013 un server attendibile è quello che soddisfa i criteri seguenti:

  - Il nome di dominio completo del server si trova nella topologia archiviata in Central Management store.

  - Il server presenta un certificato valido da una CA attendibile. Per informazioni dettagliate, vedere [requisiti per l'infrastruttura dei certificati per Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md).

Se uno di questi criteri non è presente, il server non è attendibile e la connessione viene rifiutata. Questo doppio requisito impedisce un attacco possibile, se improbabile, in cui un server Rogue tenti di assumere il nome di dominio completo del server valido.

Inoltre, per consentire alle distribuzioni di Microsoft Office Communications Server 2007 R2 e Microsoft Office Communications Server 2007 di comunicare con i server di Lync Server 2013, Lync Server 2013 crea contenitori durante la preparazione della foresta per la partecipazione a elenchi di server attendibili per le versioni precedenti. La tabella seguente descrive i contenitori creati per consentire la compatibilità con le distribuzioni precedenti.

### <a name="trusted-server-lists-and-their-active-directory-containers-for-compatibility-with-previous-releases"></a>Elenchi di server attendibili e relativi contenitori di Active Directory per la compatibilità con le versioni precedenti

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Elenco di server attendibili</th>
<th>Contenitore di Active Directory</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Server Standard Edition e server front-end del pool Enterprise</p></td>
<td><p>RTC Service/impostazioni globali</p></td>
</tr>
<tr class="even">
<td><p>Server di conferenza</p></td>
<td><p>RTC Service/trusted MCU</p></td>
</tr>
<tr class="odd">
<td><p>Server Web Components</p></td>
<td><p>RTC Service/TrustedWebComponentsServers</p></td>
</tr>
<tr class="even">
<td><p>Mediation Server e server Communicator Web Access, server applicazioni, registrar con QoE, servizio di conferenza A/V (anche server SIP di terze parti)</p></td>
<td><p>Servizio RTC/servizi attendibili</p></td>
</tr>
<tr class="odd">
<td><p>Server proxy</p></td>
<td><p>Lync Server 2013 non supporta la compatibilità con le versioni precedenti per i server proxy</p></td>
</tr>
</tbody>
</table>


Per supportare i server attendibili delle versioni precedenti, è necessario eseguire lo strumento Analizzatore procedure consigliate. Per informazioni dettagliate sull'uso dell'Analizzatore procedure consigliate, vedere [http://go.microsoft.com/fwlink/p/?LinkId=330633](http://go.microsoft.com/fwlink/p/?linkid=330633).

</div>

</div>

<span> </span>

</div>

</div>

</div>

