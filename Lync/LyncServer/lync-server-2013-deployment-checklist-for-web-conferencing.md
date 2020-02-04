---
title: Elenco di controllo della distribuzione di Lync Server 2013 per le conferenze Web
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
ms.openlocfilehash: 426f6419b2127a09dd3c758cdb7d6e418e6c4fc6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762694"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-web-conferencing-in-lync-server-2013"></a>Elenco di controllo della distribuzione per i servizi di conferenza Web in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-30_

Come per la distribuzione degli altri componenti di Lync Server 2013, la distribuzione di servizi di conferenza Web richiede l'uso di generatore di topologie per creare e pubblicare una topologia che incorpora servizi di conferenza.

<div>

## <a name="deployment-sequence"></a>Sequenza di distribuzione

È possibile distribuire i servizi di conferenza contemporaneamente alla distribuzione della topologia iniziale o dopo avere distribuito almeno un pool di front-end o un server Standard Edition.

</div>

<div>

## <a name="conferencing-deployment-process"></a>Processo di distribuzione delle conferenze

La tabella seguente offre una panoramica dei passaggi necessari per distribuire i servizi di conferenza in una topologia esistente.


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
<th>Ruoli e appartenenze ai gruppi</th>
<th>Documentazione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Installare hardware e software prerequisiti</strong></p></td>
<td><p>I servizi di conferenza vengono eseguiti nei server front-end in un pool Front-end e in Server Standard Edition. Non ha requisiti hardware o software aggiuntivi oltre a ciò che è necessario per installare tali server.</p>
<div>

> [!NOTE]  
> Lync Server 2013 usa Office Web Apps e il server Office Web Apps per gestire la condivisione e il rendering delle presentazioni di PowerPoint. Per informazioni sull'installazione e la configurazione di Office Web Apps Server, vedere <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">configurazione dell'integrazione con Office Web Apps Server e Lync server 2013</A>.


</div></td>
<td><p>Utente del dominio che è membro del gruppo Administrators locale</p></td>
<td><p><a href="lync-server-2013-supported-hardware.md">Hardware supportato per Lync Server 2013</a> nella documentazione relativa alla supportabilità</p>
<p><a href="lync-server-2013-server-software-and-infrastructure-support.md">Supporto di software e infrastrutture server in Lync server 2013</a> nella documentazione relativa al supporto tecnico</p>
<p><a href="lync-server-2013-determining-your-system-requirements.md">Determinare i requisiti di sistema per Lync Server 2013</a> nella documentazione relativa alla pianificazione.</p>
<p><a href="lync-server-2013-technical-requirements-for-archiving.md">Requisiti tecnici per l'archiviazione in Lync Server 2013</a> nella documentazione relativa alla pianificazione.</p></td>
</tr>
<tr class="even">
<td><p><strong>Creare la topologia interna appropriata per supportare i servizi di conferenza</strong></p></td>
<td><p>Eseguire Generatore di topologie per aggiungere servizi di conferenza alla topologia e quindi pubblicare la topologia.</p></td>
<td><p>Per definire una topologia, un account membro del gruppo utenti locali</p>
<p>Per pubblicare la topologia, un account che sia un membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins e che disponga delle autorizzazioni controllo completo (lettura/scrittura/modifica) nella condivisione file da usare per l'archivio di file di Lync Server 2013 (in modo che il generatore di topologia possa configurare gli elenchi DACL necessari)</p></td>
<td><p><a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">Definire e configurare una topologia in Generatore di topologia per Lync Server 2013</a> nella documentazione relativa alla distribuzione.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Configurare i criteri di conferenza e il supporto</strong></p></td>
<td><p>Usare il pannello di controllo di Lync Server 2013 o Lync Server Management Shell per configurare le impostazioni di conferenza.</p></td>
<td><p>Gruppo RTCUniversalServerAdmins (solo Windows PowerShell) oppure assegna gli utenti al ruolo [] o CSAdministrator</p></td>
<td><p><a href="lync-server-2013-conferencing-policies.md">Criteri di conferenza in Lync Server 2013</a> nella documentazione Operations.</p></td>
</tr>
</tbody>
</table>


Lync Server 2013 include ora l'impostazione **MaxUploadFileSizeMb** , che limita le dimensioni dei file che è possibile caricare durante una riunione. Il valore predefinito per questa impostazione è 500 MB. Puoi modificare **MaxUploadFileSizeMb** usando il cmdlet **Set-CsConferencingConfiguration** .

**MaxUploadFileSizeMb** non limita l'impostazione di caricamento dei file per Lync Web App. Il limite di caricamento delle dimensioni dei file per Lync Web App è impostato su circa 30MB e viene controllato dal file Web. config di\[IIS\]:/DataCollabWeb/int ext/handler/Web.config. Per configurare il limite di caricamento delle dimensioni dei file per Lync Web `maxRequestLength` app `maxAllowedContentLength` , aggiornare e nel file Web. config come illustrato di seguito.

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

È necessario aggiornare il file Web. config per ogni server front-end.

</div>

</div>

<span> </span>

</div>

</div>

</div>

