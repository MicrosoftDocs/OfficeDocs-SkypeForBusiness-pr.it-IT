---
title: 'Lync Server 2013: riepilogo del certificato-individuazione automatica'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Autodiscover
ms:assetid: 16ac96bb-882a-4141-b75c-9530637548d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945616(v=OCS.15)
ms:contentKeyID: 51541451
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8956c8a0ed4e149f336e6670aaf5b262f1868748
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736666"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---autodiscover-in-lync-server-2013"></a>Riepilogo del certificato-individuazione automatica in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-14_

Il servizio di individuazione automatica di Lync Server 2013 viene eseguito nei server Director e front end pool e, se pubblicato in DNS, può essere usato dai client Lync per individuare i servizi server e utente. Se si esegue l'aggiornamento da Lync Server 2010 e non si distribuisce la mobilità, prima che i client possano usare l'individuazione automatica, è necessario modificare gli elenchi di nomi alternativi del soggetto del certificato in qualsiasi Director e front end server in cui è in uso il servizio di rilevamento automatico. Può essere inoltre necessario modificare gli elenchi di nomi alternativi oggetto nei certificati usati per le regole di pubblicazione dei servizi Web esterni nei proxy inversi.

La decisione relativa all'uso di elenchi di nomi alternativi oggetto nei proxy inversi si basa sulla possibilità di pubblicare il servizio di individuazione automatica sulla porta 80 o sulla porta 443:

  - **Pubblicato sulla porta 80**   non sono necessarie modifiche al certificato se la query iniziale per il servizio di individuazione automatica si verifica sulla porta 80. Il motivo è che i dispositivi mobili che utilizzano Lync accederanno al proxy inverso sulla porta 80 esternamente e quindi saranno ponticellati a un amministratore o a un server front-end sulla porta 8080 internamente. Per informazioni dettagliate, vedere la sezione "procedura di individuazione automatica tramite la porta 80" [requisiti tecnici per la mobilità in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).

  - **Pubblicato in porta 443**   l'elenco dei nomi alternativi oggetto nei certificati usati dalla regola di pubblicazione dei servizi Web esterni deve contenere un *lyncdiscover.\< SipDomain\> * voce per ogni dominio SIP all'interno dell'organizzazione.
    
    <div>
    

    > [!IMPORTANT]  
    > Ti consigliamo vivamente di usare HTTPS tramite HTTP. HTTPS usa i certificati per crittografare il traffico. HTTP non prevede la crittografia e tutti i dati inviati saranno testo normale.

    
    </div>

La riemissione di certificati tramite un'autorità di certificazione interna è in genere un processo semplice. Ma per i certificati pubblici usati nella regola di pubblicazione del servizio Web, l'aggiunta di più voci di nomi alternativi soggetto può diventare costosa. Per risolvere il problema, è supportata la connessione di individuazione automatica iniziale tramite la porta 80, che viene quindi reindirizzata alla porta 8080 nel server Director o front end.

<div>


> [!NOTE]  
> Se l'infrastruttura di Lync Server 2013 USA certificati interni emessi da un'autorità di certificazione (CA) interna e si prevede di supportare i dispositivi mobili che si connettono in modalità wireless, è necessario che la catena di certificati radice della CA interna sia installata nei dispositivi mobili o è necessario passare a un certificato pubblico nell'infrastruttura di Lync Server 2013.



</div>

In questo argomento vengono descritti i nomi alternativi oggetto aggiunti necessari per il Director, Front End Server e proxy inverso. Viene fatto riferimento solo ai nomi alternativi oggetto aggiunti (SAN). Fare riferimento alle sezioni pianificazione per informazioni sulle altre voci sui certificati. Per informazioni dettagliate, vedere [scenari per il Director in Lync server 2013](lync-server-2013-scenarios-for-the-director.md), [scenari per l'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)e [scenari per il proxy inverso in Lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md).

Le tabelle seguenti definiscono le voci SAN di individuazione automatica per il pool di Director, il pool Front end e il proxy inverso:

### <a name="director-pool-certificate-requirements"></a>Requisiti dei certificati del pool di Director

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Descrizione</th>
<th>Voce alternativa nome oggetto</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>URL del servizio di individuazione automatica interno</p></td>
<td><p>SAN = LyncdiscoverInternal. &lt;nome di dominio interno&gt;</p></td>
</tr>
<tr class="even">
<td><p>URL del servizio di individuazione automatica esterna</p></td>
<td><p>SAN = lyncdiscover. &lt;SipDomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Si assegna il certificato appena aggiornato con la nuova voce SAN al certificato predefinito. In alternativa, è possibile usare SAN = *. &lt;SipDomain&gt;.



</div>

### <a name="front-end-pool-certificate-requirements"></a>Requisiti del certificato del pool Front-End

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Descrizione</th>
<th>Voce alternativa nome oggetto</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>URL del servizio di individuazione automatica interno</p></td>
<td><p>SAN = LyncdiscoverInternal. &lt;nome di dominio interno&gt;</p></td>
</tr>
<tr class="even">
<td><p>URL del servizio di individuazione automatica esterna</p></td>
<td><p>SAN = lyncdiscover. &lt;SipDomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Si assegna il certificato appena aggiornato con la nuova voce SAN al certificato predefinito. In alternativa, è possibile usare SAN = *. &lt;SipDomain&gt;



</div>

### <a name="reverse-proxy-public-ca-certificate-requirements"></a>Requisiti dei certificati reverse proxy (public CA)

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Descrizione</th>
<th>Voce alternativa nome oggetto</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>URL del servizio di individuazione automatica esterna</p></td>
<td><p>SAN = lyncdiscover. &lt;SipDomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Si assegna il certificato appena aggiornato con la nuova voce SAN al listener SSL nel proxy inverso.



</div>

</div>

<span> </span>

</div>

</div>

</div>

