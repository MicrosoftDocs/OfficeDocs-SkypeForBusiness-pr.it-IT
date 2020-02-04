---
title: 'Lync Server 2013: Configurazione della connettività per la messaggistica istantanea pubblica'
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
ms.openlocfilehash: 871f513170fcb0491f6732751cfc1b23877526b8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732256"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-public-instant-messaging-connectivity-in-lync-server-2013"></a>Configurazione della connettività per la messaggistica istantanea pubblica in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-08_

Se l'organizzazione vuole supportare la connettività di messaggistica istantanea pubblica con AOL, non è possibile usare la distribuzione guidata di Lync Server per richiedere il certificato. Eseguire invece i passaggi descritti nella procedura seguente.

<div>

## <a name="setting-up-public-instant-messaging-connectivity"></a>Configurazione della connettività di messaggistica istantanea pubblica

1.  In un server front-end aprire Generatore di topologia. Espandere pool di bordi e quindi fare clic con il pulsante destro del mouse sull'Edge Server o sul pool Edge Server. Selezionare Modifica proprietà.

2.  In modifica proprietà in generale selezionare Abilita federazione per questo pool di bordi (porta 5061). Fare clic su OK.

3.  Fare clic su azione, selezionare topologia, quindi pubblica. Quando viene richiesto di pubblicare la topologia, fare clic su Avanti. Al termine della pubblicazione, fare clic su fine.

4.  Nell'Edge Server aprire la distribuzione guidata di Lync Server. Fare clic su Installa o aggiorna Lync Server System, quindi fare clic su Imposta o Rimuovi componenti di Lync Server. Fare di nuovo clic su Esegui.

5.  In configurazione componenti di Lync Server fare clic su Avanti. La schermata di riepilogo mostrerà le azioni Man mano che vengono eseguite. Dopo aver completato la distribuzione, fare clic su Visualizza log per visualizzare i file di log disponibili. Fare clic su fine per completare la distribuzione.

</div>

<div>

## <a name="to-create-a-certificate-request-for-the-external-interface-of-the-edge-server-to-support-public-im-connectivity-with-aol"></a>Per creare una richiesta di certificato per l'interfaccia esterna di Edge Server per supportare la connettività di messaggistica istantanea pubblica con AOL

1.  Quando il modello richiesto è disponibile per la CA, usare il cmdlet di Windows PowerShell seguente da su Edge Server per richiedere il certificato
    
        Request-CsCertificate -New -Type AccessEdgeExternal  -Output C:\ <certfilename.txt or certfilename.csr>  -ClientEku $true -Template <template name>
    
    Il nome del certificato predefinito del modello usato per Lync Server è Web Server. Specifica il nome \<\> del modello solo se devi usare un modello diverso dal modello predefinito.
    
    <div>
    

    > [!IMPORTANT]  
    > Se l'organizzazione vuole supportare la connettività di messaggistica istantanea pubblica con AOL, è necessario usare Windows PowerShell invece della procedura guidata certificato per richiedere che il certificato venga assegnato al bordo esterno per il servizio Access Edge. Questo avviene perché il modello di server Web dell'autorità di certificazione (CA) che la creazione guidata certificato usa per richiedere un certificato non supporta la configurazione EKU client. Prima di usare Windows PowerShell per creare il certificato, l'amministratore della CA deve creare e distribuire un nuovo modello che supporti EKU client.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

