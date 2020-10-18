---
title: "Lync Server 2013: requisiti DNS per l'accesso automatico dei client"
description: "Lync Server 2013: requisiti DNS per l'accesso automatico dei client."
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
ms.openlocfilehash: 2247c955e0a563a22fb5d0ec20735291a836cdfc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574372"
---
# <a name="dns-requirements-for-automatic-client-sign-in-in-lync-server-2013"></a>Requisiti DNS per l'accesso automatico dei client in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-06-19_

In questa sezione vengono descritti i record DNS (Domain Name System) necessari per l'accesso client automatico. Quando si distribuiscono i Server Standard o i pool Front End, è possibile configurare i client per l'utilizzo dell'individuazione automatica in modo da accedere al Server Standard o al pool Front End appropriato. Se si prevede di richiedere ai client di connettersi manualmente a Lync Server 2013, è possibile ignorare questo argomento.

Per supportare l'accesso automatico dei client, è necessario:

  - Designare un solo server o un pool per la distribuzione e l'autenticazione delle richieste di accesso dei client. A tale scopo, è possibile designare un server o un pool disponibile nell'organizzazione che ospita gli utenti oppure un server o un pool dedicato che non ospita alcun utente. Per garantire la disponibilità elevata, è consigliabile designare un pool Front End per questa funzione.

  - Creare un record SRV DNS interno per supportare l'accesso automatico dei client per questo server o pool.
    
    <div>
    

    > [!NOTE]  
    > Nei requisiti dei record riportati di seguito il dominio SIP fa riferimento alla parte host degli URI SIP assegnati agli utenti. Se ad esempio gli URI SIP sono nel formato *@contoso.com, contoso.com è il dominio SIP. Il dominio SIP è spesso diverso dal dominio Active Directory interno. Un'organizzazione può supportare anche più domini SIP.

    
    </div>

Per abilitare la configurazione automatica per i client, è necessario creare un record SRV DNS interno che esegua il mapping tra uno dei record seguenti e il nome di dominio completo (FQDN) del pool Front end o del server Standard Edition che distribuisce le richieste di accesso dai client Lync:

  - \_sipinternaltls. \_ TCP.\<domain\> -per le connessioni TLS interne

È sufficiente creare un unico record SRV per il pool Front End o il server Standard Edition che distribuirà le richieste di accesso.

Nella tabella riportata di seguito vengono illustrati alcuni record di esempio necessari per la società fittizia Contoso, che supporta i domini SIP contoso.com e retail.contoso.com.

### <a name="example-of-dns-records-required-for-automatic-client-sign-in-with-multiple-sip-domains"></a>Esempio di record DNS obbligatori per l'accesso automatico dei client con più domini SIP

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>FQDN del pool Front End utilizzato per distribuire le richieste di accesso</th>
<th>Dominio SIP</th>
<th>Record SRV DNS</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>pool01.contoso.com</p></td>
<td><p>contoso.com</p></td>
<td><p>Record SRV per il dominio _sipinternaltls._tcp.contoso.com tramite la porta 5061 associata a pool01.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>pool01.contoso.com</p></td>
<td><p>retail.contoso.com</p></td>
<td><p>Record SRV per il dominio _sipinternaltls._tcp.retail.contoso.com tramite la porta 5061 associata a pool01.contoso.com</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Per impostazione predefinita, le query per i record DNS seguono la rigida corrispondenza dei nomi di dominio tra il dominio del nome utente e il record SRV. Se si desidera che le query DNS del client utilizzino invece la corrispondenza dei suffissi, è possibile configurare il criterio di gruppo DisableStrictDNSNaming. Per informazioni dettagliate, vedere <A href="lync-server-2013-planning-for-clients-and-devices.md">Planning for clients and Devices in Lync Server 2013</A> nella documentazione relativa alla pianificazione.



</div>

<div>

## <a name="example-of-the-certificates-and-dns-records-required-for-automatic-client-sign-in"></a>Esempio dei certificati e dei record DNS obbligatori per l'accesso automatico dei client

In questo esempio vengono utilizzati gli stessi nomi di esempio della tabella precedente. L'organizzazione Contoso supporta i domini SIP contoso.com e retail.contoso.com e tutti i relativi utenti dispongono di un URI SIP in uno dei formati seguenti:

  - \<user\>@retail. contoso.com

  - \<user\>@contoso. com

</div>

</div>

<span> </span>

</div>

</div>

</div>

