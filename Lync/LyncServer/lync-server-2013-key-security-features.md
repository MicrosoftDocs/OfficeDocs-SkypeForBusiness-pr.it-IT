---
title: 'Lync Server 2013: caratteristiche di sicurezza principali'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Key security features in Lync Server 2013
ms:assetid: bf2a3b8f-73c6-47e1-8c9e-ca1dc1a502bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn342829(v=OCS.15)
ms:contentKeyID: 56107266
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 53a6d9e23442cb127f0f08849e18f1d63bae76d6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979837"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="key-security-features-in-lync-server-2013"></a>Caratteristiche di sicurezza chiave in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-07-18_

Lync Server 2013 include diverse funzionalità di sicurezza, tra cui l'autenticazione da server a server, il controllo dell'accesso basato sui ruoli e lo spazio di archiviazione centralizzato dei dati di configurazione.

Questo articolo offre una panoramica di alto livello sulla sicurezza di Lync Server 2013.

<div>

## <a name="key-security-features-in-lync-server-2013"></a>Caratteristiche di sicurezza chiave in Lync Server 2013

La sicurezza è un argomento molto ampio. La sicurezza raggiunge tutte le funzionalità di Lync Server 2013, nonché database, servizi e hardware che costituiscono un ecosistema Lync. In questo articolo vengono illustrate alcune delle funzionalità di Lync Server 2013, in particolare progettate per la sicurezza.

<div>

## <a name="planning-and-design-tools"></a>Strumenti di pianificazione e progettazione

Lync Server 2013 offre due strumenti per semplificare la pianificazione e la progettazione e per ridurre la possibilità di configurare automaticamente i componenti di Lync Server.

  - **Lo strumento di pianificazione della topologia** automatizza gran parte del processo di progettazione della topologia. È possibile esportare i risultati dello strumento di pianificazione in Generatore di topologia, che è lo strumento necessario per installare ogni server in cui è in uso Lync Server 2013.

  - **Generatore di topologie** archivia tutte le informazioni di configurazione nell'Central Management store.

Per informazioni dettagliate su questi strumenti, vedere [pianificazione di Lync Server 2013](lync-server-2013-planning.md).

</div>

<div>

## <a name="central-management-store"></a>Central Management store

In Lync Server 2013 i dati di configurazione relativi a server e servizi fanno parte dell'Central Management store. Il Central Management store offre uno spazio di archiviazione robusto e schematizzato dei dati necessari per definire, configurare, gestire, amministrare, descrivere e gestire una distribuzione di Lync Server. Convalida inoltre i dati per garantire la coerenza della configurazione. Tutte le modifiche apportate ai dati di configurazione si verificano presso l'Central Management store, eliminando i problemi di "fuori sincrono".

Le copie di sola lettura dei dati vengono replicate in tutti i server della topologia, inclusi Edge Server e Survivable Branch Appliance. La replica è gestita da un servizio che, per impostazione predefinita, viene eseguito nel contesto del servizio di rete, riducendo i diritti e le autorizzazioni a quello di un utente semplice nel computer.

</div>

<div>

## <a name="server-to-server-authentication"></a>Autenticazione da server a server

In Lync Server 2013 l'autenticazione può essere configurata tra i server tramite il protocollo OAuth (Open Authorization). Ad esempio, è possibile configurare Lync Server 2013 per l'autenticazione con un server in cui è in uso Exchange Server 2013. Usando il protocollo OAuth, il server Lync e il server Exchange possono considerarsi attendibili. Questo consente di integrare i prodotti in modo uniforme. Per informazioni dettagliate, vedere [gestione dell'autenticazione server-Server (OAuth) e delle applicazioni partner in Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)

</div>

<div>

## <a name="windows-powershell-based-management-and-web-based-management-interface"></a>Interfaccia di gestione basata su Windows PowerShell e gestione basata sul Web

Lync Server 2013 offre una potente interfaccia di gestione, basata sull'interfaccia della riga di comando di Windows PowerShell. Include i cmdlet per la gestione della sicurezza e le funzionalità di sicurezza di Windows PowerShell sono abilitate per impostazione predefinita in modo che gli utenti non possano eseguire facilmente o inconsapevolmente gli script. Questo significa che le impostazioni predefinite del software sono impostate in modo da aiutare automaticamente a massimizzare la sicurezza e ridurre i viali di attacco. Per informazioni dettagliate sul supporto per la gestione di Windows PowerShell in Lync Server 2013, vedere [Lync server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).

</div>

<div>

## <a name="role-based-access-control-rbac"></a>Controllo di accesso basato sui ruoli (RBAC)

Microsoft Lync Server 2013 fornisce il controllo di accesso basato sui ruoli (RBAC) per consentire di delegare le attività amministrative mantenendo standard elevati per la sicurezza. È possibile usare RBAC per seguire il principio "privilegio minimo", in cui agli utenti vengono assegnati solo i diritti amministrativi necessari per i processi. Lync Server 2013 introduce la possibilità di creare un nuovo ruolo e anche la possibilità di modificare un ruolo esistente. Per informazioni dettagliate, vedere [pianificazione per il controllo dell'accesso basato sui ruoli in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md).

</div>

</div>

<div>

## <a name="network-address-translation-nat"></a>NAT (Network Address Translation)

Lync Server 2013 non supporta l'uso di NAT (Network Address Translation) nell'interfaccia interna di Edge Server, ma supporta l'inserimento dell'interfaccia esterna di Access Edge service, Web Conferencing Edge service e A/V Edge service dietro un router o un firewall che esegue la traduzione di indirizzi di rete per le topologie di server perimetrali consolidate singole e in scala. Più Edge Server dietro un bilanciamento del carico hardware non può usare NAT. Se più Edge Server usano NAT sulle loro interfacce esterne, è necessario il bilanciamento del carico DNS (Domain Name System). A sua volta, l'uso del bilanciamento del carico DNS consente di ridurre il numero di indirizzi IP pubblici per ogni server perimetrale in un pool di Edge Server. Per informazioni dettagliate, vedere[pianificazione per l'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md).

<div>


> [!NOTE]  
> Se si esegue la Federazione con le aziende che hanno una distribuzione di Microsoft Office Communications Server 2007 ed è necessario usare audio/video tra l'organizzazione e l'organizzazione federata, i requisiti della porta saranno quelli della versione precedente di Edge Server distribuiti. Ad esempio, gli intervalli di porta necessari per le versioni precedenti devono essere aperti per entrambe le aziende fino a quando il partner federativo non aggiorna i propri Edge Server a Lync Server 2013. A questo punto, i requisiti della porta possono essere rivisti e ridotti in base alla nuova configurazione.



</div>

</div>

<div>

## <a name="simplified-certificates-for-edge-servers"></a>Certificati semplificati per Edge Server

La distribuzione guidata può automaticamente popolare i nomi dei soggetti (SNs) e i nomi alternativi oggetto (SANs), riducendo la possibilità di includere voci non necessarie e potenzialmente non sicure.

</div>

<div>

## <a name="trustworthy-computing-security-development-lifecycle-sdl"></a>Ciclo di vita per lo sviluppo della sicurezza (SDL) Trustworthy Computing

Lync Server 2013 è progettato e sviluppato in conformità con il ciclo di vita Microsoft Trustworthy Computing Security Development Lifecycle (SDL), <http://go.microsoft.com/fwlink/?linkid=68761>descritto in.

  - ****   In modo affidabile in base alla progettazione il primo passaggio per creare un sistema di comunicazioni unificate più sicuro consiste nel progettare modelli di minacce e testare ogni funzionalità come è stata progettata. Microsoft esegue inoltre test al di fuori del comportamento progettato per individuare le vulnerabilità di sicurezza derivanti da un comportamento del prodotto imprevisto. Diversi miglioramenti relativi alla sicurezza sono stati integrati nel processo e nelle pratiche di codifica. Gli strumenti della fase di compilazione rilevano sovraccarichi del buffer e altre potenziali minacce alla sicurezza prima che il codice venga archiviato nel prodotto finale. Ovviamente, è impossibile progettare contro tutte le minacce alla sicurezza sconosciute. Nessun sistema può garantire una protezione completa. Tuttavia, poiché lo sviluppo del prodotto ha abbracciato i principi di progettazione sicuri fin dall'inizio, Lync Server 2013 incorpora tecnologie di sicurezza standard del settore come parte fondamentale della sua architettura.

  - **Trustworthy per**   impostazione predefinita per impostazione predefinita, le comunicazioni di rete in Lync Server 2013 sono crittografate. Poiché tutti i server usano i certificati e l'autenticazione Kerberos, TLS, Secure Real-Time Transport Protocol (SRTP) e altre tecniche di crittografia standard del settore, tra cui la crittografia AES (Advanced Encryption Standard) di 128 bit, praticamente tutti i Lync I dati del server sono protetti in rete. Il controllo di accesso basato sui ruoli consente inoltre di distribuire server che esegue Lync Server 2013 in modo che ogni ruolo del server esegua solo i servizi e disponga solo delle autorizzazioni correlate a tali servizi, che sono appropriate per il ruolo del server.

  - **Attendibile tramite distribuzione**   tutta la documentazione di Lync Server 2013 include le procedure consigliate e le raccomandazioni per determinare e configurare i livelli di sicurezza ottimali per la distribuzione e valutare i rischi per la sicurezza dell'attivazione delle opzioni non predefinite.

</div>

</div>

<span> </span>

</div>

</div>

</div>

