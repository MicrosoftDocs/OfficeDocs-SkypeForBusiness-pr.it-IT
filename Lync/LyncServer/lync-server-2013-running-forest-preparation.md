---
title: 'Lync Server 2013: esecuzione della preparazione della foresta'
description: 'Lync Server 2013: esecuzione della preparazione della foresta.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Running forest preparation
ms:assetid: 9d62f7be-bcfe-421d-8d8a-225567102a35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412732(v=OCS.15)
ms:contentKeyID: 48184991
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ad3ef2d7583d541701d6606946ca1df1bbd8cf23
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577762"
---
# <a name="running-forest-preparation-for-lync-server-2013"></a>Esecuzione della preparazione della foresta per Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-29_

È possibile utilizzare i cmdlet setup o Lync Server Management Shell per preparare la foresta. Il cmdlet che prepara la foresta è **Enable-CsAdForest**.

Dopo aver preparato la foresta, è necessario verificare che le impostazioni globali siano state replicate prima di eseguire la preparazione del dominio.

<div>

## <a name="to-use-setup-to-prepare-the-forest"></a>Per utilizzare il programma di installazione per preparare la foresta

1.  Accedere a un computer aggiunto a un dominio come membro del gruppo Enterprise Admins per il dominio radice della foresta.

2.  Dalla cartella o dal supporto di installazione di Lync Server 2013, eseguire Setup.exe per avviare la distribuzione guidata.

3.  Fare clic su **Prepara Active Directory** e quindi attendere che venga determinato lo stato della distribuzione.

4.  Al **passaggio 3: preparare la foresta corrente**, fare clic su **Esegui**.

5.  Nella pagina **Prepara foresta** fare clic su **Avanti**.
    
    <div>
    

    > [!NOTE]  
    > La preparazione della foresta consente di scegliere dove collocare i gruppi universali per Lync Server 2013. Selezionare una posizione coerente con i requisiti dell'organizzazione.

    
    </div>

6.  Nella pagina **Esecuzione comandi in corso** ricercare **Stato attività: Operazione completata** e quindi fare clic su **Visualizza registro**.

7.  Nella colonna **azione** espandere **Preparazione foresta**, cercare il **\<Success\>** risultato dell'esecuzione alla fine di ogni attività per verificare che la preparazione della foresta sia stata completata correttamente, chiudere il registro e quindi fare clic su **fine**.

8.  Attendere il completamento della replica di Active Directory oppure forzare la replica in tutti i controller di dominio elencati nello snap-in **Siti e servizi di Active Directory** per il controller di dominio della radice della foresta prima di eseguire la preparazione del dominio. Forzare la replica tra i controller di dominio in tutti i siti di Active Directory perché la replica all'interno dei siti venga eseguita entro pochi minuti.

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-forest"></a>Per utilizzare i cmdlet per la preparazione della foresta

1.  Accedere a un computer che fa parte di un dominio come membro del gruppo Domain Admins nel dominio radice della foresta.

2.  Installare i componenti di base di Lync Server come indicato di seguito:
    
    1.  Dalla cartella o dal supporto di installazione di Lync Server 2013, eseguire Setup.exe per avviare la distribuzione guidata di Lync Server.
    
    2.  Se viene chiesto di installare Microsoft Visual C++ Redistributable, fare clic su **Sì**.
    
    3.  Nella finestra di dialogo installazione di Lync Server 2013 viene visualizzata una richiesta di installazione dei file di Lync Server. Scegliere il percorso predefinito o **Sfoglia** per selezionare il percorso desiderato e quindi fare clic su **Installa**.
    
    4.  Nella pagina Contratto di Licenza selezionare **Accetto i termini del Contratto di Licenza** e quindi fare clic su **OK**. Il programma di installazione installa i componenti di base di Lync Server 2013.

3.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

4.  Eseguire: 
    
        Enable-CsAdForest [-GroupDomain <FQDN of the domain in which to create the universal groups>]
    
    Ad esempio:
    
        Enable-CsAdForest -GroupDomain domain1.contoso.com 
    
    Se non si specifica il parametro GroupDomain, il valore predefinito è il dominio locale. Se i gruppi universali sono stati creati in precedenza in un dominio che non è quello predefinito, è necessario specificare il parametro GroupDomain in modo esplicito.

5.  Attendere il completamento della replica di Active Directory oppure forzare la replica in tutti i controller di dominio elencati nello snap-in **Siti e servizi di Active Directory** per il controller del dominio radice della foresta, prima di eseguire la preparazione del dominio.

6.  Verificare che la preparazione della foresta abbia avuto esito positivo. Eseguire: 
    
        Get-CsAdForest 
    
    Questo cmdlet restituisce un valore di ** \_ stato LC \_ FORESTSETTINGS \_ pronto** se la preparazione della foresta ha avuto esito positivo.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Utilizzo dei cmdlet per annullare la preparazione della foresta per Lync Server 2013](lync-server-2013-using-cmdlets-to-reverse-forest-preparation.md)  


[Preparazione della foresta per Lync Server 2013](lync-server-2013-preparing-the-forest.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

