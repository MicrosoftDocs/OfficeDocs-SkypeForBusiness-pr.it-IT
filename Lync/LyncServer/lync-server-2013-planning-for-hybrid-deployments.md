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
ms.openlocfilehash: e0902150170d51aa590afc8b3d02c887968a2031
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41751976"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-lync-server-2013-hybrid-deployments"></a>Pianificazione di distribuzioni ibride di Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2016-05-25_

È consigliabile prendere in considerazione i requisiti seguenti per gli utenti e l'infrastruttura di rete durante la pianificazione di una distribuzione ibrida.

<div>

## <a name="infrastructure-requirements"></a>Requisiti per l'infrastruttura

Per implementare e distribuire una distribuzione ibrida, è necessario che siano configurati nell'ambiente.

  - Un tenant di Microsoft Office 365 con Skype for business online abilitato. Tieni presente che puoi usare solo un tenant per una configurazione ibrida con la distribuzione locale.

  - Una singola distribuzione locale (infrastruttura) di Skype for Business Server o Lync Server distribuito in una topologia supportata. Vedere requisiti della topologia.
    
    Per informazioni sulla configurazione della distribuzione di Lync Server 2013 o Lync Server 2010 per l'ibrido, vedere [configurazione di distribuzioni ibride di Lync server 2013](lync-server-2013-configuring-hybrid-deployments.md).

  - Strumenti di amministrazione di Skype for Business Server 2015. Se si usa Lync Server 2013 o Lync Server 2010, è possibile usare gli strumenti di amministrazione di Lync Server 2013.

  - Per supportare single sign-on con Office 365 in modo che gli utenti possano usare le stesse credenziali di accesso per l'accesso a Office come in locale, è possibile usare le caratteristiche di sincronizzazione delle password di Azure Active Directory (AAD) Connect. È anche possibile usare Active Directory Federation Services (ADFS) per Single Sign-on con Office 365.
    
    Per altre informazioni, vedere [integrazione delle identità locali con Azure Active Directory](http://go.microsoft.com/fwlink/p/?linkid=619754).

  - Una soluzione di sincronizzazione di una singola directory per sincronizzare gli oggetti Active Directory locali e online. Per informazioni dettagliate sulla sincronizzazione della directory, vedere [strumenti di integrazione della directory](http://go.microsoft.com/fwlink/p/?linkid=530320).

</div>

<div>

## <a name="lync-client-support"></a>Supporto client Lync

Esistono alcune differenze tra le funzionalità supportate nei client Lync e le funzionalità disponibili in ambienti locali e online. Prima di decidere dove si vogliono utenti privati nell'organizzazione, è possibile visualizzare il supporto client per le varie configurazioni di Lync Server. I client seguenti sono supportati con Skype for business online in una distribuzione ibrida di Lync:

  - Lync 2010

  - Lync 2013

  - App Lync di Windows Store

  - Lync Web App

  - Lync mobile

  - Lync per Mac 2011

  - Sistema di sala Lync

  - Lync Basic 2013

Per informazioni dettagliate sul supporto client, vedere gli argomenti seguenti:

  - [Client per Lync Online](http://go.microsoft.com/fwlink/?linkid=281902)

  - [Tabelle di confronto dei client per Lync Server 2013](lync-server-2013-desktop-client-comparison-tables.md)

  - [Tabelle di confronto dei client mobili per Lync Server 2013](lync-server-2013-mobile-client-comparison-tables.md)

</div>

<span id="BKMK_Topology"></span>

<div>

## <a name="topology-requirements"></a>Requisiti di topologia

Per configurare la distribuzione ibrida con Skype for business online, è necessario disporre di una delle topologie supportate seguenti:

  - Una distribuzione di Skype for Business Server 2015 con tutti i server che utilizzano Skype for Business Server 2015.

  - Una distribuzione di Lync Server 2013 con tutti i server che utilizzano Lync Server 2013.

  - Una distribuzione di Lync Server 2010 con tutti i server che utilizzano Lync Server 2010 con gli aggiornamenti cumulativi più recenti.
    
      - La Federazione Edge Server e il server hop successivo del server Edge federativo devono eseguire Lync Server 2010 con gli aggiornamenti cumulativi più recenti.
    
      - Gli strumenti di amministrazione di Skype for Business Server 2015 o Lync Server 2013 devono essere installati in almeno un server o una workstation di gestione.

  - Una distribuzione mista di Lync Server 2013 e Skype for Business Server 2015 con i ruoli del server seguenti in almeno un sito che utilizza Skype for Business Server 2015:
    
      - Almeno un pool aziendale o un server Standard Edition
    
      - Pool di Director associato alla federazione SIP, se esistente
    
      - Pool di bordi associato alla federazione SIP

  - Una distribuzione mista di Lync Server 2010 e Skype for Business Server 2015 con i ruoli dei server seguenti in almeno un sito che utilizza Skype for Business Server 2015:
    
      - Almeno un pool aziendale o un server Standard Edition
    
      - Pool di Director associato alla federazione SIP, se esistente
    
      - Pool di bordi associato alla federazione SIP per il sito

  - Una distribuzione di Lync Server 2010 e Lync Server 2013 mista con i ruoli del server seguenti in almeno un sito in cui è in uso Lync Server 2013:
    
      - Almeno un pool aziendale o un server Standard Edition nel sito
    
      - Pool di Director associato alla federazione SIP, se esistente nel sito
    
      - Pool di bordi associato alla federazione SIP per il sito

<div>


> [!IMPORTANT]  
> Tutta la gestione degli utenti, inclusi gli spostamenti degli utenti tra locale e UNRESOLVED_TOKEN_VAL (skypeforbusiness) online, deve essere eseguita usando l'ultima versione installata degli strumenti di amministrazione. Gli strumenti di amministrazione devono essere installati in un server distinto che dispone di accesso Connetti alla distribuzione locale esistente e a Internet. Il cmdlet <A href="https://docs.microsoft.com/powershell/module/skype/Move-CsUser">Move-CsUser</A> per trasferire gli utenti dalla distribuzione locale a UNRESOLVED_TOKEN_VAL (skype16_online) deve essere eseguito dagli strumenti di amministrazione connessi alla distribuzione locale.



</div>

Per altre informazioni sulle topologie supportate, vedere Topologie supportate nelle topologie di riferimento di [Lync server 2013](lync-server-2013-supported-topologies.md)e [Lync Server 2013 per le distribuzioni ibride aziendali](http://go.microsoft.com/fwlink/p/?linkid=398709).

Per informazioni sulla risoluzione dei problemi relativi alle distribuzioni ibride e sulla connessione di PowerShell a Lync Online, vedere [Lync Online: Lync PowerShell e risoluzione dei problemi ibridi](http://go.microsoft.com/fwlink/p/?linkid=306718).

</div>

<div>

## <a name="requirements-for-federation-allowedblocked-lists"></a>Requisiti per gli elenchi consentiti/bloccati della Federazione

L'elenco dei domini consentiti include i domini con il nome di dominio completo (FQDN) del partner Edge configurato. Questi sono a volte indicati come *server partner consentiti* o *partner federativi diretti*. È necessario avere familiarità con la differenza tra la Federazione aperta e la federazione chiusa, denominata rispettivamente *Individuazione partner* e *elenco dei domini partner consentiti*, nelle distribuzioni locali.

Per configurare correttamente una distribuzione ibrida, è necessario soddisfare i requisiti seguenti:

  - La corrispondenza dei domini deve essere configurata per la distribuzione locale e per il tenant di Office 365. Se l'individuazione dei partner è abilitata nella distribuzione locale, la Federazione aperta deve essere configurata per il tenant online. Se l'individuazione dei partner non è abilitata, la federazione chiusa deve essere configurata per il tenant online.

  - L'elenco dei domini bloccati nella distribuzione locale deve corrispondere esattamente all'elenco dei domini bloccati per il tenant online.

  - L'elenco dei domini consentiti nella distribuzione locale deve corrispondere esattamente all'elenco dei domini consentiti per il tenant online.

  - La Federazione deve essere abilitata per le comunicazioni esterne per il tenant online, che viene configurato tramite il pannello di controllo di Lync Online.

</div>

<div>

## <a name="dns-settings"></a>Impostazioni DNS

Quando si creano record DNS per distribuzioni ibride, tutti i record DNS esterni di Lync devono puntare all'infrastruttura locale. Per informazioni dettagliate sui record DNS necessari, vedere [requisiti DNS (Domain Name System) per Lync Server 2013](lync-server-2013-domain-name-system-dns-requirements.md).

È inoltre necessario verificare che la risoluzione DNS descritta nella tabella seguente funzioni nella distribuzione locale:


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
<td><p>Record SRV DNS per _sipfederationtls. _tcp. &lt;SipDomain.com&gt; per tutti i domini SIP supportati per la risoluzione di Access Edge IP esterni (s)</p></td>
<td><p>Server perimetrale (s)</p></td>
<td><p>Abilitare la comunicazione federata in una configurazione ibrida. Il server perimetrale deve sapere dove instradare il traffico federativo per il dominio SIP diviso tra locale e online.</p></td>
</tr>
<tr class="odd">
<td><p>DNS un record per il nome di dominio completo del servizio di conferenza Web Edge, ad esempio webcon.contoso.com che risolve in Web Conferencing Edge IP esterni (s)</p></td>
<td><p>Computer degli utenti connessi alla rete aziendale interna</p></td>
<td><p>Consentire agli utenti online di presentare o visualizzare contenuti in riunioni ospitate in locale. Il contenuto include file di PowerPoint, lavagne, sondaggi e note condivise.</p></td>
</tr>
</tbody>
</table>


A seconda del modo in cui il DNS è configurato nell'organizzazione, potrebbe essere necessario aggiungere questi record all'area DNS ospitata interna per i rispettivi domini SIP per ottenere la risoluzione DNS interna di questi record.

</div>

<div>

## <a name="firewall-considerations"></a>Considerazioni sul firewall

I computer della rete devono essere in grado di eseguire ricerche DNS Internet standard. Se questi computer possono raggiungere siti Internet standard, la rete soddisfa questo requisito.

A seconda della posizione del centro dati di Microsoft Online Services, è necessario configurare anche i dispositivi firewall di rete per accettare connessioni basate sui nomi di dominio con caratteri jolly, ad esempio tutto \*il traffico da. Outlook.com. Se i firewall dell'organizzazione non supportano le configurazioni con nome jolly, sarà necessario determinare manualmente gli intervalli di indirizzi IP che si desidera consentire e le porte specificate.

Fare riferimento all'argomento della Guida [URL e intervalli di indirizzi IP di Office 365](http://go.microsoft.com/fwlink/p/?linkid=252942).

</div>

<span id="b"></span>

<div>

## <a name="port-and-protocol-requirements"></a>Requisiti per la porta e il protocollo

Oltre ai requisiti relativi alle porte per la comunicazione interna di Lync Server 2013, è necessario configurare anche le porte seguenti.


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
<td><p>Apri in ingresso</p>
<ul>
<li><p>Active Directory Federation Services (ruolo del server federativo)</p>
<p>Per altre informazioni, vedere <a href="http://go.microsoft.com/fwlink/p/?linkid=281899">concetti relativi ai servizi ruolo ADFS</a>.</p></li>
<li><p>Active Directory Federation Services (ruolo del server proxy)</p></li>
<li><p>Portale dei Microsoft Online Services</p></li>
<li><p>Portale aziendale</p></li>
<li><p>Outlook Web App</p></li>
<li><p>Client Lync (comunicazione a Lync Online da Lync Server locale)</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>TCP 80 e 443</p></td>
<td><p>Apri in ingresso</p>
<ul>
<li><p>Strumento di sincronizzazione della directory dei Microsoft Online Services</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>TCP 5061</p></td>
<td><p>Aprire in ingresso/uscita nel server perimetrale</p></td>
</tr>
<tr class="even">
<td><p>PSOM/TLS 443</p></td>
<td><p>Aprire in ingresso/uscita per sessioni di condivisione dati</p></td>
</tr>
<tr class="odd">
<td><p>STUN/TCP 443</p></td>
<td><p>Aprire in ingresso/uscita per sessioni di condivisione di audio, video e applicazioni</p></td>
</tr>
<tr class="even">
<td><p>STUN/UDP 3478</p></td>
<td><p>Aprire in ingresso/uscita per sessioni audio e video</p></td>
</tr>
<tr class="odd">
<td><p>RTP/TCP 50000-59999</p></td>
<td><p>Apertura in uscita per sessioni audio e video</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-accounts-and-data"></a>Account utente e dati

In una distribuzione ibrida di Lync Server 2013 è necessario creare prima di tutto l'utente che si vuole inserire in Lync Online, in modo che l'account utente venga creato in servizi di dominio Active Directory. È quindi possibile trasferire l'utente in Skype for business online, che sposterà l'elenco contatti dell'utente.

Quando si sincronizzano gli account utente tra le distribuzioni locale di Lync e Lync Online con ADFS e dirsync, è necessario sincronizzare gli account degli annunci per tutti gli utenti di Lync dell'organizzazione tra le distribuzioni di Lync locali e online, anche se gli utenti non vengono spostati in Lync Online. Se non si sincronizzano tutti gli utenti, la comunicazione tra gli utenti locali e online dell'organizzazione potrebbe non funzionare come previsto.

<div>


> [!IMPORTANT]  
> Se l'utente viene creato usando il portale online per Office 365, l'account utente non verrà sincronizzato con Active Directory locale e l'utente non sarà presente nell'Active Directory locale. Se sono già stati creati utenti in Lync Online e si vuole configurare Hybrid con un server Lync locale, vedere <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">spostamento di utenti da Lync Online a Lync locale in Lync Server 2013</A>.



</div>

Quando si pianifica una distribuzione ibrida, è consigliabile considerare anche i seguenti problemi correlati agli utenti.

  - **Contatti utente il**   limite per i contatti per gli utenti di Lync Online è 250. Tutti i contatti oltre tale numero verranno rimossi dall'elenco contatti dell'utente quando l'account viene spostato in Lync Online.

  - ****   Gli elenchi di contatti, i gruppi e gli elenchi di controllo di Access (ACL) degli utenti della messaggistica istantanea e della presenza vengono migrati con l'account utente.

  - **Dati di conferenza, contenuto della riunione e riunioni**   pianificate questo contenuto non viene migrato con l'account utente. Gli utenti devono ripianificare le riunioni dopo la migrazione degli account a Lync Online.

</div>

<div>

## <a name="user-policies-and-features"></a>Criteri e funzionalità degli utenti

  - In un ambiente ibrido di Lync Server 2013 gli utenti possono essere abilitati per la messaggistica istantanea, la voce e le riunioni in locale o online, ma non contemporaneamente.

  - **Client Lync alcuni**     utenti potrebbero richiedere una nuova versione client quando vengono spostati in Lync Online. Per Office Communications Server 2007 R2, gli utenti devono essere spostati in un pool di Lync Server 2013 prima della migrazione a Lync Online.
    
    Per altre informazioni sul supporto client, vedere [client per Lync Online](http://go.microsoft.com/fwlink/p/?linkid=281902) e [client Lync supportati e configurazioni della porta di rete](http://go.microsoft.com/fwlink/p/?linkid=281901).

  - **I criteri e la configurazione locali (non utente)**   online e i criteri locali richiedono una configurazione separata. Non è possibile impostare criteri globali che si applicano a entrambi.

</div>

</div>

<span> </span>

</div>

</div>

</div>

