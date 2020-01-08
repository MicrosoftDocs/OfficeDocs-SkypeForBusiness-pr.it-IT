---
title: Trasferire più utenti nel pool pilota
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Move multiple users to the pilot pool
ms:assetid: 9492797f-2a26-4773-8ad2-97cb53fa68fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688143(v=OCS.15)
ms:contentKeyID: 49733745
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2ffc3e01df30f4a8e1b9c9b9aeca2b2013003980
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979857"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-multiple-users-to-the-pilot-pool"></a>Trasferire più utenti nel pool pilota

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-02_

È possibile trasferire più utenti dal pool di Office Communications Server 2007 R2 al pool di piloti di Lync Server 2013 usando il pannello di controllo di Lync Server 2013 o Lync Server 2013 Management Shell.

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-control-panel"></a>Per trasferire più utenti tramite il pannello di controllo di Lync Server 2013

1.  Aprire il **Pannello di controllo di Lync Server**.

2.  Nella scheda **ricerca utente** fare clic sul pulsante **Cerca** .

3.  Fare quindi clic su **Aggiungi filtro**.

4.  Creare un filtro in cui l' **utente di Office Communications Server** è uguale a **vero**.

5.  Fare clic su **trova** per cercare gli utenti legacy di Office Communications Server 2007 R2.

6.  Selezionare due utenti che si desidera trasferire nel pool di Lync Server 2013. In questo esempio verranno spostati gli utenti Chen Yang e Claus Hansen.
    
    ![Elenco di utenti visualizzato dalla ricerca di utenti OCS](images/JJ688143.76beb4fa-72e0-41ef-b96e-3553e96645c0(OCS.15).jpg "elenco utente visualizzato dalla ricerca di utenti OCS")  

7.  Nel menu **azione** selezionare **Trasferisci utenti selezionati in pool**.

8.  Nell'elenco a discesa selezionare il pool di Lync Server 2013.

9.  Fare clic su **azione** e quindi su **Trasferisci utenti selezionati in pool**. Fare clic su OK.
    
    ![Trasferire utenti, finestra di dialogo pool di registrar di destinazione](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png ", finestra di dialogo pool Registrar di destinazione")  

10. Verificare che la colonna del **pool di registrar** per gli utenti contenga ora il pool di Lync Server 2013, che indica che gli utenti sono stati spostati correttamente.

</div>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-management-shell"></a>Per trasferire più utenti tramite Lync Server 2013 Management Shell

1.  Aprire Lync Server 2013 Management Shell.

2.  Nella riga di comando digitare le opzioni seguenti e sostituire **User1** e **User2** con nomi utente specifici che si desidera trasferire e sostituire il nome di **dominio completo del pool\_** con quello del pool di destinazione. In questo esempio verranno spostati gli utenti Hao Chen e Katie Jordan.
    
        Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsLegacyUser -Target "pool_FQDN"
    
    ![Cmdlet di esempio per trasferire]un(images/JJ688143.57cfc28e-3df5-459f-83ef-8b0edf182a25(OCS.15).jpg "cmdlet di esempio utente legacy per trasferire un utente legacy")  

3.  Nella riga di comando digitare la seguente
    
        Get-CsUser -Identity "User1"

4.  L'identità del **pool di registrazione** deve ora puntare al pool specificato come **FQDN\_del pool** nel passaggio precedente. La presenza di questa identità conferma che l'utente è stato spostato correttamente. Ripetere il passaggio per verificare che **User2** sia stato spostato.
    
    ![Output di PowerShell Get-UsUser-cmdlet Identity]-(images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "output di PowerShell Get-UsUser-cmdlet Identity")  

</div>

<div>

## <a name="to-move-all-users-at-the-same-time-by-using-the-lync-server-2013-management-shell"></a>Per trasferire tutti gli utenti contemporaneamente tramite Lync Server 2013 Management Shell

In questo esempio tutti gli utenti sono stati restituiti al pool di Office Communications Server 2007 R2 (pool01.contoso.net). Usando Lync Server 2013 Management Shell, sposteremo tutti gli utenti contemporaneamente sul pool di Lync Server 2013 (pool02.contoso.net).

1.  Aprire **Lync Server 2013 Management Shell**.

2.  Nella riga di comando digitare quanto segue:
    
        Get-CsUser -OnOfficeCommunicationServer | Move-CsLegacyUser -Target "pool_FQDN"
    
    ![Cmdlet di esempio per trasferire tutti gli utenti legacy in un](images/JJ688143.e6a2d578-296e-476c-bd45-d757917ea853(OCS.15).jpg "cmdlet di esempio di pool per trasferire tutti gli utenti legacy in un pool")  

3.  Esegui quindi **Get-CsUser** per uno degli utenti pilota.
    
        Get-CsUser -Identity "Hao Chen"

4.  L'identità del **pool di registrar** per ogni utente ora punta al pool specificato come "\_FQDN del pool" nel passaggio precedente. La presenza di questa identità conferma che l'utente è stato spostato correttamente.

5.  Inoltre, è possibile visualizzare l'elenco degli utenti nel pannello di controllo di Lync Server 2013 e verificare che il valore del pool di registrazione punti ora al pool di Lync Server 2013.
    
    ![Lync server 2013 elenco utenti del pannello di controllo]di(images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Lync Server 2013 elenco utenti del pannello di controllo")  

</div>

</div>

<span> </span>

</div>

</div>

</div>

