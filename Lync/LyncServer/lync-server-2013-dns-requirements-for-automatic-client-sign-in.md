---
title: "Lync Server 2013: requisiti DNS per l'accesso automatico al client"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for automatic client sign-in
ms:assetid: 3bcd4bb3-a022-4ffa-b005-1a95ad2b1796
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425884(v=OCS.15)
ms:contentKeyID: 48183873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6d033621382587367630d9119c2176e976cb2c2d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739156"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-automatic-client-sign-in-in-lync-server-2013"></a>Requisiti DNS per l'accesso automatico client in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-06-19_

Questa sezione illustra i record DNS (Domain Name System) necessari per l'accesso automatico client. Quando si distribuiscono i server standard o i pool Front-End, è possibile configurare i client per l'uso dell'individuazione automatica per accedere al server standard o al pool Front-end appropriato. Se si prevede di richiedere la connessione manuale dei client a Lync Server 2013, è possibile ignorare questo argomento.

Per supportare l'accesso automatico al client, è necessario:

  - Designa un singolo server o pool per la distribuzione e l'autenticazione delle richieste di accesso client. Può trattarsi di un server o di un pool esistente nell'organizzazione che ospita gli utenti oppure è possibile designare un server o un pool dedicato per questo scopo che non ospita utenti. Per una disponibilità elevata, è consigliabile designare un pool Front-end per questa funzione.

  - Creare un record SRV DNS interno per supportare l'accesso automatico al client per questo server o pool.
    
    <div>
    

    > [!NOTE]  
    > Nei requisiti di record seguenti, il dominio SIP si riferisce alla parte ospitante degli URI SIP assegnati agli utenti. Ad esempio, se gli URI SIP hanno il formato * @contoso. com, contoso.com è il dominio SIP. Il dominio SIP è spesso diverso dal dominio Active Directory interno. Un'organizzazione può anche supportare più domini SIP.

    
    </div>

Per abilitare la configurazione automatica per i client, è necessario creare un record SRV DNS interno che esegue il mapping di uno dei record seguenti al nome di dominio completo (FQDN) del pool Front-end o del server Standard Edition che distribuisce le richieste di accesso da Lync client

  - \_sipinternaltls. \_TCP. \<domain\> -per le connessioni TLS interne

È sufficiente creare un singolo record SRV per il pool Front-end o per il server Standard Edition o per distribuire le richieste di accesso.

Nella tabella seguente sono riportati alcuni esempi di record necessari per la società fittizia Contoso, che supporta i domini SIP di contoso.com e retail.contoso.com.

### <a name="example-of-dns-records-required-for-automatic-client-sign-in-with-multiple-sip-domains"></a>Esempio di record DNS necessari per l'accesso automatico al client con più domini SIP

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>FQDN del pool Front End usato per distribuire le richieste di accesso</th>
<th>Dominio SIP</th>
<th>Record SRV DNS</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>pool01.contoso.com</p></td>
<td><p>contoso.com</p></td>
<td><p>Record SRV per il dominio _sipinternaltls. _tcp. contoso. com sulla porta 5061 che esegue il mapping a pool01.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>pool01.contoso.com</p></td>
<td><p>retail.contoso.com</p></td>
<td><p>Record SRV per il dominio _sipinternaltls. _tcp. retail. contoso. com sulla porta 5061 mappata a pool01.contoso.com</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Per impostazione predefinita, le query per i record DNS si applicano a una corrispondenza di nomi di dominio rigorosa tra il dominio nel nome utente e il record SRV. Se si preferisce che le query DNS client usino invece la corrispondenza dei suffissi, è possibile configurare i criteri di gruppo di DisableStrictDNSNaming. Per informazioni dettagliate, vedere <A href="lync-server-2013-planning-for-clients-and-devices.md">pianificazione di client e dispositivi in Lync Server 2013</A> nella documentazione relativa alla pianificazione.



</div>

<div>

## <a name="example-of-the-certificates-and-dns-records-required-for-automatic-client-sign-in"></a>Esempio di certificati e record DNS necessari per l'accesso automatico al client

Questo esempio usa gli stessi nomi di esempio nella tabella precedente. L'organizzazione Contoso supporta i domini SIP di contoso.com e retail.contoso.com e tutti gli utenti hanno un URI SIP in uno dei moduli seguenti:

  - \<User\>@retail. contoso.com

  - \<User\>@contoso. com

</div>

</div>

<span> </span>

</div>

</div>

</div>

