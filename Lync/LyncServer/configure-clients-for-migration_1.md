---
title: Configurare i client per la migrazione
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Configure clients for migration
ms:assetid: 8f17862b-d9d1-47f6-b248-51f4710f5030
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688130(v=OCS.15)
ms:contentKeyID: 49733729
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 710a5cf6cb23b91431b340c44ebe6ff2738b0822
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "40980585"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-clients-for-migration"></a>Configurare i client per la migrazione

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-11-21_

Questo argomento contiene le procedure consigliate per la distribuzione del client da eseguire prima di eseguire la migrazione a Lync Server 2013. Queste modifiche alla configurazione devono essere eseguite in Office Communications Server 2007 R2. È molto importante eseguire questi passaggi prima della migrazione. Per informazioni dettagliate, vedere [pianificazione per client e dispositivi in Lync Server 2013](lync-server-2013-planning-for-clients-and-devices.md).

<div>

## <a name="to-configure-clients-prior-to-migration"></a>Per configurare i client prima della migrazione

1.  Distribuire gli aggiornamenti più recenti per server, client e dispositivi di Office Communications Server 2007 R2 (hotfix):
    
      - [Applicare gli aggiornamenti di Office Communications Server 2007 R2](apply-office-communications-server-2007-r2-updates.md)
    
      - [Descrizione del pacchetto di aggiornamento cumulativo per Communicator 2007 R2](http://go.microsoft.com/fwlink/p/?linkid=335808)
    
      - [Ottenere gli aggiornamenti software per i dispositivi](http://go.microsoft.com/fwlink/?linkid=335809)

2.  In Office Communications Server 2007 R2 usare il filtro della versione client per consentire solo i client Office Communications Server 2007 R2 con gli aggiornamenti più recenti installati per l'accesso.

3.  In Office Communications Server 2007 R2 usare il filtro della versione client per bloccare i client di Lync Server 2013 dall'accesso. Seguire i passaggi descritti in **configurazione del filtro delle versioni client** in [http://go.microsoft.com/fwlink/p/?linkId=202488](http://go.microsoft.com/fwlink/p/?linkid=202488) per aggiungere i filtri della versione elencati nella tabella seguente. Per ogni filtro della versione, assegnare il **blocco**di azioni.
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Client</th>
    <th>Intestazione dell'agente utente</th>
    <th>Versione</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Lync 2013</p></td>
    <td><p>OC</p></td>
    <td><p>15.*.*. *</p></td>
    </tr>
    <tr class="even">
    <td><p>Lync Web App</p></td>
    <td><p>CWA</p></td>
    <td><p>5.*.*. *</p></td>
    </tr>
    <tr class="odd">
    <td><p>Lync Phone Edition</p></td>
    <td><p>OCPhone</p></td>
    <td><p>4.*.*. *</p></td>
    </tr>
    </tbody>
    </table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

