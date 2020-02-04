---
title: 'Lync Server 2013: Pianificazione degli URL semplici'
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
ms.openlocfilehash: 224ca0315aff2618500182398cfe792c9626b883
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41750466"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-simple-urls-in-lync-server-2013"></a>Pianificazione degli URL semplici in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2015-12-11_

Gli URL semplici semplificano la partecipazione alle riunioni per gli utenti e rendono più semplice l'accesso agli strumenti di amministrazione di Lync Server per gli amministratori.

Lync Server supporta tre semplici URL:

  - L' **incontro** viene usato come URL di base per tutte le conferenze nel sito o nell'organizzazione. Un esempio di URL semplice Meet è https://meet.contoso.com. Un URL per una determinata riunione può essere https://meet.contoso.com/ *nomeutente*/7322994.
    
    Con l'URL semplice Meet, i collegamenti alle riunioni di partecipazione sono facili da comprendere e facili da comunicare e distribuire.

  - L'accesso esterno consente di accedere alla pagina Web delle impostazioni dei servizi di conferenza telefonica con **chiamata in ingresso** . In questa pagina vengono visualizzati i numeri di accesso esterno per conferenze con le lingue disponibili, le informazioni sulla conferenza assegnate, ovvero per le riunioni che non devono essere pianificate, e i controlli DTMF in conferenza e supportano la gestione del numero di identificazione personale ( PIN) e informazioni di conferenza assegnate. L'URL semplice per la chiamata in ingresso è incluso in tutti gli inviti alle riunioni, in modo che gli utenti che vogliono connettersi alla riunione possano accedere al numero di telefono e alle informazioni PIN necessarie. Un esempio dell'URL semplice in accesso esterno è https://dialin.contoso.com.

  - L' **amministratore** consente l'accesso rapido al pannello di controllo di Lync Server. Da qualsiasi computer all'interno del firewall dell'organizzazione, un amministratore può aprire il pannello di controllo di Lync Server digitando l'URL semplice amministratore in un browser. L'URL semplice amministratore è interno dell'organizzazione. Un esempio dell'URL semplice di amministrazione èhttps://admin.contoso.com

<div>

## <a name="simple-url-scope"></a>Ambito URL semplice

Puoi configurare gli URL semplici per avere un ambito globale oppure puoi specificare URL semplici diversi per ogni sito centrale dell'organizzazione. Se sono specificati sia un URL semplice dell'ambito globale che un URL semplice per l'ambito del sito, l'URL semplice dell'ambito del sito ha la precedenza.

Nella maggior parte dei casi è consigliabile impostare URL semplici solo a livello globale, in modo che l'URL di riunione semplice dell'utente non venga modificato se si passa da un sito a un altro. L'eccezione è costituita dalle organizzazioni che devono usare numeri di telefono diversi per gli utenti con accesso esterno in siti diversi. Tieni presente che se imposti un semplice URL (ad esempio l'URL semplice in accesso esterno) in un sito per essere un URL semplice a livello di sito, devi anche impostare gli altri URL semplici di tale sito come a livello di sito.

<div>


> [!NOTE]  
> Se si sceglie di usare URL semplici con ambito sito, gli utenti non saranno in grado di spostarsi tra i pool Front-end in siti diversi senza che gli utenti riprogrammano tutte le riunioni pianificate, poiché gli URL semplici della riunione sono diversi tra i siti. Questo include scenari di failover in cui i pool nelle relazioni di backup si trovano in siti distinti. Quando è necessario eseguire il failover tra i siti in cui vengono distribuiti URL semplici con ambito sito, gli utenti non potranno partecipare alle riunioni per l'ambito dell'URL. Per altre informazioni, selezionare <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsSimpleUrlConfiguration">Get-CsSimpleUrlConfiguration</A>.



</div>

Puoi impostare URL semplici globali in Generatore di topologie. Per impostare un URL semplice a livello di sito, è necessario utilizzare il cmdlet Set-CsSimpleURLConfiguration.

</div>

<div>

## <a name="naming-your-simple-urls"></a>Denominazione degli URL semplici

Sono disponibili tre opzioni consigliate per la denominazione degli URL semplici. Quale opzione si sceglie ha implicazioni per configurare i record DNS e i certificati che supportano gli URL semplici. In ogni opzione è necessario configurare un URL semplice di riunione per ogni dominio SIP dell'organizzazione.

È sempre necessario un solo URL semplice nell'intera organizzazione per l'accesso esterno e uno per l'amministratore, indipendentemente dal numero di domini SIP.

Per informazioni dettagliate sui record e i certificati DNS necessari, vedere [requisiti DNS per gli URL semplici in Lync server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) e i [requisiti dei certificati per i server interni in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) nella documentazione relativa alla pianificazione.

Nell'opzione 1 si crea un nuovo nome di dominio SIP per ogni URL semplice.

Se si usa questa opzione, è necessario un record DNS distinto per ogni URL semplice e ogni URL semplice Meet deve essere denominato nei certificati.

### <a name="simple-url-naming-option-1"></a>Opzione di denominazione semplice URL 1

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


Con l'opzione 2, gli URL semplici si basano sul nome di dominio lync.contoso.com. Di conseguenza, è necessario un solo record DNS che consenta A tutti e tre i tipi di URL semplici. Questo record DNS fa riferimento A lync.contoso.com. È inoltre necessario separare i record DNS per altri domini SIP nell'organizzazione.

### <a name="simple-url-naming-option-2"></a>Opzione di denominazione semplice URL 2

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


L'opzione 3 è molto utile se si hanno molti domini SIP e si vuole che dispongano di URL semplici per riunioni separate, ma che si vogliano ridurre al minimo i requisiti di record e certificati DNS per questi URL semplici.

### <a name="simple-url-naming-option-3"></a>Opzione di denominazione URL semplice 3

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
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p>Admin</p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="simple-url-naming-and-validation-rules"></a>Regole di denominazione e convalida URL semplici

Generatore di topologie e i cmdlet di Lync Server Management Shell applicano diverse regole di convalida per gli URL semplici. È necessario impostare URL semplici per le riunioni e la chiamata, ma l'impostazione di una per l'amministratore è facoltativa. Ogni dominio SIP deve avere un URL semplice Meet distinto, ma è necessario un solo URL semplice dialin e un URL semplice per l'amministratore per l'intera organizzazione.

Ogni URL semplice nell'organizzazione deve avere un nome univoco e non può essere un prefisso di un altro URL semplice (ad esempio, non è stato possibile impostare lync.contoso.com/Meet come URL semplice di riunione e lync.contoso.com/Meet/Dialin come URL semplice di accesso esterno). I nomi di URL semplici non possono contenere il nome di dominio completo di uno dei pool o qualsiasi informazione sulla https://FQDN:88/meet porta, ad esempio non è consentita. Tutti gli URL semplici devono iniziare con il prefisso https://.

Gli URL semplici possono contenere solo caratteri alfanumerici, ovvero a-z, A-Z, 0-9 e il punto (.). Se si usano altri caratteri, gli URL semplici potrebbero non funzionare come previsto.

</div>

<div>

## <a name="changing-simple-urls-after-deployment"></a>Modifica di URL semplici dopo la distribuzione

Se si modifica un URL semplice dopo la distribuzione iniziale, è necessario essere consapevoli del modo in cui la modifica influisce sui record DNS e sui certificati per gli URL semplici. Se la base di un URL semplice cambia, è necessario modificare anche i record DNS e i certificati. Ad esempio, passando da https://lync.contoso.com/Meet per https://meet.contoso.com cambiare l'URL di base da Lync.contoso.com a meet.contoso.com, è necessario modificare i record DNS e i certificati per fare riferimento a meet.contoso.com. Se è stato modificato l'URL https://lync.contoso.com/Meet semplice https://lync.contoso.com/Meetings, l'url di base di Lync.contoso.com rimane invariato, quindi non sono necessarie modifiche DNS o di certificato.

Ogni volta che si modifica un nome di URL semplice, è necessario eseguire **Enable-CsComputer** su ogni Director e front end server per registrare la modifica.

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

