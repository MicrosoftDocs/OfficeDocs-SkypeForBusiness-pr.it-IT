---
title: 'Lync Server 2013: Requisiti DNS per gli URL semplici'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS requirements for simple URLs
ms:assetid: 3a3c9b22-892f-45a7-b05c-539d358a1a86
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425874(v=OCS.15)
ms:contentKeyID: 48183912
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: adcf537db908fcc0b69e95bec99b73a0e57e9ab4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979385"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-simple-urls-in-lync-server-2013"></a>Requisiti DNS per gli URL semplici in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-22_

Lync Server 2013 supporta gli URL semplici, che semplificano le riunioni di partecipazione per gli utenti e rendono più semplice l'accesso agli strumenti di amministrazione di Lync Server per gli amministratori. Per informazioni dettagliate sugli URL semplici, vedere [pianificazione di URL semplici in Lync Server 2013](lync-server-2013-planning-for-simple-urls.md).

Lync Server supporta i tre semplici URL seguenti: Meet, Dial-in e admin. È necessario configurare URL semplici per riunioni e accesso esterno e l'URL semplice per l'amministratore è facoltativo. I record DNS (Domain Name System) necessari per supportare gli URL semplici dipendono dal modo in cui sono stati definiti questi URL semplici e se si vuole supportare il ripristino di emergenza per gli URL semplici.

<div>

## <a name="simple-url-option-1"></a>Opzione semplice URL 1

Nell'opzione 1 si crea un nuovo URL di base per ogni URL semplice.

<div class="">


> [!NOTE]  
> Quando un utente fa clic su un collegamento a una riunione URL semplice, il server che il record DNS risolve per determinare il software client corretto per l'avvio. Dopo l'avvio del software client, la comunicazione viene comunicata automaticamente con il pool in cui è ospitata la conferenza. In questo modo, gli utenti vengono indirizzati al server appropriato per il contenuto della riunione, indipendentemente dal server o dal pool in cui vengono risolti i record DNS dell'URL semplice.



</div>

### <a name="simple-url-option-1"></a>Opzione semplice URL 1

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>URL semplice</strong></p></td>
<td><p><strong>Esempio</strong></p></td>
</tr>
<tr class="even">
<td><p>Soddisfano</p></td>
<td><p>https://meet.contoso.com, https://meet.fabrikam.come così via (uno per ogni dominio SIP nell'organizzazione)</p></td>
</tr>
<tr class="odd">
<td><p>Accesso esterno</p></td>
<td><p>https://dialin.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>Admin</p></td>
<td><p>https://admin.contoso.com</p></td>
</tr>
</tbody>
</table>


Se si usa l'opzione 1, è necessario definire le operazioni seguenti:

  - Per ogni URL semplice di riunione, è necessario un record DNS che risolva l'URL per l'indirizzo IP del direttore, se ne è stato distribuito uno. In caso contrario, deve essere risolto nell'indirizzo IP del bilanciamento del carico di un pool Front-end. Se non è stato distribuito un pool e si usa una distribuzione di server Standard Edition, il record DNS deve essere risolto nell'indirizzo IP di un server standard dell'organizzazione.
    
    Se si hanno più domini SIP nell'organizzazione e si usa questa opzione, è necessario creare URL semplici per ogni dominio SIP ed è necessario un record DNS per ogni URL semplice di riunione. Se ad esempio sono presenti sia contoso.com che fabrikam.com, verranno creati record DNS per entrambi https://meet.contoso.com e. https://meet.fabrikam.com
    
    In alternativa, se si hanno più domini SIP e si vuole minimizzare il record DNS e i requisiti di certificato per questi URL semplici, usare l'opzione 3 come descritto più avanti in questo argomento.

  - Per l'URL semplice con accesso esterno, è necessario un record DNS che risolva l'URL per l'indirizzo IP del direttore, se ne è stato distribuito uno. In caso contrario, deve essere risolto nell'indirizzo IP del bilanciamento del carico di un pool Front-end. Se non è stato distribuito un pool e si usa una distribuzione di server Standard Edition, il record DNS deve essere risolto nell'indirizzo IP di un server standard dell'organizzazione.

  - L'URL semplice amministratore è solo interno. Richiede un record DNS che risolva l'URL per l'indirizzo IP del direttore, se ne è stato distribuito uno. In caso contrario, deve essere risolto nell'indirizzo IP del bilanciamento del carico di un pool Front-end. Se non è stato distribuito un pool e si usa una distribuzione di server Standard Edition, il record DNS deve essere risolto nell'indirizzo IP di un server standard dell'organizzazione.

</div>

<div>

## <a name="simple-url-option-2"></a>Opzione semplice URL 2

Con l'opzione 2, gli URL semplici Meet, Dial-in e admin hanno tutti un URL di base comune, ad esempio lync.contoso.com. Di conseguenza, è necessario un solo record DNS per questi URL semplici, che risolve lync.contoso.com nell'indirizzo IP di un pool di Director o di un pool di front-end. Se non è stato distribuito un pool e si usa una distribuzione di server Standard Edition, il record DNS deve essere risolto nell'indirizzo IP di un server standard dell'organizzazione.

Tieni presente che se si hanno più domini SIP nell'organizzazione, è comunque necessario creare URL semplici per ogni dominio SIP ed è necessario un record DNS per ogni URL semplice di riunione. In questo esempio, mentre tre URL semplici sono tutti basati su lync.contoso.com, viene configurato un URL di riunione semplice aggiuntivo per fabrikam.com con un URL di base diverso. In questo esempio è necessario creare record DNS per entrambi https://lync.contoso.com e. https://lync.fabrikam.com L'opzione semplice URL 3 Mostra un altro modo per gestire i record di denominazione e DNS se si hanno più domini SIP.

### <a name="simple-url-option-2"></a>Opzione semplice URL 2

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>URL semplice</strong></p></td>
<td><p><strong>Esempio</strong></p></td>
</tr>
<tr class="even">
<td><p>Soddisfano</p></td>
<td><p>https://lync.contoso.com/Meet, https://lync.fabrikam.com/Meete così via (uno per ogni dominio SIP nell'organizzazione)</p></td>
</tr>
<tr class="odd">
<td><p>Accesso esterno</p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p>Admin</p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="simple-url-option-3"></a>Opzione semplice URL 3

L'opzione 3 è molto utile se si hanno molti domini SIP e si vuole che dispongano di URL semplici separati, ma che si vogliano minimizzare il record DNS e i requisiti di certificato per questi URL semplici. In questo esempio è necessario un solo record DNS, che risolve lync.contoso.com con l'indirizzo IP di un pool di Director o di un pool di front-end.

### <a name="simple-url-option-3"></a>Opzione semplice URL 3

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>URL semplice</strong></p></td>
<td><p><strong>Esempio</strong></p></td>
</tr>
<tr class="even">
<td><p>Soddisfano</p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Meet</p>
<p>https://lync.contoso.com/fabrikamSIPdomain/Meet</p></td>
</tr>
<tr class="odd">
<td><p>Accesso esterno</p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Dialin</p></td>
</tr>
<tr class="even">
<td><p>Admin</p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Admin</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="disaster-recovery-option-for-simple-urls"></a>Opzione di ripristino di emergenza per URL semplici

Se si hanno più siti che contengono pool Front-end e il provider DNS supporta GeoDNS, è possibile configurare i record DNS per gli URL semplici per supportare il ripristino di emergenza, in modo che le funzionalità degli URL semplici continuino anche se si abbassa un intero pool Front-end. Questa funzionalità di ripristino di emergenza supporta gli URL semplici di riunione e accesso esterno.

Per configurare la configurazione, creare due indirizzi di GeoDNS. Ogni indirizzo contiene due record DNS A o CNAME che vengono risolti in due pool combinati per scopi di ripristino di emergenza. Un indirizzo GeoDNS viene usato per l'accesso interno e viene risolto nell'indirizzo IP di FQDN Web interno o di bilanciamento del carico per i due pool. L'altro indirizzo GeoDNS viene usato per l'accesso esterno e si risolve nell'FQDN Web esterno o nell'indirizzo IP del bilanciamento del carico per i due pool. Di seguito è riportato un esempio per l'URL semplice Meet, che usa i nomi di dominio completi per i pool.

   ```
    Meet-int.geolb.contoso.com
         Pool1InternalWebFQDN.contoso.com
         Pool2InternalWebFQDN.contoso.com
   ```

   ```
   Meet-ext.geolb.contoso.com
         Pool1ExternalWebFQDN.contoso.com
         Pool2ExternalWebFQDN.contoso.com
   ``` 

Crea quindi i record CNAME che risolvono l'URL semplice di riunione (ad esempio meet.contoso.com) ai due indirizzi di GeoDNS.

<div class="">


> [!NOTE]  
> Se la rete usa <EM>hairpinning</EM> (instradando tutto il traffico di URL semplice tramite il collegamento esterno, incluso il traffico proveniente dall'interno dell'organizzazione), è possibile configurare l'indirizzo di GeoDNS esterno e risolvere l'URL semplice che si incontra solo per l'indirizzo esterno.



</div>

Quando usi questo metodo, puoi configurare ogni indirizzo di GeoDNS in modo da usare un metodo Round Robin per distribuire le richieste ai due pool oppure per connetterti principalmente a un pool, ad esempio il pool situato geograficamente più vicino, e usare l'altro pool solo in caso di errore di connettività.

È possibile configurare la stessa configurazione per l'URL semplice con accesso esterno. A questo scopo, crea altri record come quelli nell'esempio precedente, sostituendo `dialin` per `meet` i record DNS. Per l'URL semplice amministratore, usa una delle tre opzioni elencate in precedenza in questa sezione.

Una volta configurata questa configurazione, è necessario usare un'applicazione di monitoraggio per configurare il monitoraggio HTTP per la visualizzazione degli errori. Per l'accesso esterno, monitorare per assicurarsi che HTTPS ottenere le richieste di individuazione automatica per l'FQDN Web esterno o l'indirizzo IP del bilanciamento del carico per i due pool abbia successo. Ad esempio, le richieste seguenti non devono contenere alcuna intestazione **Accept** e devono restituire **200 OK**.

    HTTPS GET Pool1ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
    HTTPS GET Pool2ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root

Per l'accesso interno, è necessario monitorare la porta 5061 nell'FQDN Web interno o nell'indirizzo IP del bilanciamento del carico per i due pool. Se vengono rilevati errori di connettività, il VIP per questi pool deve chiudere le porte 80, 443 e 444.

</div>

</div>

<span> </span>

</div>

</div>

</div>

