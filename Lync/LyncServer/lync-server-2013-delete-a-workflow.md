---
title: 'Lync Server 2013: eliminare un flusso di lavoro'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a workflow
ms:assetid: 0469a6b8-ce1e-459b-bc3d-4c8adf2d97d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520944(v=OCS.15)
ms:contentKeyID: 48183274
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 70f2dac3aeceb2c8f6c2cbfe2d0967ac9997cd6f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154558"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-a-workflow-in-lync-server-2013"></a>Eliminare un flusso di lavoro in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-11-01_

Utilizzare una delle procedure seguenti per eliminare un flusso di lavoro.

<div>

## <a name="to-use-lync-server-control-panel-delete-a-workflow"></a>Per utilizzare il pannello di controllo di Lync Server eliminare un flusso di lavoro

1.  Accedere come membro del gruppo RTCUniversalServerAdmins oppure come membro di uno dei ruoli amministrativi predefiniti che supportano Response Group.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **Response Group** e quindi su **Flusso di lavoro**.

4.  Nella pagina **Flusso di lavoro** fare clic su **Crea o modifica un flusso di lavoro**.

5.  Nel campo di ricerca **Seleziona un servizio** digitare parte o tutto il nome del servizio **ApplicationServer** in cui è ospitato il flusso di lavoro che si desidera eliminare.

6.  Nell'elenco dei servizi fare clic sul servizio desiderato, quindi fare clic su **OK**.
    
    <div>
    

    > [!NOTE]  
    > Verrà visualizzata la pagina Web dello strumento di configurazione di Response Group. È inoltre possibile aprire la pagina Web dello strumento di configurazione di Response Group direttamente da un browser tramite la connessione a <STRONG>&lt;https://FQDNpoolWeb&gt;/rgsconfig</STRONG>.

    
    </div>

7.  In **Gestisci un flusso di lavoro esistente** individuare il flusso di lavoro da eliminare e quindi in **Azione** fare clic su **Elimina**.

8.  Fare clic su **Sì**.

</div>

<div>

## <a name="to-use-windows-powershell-to-delete-a-workflow"></a>Per utilizzare Windows PowerShell per eliminare un flusso di lavoro

1.  Accedere come membro del gruppo RTCUniversalServerAdmins oppure come membro di uno dei ruoli amministrativi predefiniti che supportano Response Group.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

3.  Nella riga di comando digitare il comando seguente:
    
        Get-CsRgsWorkflow -Identity <Application Server service> -Name "<name of workflow>" | Remove-CsRgsWorkflow
    
    Ad esempio:
    
        Get-CsRgsWorkflow -Identity service:ApplicationServer:redmond.contoso.com -Name "Help Desk" | Remove-CsRgsWorkflow

</div>

</div>

<span> </span>

</div>

</div>

</div>

