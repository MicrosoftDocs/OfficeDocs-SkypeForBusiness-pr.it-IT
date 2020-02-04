---
title: Trasferire un singolo utente nel pool pilota
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Move a single user to the pilot pool
ms:assetid: 80d5b365-f153-4c61-a148-f9e18ce6e027
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688109(v=OCS.15)
ms:contentKeyID: 49733708
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e8cb89fde2a62858c3bd9a402207f4b23fd51643
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756050"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-a-single-user-to-the-pilot-pool"></a>Trasferire un singolo utente nel pool pilota

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-28_

È possibile trasferire un utente dal pool di Office Communications Server 2007 R2 al pool di piloti di Lync Server 2013 usando il pannello di controllo di Lync Server 2013 o Lync Server 2013 Management Shell. Nell'esempio seguente, nella colonna del pool di registrazione, ** \<Office Communications Server\> ** è il pool di Office Communications Server 2007 R2 e tutti e sei gli utenti sono connessi al pool. Usare le procedure seguenti per trasferire un utente nel pool di Lync Server 2013 tramite il pannello di controllo di Lync Server 2013 e Lync Server Management Shell.

![Ricerca di utenti OCS nel Pannello di controllo di Lync Server](images/JJ688109.d2008fd6-868b-4f26-84cf-57bb69e073d3(OCS.15).jpg "Ricerca di utenti OCS nel Pannello di controllo di Lync Server")

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-control-panel"></a>Per trasferire un utente tramite il pannello di controllo di Lync Server 2013

1.  Accedere al server front-end con un account che sia un membro del gruppo RTCUniversalServerAdmins o un membro del ruolo di amministratore di CsAdministrator o CsUserAdministrator.

2.  Aprire il pannello di controllo di Lync Server.

3.  Fare clic su **utenti**.

4.  Nella scheda **ricerca utente** fare clic sul pulsante **Cerca** .

5.  Fare quindi clic su **Aggiungi filtro**.

6.  Creare un filtro in cui l' **utente di Office Communications Server** è uguale a **vero**.

7.  Fare clic su **trova** per cercare gli utenti legacy di Office Communications Server 2007 R2.
    
    ![Ricerca di utenti OCS nel Pannello di controllo di Lync Server](images/JJ688109.09528349-7915-41e1-91b4-6ab5c12b1b38(OCS.15).jpg "Ricerca di utenti OCS nel Pannello di controllo di Lync Server")  

8.  Selezionare un utente che si vuole trasferire nel pool di Lync Server 2013. In questo esempio si sposterà l'utente Sara Davis.

9.  Nel menu **azione** selezionare **Trasferisci utenti selezionati in pool**.

10. Nell'elenco a discesa selezionare il pool di Lync Server 2013.

11. Fare clic su **azione** e quindi su **Trasferisci utenti selezionati in pool**. Fare clic su **OK**.
    
    ![Impostazione del pool di destinazione nella finestra di dialogo Sposta utenti](images/JJ688109.d7dc0759-87c5-4c23-938f-361576621504(OCS.15).jpg "Impostazione del pool di destinazione nella finestra di dialogo Sposta utenti")  

12. Verificare che la colonna del **pool di registrar** per l'utente contenga ora il pool di Lync Server 2013, che indica che l'utente è stato spostato correttamente

</div>

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-management-shell"></a>Per trasferire un utente tramite Lync Server 2013 Management Shell

1.  Aprire Lync Server Management Shell.

2.  Nella riga di comando digitare quanto segue:
    
        Move-CsLegacyUser -Identity "David Pelton" -Target "pool02.contoso.net"

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

