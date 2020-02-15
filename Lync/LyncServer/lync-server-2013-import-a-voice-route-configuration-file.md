---
title: 'Lync Server 2013: importazione di un file di configurazione di route vocali'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Import a voice route configuration file
ms:assetid: 4bac05e5-ed8b-4f10-96b0-b8a65ff356ec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398301(v=OCS.15)
ms:contentKeyID: 48184049
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1ce270b4321c484b40a20271ad21c2701c749d6a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038738"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="import-a-voice-route-configuration-file-in-lync-server-2013"></a>Importare un file di configurazione di route vocali in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-11-01_

Se si desidera salvare la configurazione del routing vocale senza pubblicarla, eseguire la procedura seguente per utilizzare i comandi di esportazione e importazione della configurazione del pannello di controllo di Lync Server per salvare e recuperare uno snapshot della configurazione del routing vocale. Quando si importa un file di configurazione per il routing vocale (con estensione vcfg), ma nel frattempo sono state apportate modifiche alla configurazione del routing vocale nel server, le pagine del gruppo di **routing vocale** nel pannello di controllo di Lync Server indicheranno che sono state apportate modifiche non salvate al routing vocale. Tali modifiche costituiscono le differenze tra le due configurazioni di cui deve essere eseguita la riconciliazione.

Se sono state apportate modifiche non salvate alle impostazioni in una pagina all'interno del gruppo, le modifiche vengono salvate nel file di configurazione vocale esportato (con estensione vcfg). In questo modo è possibile apportare modifiche alla configurazione del routing vocale durante più sessioni prima di pubblicare le modifiche.

<div>

## <a name="to-import-a-voice-routing-configuration"></a>Per importare una configurazione di routing vocale

1.  Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Per informazioni dettagliate, vedere [delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **Routing vocale**.

4.  Scegliere **Importa configurazione** dal menu **Azioni**.

5.  Trovare il file di configurazione che si desidera importare e quindi fare clic su **Apri**.

6.  Fare clic su **Commit** e quindi su **Salva tutto**.
    
    <div>
    

    > [!NOTE]  
    > Ogni volta che si importa un file di configurazione vocale, è necessario usare il comando <STRONG>Salva tutto</STRONG> per pubblicare la modifica di configurazione. Per ulteriori informazioni, vedere <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">pubblicare le modifiche in sospeso alla configurazione del routing vocale in Lync Server 2013</A> nella documentazione relativa alle operazioni.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Esportare un file di configurazione di route vocali in Lync Server 2013](lync-server-2013-export-a-voice-route-configuration-file.md)  
[Pubblicare le modifiche in sospeso alla configurazione del routing vocale in Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

