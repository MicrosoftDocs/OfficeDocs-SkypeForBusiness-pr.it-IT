---
title: 'Lync Server 2013: riepilogo del certificato-federazione XMPP (Extensible Messaging and Presence Protocol)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Extensible messaging and presence protocol (XMPP) federation
ms:assetid: b059a34e-99df-40af-91fe-fe2aa52841f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618374(v=OCS.15)
ms:contentKeyID: 49105661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7af2c226397c5225fc26f6dbdf40d12a4bdb1ca0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736626"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a>Riepilogo del certificato-federazione XMPP (Extensible Messaging and Presence Protocol) in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-12-23_

I requisiti di certificato per l'abilitazione e la creazione di comunicazioni con i partner del protocollo XMPP (Extensible Messaging and Presence Protocol) richiedono il record aggiuntivo dei domini XMPP. Il record incluso nel certificato come nome alternativo soggetto (SAN) sarà il dominio che può partecipare alle comunicazioni XMPP. Il dominio può essere il dominio a livello di radice (ad esempio contoso.com) se si vuole abilitare XMPP per l'intero dominio oppure i domini figlio selezionati, ad esempio corp.contoso.com, finance.contoso.com, se si Abilita XMPP per un sottoinsieme di utenti.

<div>

## <a name="certificate-summary-for-extensible-messaging-and-presence-protocol"></a>Riepilogo del certificato per il protocollo di messaggistica e presenza estensibile


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Componente</th>
<th>Nome oggetto</th>
<th>Nomi alternativi oggetto (SAN)/Order</th>
<th>Commenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Assegna a servizio Edge di Access di Edge Server o pool di Edge</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>webcon.contoso.com</p>
<p>sip.contoso.com</p>
<p>sip.fabrikam.com</p>
<p>contoso.com</p></td>
<td><p>Le prime tre voci SAN sono le normali voci di SAN per un server perimetrale completo. Contoso.com è la voce necessaria per la Federazione con il partner XMPP a livello di dominio radice. Questa voce consentirà XMPP per tutti i domini con il suffisso contoso.com.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>Vedere anche


[Esempio di configurazione XMPP in Lync Server 2013 - federazione di XMPP con Google Talk](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[Pianificare i certificati dei server perimetrali in Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md)  


[Configurare i certificati perimetrali per Lync Server 2013](lync-server-2013-set-up-edge-certificates.md)  
[Request-CsCertificate](https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate)  
[Set-CsCertificate](https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

