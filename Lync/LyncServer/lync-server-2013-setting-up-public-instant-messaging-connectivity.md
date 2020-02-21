---
title: 'Lync Server 2013: configurazione della connettività per la messaggistica istantanea pubblica'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up public instant messaging connectivity
ms:assetid: 816dea2a-96fa-4a36-b6c2-a9402675868b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205041(v=OCS.15)
ms:contentKeyID: 48184661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e4b3efe4e5d8e5cb84631969205842e56024394c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200542"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-public-instant-messaging-connectivity-in-lync-server-2013"></a>Configurazione della connettività per la messaggistica istantanea pubblica in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-08_

Se l'organizzazione desidera supportare la connettività di messaggistica istantanea pubblica con AOL, non è possibile utilizzare la Distribuzione guidata di Lync Server per richiedere il certificato. Eseguire le operazioni della procedura seguente.

<div>

## <a name="setting-up-public-instant-messaging-connectivity"></a>Configurazione della connettività di messaggistica istantanea pubblica

1.  In un Front End server, aprire Generatore di topologie. Espandere Edge pool, quindi fare clic con il tasto destro del mouse su Server perimetrale o Pool di server perimetrali. or Edge server pool. Scegliere Modifica proprietà.

2.  In Modifica Proprietà, sotto Generale, selezionare Abilita federazione per pool di server perimetrali (porta 5061). Fare clic su OK.

3.  Fare clic su Azione, selezionare Topologia, selezionare Pubblica. Quando viene richiesto di pubblicare la topologia, fare clic su Avanti. Quando la pubblicazione è terminata, fare clic su Fine.

4.  Nel server perimetrale, aprire la Distribuzione guidata di Lync Server. Fare clic su Installa o aggiorna il sistema Lync Server, quindi fare clic su Installazione o rimozione componenti di Lync Server.

5.  In Installazione componenti di Lync Server fare clic su Avanti. Nella schermata di riepilogo sono mostrate le azioni che vengono eseguite. Al termine della distribuzione, fare clic su Visualizza log per visualizzare i file di log disponibili. Fare clic su Fine per completare la distribuzione.

</div>

<div>

## <a name="to-create-a-certificate-request-for-the-external-interface-of-the-edge-server-to-support-public-im-connectivity-with-aol"></a>Per creare una richiesta di certificato per l'interfaccia esterna del server perimetrale per il supporto della connettività di messaggistica istantanea pubblica con AOL

1.  Quando il modello richiesto è disponibile per la CA, utilizzare il cmdlet di Windows PowerShell seguente dal server perimetrale per richiedere il certificato:
    
        Request-CsCertificate -New -Type AccessEdgeExternal  -Output C:\ <certfilename.txt or certfilename.csr>  -ClientEku $true -Template <template name>
    
    Il nome del certificato predefinito del modello utilizzato per Lync Server è il server Web. Specificare il nome \<\> del modello solo se è necessario utilizzare un modello diverso dal modello predefinito.
    
    <div>
    

    > [!IMPORTANT]  
    > Se l'organizzazione desidera supportare la connettività di messaggistica istantanea pubblica con AOL, è necessario utilizzare Windows PowerShell anziché la procedura guidata per richiedere il certificato da assegnare al server perimetrale esterno per il servizio Access Edge. Il motivo è che il modello Web Server dell'Autorità di certificazione utilizzato dalla Configurazione guidata certificato per richiedere un certificato non supporta la configurazione dell'utilizzo chiavi avanzato (EKU) client. Prima di utilizzare Windows PowerShell per creare il certificato, l'amministratore della CA deve creare e distribuire un nuovo modello che supporti l'EKU client.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

