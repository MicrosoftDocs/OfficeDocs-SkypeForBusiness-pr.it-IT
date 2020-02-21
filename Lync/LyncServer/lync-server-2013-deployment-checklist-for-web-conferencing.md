---
title: Elenco di controllo di distribuzione di Lync Server 2013 per Web Conferencing
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for web conferencing
ms:assetid: 9908ebe0-e5d3-4920-b9b1-85021f7e69e9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205104(v=OCS.15)
ms:contentKeyID: 48184878
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 54d3825891fe6934699e310073825e50a4aee731
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213776"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-web-conferencing-in-lync-server-2013"></a>Elenco di controllo di distribuzione per le conferenze Web in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-30_

Come per la distribuzione degli altri componenti di Lync Server 2013, la distribuzione di Web Conferencing richiede l'utilizzo di generatore di topologie per creare e pubblicare una topologia che incorpora servizi di conferenza.

<div>

## <a name="deployment-sequence"></a>Sequenza di distribuzione

È possibile distribuire le conferenze nello stesso momento in cui si distribuisce la topologia iniziale o dopo aver distribuito almeno un pool Front end o un server Standard Edition.

</div>

<div>

## <a name="conferencing-deployment-process"></a>Processo di distribuzione delle funzioni di conferenza

Nella tabella seguente viene fornita una panoramica dei passaggi da eseguire per distribuire il supporto per la conferenza in una topologia esistente.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Fase</th>
<th>Passaggi</th>
<th>Ruoli e gruppi a cui è necessario appartenere</th>
<th>Documentazione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Installare l'hardware e il software prerequisiti</strong></p></td>
<td><p>I servizi di conferenza vengono eseguiti nei front end server in un pool Front end e server Standard Edition. Non esistono ulteriori requisiti di hardware o software oltre a quelli necessari per l'installazione di questi server.</p>
<div>

> [!NOTE]  
> Lync Server 2013 utilizza Office Web Apps e il server Office Web Apps per gestire la condivisione e il rendering delle presentazioni di PowerPoint. Per informazioni sull'installazione e sulla configurazione del server Office Web Apps, vedere <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">configurazione dell'integrazione con Office Web Apps Server e Lync server 2013</A>.


</div></td>
<td><p>Utente del dominio membro del gruppo Administrators locale</p></td>
<td><p><a href="lync-server-2013-supported-hardware.md">Hardware supportato per Lync Server 2013</a> nella documentazione relativa alla supportabilità</p>
<p><a href="lync-server-2013-server-software-and-infrastructure-support.md">Supporto dell'infrastruttura e del software server in Lync server 2013</a> nella documentazione relativa alla supportabilità</p>
<p><a href="lync-server-2013-determining-your-system-requirements.md">Determinazione dei requisiti di sistema per Lync Server 2013</a> nella documentazione relativa alla pianificazione.</p>
<p><a href="lync-server-2013-technical-requirements-for-archiving.md">Requisiti tecnici per l'archiviazione in Lync Server 2013</a> nella documentazione relativa alla pianificazione.</p></td>
</tr>
<tr class="even">
<td><p><strong>Creare la topologia interna appropriata per supportare le funzioni di conferenza</strong></p></td>
<td><p>Eseguire Generatore di topologie per aggiungere servizi di conferenza alla topologia e quindi pubblicare la topologia.</p></td>
<td><p>Per definire una topologia, un account membro del gruppo Users locale</p>
<p>Per pubblicare la topologia, un account che sia membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins e che disponga di autorizzazioni di controllo completo (lettura/scrittura/modifica) sulla condivisione file da utilizzare per l'archivio file di Lync Server 2013 (in modo che il generatore di topologie possa configurare gli elenchi DACL necessari)</p></td>
<td><p><a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">Definire e configurare una topologia in Generatore di topologie per Lync Server 2013</a> nella documentazione relativa alla distribuzione.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Configurare i criteri e il supporto per le funzioni di conferenza</strong></p></td>
<td><p>Utilizzare il pannello di controllo di Lync Server 2013 o Lync Server Management Shell per configurare le impostazioni di conferenza.</p></td>
<td><p>Gruppo RTCUniversalServerAdmins (solo Windows PowerShell) oppure assegnare gli utenti al ruolo [] o CSAdministrator</p></td>
<td><p><a href="lync-server-2013-conferencing-policies.md">Criteri di conferenza in Lync Server 2013</a> nella documentazione relativa alle operazioni.</p></td>
</tr>
</tbody>
</table>


Lync Server 2013 ora include l'impostazione **MaxUploadFileSizeMb** , che consente di limitare le dimensioni dei file che possono essere caricati durante una riunione. Il valore predefinito per questa impostazione è di 500 MB. È possibile modificare **MaxUploadFileSizeMb** mediante il cmdlet **Set-CsConferencingConfiguration**.

**MaxUploadFileSizeMb** non limita l'impostazione di caricamento dei file per Lync Web App. Il limite di caricamento delle dimensioni dei file per Lync Web App è impostato su approssimativamente 30MB ed è controllato dal file Web. config di\[IIS\]:/DataCollabWeb/int ext/handler/Web.config. Per configurare il limite di caricamento delle dimensioni dei file per Lync Web `maxRequestLength` app `maxAllowedContentLength` , aggiornarlo e nel file Web. config come illustrato di seguito.

    <system.web>
        <!-- 
            Since this handler is used to upload files to DMCU the request size (in kilobytes) 
            has to fit max allowed file size uploaded by LWA client.
            The timeout has to reflect the min client bandwidth. Timeout of 600 secs 
            and 512 Kbits of *client* bandwidth would result into aproximately 30 Mbytes 
            for LWA upload size limit.
        -->
          <httpRuntime maxRequestLength="500000" executionTimeout="600" />
    
    
    
                    <security>
                    <requestFiltering>
                               <requestLimits maxAllowedContentLength="524288000" />
                    </requestFiltering>
                    </security>

È necessario aggiornare il file Web. config per ogni Front End Server.

</div>

</div>

<span> </span>

</div>

</div>

</div>

