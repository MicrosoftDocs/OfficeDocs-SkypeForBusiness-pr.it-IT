---
title: 'Lync Server 2013: requisiti del servizio di individuazione automatica'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Autodiscover service requirements
ms:assetid: 0ac5dbf7-9acd-4d25-b21a-932022b8b983
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690012(v=OCS.15)
ms:contentKeyID: 48183368
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4dc50b7eedf6aa815c52b44ed4c1ddb88cea5217
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145455"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="autodiscover-service-requirements-for-lync-server-2013"></a>Requisiti del servizio di individuazione automatica per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-25_

Il servizio di individuazione automatica di Microsoft Lync Server 2013 viene eseguito nei server Director e front end pool e, se pubblicato in DNS, può essere utilizzato dai dispositivi mobili che eseguono Lync mobile per individuare i servizi di mobilità. Prima che i dispositivi mobili che eseguono Lync mobile possano trarre vantaggio dall'individuazione automatica, è necessario modificare gli elenchi di nomi alternativi del soggetto del certificato su qualsiasi server Director e front end che esegue il servizio di Autodiscover. Potrebbe inoltre essere necessario modificare gli elenchi dei nomi alternativi del soggetto nei certificati utilizzati per le regole di pubblicazione dei servizi Web esterni nei proxy inversi.

Per informazioni dettagliate sulle voci dei nomi alternativi del soggetto necessarie per i direttori, i Front End Server e i proxy inversi, vedere [Technical Requirements for Mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md) in Planning for Mobility.

La decisione relativa agli elenchi dei nomi alternativi del soggetto nei proxy inversi dipende dal fatto che il servizio di individuazione automatica venga pubblicato sulla porta 80 o sulla porta 443:

  - **Pubblicati sulla porta 80**   non sono necessarie modifiche del certificato se la query iniziale al servizio di individuazione automatica si verifica sulla porta 80. Ciò è dovuto al fatto che i dispositivi mobili che eseguono Lync accederanno al proxy inverso sulla porta 80 esternamente e quindi verranno reindirizzati a un server Director o front end su porta 8080 internamente. Per informazioni dettagliate, vedere la sezione "Processo di individuazione automatica iniziale tramite la porta 80" più avanti in questo argomento.

  - **Pubblicati sulla porta 443**   l'elenco dei nomi alternativi del soggetto sui certificati utilizzati dalla regola di pubblicazione dei servizi Web esterni deve contenere un *lyncdiscover.\< voce\> SipDomain* per ogni dominio SIP all'interno dell'organizzazione.

La riemissione dei certificati tramite un'autorità di certificazione interna in genere è un processo semplice, ma per i certificati pubblici utilizzati nella regola di pubblicazione dei servizi Web l'aggiunta di più voci dei nomi alternativi del soggetto può diventare un'attività dispendiosa. Per ovviare a questo problema, è supportata la connessione di individuazione automatica iniziale tramite la porta 80, che viene quindi reindirizzata alla porta 8080 nel server Director o front end.

Si supponga, ad esempio, che un client mobile che esegue Lync mobile sia configurato per l'accesso a Lync Server 2013 utilizzando la funzionalità di individuazione automatica tramite HTTP per la richiesta iniziale.

<div>

## <a name="initial-autodiscover-process-for-mobile-devices-using-port-80"></a>Processo di individuazione automatica iniziale per i dispositivi mobili tramite la porta 80

1.  Il dispositivo mobile che esegue Lync mobile cerca lyncdiscover.contoso.com con DNS, dove esiste un record A.

2.  DNS esterno restituisce l'indirizzo IP per i servizi Web esterni al client.

3.  Dispositivo mobile che esegue Lync mobile invia http://lyncdiscover.contoso.com?sipuri=lyncUser1@contoso.com una richiesta al proxy inverso

4.  La regola di pubblicazione Web colmerà la richiesta dalla porta 80 esternamente alla porta 8080 internamente, che lo instraderà a un Director o a un front end server.
    
    Poiché si tratta di una richiesta HTTP e non HTTPS, per supportare il servizio di individuazione automatica non sono necessarie modifiche per il certificato nella regola di pubblicazione dei servizi Web esterni.

5.  Il servizio di individuazione automatica restituisce gli URL dei servizi Web esterni nel formato HTTPS.

6.  Il dispositivo mobile che esegue Lync mobile può quindi riconnettersi al proxy inverso sulla porta 443 ed essere reindirizzato su 4443 al servizio per dispositivi mobili in esecuzione nel pool di casa dell'utente.
    
    Poiché la query HTTPS riguarda l'URL dei servizi Web esterni e non l'URL del servizio di individuazione automatica, ha esito positivo perché il certificato conterrà già le voci dei nomi alternativi del soggetto per i nomi di dominio completi (FQDN) dei servizi Web esterni.
    
    In questo scenario non è necessario apportare modifiche ai certificati per supportare i servizi per dispositivi mobili.
    
    <div>
    

    > [!NOTE]  
    > Se nel server Web di destinazione è presente un certificato che include lyncdiscover.contoso.com come valore dell'elenco dei nomi alternativi del soggetto:<BR>a.&nbsp;&nbsp;&nbsp;il server Web risponde con "Server Hello" e nessun certificato.<BR>b.&nbsp;&nbsp;&nbsp;il dispositivo mobile che esegue Lync mobile interrompe immediatamente la sessione.<BR>Se nel server Web di destinazione è presente un certificato che include lyncdiscover.contoso.com come valore dell'elenco dei nomi alternativi del soggetto:<BR>a.&nbsp;&nbsp;&nbsp;il server Web risponde con un "Server Hello" e un certificato.<BR>b.&nbsp;&nbsp;&nbsp;dispositivo mobile che esegue Lync mobile convalida il certificato e completa l'handshake.

    
    </div>

Per supportare una connessione iniziale al servizio di individuazione automatica utilizzando la porta 80 nel server proxy inverso, è possibile creare una regola di pubblicazione http simile a questo esempio per una regola di pubblicazione Web di proxy inverso di Forefront Threat Management Gateway 2010:

1.  Creare una nuova regola di pubblicazione Web, ad esempio **Individuazione automatica Lync Server (HTTP)**.

2.  In **Nome pubblico** immettere lyncdiscover.contoso.com.

3.  Nella scheda **Bridging** selezionare solo l'opzione per inoltrare le richieste dalla porta 80 alla porta 8080.

4.  Nella scheda **Autenticazione** selezionare **Nessuna delega.****Il client non può eseguire l'autenticazione direttamente**.

5.  Eseguire il commit delle modifiche e spostare la regola all'inizio dell'elenco delle regole di Lync (primo in ordine di elaborazione).

</div>

<div>

## <a name="mobility-for-the-split-domain-deployment"></a>Mobilità per la distribuzione del dominio diviso

Uno spazio indirizzo SIP condiviso, noto anche come *dominio diviso* o *distribuzione ibrida*, è una configurazione in cui gli utenti sono distribuiti in una distribuzione locale e un ambiente online. Il risultato desiderato è che gli utenti, indipendentemente dalla posizione in cui si trova il server principale (in locale oppure online), accedano alla distribuzione e vengano reindirizzati alla posizione del server principale. A tale scopo, la caratteristica di individuazione automatica di Microsoft Lync Server 2013 viene utilizzata per reindirizzare l'utente online alla topologia online. Per ottenere questo risultato, è necessario configurare l'URL (Uniform Resource Locator) di individuazione automatica utilizzando Lync Server Management Shell e i cmdlet **Get-CsHostingProvider** e **Set-CsHostingProvider**.

Sarà necessario raccogliere e prendere nota degli attributi distribuiti seguenti:

  - Da Lync Server Management Shell, digitare
    
        Get-CsHostingProvider

  - Nei risultati, individuare il provider online con l'attributo **ProxyFQDN**. Ad esempio, sipfed.online.lync.com

  - Prendere nota del valore di ProxyFQDN

  - Abilitare la Federazione nel pannello di controllo di Lync Server locale, consentendo la Federazione con il provider online

  - Abilitare la federazione per il provider online. Per impostazione predefinita, tutti gli utenti online sono abilitati per la federazione dei domini e possono comunicare con tutti i domini

  - Se si prevede di definire domini bloccati e consentiti, determinare i domini che verranno esplicitamente consentiti o bloccati

  - Per la federazione online è necessario pianificare le eccezioni del firewall, i certificati e i record dell'host DNS (A oppure AAAA se si utilizza IPv6). È inoltre necessario configurare i criteri di federazione. Per informazioni dettagliate, vedere [Planning for Lync Server 2013 and Office Communications Server Federation](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

