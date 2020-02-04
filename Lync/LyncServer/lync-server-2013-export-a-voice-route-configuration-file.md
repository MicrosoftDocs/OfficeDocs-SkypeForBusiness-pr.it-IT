---
title: 'Lync Server 2013: esportare un file di configurazione della route vocale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Export a voice route configuration file
ms:assetid: 02ce922d-9ca8-4513-b09f-9de51f5c5bdc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398081(v=OCS.15)
ms:contentKeyID: 48183248
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 55ecc35d2724fa8c635b9d4099764c25e76874c9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756230"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="export-a-voice-route-configuration-file-in-lync-server-2013"></a>Esportare un file di configurazione della route vocale in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-11-01_

Se si vuole salvare la configurazione del routing vocale senza pubblicarla, seguire questa procedura per usare i comandi di esportazione e importazione della configurazione del pannello di controllo di Lync Server per salvare e recuperare uno snapshot della configurazione del routing vocale. Quando si importa un file di configurazione del routing vocale (con estensione vcfg), ma nel frattempo sono state apportate modifiche alla configurazione del routing vocale nel server, le pagine del gruppo **routing vocale** nel pannello di controllo di Lync Server indicheranno che non sono state salvate modifiche al routing vocale. Le modifiche non salvate sono le differenze tra le due configurazioni che richiedono la riconciliazione.

Se sono state apportate modifiche non salvate alle impostazioni di una pagina all'interno del gruppo, le modifiche vengono salvate nel file di configurazione vocale esportato (. vcfg). In questo modo è possibile apportare modifiche alla configurazione del routing vocale durante più sessioni prima di pubblicare le modifiche.

<div>

## <a name="to-export-a-voice-routing-configuration"></a>Per esportare una configurazione di routing vocale

1.  Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo di CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Per informazioni dettagliate, vedere [delegare le autorizzazioni di configurazione in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **routing vocale**.

4.  Nel menu **azioni** fare clic su **Esporta configurazione**.

5.  Specificare un percorso e un nome file e quindi fare clic su **Salva**.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Importare un file di configurazione di route vocali in Lync Server 2013](lync-server-2013-import-a-voice-route-configuration-file.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

