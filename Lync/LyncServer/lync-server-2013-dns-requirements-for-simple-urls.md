---
title: 'Lync Server 2013: requisiti DNS per gli URL semplici'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for simple URLs
ms:assetid: 3a3c9b22-892f-45a7-b05c-539d358a1a86
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425874(v=OCS.15)
ms:contentKeyID: 48183912
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 98db338c48bbb764aefe3d5cab4bcba58b2b23c4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501373"
---
# <a name="dns-requirements-for-simple-urls-in-lync-server-2013"></a>Requisiti DNS per gli URL semplici in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-22_

Lync Server 2013 supporta gli URL semplici, che rendono più semplice partecipare alle riunioni per gli utenti e semplificare gli strumenti di amministrazione di Lync Server per gli amministratori. Per informazioni dettagliate sugli URL semplici, vedere [Planning for Simple URLs in Lync Server 2013](lync-server-2013-planning-for-simple-urls.md).

Lync Server supporta i tre URL semplici seguenti: Meet, Dial-in e admin. È necessario configurare gli URL semplici per gli incontri e l'accesso esterno e l'URL semplice di amministrazione è facoltativo. I record DNS (Domain Name System) necessari per supportare gli URL semplici dipendono da come sono stati definiti gli URL e dall'eventuale impostazione del supporto del ripristino di emergenza per gli URL semplici.

<div>

## <a name="simple-url-option-1"></a>Opzione 1 per gli URL semplici

Nell'opzione 1 viene creato un nuovo URL di base per ogni URL semplice.

<div class="">


> [!NOTE]  
> Quando un utente fa clic sul collegamento di una riunione con URL semplice, il server in cui viene risolto il record A DNS determina il software client corretto da avviare. Dopo l'avvio, il software client comunica automaticamente con il pool in cui è ospitata la conferenza. In questo modo, gli utenti vengono indirizzati al server appropriato per il contenuto della riunione, indipendentemente dal server o dal pool in cui vengono risolti i record A DNS degli URL semplici.



</div>

### <a name="simple-url-option-1"></a>Opzione 1 per gli URL semplici

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
<td><p>Soddisfare</p></td>
<td><p>https://meet.contoso.comhttps://meet.fabrikam.come così via (uno per ogni dominio SIP dell'organizzazione)</p></td>
</tr>
<tr class="odd">
<td><p>Accesso esterno</p></td>
<td><p>https://dialin.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>Amministratore</p></td>
<td><p>https://admin.contoso.com</p></td>
</tr>
</tbody>
</table>


Se si utilizza l'opzione 1, è necessario definire quanto segue:

  - Per ogni URL semplice riunione, è necessario un record A DNS che risolva l'URL nell'indirizzo IP del Director, se ne è stato distribuito uno, altrimenti nell'indirizzo IP del servizio di bilanciamento del carico di un pool Front End. Se non è stato distribuito un pool e si utilizza una distribuzione di server Standard Edition, il record A DNS deve risolversi nell'indirizzo IP di un server Standard Edition dell'organizzazione.
    
    Se nell'organizzazione sono presenti più domini SIP e si utilizza questa opzione, è necessario creare URL semplici riunione per ogni dominio SIP e disporre di un record A DNS per ogni URL semplice riunione. Ad esempio, se si dispone sia di contoso.com che di fabrikam.com, verranno creati record A DNS per entrambi https://meet.contoso.com e https://meet.fabrikam.com .
    
    In alternativa, se si dispone di più domini SIP e si desidera ridurre al minimo i requisiti di record DNS e certificati per questi URL semplici, utilizzare l'opzione 3 descritta più avanti in questo argomento.

  - Per ogni URL semplice per accesso esterno, è necessario un record A DNS che risolva l'URL nell'indirizzo IP del Director, se ne è stato distribuito uno, altrimenti nell'indirizzo IP del servizio di bilanciamento del carico di un pool Front End. Se non è stato distribuito un pool e si utilizza una distribuzione di server Standard Edition, il record A DNS deve risolversi nell'indirizzo IP di un server Standard Edition dell'organizzazione.

  - L'URL semplice di amministrazione è solo per uso interno. Richiede un record A DNS che risolva l'URL nell'indirizzo IP del Director, se ne è stato distribuito uno, altrimenti nell'indirizzo IP del servizio di bilanciamento del carico di un pool Front End. Se non è stato distribuito un pool e si utilizza una distribuzione di server Standard Edition, il record A DNS deve risolversi nell'indirizzo IP di un server Standard Edition dell'organizzazione.

</div>

<div>

## <a name="simple-url-option-2"></a>Opzione 2 per gli URL semplici

Con l'opzione 2, tutti gli URL di base riunione, per accesso esterno e di amministrazione dispongono di un URL di base comune, ad esempio lync.contoso.com. È necessario pertanto un solo record A DNS per questi URL semplici che risolva lync.contoso.com nell'indirizzo IP di un pool di server Director o di un pool Front End. Se non è stato distribuito un pool e si utilizza una distribuzione di server Standard Edition, il record A DNS deve risolversi nell'indirizzo IP di un server Standard Edition dell'organizzazione.

Si noti che se nell'organizzazione sono presenti più domini SIP, è sempre necessario creare URL semplici riunione per ogni dominio SIP e disporre di un record A DNS per ogni URL semplice riunione. In questo esempio tre URL semplici sono tutti basati su lync.contoso.com, mentre un URL semplice riunione aggiuntivo per fabrikam.com è configurato con un URL di base diverso. In questo esempio, è necessario creare record DNS A per entrambi https://lync.contoso.com e https://lync.fabrikam.com . L'opzione 3 per gli URL semplici consente di gestire in un altro modo ancora la denominazione e i record A DNS in presenza di più domini SIP.

### <a name="simple-url-option-2"></a>Opzione 2 per gli URL semplici

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
<td><p>Soddisfare</p></td>
<td><p>https://lync.contoso.com/Meethttps://lync.fabrikam.com/Meete così via (uno per ogni dominio SIP dell'organizzazione)</p></td>
</tr>
<tr class="odd">
<td><p>Accesso esterno</p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p>Amministratore</p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="simple-url-option-3"></a>Opzione 3 per gli URL semplici

L'opzione 3 è più utile se si dispone di numerosi domini SIP e si desidera che dispongano di URL semplici separati, riducendo però al minimo i requisiti dei certificati e dei record DNS per questi URL semplici. In questo esempio è necessario un solo record A DNS per la risoluzione di lync.contoso.com nell'indirizzo IP di un pool di server Director o di un pool Front End.

### <a name="simple-url-option-3"></a>Opzione 3 per gli URL semplici

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
<td><p>Soddisfare</p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Meet</p>
<p>https://lync.contoso.com/fabrikamSIPdomain/Meet</p></td>
</tr>
<tr class="odd">
<td><p>Accesso esterno</p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Dialin</p></td>
</tr>
<tr class="even">
<td><p>Amministratore</p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Admin</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="disaster-recovery-option-for-simple-urls"></a>Opzione di ripristino di emergenza per gli URL semplici

Se si dispone di più siti che contengono pool Front end e il provider DNS supporta GeoDNS, è possibile configurare i record DNS per gli URL semplici che supportano il ripristino di emergenza, in modo che la funzionalità degli URL semplici prosegua anche se un intero pool Front-end viene premuto. Questa funzionalità di ripristino di emergenza supporta gli URL semplici Meet e dial-in.

Per eseguire questa configurazione, creare due indirizzi GeoDNS. Ogni indirizzo presenta due record DNS A o CNAME che si risolvono in due pool che vengono accoppiati per il ripristino di emergenza. Un indirizzo GeoDNS viene usato per l'accesso interno e si risolve nell'FQDN Web interno o nell'indirizzo IP del bilanciamento del carico per i due pool. L'altro indirizzo GeoDNS viene usato per l'accesso esterno e si risolve nell'FQDN Web esterno o nell'indirizzo IP del bilanciamento del carico per i due pool. Di seguito viene riportato un esempio dell'URL semplice Riunione, in cui vengono usati gli FQDN per i pool.

   ```console
    Meet-int.geolb.contoso.com
         Pool1InternalWebFQDN.contoso.com
         Pool2InternalWebFQDN.contoso.com
   ```

   ```console
   Meet-ext.geolb.contoso.com
         Pool1ExternalWebFQDN.contoso.com
         Pool2ExternalWebFQDN.contoso.com
   ``` 

Creare quindi i record CNAME che risolvono l'URL semplice riunione (ad esempio meet.contoso.com) nei due indirizzi GeoDNS.

<div class="">


> [!NOTE]  
> Se la rete usa l'<EM>hairpin</EM> (ovvero il routing di tutto il traffico degli URL semplici attraverso il collegamento esterno, incluso il traffico proveniente dall'organizzazione), è sufficiente configurare l'indirizzo GeoDNS esterno e risolvere l'URL semplice riunione solo nell'indirizzo esterno specifico.



</div>

Quando si usa questo metodo, è possibile configurare ciascun indirizzo GeoDNS in modo che usi un metodo round robin per distribuire le richieste nei due pool oppure per effettuare la connessione principalmente a un pool (ad esempio il pool geograficamente più vicino) e usare l'altro pool solo in caso di errore di connettività.

È possibile specificare la stessa configurazione per l'URL semplice per accesso esterno. A tale scopo, creare record aggiuntivi come quelli nell'esempio precedente, sostituendo `dialin` `meet` nei record DNS. Per l'URL semplice di amministrazione, usare una delle tre opzioni elencate precedentemente in questa sezione.

Dopo avere completato la configurazione, è necessario usare un'applicazione di monitoraggio per impostare il monitoraggio HTTP per il controllo degli errori. Per l'accesso esterno, monitorare per assicurarsi che HTTPS ottenere richieste di individuazione automatica per l'FQDN Web esterno o l'indirizzo IP del bilanciamento del carico per i due pool siano riusciti. Ad esempio, le richieste seguenti non devono includere alcuna intestazione **ACCEPT** e devono restituire **200 OK**.

```console
    HTTPS GET Pool1ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
    HTTPS GET Pool2ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
```

Per l'accesso interno, è necessario monitorare la porta 5061 nell'FQDN Web interno o nell'indirizzo IP del bilanciamento del carico per i due pool. Se vengono rilevati errori di connettività, il VIP per i pool interessati deve chiudere le porte 80, 443 e 444.

</div>

</div>

<span> </span>

</div>

</div>

</div>

