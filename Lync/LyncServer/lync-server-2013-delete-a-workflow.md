---
title: 'Lync Server 2013: eliminare un flusso di lavoro'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete a workflow
ms:assetid: 0469a6b8-ce1e-459b-bc3d-4c8adf2d97d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520944(v=OCS.15)
ms:contentKeyID: 48183274
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1aabb1b46d3f67408d586bada6db3d1efaf0538e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975188"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-workflow-in-lync-server-2013"></a>Eliminare un flusso di lavoro in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-11-01_

Per eliminare un flusso di lavoro, usare una delle procedure seguenti.

<div>

## <a name="to-use-lync-server-control-panel-delete-a-workflow"></a>Per usare il pannello di controllo di Lync Server eliminare un flusso di lavoro

1.  Accedere come membro del gruppo RTCUniversalServerAdmins o come membro di uno dei ruoli amministrativi predefiniti che supportano il gruppo di risposte.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Nella barra di spostamento sinistra fare clic su **gruppi di risposte**e quindi su flusso di **lavoro**.

4.  Nella pagina **flusso di lavoro** fare clic su **Crea o modifica flusso di lavoro**.

5.  Nel campo **selezionare un servizio** di ricerca digitare parte o tutto il nome del servizio **ApplicationServer** che ospita il flusso di lavoro che si desidera eliminare.

6.  Nell'elenco dei servizi fare clic sul servizio desiderato e quindi fare clic su **OK**.
    
    <div>
    

    > [!NOTE]  
    > Verrà visualizzata la pagina web strumento di configurazione Response Group. È anche possibile aprire la pagina web strumento di configurazione di Response Group direttamente da un browser tramite la <STRONG>connessione&lt;a&gt;https://webPoolFqdn/rgsconfig</STRONG>.

    
    </div>

7.  In **Gestisci un flusso di lavoro esistente**individuare il flusso di lavoro che si vuole eliminare e quindi in **azione**fare clic su **Elimina**.

8.  Fare clic su **Sì**.

</div>

<div>

## <a name="to-use-windows-powershell-to-delete-a-workflow"></a>Per usare Windows PowerShell per eliminare un flusso di lavoro

1.  Accedere come membro del gruppo RTCUniversalServerAdmins o come membro di uno dei ruoli amministrativi predefiniti che supportano il gruppo di risposte.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

3.  Nella riga di comando eseguire:
    
        Get-CsRgsWorkflow -Identity <Application Server service> -Name "<name of workflow>" | Remove-CsRgsWorkflow
    
    Ad esempio:
    
        Get-CsRgsWorkflow -Identity service:ApplicationServer:redmond.contoso.com -Name "Help Desk" | Remove-CsRgsWorkflow

</div>

</div>

<span> </span>

</div>

</div>

</div>

