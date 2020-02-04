---
title: Trasferire un singolo utente nel pool pilota
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Move a single user to the pilot pool
ms:assetid: e9de81a8-40dd-4446-81e7-a2b810eaea50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205401(v=OCS.15)
ms:contentKeyID: 48185905
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c14c4a772ced3939d979bd8d4cd053207b0c5613
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765304"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-a-single-user-to-the-pilot-pool"></a>Trasferire un singolo utente nel pool pilota

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-26_

È possibile trasferire un utente dal pool di Lync Server 2010 al pool di piloti di Lync Server 2013 usando il pannello di controllo di Lync Server 2013 o Lync Server 2013 Management Shell. Nell'esempio seguente, nella colonna del pool di registrazione, **pool01.contoso.NET** è il pool di Lync Server 2010 e tutti e sei questi utenti sono connessi al pool. Usare le procedure seguenti per trasferire un utente nel pool di Lync Server 2013 tramite il pannello di controllo di Lync Server 2013 e Lync Server Management Shell.

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-control-panel"></a>Per trasferire un utente tramite il pannello di controllo di Lync Server 2013

**Elenco di utenti nel pannello di controllo di Lync Server 2013**

![Pannello di controllo di Lync Server - Finestra di dialogo Spostare un utente](images/JJ721870.a2bce284-0392-4db3-9bb2-9f12699738e7(OCS.15).jpg "Pannello di controllo di Lync Server - Finestra di dialogo Spostare un utente")

1.  Accedere al server front-end con un account che sia un membro del gruppo RTCUniversalServerAdmins o un membro del ruolo di amministratore di CsAdministrator o CsUserAdministrator.

2.  Aprire il **Pannello di controllo di Lync Server**.

3.  Fare clic su **utenti**, fare clic su Cerca e quindi su **trova**.

4.  Selezionare un utente che si vuole trasferire nel pool di Lync Server 2013. In questo esempio si sposterà l'utente Sara Davis.

5.  Nel menu **azione** selezionare **Trasferisci utenti selezionati in pool**.

6.  Nell'elenco a discesa selezionare il pool di Lync Server 2013.

7.  Fare clic su **azione** e quindi su **Trasferisci utenti selezionati in pool**. Fare clic su **OK**.
    
    ![Finestra di dialogo per lo spostamento di utenti nel pool di registrazione di destinazione](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Finestra di dialogo per lo spostamento di utenti nel pool di registrazione di destinazione")  

8.  Verificare che la colonna del **pool di registrar** per l'utente contenga ora il pool di Lync Server 2013, che indica che l'utente è stato spostato correttamente.

</div>

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-management-shell"></a>Per trasferire un utente tramite Lync Server 2013 Management Shell

1.  Aprire Lync Server Management Shell.

2.  Nella riga di comando digitare quanto segue:
    
        Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"

3.  Nella riga di comando, quindi, digitare quanto segue:
    
        Get-CsUser -Identity "David Pelton"

4.  L'identità **RegistrarPool** punta ora sul pool di Lync Server 2013. La presenza di questa identità conferma che l'utente è stato spostato correttamente.
    
    ![Output del cmdlet Get-CsUser con filtro Identity](images/JJ205401.bc5d4672-8068-4475-b882-dbd305c801a9(OCS.15).jpg "Output del cmdlet Get-CsUser con filtro Identity")  
    
    <div>
    

    > [!NOTE]  
    > Per informazioni dettagliate sul cmdlet <STRONG>Get-CsUser</STRONG> , eseguire: <STRONG>Get-Help Get-CsUser-detailed</STRONG>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

