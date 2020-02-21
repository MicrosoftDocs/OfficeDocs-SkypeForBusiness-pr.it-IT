---
title: 'Lync Server 2013: pianificazione per le distribuzioni ibride'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for hybrid deployments
ms:assetid: f8b3d240-bc2e-42c9-acf8-d532d641a14c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205403(v=OCS.15)
ms:contentKeyID: 48185910
ms.date: 05/25/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8f9572df29681d6b2ee754fe51702fcc8f0b0163
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184289"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-lync-server-2013-hybrid-deployments"></a>Pianificazione delle distribuzioni ibride di Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2016-05-25_

È consigliabile prendere in considerazione i requisiti seguenti per gli utenti e l'infrastruttura di rete durante la pianificazione di una distribuzione ibrida.

<div>

## <a name="infrastructure-requirements"></a>Requisiti dell'infrastruttura

Per implementare e distribuire una distribuzione ibrida, è necessario che nel proprio ambiente siano configurati i seguenti elementi.

  - Un tenant di Microsoft Office 365 con Skype for business online abilitato. Si noti che è possibile utilizzare solo un singolo tenant per una configurazione ibrida con la distribuzione locale.

  - Una singola distribuzione locale (Infrastructure) di Skype for Business Server o Lync Server distribuito in una topologia supportata. Vedere Requisiti per la topologia.
    
    Per informazioni sulla configurazione della distribuzione di Lync Server 2013 o Lync Server 2010 per l'ambiente ibrido, vedere [Configuring Lync server 2013 Hybrid Deployments](lync-server-2013-configuring-hybrid-deployments.md).

  - Strumenti di amministrazione di Skype for Business Server 2015. Se si utilizza Lync Server 2013 o Lync Server 2010, è possibile utilizzare gli strumenti di amministrazione di Lync Server 2013.

  - Per supportare l'accesso Single Sign-on con Office 365 in modo che gli utenti possano utilizzare le stesse credenziali di accesso per l'accesso a Office come in locale, è possibile utilizzare le funzionalità di sincronizzazione delle password di Azure Active Directory (AAD) Connect. È inoltre possibile utilizzare Active Directory Federation Services (AD FS) per l'accesso Single Sign-on con Office 365.
    
    Per ulteriori informazioni, vedere [Integrazione delle identità locali con Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=619754).

  - Una singola soluzione di sincronizzazione della directory per sincronizzare gli oggetti di Active Directory locali e online. Per informazioni dettagliate sulla sincronizzazione della directory, vedere [Directory Integration Tools](https://go.microsoft.com/fwlink/p/?linkid=530320).

</div>

<div>

## <a name="lync-client-support"></a>Supporto per client Lync

Esistono alcune differenze nelle funzionalità supportate nei client Lync, nonché le funzionalità disponibili negli ambienti locali e online. Prima di decidere dove si desiderano gli utenti privati nell'organizzazione, è possibile visualizzare il supporto client per le diverse configurazioni di Lync Server. I client seguenti sono supportati con Skype for business online in una distribuzione ibrida di Lync:

  - Lync 2010

  - Lync 2013

  - App Lync Windows Store

  - Lync Web App

  - Lync Mobile

  - Lync per Mac 2011

  - Sistema chat room Lync

  - Lync Basic 2013

Per informazioni dettagliate sul supporto dei client, vedere i seguenti argomenti:

  - [Client per Lync Online](https://go.microsoft.com/fwlink/?linkid=281902)

  - [Tabelle di confronto dei client per Lync Server 2013](lync-server-2013-desktop-client-comparison-tables.md)

  - [Tabelle di confronto dei client per dispositivi mobili per Lync Server 2013](lync-server-2013-mobile-client-comparison-tables.md)

</div>

<span id="BKMK_Topology"></span>

<div>

## <a name="topology-requirements"></a>Requisiti della topologia

Per configurare la distribuzione ibrida con Skype for business online, è necessario disporre di una delle topologie supportate seguenti:

  - Una distribuzione di Skype for Business Server 2015 con tutti i server che eseguono Skype for Business Server 2015.

  - Una distribuzione di Lync Server 2013 con tutti i server che eseguono Lync Server 2013.

  - Una distribuzione di Lync Server 2010 con tutti i server che eseguono Lync Server 2010 con gli aggiornamenti cumulativi più recenti.
    
      - È necessario che il server perimetrale federativo e il server dell'hop successivo del server perimetrale federativo esegua l'esecuzione di Lync Server 2010 con gli aggiornamenti cumulativi più recenti.
    
      - Gli strumenti di amministrazione di Skype for Business Server 2015 o Lync Server 2013 devono essere installati in almeno un server o una workstation di gestione.

  - Distribuzione di Lync Server 2013 e Skype for business 2015 server misto con i ruoli del server seguenti in almeno un sito che esegue Skype for Business Server 2015:
    
      - Almeno un pool Enterprise o un server Standard Edition
    
      - Il pool di server Director associato alla federazione SIP, se esistente.
    
      - Pool di server perimetrali associati alla federazione SIP

  - Una distribuzione mista di Lync Server 2010 e Skype for Business Server 2015 con i ruoli dei server seguenti in almeno un sito che esegue Skype for Business Server 2015:
    
      - Almeno un pool Enterprise o un server Standard Edition
    
      - Il pool di server Director associato alla federazione SIP, se esistente.
    
      - Pool di server perimetrali associati alla federazione SIP per il sito

  - Distribuzione di Lync Server 2010 e Lync Server 2013 mista con i ruoli del server seguenti in almeno un sito in cui è in esecuzione Lync Server 2013:
    
      - Almeno un pool Enterprise o un server Standard Edition nel sito
    
      - Il pool di server Director associato alla federazione SIP, se esiste nel sito
    
      - Pool di server perimetrali associati alla federazione SIP per il sito

<div>


> [!IMPORTANT]  
> Tutte le attività di gestione degli utenti, inclusi gli spostamenti degli utenti tra locali e UNRESOLVED_TOKEN_VAL (skypeforbusiness) online, devono essere eseguite utilizzando la versione più recente installata degli strumenti di amministrazione. Gli strumenti di amministrazione devono essere installati in un server separato che dispone dell'accesso connesso alla distribuzione locale esistente e a Internet. Il cmdlet <A href="https://docs.microsoft.com/powershell/module/skype/Move-CsUser">Move-CsUser</A> per spostare gli utenti dalla distribuzione locale a UNRESOLVED_TOKEN_VAL (skype16_online) deve essere eseguito dagli strumenti di amministrazione connessi alla distribuzione locale.



</div>

Per ulteriori informazioni sulle topologie supportate, vedere [Supported topologies in Lync server 2013](lync-server-2013-supported-topologies.md)e [Lync Server 2013 Reference Topologies for Enterprise Hybrid Deployments](https://go.microsoft.com/fwlink/p/?linkid=398709).

Per informazioni sulla risoluzione dei problemi relativi alle distribuzioni ibride e sulla connessione di PowerShell a Lync Online, vedere [Lync Online: Lync PowerShell e la risoluzione dei problemi ibridi](https://go.microsoft.com/fwlink/p/?linkid=306718).

</div>

<div>

## <a name="requirements-for-federation-allowedblocked-lists"></a>Requisiti per gli elenchi di Federazione consentiti/bloccati

L'elenco dei domini consentiti include i domini che dispongono di un nome di dominio completo (FQDN) del partner perimetrale configurato. A volte sono indicati come *server partner consentiti* o *partner di Federazione diretti*. È necessario avere familiarità con la differenza tra la Federazione aperta e la federazione chiusa, denominate rispettivamente come *Individuazione partner* e *elenco di domini consentiti partner*, nelle distribuzioni locali.

Per configurare correttamente una distribuzione ibrida, è necessario soddisfare i requisiti seguenti:

  - La corrispondenza del dominio deve essere configurata per la distribuzione locale e per il tenant di Office 365. Se l'individuazione dei partner è abilitata nella distribuzione locale, è necessario configurare la Federazione aperta per il tenant online. Se l'individuazione dei partner non è abilitata, la federazione chiusa deve essere configurata per il tenant online.

  - L'elenco dei domini bloccati nella distribuzione locale deve corrispondere esattamente all'elenco dei domini bloccati per il tenant online.

  - L'elenco dei domini consentiti nella distribuzione locale deve corrispondere esattamente all'elenco dei domini consentiti per il tenant online.

  - La Federazione deve essere abilitata per le comunicazioni esterne per il tenant online, configurata utilizzando il pannello di controllo di Lync Online.

</div>

<div>

## <a name="dns-settings"></a>Impostazioni DNS

Quando si creano record DNS per le distribuzioni ibride, tutti i record DNS esterni di Lync devono puntare all'infrastruttura locale. Per informazioni dettagliate sui record DNS necessari, fare riferimento ai [requisiti DNS (Domain Name System) per Lync Server 2013](lync-server-2013-domain-name-system-dns-requirements.md).

Inoltre, è necessario assicurarsi che la risoluzione DNS descritta nella tabella seguente sia compatibile con la distribuzione locale:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Record DNS</p></td>
<td><p>Risolvibile da</p></td>
<td><p>Requisito DNS</p></td>
</tr>
<tr class="even">
<td><p>Record SRV DNS per _sipfederationtls. _tcp. &lt;SipDomain.com&gt; per tutti i domini SIP supportati che si risolvono in Access Edge IP esterni (s)</p></td>
<td><p>Server perimetrali</p></td>
<td><p>Abilitare la comunicazione federata in una configurazione ibrida. Il server perimetrale deve sapere dove instradare il traffico federato per il dominio SIP suddiviso tra locali e online.</p></td>
</tr>
<tr class="odd">
<td><p>DNS un record (s) per FQDN del servizio Web Conferencing Edge, ad esempio webcon.contoso.com che si risolvono in Web Conferencing Edge IP esterno (s)</p></td>
<td><p>Computer degli utenti connessi alla rete aziendale interna</p></td>
<td><p>Consente agli utenti online di presentare o visualizzare il contenuto nelle riunioni ospitate locali. Il contenuto include file di PowerPoint, lavagne, sondaggi e note condivise.</p></td>
</tr>
</tbody>
</table>


A seconda del modo in cui il DNS è configurato nell'organizzazione, potrebbe essere necessario aggiungere questi record all'area DNS interna ospitata per i domini SIP corrispondenti per fornire la risoluzione DNS interna a questi record.

</div>

<div>

## <a name="firewall-considerations"></a>Considerazioni sui firewall

I computer della rete devono essere in grado di eseguire ricerche DNS standard su Internet. Se questi computer possono connettersi a siti Internet standard, la rete soddisfa questo requisito.

A seconda della posizione del data center dei Microsoft Online Services, è inoltre necessario configurare i dispositivi firewall di rete in modo che accettino connessioni basate su nomi di dominio con caratteri jolly, \*ad esempio tutto il traffico proveniente da. Outlook.com. Se i firewall dell'organizzazione non supportano le configurazioni del nome con caratteri jolly, sarà necessario determinare manualmente gli intervalli di indirizzi IP che si desidera consentire e le porte specificate.

Fare riferimento all'argomento della Guida per gli [URL e gli intervalli di indirizzi IP di Office 365](https://go.microsoft.com/fwlink/p/?linkid=252942).

</div>

<span id="b"></span>

<div>

## <a name="port-and-protocol-requirements"></a>Requisiti relativi a porte e protocolli

Oltre ai requisiti delle porte per la comunicazione interna di Lync Server 2013, è inoltre necessario configurare le porte seguenti.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Protocollo/porta</th>
<th>Applicazioni</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TCP 443</p></td>
<td><p>Aperta in ingresso</p>
<ul>
<li><p>Active Directory Federation Services (ruolo del server federativo)</p>
<p>Per ulteriori informazioni, vedere <a href="https://go.microsoft.com/fwlink/p/?linkid=281899">Understanding ADFS Role Services</a>.</p></li>
<li><p>Active Directory Federation Services (ruolo del server proxy)</p></li>
<li><p>Portale dei Microsoft Online Services</p></li>
<li><p>Portale della società personale</p></li>
<li><p>Outlook Web App</p></li>
<li><p>Client Lync (comunicazione con Lync Online da Lync Server locale)</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>TCP 80 e 443</p></td>
<td><p>Aperta in ingresso</p>
<ul>
<li><p>Strumento di sincronizzazione della directory dei Microsoft Online Services</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>TCP 5061</p></td>
<td><p>Apertura in ingresso/in uscita sul server perimetrale</p></td>
</tr>
<tr class="even">
<td><p>PSOM/TLS 443</p></td>
<td><p>Aprire in ingresso/in uscita per le sessioni di condivisione dei dati</p></td>
</tr>
<tr class="odd">
<td><p>STUN/TCP 443</p></td>
<td><p>Aprire in ingresso/in uscita per le sessioni di audio, video, condivisione applicazioni</p></td>
</tr>
<tr class="even">
<td><p>STUN/UDP 3478</p></td>
<td><p>Aprire in ingresso/in uscita per le sessioni audio e video</p></td>
</tr>
<tr class="odd">
<td><p>RTP/TCP 50000-59999</p></td>
<td><p>Aprire le sessioni audio e video in uscita</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-accounts-and-data"></a>Account utente e dati

In una distribuzione ibrida di Lync Server 2013, tutti gli utenti che desiderano effettuare la propria abitazione in Lync Online devono essere prima creati nella distribuzione locale, in modo che l'account utente venga creato in servizi di dominio Active Directory. È quindi possibile spostare l'utente in Skype for business online, che sposterà l'elenco dei contatti dell'utente.

Quando si sincronizzano gli account utente tra le distribuzioni di Lync in locale e Lync Online con ADFS e dirsync, è necessario sincronizzare gli account di Active Directory per tutti gli utenti di Lync nell'organizzazione tra le distribuzioni di Lync locali e online, anche se gli utenti non vengono spostati in Lync Online. Se non si sincronizzano tutti gli utenti, la comunicazione tra gli utenti locali e quelli online nell'organizzazione potrebbe non funzionare come previsto.

<div>


> [!IMPORTANT]  
> Se l'utente viene creato utilizzando il portale online per Office 365, l'account utente non verrà sincronizzato con Active Directory locale e l'utente non sarà presente in Active Directory locale. Se gli utenti sono già stati creati in Lync Online e si desidera configurare l'ambiente ibrido con un server Lync locale, vedere <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">moveing users from Lync Online to Lync on-premises in Lync Server 2013</A>.



</div>

Durante la pianificazione di una distribuzione ibrida, è consigliabile considerare anche i seguenti problemi relativi all'utente.

  - **Contatti utente il**   limite per i contatti per gli utenti di Lync Online è 250. Tutti i contatti oltre tale numero verranno rimossi dall'elenco contatti dell'utente quando l'account viene spostato in Lync Online.

  - ****   Gli elenchi di contatti, i gruppi e gli elenchi di controllo di accesso per gli utenti di messaggistica istantanea e presenza vengono migrati con l'account utente.

  - **Dati per le conferenze, contenuto di riunioni e riunioni**   pianificate questo contenuto non viene migrato con l'account utente. Gli utenti devono ripianificare le riunioni dopo la migrazione degli account a Lync Online.

</div>

<div>

## <a name="user-policies-and-features"></a>Criteri e funzionalità per gli utenti

  - In un ambiente ibrido di Lync Server 2013, gli utenti possono essere abilitati per la messaggistica istantanea, la voce e le riunioni sia in locale che online, ma non entrambi contemporaneamente.

  - **Client Lync alcuni**     utenti potrebbero richiedere una nuova versione client quando vengono spostati in Lync Online. Per Office Communications Server 2007 R2, gli utenti devono essere spostati in un pool Lync Server 2013 prima della migrazione a Lync Online.
    
    Per ulteriori informazioni sul supporto client, vedere client [per Lync Online](https://go.microsoft.com/fwlink/p/?linkid=281902) e [i client Lync supportati e le configurazioni delle porte di rete](https://go.microsoft.com/fwlink/p/?linkid=281901).

  - **I criteri locali e i criteri di configurazione (non utente)**   online e locale richiedono una configurazione separata. Non è possibile impostare criteri globali che si applicano a entrambi.

</div>

</div>

<span> </span>

</div>

</div>

</div>

