---
title: Configurare i client per la migrazione
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure clients for migration
ms:assetid: 8f17862b-d9d1-47f6-b248-51f4710f5030
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688130(v=OCS.15)
ms:contentKeyID: 49733729
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b63ad4dfd4b69966a6d206ab19330d7088aff434
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180979"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-clients-for-migration"></a>Configurare i client per la migrazione

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-11-21_

Questo argomento contiene le procedure consigliate per la distribuzione del client che è necessario eseguire prima di eseguire la migrazione a Lync Server 2013. Queste modifiche alla configurazione devono essere eseguite su Office Communications Server 2007 R2. È molto importante eseguire questa procedura prima della migrazione. Per informazioni dettagliate, vedere [Planning for clients and Devices in Lync Server 2013](lync-server-2013-planning-for-clients-and-devices.md).

<div>

## <a name="to-configure-clients-prior-to-migration"></a>Per configurare i client prima della migrazione

1.  Distribuire gli aggiornamenti più recenti per il server, il client e i dispositivi di Office Communications Server 2007 R2 (hotfix):
    
      - [Applicare gli aggiornamenti di Office Communications Server 2007 R2](apply-office-communications-server-2007-r2-updates.md)
    
      - [Descrizione del pacchetto di aggiornamento cumulativo per Communicator 2007 R2](https://go.microsoft.com/fwlink/p/?linkid=335808)
    
      - [Acquisizione degli aggiornamenti software per i dispositivi](https://go.microsoft.com/fwlink/?linkid=335809)

2.  In Office Communications Server 2007 R2, utilizzare il filtro delle versioni client per consentire l'accesso solo ai client di Office Communications Server 2007 R2 con gli aggiornamenti più recenti installati.

3.  In Office Communications Server 2007 R2, utilizzare il filtro delle versioni client per bloccare i client di Lync Server 2013 dall'accesso. Attenersi alla procedura descritta in **Configuring Client Version Filtering** [https://go.microsoft.com/fwlink/p/?linkId=202488](https://go.microsoft.com/fwlink/p/?linkid=202488) to per aggiungere i filtri di versione elencati nella tabella seguente. Per ogni filtro di versione assegnare l'azione **Blocca**.
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Client</th>
    <th>Intestazione agente utente</th>
    <th>Version</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Lync 2013</p></td>
    <td><p>OC</p></td>
    <td><p>15.*..* *</p></td>
    </tr>
    <tr class="even">
    <td><p>Lync Web App</p></td>
    <td><p>CWA</p></td>
    <td><p>5.*..* *</p></td>
    </tr>
    <tr class="odd">
    <td><p>Lync Phone Edition</p></td>
    <td><p>OCPhone</p></td>
    <td><p>4.*..* *</p></td>
    </tr>
    </tbody>
    </table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

