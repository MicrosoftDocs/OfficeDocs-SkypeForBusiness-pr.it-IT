---
title: 'Lync Server 2013: Requisiti del servizio di individuazione automatica'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Autodiscover service requirements
ms:assetid: 0ac5dbf7-9acd-4d25-b21a-932022b8b983
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690012(v=OCS.15)
ms:contentKeyID: 48183368
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2ea9d9be05561d200696a5ad0256c0d5424cf9b8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982193"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="autodiscover-service-requirements-for-lync-server-2013"></a>Requisiti del servizio di individuazione automatica per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-25_

Il servizio di individuazione automatica di Microsoft Lync Server 2013 viene eseguito nei server Director e front end pool e, se pubblicato in DNS, può essere usato dai dispositivi mobili che usano Lync mobile per individuare i servizi di mobilità. Prima che i dispositivi mobili che utilizzano Lync mobile possano sfruttare l'individuazione automatica, è necessario modificare gli elenchi di nomi alternativi del soggetto del certificato in qualsiasi Director e front end server che gestisce il servizio di rilevamento automatico. Può essere inoltre necessario modificare gli elenchi di nomi alternativi oggetto nei certificati usati per le regole di pubblicazione dei servizi Web esterni nei proxy inversi.

Per informazioni dettagliate sulle voci di nome alternative oggetto necessarie per direttori, server front-end e reverse proxy, vedere [requisiti tecnici per la mobilità in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md) nella pianificazione della mobilità.

La decisione relativa all'uso di elenchi di nomi alternativi per i proxy inversi si basa sulla possibilità di pubblicare il servizio di individuazione automatica sulla porta 80 o sulla porta 443:

  - **Pubblicato sulla porta 80**   non sono necessarie modifiche al certificato se la query iniziale per il servizio di individuazione automatica si verifica sulla porta 80. Il motivo è che i dispositivi mobili che utilizzano Lync accederanno al proxy inverso sulla porta 80 esternamente e quindi verranno reindirizzati a un amministratore o a un server front-end sulla porta 8080 internamente. Per informazioni dettagliate, vedere la sezione "processo di individuazione automatica iniziale tramite la porta 80" più avanti in questo argomento.

  - **Pubblicato in porta 443**   l'elenco dei nomi alternativi oggetto nei certificati usati dalla regola di pubblicazione dei servizi Web esterni deve contenere un *lyncdiscover.\< SipDomain\> * voce per ogni dominio SIP all'interno dell'organizzazione.

La riemissione di certificati tramite un'autorità di certificazione interna è in genere un processo semplice, ma per i certificati pubblici usati nella regola di pubblicazione del servizio Web, l'aggiunta di più voci di nomi alternativi soggetto può diventare costosa. Per risolvere il problema, è supportata la connessione di individuazione automatica iniziale tramite la porta 80, che viene quindi reindirizzata alla porta 8080 nel server Director o front end.

Supponiamo ad esempio che un client mobile che usa Lync mobile sia configurato per accedere a Lync Server 2013 usando la funzionalità di individuazione automatica tramite HTTP per la richiesta iniziale.

<div>

## <a name="initial-autodiscover-process-for-mobile-devices-using-port-80"></a>Processo di individuazione automatica iniziale per i dispositivi mobili tramite la porta 80

1.  Il dispositivo mobile che usa Lync mobile cerca lyncdiscover.contoso.com con DNS, dove esiste un record A.

2.  DNS esterno restituisce l'indirizzo IP per i servizi Web esterni al client.

3.  Dispositivo mobile che esegue Lync mobile invia http://lyncdiscover.contoso.com?sipuri=lyncUser1@contoso.com una richiesta al proxy inverso

4.  La regola di pubblicazione Web eseguirà il Bridge della richiesta dalla porta 80 esternamente alla porta 8080 internamente, che lo instraderà a un amministratore o a un server front-end.
    
    Dato che la richiesta è HTTP e non HTTPS, non è necessario apportare modifiche al certificato della regola di pubblicazione del servizio Web esterno per supportare il servizio di individuazione automatica.

5.  Il servizio di individuazione automatica restituisce gli URL del servizio Web esterno (in formato HTTPS).

6.  Il dispositivo mobile che utilizza Lync mobile può quindi riconnettersi al proxy inverso sulla porta 443 e viene reindirizzato su 4443 al servizio di mobilità in uso nel pool Home dell'utente.
    
    Poiché la query HTTPS è per l'URL dei servizi Web esterni e l'URL del servizio di individuazione automatica, viene eseguita correttamente perché il certificato includerà già voci di nome alternative per i servizi Web esterni, nomi di dominio completi.
    
    In questo scenario non sono necessarie modifiche al certificato per supportare la mobilità.
    
    <div>
    

    > [!NOTE]  
    > Se il server Web di destinazione ha un certificato che non ha un valore corrispondente per lyncdiscover.contoso.com come valore di elenco nome alternativo soggetto:<BR>a.&nbsp;&nbsp;&nbsp;Web server risponde con un "Server Hello" e nessun certificato.<BR>b.&nbsp;&nbsp;&nbsp;un dispositivo mobile con Lync mobile termina immediatamente la sessione.<BR>Se il server Web di destinazione ha un certificato che include lyncdiscover.contoso.com come valore di elenco nome alternativo soggetto:<BR>a.&nbsp;&nbsp;&nbsp;Web server risponde con un "Server Hello" e un certificato.<BR>b.&nbsp;&nbsp;&nbsp;dispositivo mobile che utilizza Lync mobile convalida il certificato e completa l'handshake.

    
    </div>

Per supportare una connessione iniziale al servizio di individuazione automatica tramite la porta 80 nel server proxy inverso, è possibile creare una regola di pubblicazione http simile a questo esempio per una regola di pubblicazione Web proxy inversa del gateway di Forefront Threat Management 2010:

1.  Creare una nuova regola di pubblicazione Web, ad esempio **Lync Server autodiscover (http)**).

2.  In **nome pubblico**immettere lyncdiscover.contoso.com.

3.  Nella scheda **bridging** selezionare solo l'opzione per eseguire il Bridge delle richieste dalla porta 80 alla porta 8080.

4.  Nella scheda **autenticazione** selezionare **Nessuna autenticazione**e il **client non può eseguire**l'autenticazione direttamente.

5.  Confermare le modifiche e posizionare la regola all'inizio dell'elenco delle regole di Lync (prima in ordine di elaborazione).

</div>

<div>

## <a name="mobility-for-the-split-domain-deployment"></a>Mobilità per la distribuzione di domini divisi

Uno spazio di indirizzi SIP condiviso, noto anche come *Split-Domain*o una *distribuzione ibrida* , è una configurazione in cui gli utenti vengono distribuiti in una distribuzione locale e in un ambiente online. Il risultato desiderato consiste nell'avere un utente, indipendentemente da dove si trova il proprio Home Server (locale o online), per accedere alla distribuzione ed essere reindirizzati alla posizione del proprio Home Server. A questo scopo, la funzionalità di individuazione automatica di Microsoft Lync Server 2013 viene usata per reindirizzare l'utente online alla topologia online. Questa operazione viene eseguita configurando l'URL (Uniform Resource Locator) di individuazione automatica tramite Lync Server Management Shell e i cmdlet **Get-CsHostingProvider** e **Set-CsHostingProvider**.

Sarà necessario raccogliere e registrare i seguenti attributi distribuiti:

  - In Lync Server Management Shell digitare
    
        Get-CsHostingProvider

  - Nei risultati trovare il provider online con l'attributo **ProxyFqdn**. Ad esempio, sipfed.online.lync.com

  - Registrare il valore di ProxyFQDN

  - Abilitare la Federazione nel pannello di controllo di Lync Server locale, consentendo la Federazione con il provider online

  - Abilitare la Federazione per il provider online. Per impostazione predefinita, tutti gli utenti online sono abilitati per la Federazione del dominio e possono comunicare con tutti i domini

  - Se si definiscono i domini bloccati e consentiti, determinare i domini che verranno esplicitamente consentiti o bloccati esplicitamente

  - Per la Federazione online, è necessario pianificare le eccezioni del firewall, i certificati e l'host DNS (A o AAAA, se si usano i record IPv6). È inoltre necessario configurare i criteri federativi. Per informazioni dettagliate, vedere [pianificazione per Lync server 2013 e Office Communications Server Federation](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

