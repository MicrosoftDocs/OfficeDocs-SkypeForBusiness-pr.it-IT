---
title: Riepilogo DNS-SIP, Federazione XMPP e messaggistica istantanea pubblica
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - SIP, XMPP federation, and public instant messaging
ms:assetid: 1ed24fb8-a849-44c0-a52e-7aef7527e644
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618369(v=OCS.15)
ms:contentKeyID: 49105656
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c2ccaab6d1d3bcb1cf597bef076601544f47aad
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42192789"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>Riepilogo DNS-SIP, Federazione XMPP e messaggistica istantanea pubblica in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2017-03-09_

I record DNS (Domain Name System) necessari per la definizione di una federazione con Office Communications Server o Lync Server Partners sono determinati dalla decisione di consentire all'individuazione automatica dei DNS del dominio da parte di altri partner prospettici. Se si pubblica il \_sipfederationtls. \_TCP. * \<Nome\> di dominio SIP* Record SRV, qualsiasi altro dominio federato SIP sarà in grado di "individuare" la Federazione. È possibile controllare i domini federati in grado di comunicare con l'utente utilizzando le impostazioni Consenti domini e domini bloccati nel pannello di controllo di Lync Server o impostando la configurazione dei domini consentiti o bloccati utilizzando Lync Server Management Shell e i cmdlet **Get**, **set**, **New**, **Remove-CsAllowedDomain** e **-CsBlockedDomain** PowerShell. Per ulteriori informazioni su come configurare queste impostazioni e l'utilizzo dei cmdlet di PowerShell, vedere **argomenti correlati** alla fine di questo argomento.

La tabella di riepilogo dei record DNS indica le voci obbligatorie per una federazione aperta o individuabile. Se non si desidera implementare l'individuazione della Federazione, è possibile decidere di non configurare il \_sipfederationtls. \_TCP. Record del *nome\> di dominio SIP. \<*

<div>


> [!IMPORTANT]
> Esistono scenari specifici in cui è necessario disporre del _sipfederationtls. _tcp. <EM> &lt;Nome&gt; di dominio SIP</EM> Record SRV, ma non si desidera disporre di una Federazione individuabile. Un'istanza di questo tipo è la posizione in cui è stata distribuita la mobilità per gli utenti. La funzionalità di compensazione delle notifiche push per dispositivi mobili (centro PNCH) è un tipo speciale di Federazione utilizzato per i client Microsoft Lync Mobile su Apple iPhone o iPad utilizzando il client Lync 2010 mobile o Windows Phone utilizzando i client mobili Lync 2010 mobile o Lync 2013. Il _sipfederationtls. _tcp. <EM> &lt;Nome&gt; di dominio SIP</EM> Il record SRV viene utilizzato in caso di mobilità e di notifica push. Per attenuare il problema e controllare la propria individuabilità, annullare l'impostazione <STRONG>Abilita individuazione dominio partner</STRONG> per disattivare l'individuazione.



</div>

Per configurare il protocollo XMPP (Extensible Messaging and Presence Protocol) per la distribuzione, è necessario creare due record DNS (Domain Name System) in un server DNS esterno che consente di risolvere i record per il servizio Access Edge del server perimetrale o del pool di Edge.

Quando si configura il DNS (Domain Name System) per la connettività di messaggistica istantanea pubblica, si noterà che la configurazione che supporta gli utenti esterni supporterà la connettività per la messaggistica istantanea pubblica. Se è già stato configurato un server perimetrale o un pool di Edge, è necessario disporre dei record DNS necessari per supportare la connettività per la messaggistica istantanea pubblica.

<div>

## <a name="dns-summary---sip-federation-including-public-instant-messaging-connectivity"></a>Riepilogo DNS-federazione SIP inclusa la connettività per la messaggistica istantanea pubblica


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Posizione/tipo/porta</th>
<th>FQDN</th>
<th>Indirizzo IP/FQDN record host</th>
<th>Mapping a/Commenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS esterno/SRV/5061</p></td>
<td><p>_sipfederationtls. _tcp. contoso. com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Interfaccia esterna del servizio Access Edge necessario per l'individuazione automatica dei DNS della Federazione verso altri potenziali partner di federazione ed è nota come "domini SIP consentiti" (chiamata federazione avanzata nelle versioni precedenti). Ripetere il necessario per tutti i domini SIP con gli utenti abilitati per Lync</p>



> [!IMPORTANT]
> Questo record SRV è necessario per la mobilità e PNCH. Nei casi in cui esiste più di un dominio SIP, creare e pubblicare un record SRV per ogni dominio che avrà client mobili di Lync. Il servizio di notifica push e il servizio di notifica push di Apple potrebbero non funzionare come previsto se non è presente un record SRV esplicito per ogni dominio SIP supportato dalla distribuzione.

</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary---extensible-messaging-and-presence-protocol-xmpp"></a>Riepilogo DNS-protocollo XMPP (Extensible Messaging and Presence Protocol)


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Posizione/tipo/porta</th>
<th>FQDN</th>
<th>Indirizzo IP/FQDN record host</th>
<th>Mapping a/Commenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS esterno/SRV/5269</p></td>
<td><p>_xmpp-server. _tcp. contoso. com</p></td>
<td><p>xmpp.contoso.com</p></td>
<td><p>Interfaccia esterna del proxy XMPP nel servizio Access Edge o nel pool di server perimetrali. Ripetere quanto necessario per tutti i domini SIP interni con gli utenti abilitati per Lync, in cui è consentito il contatto con i contatti XMPP tramite la configurazione del criterio di accesso esterno tramite un criterio globale, il criterio del sito in cui si trova l'utente o il criterio utente applicato all' Utente abilitato per Lync. Un dominio XMPP consentito deve inoltre essere configurato nel criterio dei partner XMPP federati. Per informazioni dettagliate, vedere gli argomenti in <strong>Vedere anche</strong></p></td>
</tr>
<tr class="even">
<td><p>DNS esterno/A</p></td>
<td><p>xmpp.contoso.com (esempio)</p></td>
<td><p>Indirizzo IP del servizio Access Edge nel server perimetrale o nel pool perimetrale che ospita il proxy XMPP</p></td>
<td><p>Punta al servizio Access Edge o al pool di server perimetrali che ospita il servizio proxy XMPP. Il record SRV creato punterà a questo record host (A o AAAA).</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>Vedere anche


[Configurazione della Federazione XMPP in Lync Server 2013](lync-server-2013-setting-up-xmpp-federation.md)  
[Configurazione delle notifiche push in Lync Server 2013](lync-server-2013-configuring-for-push-notifications.md)  
[Abilitare o disabilitare l'individuazione dei partner federativi in Lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)  


[Scenari per l'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)  
[Determinare i requisiti DNS per Lync Server 2013](lync-server-2013-determine-dns-requirements.md)  


[Gestire i domini federati SIP per l'organizzazione in Lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

