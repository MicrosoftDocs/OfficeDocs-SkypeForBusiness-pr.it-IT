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
ms.openlocfilehash: 00038dce85a7461be37456d9dee263a71f60c113
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199589"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="active-directory-domain-services-for-lync-server-2013"></a>Servizi di dominio Active Directory per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-11-13_

Servizi di dominio Active Directory funge da servizio directory per le reti Windows Server 2003, Windows Server 2008, Windows Server 2012 e Windows Server 2012 R2. Servizi di dominio Active Directory funge anche da fondamento su cui è stata creata l'infrastruttura di sicurezza di Microsoft Lync Server 2013. Lo scopo di questa sezione è descrivere come Lync Server 2013 utilizza servizi di dominio Active Directory per creare un ambiente affidabile per messaggistica istantanea, Web Conferencing, multimediale e vocale. Per informazioni dettagliate sulle estensioni di Lync Server per i servizi di dominio Active Directory e sulla preparazione dell'ambiente per i servizi di dominio Active Directory, vedere [preparazione di servizi di dominio Active Directory per Lync server 2013](lync-server-2013-preparing-active-directory-domain-services.md) nella documentazione relativa alla distribuzione. Per informazioni dettagliate sul ruolo di Servizi di dominio Active Directory nelle reti Windows Server, vedere la documentazione per la versione del sistema operativo in uso.

Lync Server 2013 utilizza servizi di dominio Active Directory per archiviare:

  - Impostazioni globali che richiedono tutti i server che eseguono Lync Server 2013 in una foresta.

  - Informazioni sui servizi che identificano i ruoli di tutti i server che eseguono Lync Server 2013 in una foresta.

  - Alcune impostazioni utente.

<div>

## <a name="active-directory-infrastructure"></a>Infrastruttura di Active Directory

I requisiti di infrastruttura per Active Directory includono i seguenti:

  - Requisiti del sistema operativo per i controller di dominio

  - Requisiti per il livello funzionale di foresta e dominio

  - Requisiti di dominio per il catalogo globale

Per informazioni dettagliate, vedere [Active Directory Infrastructure requirements for Lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md) nella documentazione relativa alla distribuzione.

</div>

<div>

## <a name="active-directory-domain-services-preparation"></a>Preparativi per Servizi di dominio Active Directory

<div>


> [!NOTE]  
> È consigliabile distribuire le impostazioni globali nel contenitore della configurazione anziché nel contenitore di sistema. Ciò non consente miglioramenti della sicurezza, ma può consentire miglioramenti della scalabilità per alcune topologie di Servizi di dominio Active Directory. Se si esegue la migrazione da Microsoft Office Communications Server 2007 ed è stato utilizzato il contenitore di sistema ma si intende utilizzare il contenitore di configurazione, è necessario spostare le impostazioni nel contenitore di sistema prima di eseguire qualsiasi preparazione all'aggiornamento. Per eseguire la migrazione delle impostazioni del contenitore di sistema nel contenitore di configurazione, vedere Office Communications Server 2007 Global <A href="https://go.microsoft.com/fwlink/p/?linkid=145236">https://go.microsoft.com/fwlink/p/?LinkId=145236</A>Settings Migration Tool at.



</div>

Quando si distribuisce Lync Server 2013, il primo passaggio consiste nel preparare i servizi di dominio Active Directory. La preparazione di servizi di dominio Active Directory per Lync Server 2013 è costituita dai tre passaggi seguenti:

  - **Prepara schema**. Questa attività consente di estendere lo schema in servizi di dominio Active Directory per includere classi e attributi specifici di Lync Server 2013. Per informazioni dettagliate sulla preparazione dello schema, vedere [running Active Directory schema preparation in Lync Server 2013](lync-server-2013-running-schema-preparation.md) nella documentazione relativa alla distribuzione. Per ulteriori informazioni, vedere [migrazione da Office Communications Server 2007 R2 a Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md).

  - **Preparare la foresta**. Questa attività consente di creare le impostazioni globali e gli oggetti nel dominio radice della foresta, insieme ai gruppi amministrativi e di servizi universali che regolano l'accesso a queste impostazioni e oggetti. Per informazioni dettagliate sulla preparazione della foresta, vedere [Running Forest Preparation for Lync Server 2013](lync-server-2013-running-forest-preparation.md) nella documentazione relativa alla distribuzione.

  - **Prepara dominio**. Questa attività consente di aggiungere le voci di controllo di accesso (ACE, Access Control Entry) necessarie ai gruppi universali che concedono le autorizzazioni per ospitare e gestire gli utenti nel dominio. Questa attività deve essere completata in tutti i domini in cui si desidera distribuire i server che eseguono Lync Server 2013 e tutti i domini in cui risiedono gli utenti di Lync Server. Per informazioni dettagliate sulla preparazione del dominio, vedere [Running domain preparation for Lync Server 2013](lync-server-2013-running-domain-preparation.md) nella documentazione relativa alla distribuzione.

Per una panoramica del processo completo per la preparazione di Active Directory e dei diritti e delle autorizzazioni necessari per eseguire ogni passaggio, vedere [Active Directory Infrastructure requirements for Lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md) nella documentazione relativa alla distribuzione.

</div>

<div>

## <a name="universal-groups"></a>Gruppi universali

Durante la preparazione della foresta, Lync Server 2013 crea vari gruppi universali all'interno dei servizi di dominio Active Directory che dispongono dell'autorizzazione per l'accesso e la gestione delle impostazioni e dei servizi globali. Questi gruppi universali includono:

  - **Gruppi amministrativi**. Questi gruppi definiscono i ruoli di amministratore fondamentali per una rete di Lync Server. Durante la preparazione della foresta, questi gruppi di amministratori vengono aggiunti ai gruppi di infrastruttura di Lync Server.

  - **Gruppi di servizi**. Questi gruppi sono account di servizio necessari per accedere ai diversi servizi forniti da Lync Server.

  - **Gruppi di infrastrutture**. Questi gruppi forniscono l'autorizzazione per accedere a aree specifiche dell'infrastruttura di Lync Server. Fungono da componenti dei gruppi amministrativi ed è consigliabile non modificarli o aggiungervi direttamente utenti. Durante la preparazione della foresta, i gruppi di servizi e di amministrazione specifici vengono aggiunti ai gruppi di infrastruttura corretti.

Per informazioni dettagliate sugli specifici gruppi universali creati durante la preparazione di Active Directory per Lync Server, nonché i gruppi di servizi e di amministrazione che vengono aggiunti ai gruppi di infrastruttura, vedere [changes made by Forest preparation in Lync server 2013](lync-server-2013-changes-made-by-forest-preparation.md) nella documentazione relativa alla distribuzione.

<div>


> [!NOTE]  
> Lync Server 2013 supporta i gruppi universali in Windows Server 2012 per i server che eseguono Lync Server 2013, nonché i sistemi operativi Windows Server 2003 per i controller di dominio. Ai membri dei gruppi universali, che possono includere altri gruppi e account di qualsiasi dominio della foresta o dell'albero di dominio, è possibile assegnare autorizzazioni in qualsiasi dominio della foresta o dell'albero di dominio. Il supporto di gruppo universale, Unito alla delega dell'amministratore, semplifica la gestione di una distribuzione di Lync Server. Non è più necessario, ad esempio, aggiungere un dominio a un altro per consentire a un amministratore di gestirli entrambi.



</div>

</div>

<div>

## <a name="role-based-access-control"></a>Controllo di accesso basato sui ruoli

Oltre alla creazione di gruppi di amministrazione e di servizio universali e all'aggiunta di gruppi di servizi e di amministrazione ai gruppi universali, la preparazione della foresta crea anche gruppi di controllo dell'accesso basato sui ruoli (RBAC). Per informazioni dettagliate sui gruppi RBAC specifici creati dalla preparazione della foresta, vedere [changes made by Forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) nella documentazione relativa alla distribuzione. Per ulteriori informazioni sui gruppi RBAC, vedere [controllo di accesso basato sui ruoli (RBAC) per Lync Server 2013](lync-server-2013-role-based-access-control-rbac.md).

</div>

<div>

## <a name="access-control-entries-aces-and-inheritance"></a>Voci di controllo di accesso ed ereditarietà

Il processo di preparazione della foresta prevede la creazione sia di voci di controllo di accesso pubbliche che private e l'aggiunta delle voci di controllo di accesso per i gruppi universali creati. Crea voci ACE private specifiche nel contenitore delle impostazioni globali utilizzato da Lync Server. Questo contenitore viene utilizzato solo da Lync Server e si trova nel contenitore di configurazione o nel contenitore di sistema nel dominio radice, a seconda della posizione in cui vengono archiviate le impostazioni globali.

Questa operazione comporta l'aggiunta delle voci di controllo di accesso necessarie ai gruppi universali che concedono autorizzazioni per ospitare e gestire gli utenti nell'ambito del dominio. Con la preparazione del dominio vengono create voci di controllo di accesso nella radice del dominio e tre contenitori predefiniti per utenti, computer e controller di dominio.

Per informazioni dettagliate sulle voci di accesso pubbliche create e aggiunte dalla preparazione della foresta e dalla preparazione del dominio, vedere [changes made by Forest preparation in Lync server 2013](lync-server-2013-changes-made-by-forest-preparation.md) e [changes made by domain preparation in Lync Server 2013](lync-server-2013-changes-made-by-domain-preparation.md) nella documentazione relativa alla distribuzione.

Le organizzazioni scelgono spesso di bloccare Servizi di dominio Active Directory per ridurre i rischi per la sicurezza. Tuttavia, un ambiente Active Directory bloccato può limitare le autorizzazioni richieste da Lync Server 2013. Ciò può includere la rimozione delle voci di controllo di accesso dai contenitori e dalle unità organizzative, nonché la disabilitazione dell'ereditarietà delle autorizzazioni negli oggetti User, Contact, InetOrgPerson o Computer. In un ambiente Active Directory bloccato, le autorizzazioni devono essere impostate manualmente nei contenitori e nelle unità organizzative per cui sono necessarie. Per ulteriori informazioni, vedere [preparazione di servizi di dominio Active Directory bloccati in Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md) nella documentazione relativa alla distribuzione.

</div>

<div>

## <a name="server-information"></a>Informazioni sui server

Durante l'attivazione, Lync Server 2013 pubblica le informazioni sui server nelle tre posizioni seguenti in servizi di dominio Active Directory:

  - Un punto di connessione del servizio (SCP, Service Connection Point) su ogni oggetto computer di Active Directory corrispondente a un computer fisico in cui è installato Lync Server 2013.

  - Oggetti server creati nel contenitore della classe **msRTCSIP-Pools**.

  - Server attendibili specificati in Generatore di topologie.

</div>

<div>

## <a name="service-connection-points"></a>Punti di connessione del servizio

Ogni oggetto Lync Server 2013 in servizi di dominio Active Directory ha un SCP denominato RTC Services, che a sua volta contiene una serie di attributi che identificano ogni computer e specificano i servizi forniti. *serviceDNSName*, *serviceDNSNameType*, *serviceClassname* e *serviceBindingInformation* sono alcuni degli attributi SCP più importanti. Le applicazioni di terze parti per la gestione delle risorse possono recuperare le informazioni sui server in una distribuzione eseguendo una query a fronte di questi e altri attributi SCP.

</div>

<div>

## <a name="active-directory-server-objects"></a>Oggetti server Active Directory

Ogni ruolo del server Lync Server 2013 dispone di un oggetto Active Directory corrispondente i cui attributi definiscono i servizi forniti da tale ruolo. Inoltre, quando un server Standard Edition viene attivato o quando viene creato un pool Enterprise Edition, Lync Server 2013 crea un nuovo oggetto **msRTCSIP-Pool** nel contenitore **msRTCSIP-** pools. La classe **msRTCSIP-Pool** specifica il nome di dominio completo (FQDN) del pool, insieme all'associazione tra i componenti front-end e back-end del pool. Un server Standard Edition viene considerato un pool logico i cui componenti front-end e back-end sono collocati in un solo computer.

</div>

<div>

## <a name="trusted-servers"></a>Server trusted

In Lync Server 2013, i server attendibili sono quelli specificati durante l'esecuzione di generatore di topologie e la pubblicazione della topologia. La topologia pubblicata, incluse tutte le informazioni del server, viene archiviata nell'archivio di gestione centrale. Solo i server definiti nell'archivio di gestione centrale sono trusted. In Lync Server 2013, un server attendibile è in grado di soddisfare i seguenti criteri:

  - Il nome FQDN del server compare nella topologia archiviata nell'archivio di gestione centrale.

  - Il server presenta un certificato valido da un'autorità di certificazione attendibile. Per informazioni dettagliate, vedere [Certificate Infrastructure requirements for Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md).

Se uno di questi criteri non risulta soddisfatto, il server non è trusted e la connessione viene rifiutata. Questo duplice requisito impedisce un possibile, anche se improbabile, attacco in cui un server non autorizzato tenta di prendere il controllo del nome FQDN di un server valido.

Inoltre, per consentire alle distribuzioni di Microsoft Office Communications Server 2007 R2 e Microsoft Office Communications Server 2007 di comunicare con i server di Lync Server 2013, Lync Server 2013 crea contenitori durante la preparazione della foresta per la conservazione degli elenchi di server attendibili per le versioni precedenti. Nella tabella seguente vengono descritti i contenitori creati per abilitare la compatibilità con le distribuzioni precedenti.

### <a name="trusted-server-lists-and-their-active-directory-containers-for-compatibility-with-previous-releases"></a>Elenchi di server trusted e contenitori Active Directory corrispondenti per la compatibilità con le versioni precedenti

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Elenco di server trusted</th>
<th>Contenitore di Active Directory</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Server Standard Edtion e Front End Server del pool Enterprise</p></td>
<td><p>RTC Service/Global Settings</p></td>
</tr>
<tr class="even">
<td><p>Conferencing Server</p></td>
<td><p>RTC Service/Trusted MCUs</p></td>
</tr>
<tr class="odd">
<td><p>Web Components Server</p></td>
<td><p>RTC Service/TrustedWebComponentsServers</p></td>
</tr>
<tr class="even">
<td><p>Mediation Server e Communicator Web Access Server, server applicazioni, funzione di registrazione con QoE, servizio A/V Conferencing (anche server SIP di terze parti)</p></td>
<td><p>RTC Service/Trusted Services</p></td>
</tr>
<tr class="odd">
<td><p>Server proxy</p></td>
<td><p>Lync Server 2013 non supporta la compatibilità con le versioni precedenti per i server proxy</p></td>
</tr>
</tbody>
</table>


Per supportare i server attendibili delle versioni precedenti, è necessario eseguire lo strumento Analizzatore procedure consigliate. Per informazioni dettagliate sull'esecuzione dell'Analizzatore procedure consigliate, vedere [https://go.microsoft.com/fwlink/p/?LinkId=330633](https://go.microsoft.com/fwlink/p/?linkid=330633).

</div>

</div>

<span> </span>

</div>

</div>

</div>

