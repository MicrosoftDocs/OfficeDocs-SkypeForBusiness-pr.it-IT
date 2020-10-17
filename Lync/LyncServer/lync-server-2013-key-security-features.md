---
title: 'Lync Server 2013: caratteristiche di sicurezza principali'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Key security features in Lync Server 2013
ms:assetid: bf2a3b8f-73c6-47e1-8c9e-ca1dc1a502bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn342829(v=OCS.15)
ms:contentKeyID: 56107266
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a1ff88b11c7d0ce007fc3bac38e7e3618771fb7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514023"
---
# <a name="key-security-features-in-lync-server-2013"></a>Caratteristiche principali di sicurezza in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-07-18_

Lync Server 2013 include diverse funzionalità di sicurezza, tra cui l'autenticazione da server a server, il controllo di accesso basato sui ruoli e l'archiviazione centralizzata dei dati di configurazione.

In questo articolo viene fornita una panoramica di alto livello sulla sicurezza di Lync Server 2013.

<div>

## <a name="key-security-features-in-lync-server-2013"></a>Caratteristiche principali di sicurezza in Lync Server 2013

La sicurezza è un argomento molto ampio. La sicurezza raggiunge tutte le funzionalità di Lync Server 2013, nonché i database, i servizi e i componenti hardware che compongono un ecosistema di Lync. In questo articolo vengono illustrate alcune delle funzionalità di Lync Server 2013 in particolare progettate per la sicurezza.

<div>

## <a name="planning-and-design-tools"></a>Strumenti di pianificazione e progettazione

Lync Server 2013 offre due strumenti per semplificare la pianificazione e la progettazione e ridurre la possibilità di configurare in modo non configurabile i componenti di Lync Server.

  - **Lo strumento di pianificazione della topologia** automatizza gran parte del processo di progettazione della topologia. È possibile esportare i risultati dello strumento di pianificazione in Generatore di topologie, che è lo strumento necessario per installare ogni server su cui è in esecuzione Lync Server 2013.

  - **Generatore di topologie** archivia tutte le informazioni di configurazione nell'archivio di gestione centrale.

Per informazioni dettagliate su questi strumenti, vedere [Planning for Lync Server 2013](lync-server-2013-planning.md).

</div>

<div>

## <a name="central-management-store"></a>Archivio di gestione centrale

In Lync Server 2013, i dati di configurazione relativi a server e servizi fanno parte dell'archivio di gestione centrale. Nell'archivio di gestione centrale è disponibile un'archiviazione schematizzato e robusta dei dati necessari per definire, configurare, gestire, amministrare, descrivere e gestire una distribuzione di Lync Server. Convalida inoltre i dati per garantire la coerenza della configurazione. Tutte le modifiche apportate ai dati di configurazione si verificano nell'archivio di gestione centrale, eliminando i problemi di "fuori sincrono".

Le copie di sola lettura dei dati sono replicate in tutti i server della topologia, inclusi i server perimetrali e i Survivable Branch Appliance. La replica viene gestita da un servizio eseguito per impostazione predefinita nel contesto del servizio di rete, riducendo i diritti e le autorizzazioni a quelli di un semplice utente nel computer.

</div>

<div>

## <a name="server-to-server-authentication"></a>Autenticazione da server a server

In Lync Server 2013, l'autenticazione può essere configurata tra i server tramite il protocollo di autorizzazione aperta (OAuth). Ad esempio, è possibile configurare Lync Server 2013 per l'autenticazione con un server su cui è in esecuzione Exchange Server 2013. Se si utilizza il protocollo OAuth, Lync Server e il server Exchange possono considerarsi attendibili. Questo fornisce la possibilità di integrare i prodotti in modo semplice. Per informazioni dettagliate, vedere [Managing server-to-Server Authentication (OAuth) and partner Applications in Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)

</div>

<div>

## <a name="windows-powershell-based-management-and-web-based-management-interface"></a>Interfaccia di gestione basata su Windows PowerShell e gestione basata sul Web

Lync Server 2013 fornisce una potente interfaccia di gestione, basata sull'interfaccia della riga di comando di Windows PowerShell. Questa interfaccia include cmdlet per la gestione della sicurezza e le funzionalità di sicurezza di Windows PowerShell sono abilitate per impostazione predefinita in modo che gli utenti non possano eseguire script facilmente o inconsapevolmente. Ciò significa che le impostazioni predefinite del software sono configurare in modo da ottimizzare automaticamente la sicurezza e ridurre i rischi di attacco. Per informazioni dettagliate sul supporto per la gestione di Windows PowerShell in Lync Server 2013, vedere [Lync server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).

</div>

<div>

## <a name="role-based-access-control-rbac"></a>Controllo di accesso Role-Based (RBAC)

Microsoft Lync Server 2013 fornisce il controllo di accesso basato sui ruoli (RBAC) per consentire di delegare le attività amministrative mantenendo standard elevati per la sicurezza. È possibile utilizzare il controllo di accesso basato sui ruoli per seguire il principio dei privilegi minimi, in base al quale agli utenti vengono concessi solo i diritti amministrativi richiesti dalle loro mansioni. Lync Server 2013 introduce la possibilità di creare un nuovo ruolo e anche la possibilità di modificare un ruolo esistente. Per informazioni dettagliate, vedere [Planning for Role-Based Access Control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md).

</div>

</div>

<div>

## <a name="network-address-translation-nat"></a>NAT (Network Address Translation)

Lync Server 2013 non supporta l'utilizzo di NAT (Network Address Translation) sull'interfaccia interna del server perimetrale, ma supporta l'inserimento dell'interfaccia esterna del servizio Access Edge, del servizio Web Conferencing Edge e del servizio A/V Edge dietro un router o un firewall che esegue la conversione NAT (Network Address Translation) per topologie di server perimetrali consolidate singole e in scala. Più server perimetrali dietro un dispositivo di bilanciamento del carico hardware non possono utilizzare NAT. Se più server perimetrali utilizzano NAT nelle interfacce esterne, è necessario il bilanciamento del carico DNS (Domain Name System). A sua incirca, l'utilizzo del bilanciamento del carico DNS consente di ridurre il numero di indirizzi IP pubblici per ogni server perimetrale in un pool di server perimetrali. Per informazioni dettagliate, vedere[Planning for External User Access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md).

<div>


> [!NOTE]  
> Se si esegue la Federazione con le aziende che dispongono di una distribuzione di Microsoft Office Communications Server 2007 ed è necessario utilizzare audio/video tra l'organizzazione e l'organizzazione federata, i requisiti di porta saranno quelli per la versione precedente dei server perimetrali distribuiti. Ad esempio, gli intervalli di porte necessari per le versioni precedenti devono essere aperti per entrambe le aziende finché il partner federato non aggiorna i server perimetrali a Lync Server 2013. A quel punto, sarà possibile verificare e ridurre i requisiti delle porte in base alla nuova configurazione.



</div>

</div>

<div>

## <a name="simplified-certificates-for-edge-servers"></a>Certificati semplificati per i server perimetrali

La Distribuzione guidata consente di popolare automaticamente i nomi soggetto (SN) e i nomi soggetto alternativi (SAN) riducendo la possibilità di includere voci superflue e potenzialmente non sicure.

</div>

<div>

## <a name="trustworthy-computing-security-development-lifecycle-sdl"></a>Ciclo di vita dello sviluppo della sicurezza del calcolo Trustworthy (SDL)

Lync Server 2013 è stato progettato e sviluppato in conformità con Microsoft Trustworthy Computing Security Development Lifecycle (SDL), descritto in <https://go.microsoft.com/fwlink/?linkid=68761> .

  - **Attendibilità per progettazione**     Il primo passaggio per la creazione di un sistema di comunicazioni unificate più sicuro consisteva nel progettare modelli di minacce e testare ogni caratteristica come è stato progettato. Microsoft esegue inoltre test al di fuori del comportamento disegnato per individuare vulnerabilità di sicurezza derivanti da comportamenti di prodotto imprevisti. Diversi miglioramenti correlati alla sicurezza sono stati integrati nelle procedure e nel processo di codifica. Gli strumenti in fase di compilazione rilevano i sovraccarichi del buffer e altre potenziali minacce per la sicurezza prima che il codice venga introdotto nel prodotto finale. È ovviamente impossibile progettare un sistema in grado di far fronte a tutte le minacce per la sicurezza sconosciute. Nessun sistema può garantire una completa sicurezza. Tuttavia, poiché lo sviluppo del prodotto ha abbracciato i principi di progettazione sicuri fin dall'inizio, Lync Server 2013 incorpora tecnologie di sicurezza standard del settore come parte fondamentale della sua architettura.

  - **Attendibile per impostazione predefinita**     Per impostazione predefinita, le comunicazioni di rete in Lync Server 2013 sono crittografate. Poiché tutti i server utilizzano i certificati e l'autenticazione Kerberos, TLS, Secure Real-Time Transport Protocol (SRTP) e altre tecniche di crittografia standard del settore, tra cui la crittografia AES (Advanced Encryption Standard) di 128 bit, praticamente tutti i dati di Lync Server sono protetti in rete. Il controllo di accesso basato sui ruoli, inoltre, consente di distribuire server che eseguono Lync Server 2013 in modo che ogni ruolo del server esegua solo i servizi e disponga solo delle autorizzazioni relative a tali servizi, appropriate per il ruolo del server.

  - **Attendibilità mediante la distribuzione**     Tutta la documentazione di Lync Server 2013 include procedure consigliate e consigli utili per determinare e configurare i livelli di sicurezza ottimali per la distribuzione e valutare i rischi di sicurezza per l'attivazione delle opzioni non predefinite.

</div>

</div>

<span> </span>

</div>

</div>

</div>

