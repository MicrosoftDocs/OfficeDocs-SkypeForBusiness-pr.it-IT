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
ms.openlocfilehash: c7d45183b3dac5d96d65d771bf1425546f861c38
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135232"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-summary---autodiscover-in-lync-server-2013"></a>Riepilogo del certificato-individuazione automatica in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-14_

Il servizio di individuazione automatica di Lync Server 2013 viene eseguito sui server del pool Director e front end e, quando viene pubblicato in DNS, può essere utilizzato dai client Lync per individuare i servizi utente e server. Se si esegue l'aggiornamento da Lync Server 2010 e non è stata distribuita la funzionalità di mobilità, prima che i client possano utilizzare l'individuazione automatica, è necessario modificare gli elenchi di nomi alternativi del soggetto del certificato su qualsiasi Director e front end server che esegue il servizio Autodiscover. Potrebbe inoltre essere necessario modificare gli elenchi dei nomi alternativi del soggetto nei certificati utilizzati per le regole di pubblicazione dei servizi Web esterni nei proxy inversi.

La decisione sull'eventuale utilizzo degli elenchi di nomi alternativi del soggetto nei proxy inversi è basata sulla possibilità di pubblicare il servizio di individuazione automatica sulla porta 80 o sulla porta 443:

  - **Pubblicati sulla porta 80**   non sono necessarie modifiche del certificato se la query iniziale al servizio di individuazione automatica si verifica sulla porta 80. Ciò è dovuto al fatto che i dispositivi mobili che eseguono Lync accederanno al proxy inverso sulla porta 80 esternamente e quindi verranno ponticellati su un server Director o front end su porta 8080 internamente. Per informazioni dettagliate, vedere la sezione "processo di individuazione automatica iniziale tramite la porta 80" [requisiti tecnici per i dispositivi mobili in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).

  - **Pubblicati sulla porta 443**   l'elenco dei nomi alternativi del soggetto sui certificati utilizzati dalla regola di pubblicazione dei servizi Web esterni deve contenere un *lyncdiscover.\< voce\> SipDomain* per ogni dominio SIP all'interno dell'organizzazione.
    
    <div>
    

    > [!IMPORTANT]  
    > Si consiglia vivamente di utilizzare HTTPS su HTTP. HTTPS utilizza i certificati per crittografare il traffico. HTTP non fornisce la crittografia e tutti i dati inviati diventeranno di testo normale.

    
    </div>

La riemissione di certificati tramite un'autorità di certificazione interna è in genere un processo semplice. Tuttavia, per i certificati pubblici utilizzati nella regola di pubblicazione dei servizi Web, l'aggiunta di più voci del nome alternativo soggetto può essere costosa. Per ovviare a questo problema, è supportata la connessione di individuazione automatica iniziale tramite la porta 80, che viene quindi reindirizzata alla porta 8080 nel server Director o front end.

<div>


> [!NOTE]  
> Se l'infrastruttura di Lync Server 2013 utilizza certificati interni emessi da un'autorità di certificazione (CA) interna e si prevede di supportare i dispositivi mobili che si connettono in modalità wireless, è necessario che sia installata la catena di certificati radice dalla CA interna. sui dispositivi mobili o è necessario passare a un certificato pubblico nell'infrastruttura di Lync Server 2013.



</div>

In questo argomento vengono descritti i nomi alternativi del soggetto aggiunti necessari per il server Director, front-end e il proxy inverso. Si fa riferimento solo ai nomi alternativi del soggetto (SAN) aggiunti. Fare riferimento alle sezioni di pianificazione per le indicazioni sulle altre voci sui certificati. Per informazioni dettagliate, vedere [Scenarios for the Director in Lync server 2013](lync-server-2013-scenarios-for-the-director.md), [scenari per l'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)e [scenari per il proxy inverso in Lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md).

Nelle tabelle riportate di seguito vengono definite le voci SAN di individuazione automatica per il pool di server Director, il pool Front end e il proxy inverso:

### <a name="director-pool-certificate-requirements"></a>Requisiti relativi ai certificati per il pool di server Director

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Descrizione</th>
<th>Voce nome alternativo soggetto</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>URL interno del servizio di individuazione automatica</p></td>
<td><p>SAN = LyncdiscoverInternal. &lt;nome di dominio interno&gt;</p></td>
</tr>
<tr class="even">
<td><p>URL esterno del servizio di individuazione automatica</p></td>
<td><p>SAN = lyncdiscover. &lt;SipDomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> È possibile assegnare il certificato appena aggiornato con la nuova voce di SAN al certificato predefinito. In alternativa, è possibile utilizzare SAN = *. &lt;SipDomain&gt;.



</div>

### <a name="front-end-pool-certificate-requirements"></a>Requisiti relativi ai certificati per il pool Front End

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Descrizione</th>
<th>Voce nome alternativo soggetto</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>URL interno del servizio di individuazione automatica</p></td>
<td><p>SAN = LyncdiscoverInternal. &lt;nome di dominio interno&gt;</p></td>
</tr>
<tr class="even">
<td><p>URL esterno del servizio di individuazione automatica</p></td>
<td><p>SAN = lyncdiscover. &lt;SipDomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> È possibile assegnare il certificato appena aggiornato con la nuova voce di SAN al certificato predefinito. In alternativa, è possibile utilizzare SAN = *. &lt;SipDomain&gt;



</div>

### <a name="reverse-proxy-public-ca-certificate-requirements"></a>Requisiti relativi ai certificati del proxy inverso (CA pubblica)

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Descrizione</th>
<th>Voce nome alternativo soggetto</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>URL esterno del servizio di individuazione automatica</p></td>
<td><p>SAN = lyncdiscover. &lt;SipDomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> È possibile assegnare il certificato appena aggiornato con la nuova voce di SAN al listener SSL nel proxy inverso.



</div>

</div>

<span> </span>

</div>

</div>

</div>

