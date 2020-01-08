---
title: 'Lync Server 2013: Esecuzione della preparazione della foresta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Running forest preparation
ms:assetid: 9d62f7be-bcfe-421d-8d8a-225567102a35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412732(v=OCS.15)
ms:contentKeyID: 48184991
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b011623b9091c1c707ae77381dacb99ba4642a21
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981375"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="running-forest-preparation-for-lync-server-2013"></a>Esecuzione della preparazione della foresta per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-29_

È possibile usare i cmdlet setup o Lync Server Management Shell per preparare la foresta. Il cmdlet che prepara la foresta è **Enable-CsAdForest**.

Dopo aver preparato la foresta, è necessario verificare che le impostazioni globali siano state replicate prima di eseguire la preparazione del dominio.

<div>

## <a name="to-use-setup-to-prepare-the-forest"></a>Per usare la configurazione per preparare la foresta

1.  Accedere a un computer collegato a un dominio come membro del gruppo amministratori aziendali per il dominio radice della foresta.

2.  Nella cartella di installazione o nel supporto di Lync Server 2013 eseguire Setup. exe per avviare la distribuzione guidata.

3.  Fare clic su **Prepara Active Directory** e quindi attendere che venga determinato lo stato della distribuzione.

4.  Al **passaggio 3: preparare la foresta corrente**, fare clic su **Esegui**.

5.  Nella pagina **Preparazione foresta** fare clic su **Avanti**.
    
    <div>
    

    > [!NOTE]  
    > La preparazione della foresta consente di scegliere dove posizionare i gruppi universali per Lync Server 2013. Scegliere una posizione conforme ai requisiti dell'organizzazione.

    
    </div>

6.  Nella pagina **Esecuzione comandi in corso** ricercare **Stato attività: Operazione completata** e quindi fare clic su **Visualizza registro**.

7.  Nella colonna **Action** espandere **Forest Prep**cercare un ** \<\> ** risultato di esecuzione di successo alla fine di ogni attività per verificare che la preparazione della foresta sia stata completata correttamente, chiudere il log e quindi fare clic su **fine**.

8.  Attendere il completamento della replica di Active Directory oppure forzare la replica a tutti i controller di dominio elencati nello snap-in **siti e servizi di Active Directory** per il controller di dominio radice della foresta, prima di eseguire la preparazione del dominio. Forzare la replica tra i controller di dominio in tutti i siti di Active Directory per provocare la replica nei siti in pochi minuti.

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-forest"></a>Per usare i cmdlet per preparare la foresta

1.  Accedere a un computer collegato a un dominio come membro del gruppo Domain Admins nel dominio radice della foresta.

2.  Installare i componenti di base di Lync Server nel modo seguente:
    
    1.  Nella cartella di installazione o nel supporto di Lync Server 2013 eseguire Setup. exe per avviare la distribuzione guidata di Lync Server.
    
    2.  Se viene richiesto di installare Microsoft Visual C++ ridistribuibile, fare clic su **Sì**.
    
    3.  Nella finestra di dialogo configurazione di Lync Server 2013 viene richiesto di installare i file di Lync Server. Scegliere il percorso predefinito o **passare** a una posizione a scelta e quindi fare clic su **Installa**.
    
    4.  Nella pagina Contratto di licenza selezionare **Accetto i termini del contratto di licenza**e quindi fare clic su **OK**. Il programma di installazione installa i componenti principali di Lync Server 2013.

3.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

4.  Eseguire
    
        Enable-CsAdForest [-GroupDomain <FQDN of the domain in which to create the universal groups>]
    
    Ad esempio:
    
        Enable-CsAdForest -GroupDomain domain1.contoso.com 
    
    Se non specifichi il parametro GroupDomain, il valore predefinito è il dominio locale. Se i gruppi universali sono stati creati in precedenza in un dominio che non è il dominio predefinito, è necessario specificare in modo esplicito il parametro GroupDomain.

5.  Attendere il completamento della replica di Active Directory oppure forzare la replica a tutti i controller di dominio elencati nello snap-in **siti e servizi di Active Directory** per il controller di dominio radice della foresta, prima di eseguire la preparazione del dominio.

6.  Verificare che la preparazione della foresta sia riuscita. Eseguire
    
        Get-CsAdForest 
    
    Questo cmdlet restituisce il valore di **LC\_FORESTSETTINGS\_stato\_pronto** se la preparazione della foresta è riuscita.

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

