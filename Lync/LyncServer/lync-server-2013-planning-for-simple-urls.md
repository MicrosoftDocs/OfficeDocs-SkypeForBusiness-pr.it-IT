---
title: 'Lync Server 2013: pianificazione per gli URL semplici'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for simple URLs
ms:assetid: 20e4f4b6-b7ff-4297-b00d-d1211ee800ac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398287(v=OCS.15)
ms:contentKeyID: 48183610
ms.date: 12/12/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d36e730aeef637c12102fbf425c04235d72eb382
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045198"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-simple-urls-in-lync-server-2013"></a>Pianificazione degli URL semplici in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2015-12-11_

Gli URL semplici agevolano la partecipazione alle riunioni per gli utenti e semplificano gli strumenti di amministrazione di Lync Server per gli amministratori.

Lync Server supporta tre URL semplici:

  - L'URL **riunione** (meet) viene utilizzato come URL di base per tutte le conferenze nel sito o nell'organizzazione. Un esempio di URL semplice Meet è https://meet.contoso.com. Un URL per una riunione specifica può essere https://meet.contoso.com/ *nomeutente*/7322994.
    
    Con l'URL semplice riunione, i collegamenti per partecipare alle riunioni sono semplici da capire, da comunicare e da distribuire.

  - L'URL **per accesso esterno** (dialin) consente di accedere alla pagina Web Impostazioni conferenza telefonica con accesso esterno. In questa pagina vengono visualizzati i numeri di accesso esterno alle conferenze con le lingue disponibili, le informazioni sulle conferenze assegnate, ovvero per le riunioni che non devono essere pianificate, e i controlli DTMF in-Conference e che supportano la gestione del numero di identificazione personale ( PIN) e informazioni per le conferenze assegnate. L'URL semplice per accesso esterno è incluso in tutti gli inviti a riunioni, in modo che gli utenti che desiderano eseguire l'accesso esterno alla riunione dispongano delle informazioni necessarie sul numero di telefono e sul PIN. Un esempio di URL semplice in accesso esterno è https://dialin.contoso.com.

  - L' **amministratore** consente di accedere rapidamente al pannello di controllo di Lync Server. Da qualsiasi computer all'interno dei firewall dell'organizzazione, un amministratore può aprire il pannello di controllo di Lync Server digitando l'URL semplice di amministrazione in un browser. L'URL semplice di amministrazione è interno all'organizzazione. Un esempio di URL semplice di amministrazione èhttps://admin.contoso.com

<div>

## <a name="simple-url-scope"></a>Ambito degli URL semplici

È possibile configurare gli URL semplici per un ambito globale oppure specificare URL semplici diversi per ogni sito centrale dell'organizzazione. Se sono specificati sia un URL semplice dell'ambito globale che un URL semplice dell'ambito del sito, l'URL semplice dell'ambito del sito ha la precedenza.

Nella maggior parte dei casi, è consigliabile impostare gli URL semplici solo a livello globale, in modo che l'URL semplice riunione di un utente non cambi con lo spostamento da un sito a un altro. L'eccezione è rappresentata da organizzazioni che devono utilizzare numeri di telefono diversi per gli utenti connessi tramite chiamata in ingresso in siti diversi. Si noti che se si imposta in un sito un URL semplice a livello di sito, ad esempio per l'accesso esterno, sarà necessario impostare a livello di sito anche gli altri URL semplici del sito.

<div>


> [!NOTE]  
> Se si sceglie di utilizzare gli URL semplici con ambito sito, gli utenti non saranno in grado di spostarsi tra i pool Front-end in siti diversi senza che gli utenti ripianificano tutte le riunioni pianificate, in quanto gli URL semplici della riunione sono diversi tra i siti. Sono inclusi gli scenari di failover nei quali i pool nelle relazioni di backup si trovano in siti separati. Quando è necessario eseguire il failover tra i siti in cui vengono distribuiti gli URL semplici con ambito del sito, gli utenti non saranno in grado di partecipare alle riunioni a causa dell'ambito per l'URL. Per ulteriori informazioni, vedere <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsSimpleUrlConfiguration">Get-CsSimpleUrlConfiguration</A>.



</div>

È possibile impostare gli URL semplici globali in Generatore di topologie. Per impostare un URL semplice a livello di sito, è necessario utilizzare il cmdlet Set-CsSimpleURLConfiguration.

</div>

<div>

## <a name="naming-your-simple-urls"></a>Denominazione degli URL semplici

Sono disponibili tre opzioni consigliate per denominare gli URL semplici. L'opzione scelta determina il modo in cui vengono configurati i certificati e i record A DNS che supportano gli URL semplici. In ogni opzione è necessario configurare un URL semplice riunione per ogni dominio SIP dell'organizzazione.

Sono sufficienti sempre nell'intera organizzazione un solo URL semplice per accesso esterno e uno di amministrazione, indipendentemente dal numero di domini SIP presenti.

Per informazioni dettagliate sui record e i certificati DNS necessari, vedere [DNS requirements for Simple URLs in Lync server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) e [Certificate Requirements for Internal Servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) nella documentazione relativa alla pianificazione.

Nell'opzione 1 viene creato un nuovo nome di dominio SIP per ogni URL semplice.

Se si utilizza questa opzione, è necessario un record A DNS separato per ogni URL semplice e ogni URL semplice riunione deve essere denominato nei certificati.

### <a name="simple-url-naming-option-1"></a>Opzione 1 di denominazione degli URL semplici

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


Con l'opzione 2, gli URL semplici sono basati sul nome di dominio lync.contoso.com. È necessario pertanto un solo record A DNS che consenta tutti e tre i tipi di URL semplici. Questo record A DNS fa riferimento a lync.contoso.com. Sono sempre necessari però record A DNS separati per altri domini SIP dell'organizzazione.

### <a name="simple-url-naming-option-2"></a>Opzione 2 di denominazione degli URL semplici

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


L'opzione 3 è più utile se si dispone di numerosi domini SIP e si desidera che dispongano di URL semplici riunione separati, riducendo però al minimo i requisiti dei certificati e dei record DNS per questi URL semplici.

### <a name="simple-url-naming-option-3"></a>Opzione 3 di denominazione degli URL semplici

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
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p>Amministratore</p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="simple-url-naming-and-validation-rules"></a>Regole di denominazione e convalida degli URL semplici

Il generatore di topologie e i cmdlet di Lync Server Management Shell applicano diverse regole di convalida per gli URL semplici. È obbligatorio impostare URL semplici riunione e per accesso esterno, mentre l'impostazione dell'URL semplice di amministrazione è facoltativa. Ogni dominio SIP deve disporre di un URL semplice riunione separato, ma sono sufficienti un URL semplice per accesso esterno e un URL semplice di amministrazione per l'intera organizzazione.

Ogni URL semplice nell'organizzazione deve avere un nome univoco e non può essere un prefisso di un altro URL semplice (ad esempio, non è stato possibile impostare lync.contoso.com/Meet come URL semplice Meet e lync.contoso.com/Meet/Dialin come URL semplice di accesso esterno). Gli URL semplici non possono contenere il nome di dominio completo di uno dei pool o qualsiasi altra informazione sulla porta https://FQDN:88/meet , ad esempio, non è consentita. Tutti gli URL semplici devono iniziare con il prefisso https://.

Gli URL semplici possono includere solo caratteri alfanumerici, ovvero a-z, A-Z, 0-9 e il punto (.). Se si utilizzano altri caratteri, gli URL semplici potrebbero non funzionare come previsto.

</div>

<div>

## <a name="changing-simple-urls-after-deployment"></a>Modifica degli URL semplici dopo la distribuzione

Se si modifica un URL semplice dopo la distribuzione iniziale, è necessario essere a conoscenza del modo in cui la modifica influisce sui record DNS e sui certificati per gli URL semplici. Se si modifica la base di un URL semplice, è necessario modificare anche i record DNS e i certificati. Ad esempio, se si https://lync.contoso.com/Meet cambia https://meet.contoso.com da per cambiare l'URL di base da Lync.contoso.com a meet.contoso.com, è necessario modificare i record DNS e i certificati in modo che facciano riferimento a meet.contoso.com. Se l'URL semplice è stato modificato https://lync.contoso.com/Meet da https://lync.contoso.com/Meetingsa, l'url di base di Lync.contoso.com rimane invariato, quindi non sono necessarie modifiche a DNS o certificati.

Ogni volta che si modifica un nome URL semplice, è necessario eseguire **Enable-CsComputer** in ogni Director e front end server per registrare la modifica.

</div>

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Requisiti DNS per gli URL semplici in Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

