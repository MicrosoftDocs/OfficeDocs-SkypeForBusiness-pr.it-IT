---
title: 'Lync Server 2013: Esecuzione della preparazione dello schema'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Running schema preparation
ms:assetid: 9d02bdb1-ff29-417a-bcce-b068b31207d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412729(v=OCS.15)
ms:contentKeyID: 48184911
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4b743e5ef93b14279f5f2f16cb70241617a0c8f0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981408"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="running-active-directory-schema-preparation-in-lync-server-2013"></a>Esecuzione della preparazione dello schema in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-29_

È possibile usare i cmdlet setup o Lync Server Management Shell per preparare lo schema Active Directory. Il cmdlet che estende lo schema di Active Directory è **Install-CsAdServerSchema**.

<div>


> [!NOTE]  
> Il cmdlet di preparazione dello schema (<STRONG>Install-CsAdServerSchema</STRONG>) deve accedere al master schema, che richiede che il servizio Registro di sistema remoto sia in uso e che la chiave del registro di sistema remota sia abilitata. Se il servizio Registro di sistema remoto non può essere abilitato nello schema master, è possibile eseguire il cmdlet localmente nello schema master. Per informazioni dettagliate sull'accesso remoto del registro di sistema, vedere l'articolo 314837 della Microsoft Knowledge Base "come gestire l'accesso remoto al <A href="http://go.microsoft.com/fwlink/p/?linkid=125769">http://go.microsoft.com/fwlink/p/?linkId=125769</A>registro di sistema".



</div>

Dopo aver completato la preparazione dello schema, verificare manualmente che la partizione dello schema sia stata replicata prima di procedere con la preparazione della foresta. Per informazioni dettagliate, vedere [Verifica della replica dello schema di Active Directory in Lync Server 2013](lync-server-2013-verifying-schema-replication.md).

<div>

## <a name="to-use-setup-to-prepare-the-schema-of-the-current-forest"></a>Per usare la configurazione per preparare lo schema della foresta corrente

1.  Accedere a un server della foresta come membro del gruppo amministratori schema e con i diritti di amministratore dello schema.

2.  Nella cartella di installazione o nel supporto di Lync Server 2013 eseguire Setup. exe per avviare la distribuzione guidata.

3.  Se viene richiesto di installare Microsoft Visual C++ ridistribuibile, fare clic su **Sì**.

4.  Nella finestra di dialogo configurazione di Lync Server 2013 viene richiesto di installare i file di Lync Server. Scegliere il percorso predefinito o **passare** a una posizione a scelta e quindi fare clic su **Installa**.

5.  Nella pagina Contratto di licenza selezionare **Accetto i termini del contratto di licenza**e quindi fare clic su **OK**.

6.  Il programma di installazione installa i componenti principali di Lync Server.

7.  Quando la distribuzione guidata è pronta, fare clic su **prepara Active Directory**e quindi attendere che venga determinato lo stato di distribuzione.

8.  Al **passaggio 1: preparare lo schema**, fare clic su **Esegui**.

9.  Nella pagina **Prepara schema** fare clic su **Avanti**.

10. Nella pagina **Esecuzione comandi in corso** cercare il messaggio **Stato attività: Completata** e quindi fare clic su **Visualizza registro**.

11. Nella colonna **azione** espandere **schema Prep**, cercare il ** \<\> ** risultato dell'esecuzione di successo alla fine di ogni attività per verificare che la preparazione dello schema sia stata completata correttamente, chiudere il log e quindi fare clic su **fine**.

12. Attendere che la replica di Active Directory completi o forzi la replica.

13. Verificare manualmente che lo schema cambi replicato in tutti gli altri controller di dominio. Per informazioni dettagliate, vedere [Verifica della replica dello schema di Active Directory in Lync Server 2013](lync-server-2013-verifying-schema-replication.md).

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-schema-of-the-current-forest"></a>Per usare i cmdlet per preparare lo schema della foresta corrente

1.  Accedere a un computer della foresta come membro del gruppo amministratori schema e con i diritti di amministratore dello schema.

2.  Installare i componenti di base di Lync Server nel modo seguente:
    
    1.  Nella cartella di installazione o nel supporto di Lync Server 2013 eseguire Setup. exe per avviare la distribuzione guidata di Lync Server.
    
    2.  Se viene richiesto di installare Microsoft Visual C++ ridistribuibile, fare clic su **Sì**.
    
    3.  Nella finestra di dialogo configurazione di Lync Server 2013 viene richiesto di installare i file di Lync Server. Scegliere il percorso predefinito o **passare** a una posizione a scelta e quindi fare clic su **Installa**.
    
    4.  Nella pagina Contratto di licenza selezionare **Accetto i termini del contratto di licenza**e quindi fare clic su **OK**. Il programma di installazione installa i componenti principali di Lync Server 2013.

3.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

4.  Eseguire
    
        Install-CsAdServerSchema [-Ldf <directory where the .ldf file is located>] 
    
    Se non specifichi il parametro ldf, il valore predefinito è il percorso di installazione di Lync Server 2013 che viene letto dal registro di sistema.
    
    Ad esempio:
    
        Install-CsAdServerSchema -Ldf "C:\Program Files\Microsoft Lync Server 2013\Deployment\Setup"

5.  Usa il cmdlet seguente per verificare che la preparazione dello schema sia stata eseguita fino al completamento.
    
        Get-CsAdServerSchema 
    
    Questo cmdlet restituisce un valore di **stato\_\_della\_versione dello schema corrente** se la preparazione dello schema ha avuto esito positivo.

6.  Attendere che la replica di Active Directory completi o forzi la replica.

7.  Verificare manualmente che lo schema cambi replicato in tutti gli altri controller di dominio. Per informazioni dettagliate, vedere [Verifica della replica dello schema di Active Directory in Lync Server 2013](lync-server-2013-verifying-schema-replication.md).

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Verifica della replica dello schema in Lync Server 2013](lync-server-2013-verifying-schema-replication.md)  


[Preparazione dello schema di Active Directory in Lync Server 2013](lync-server-2013-preparing-the-active-directory-schema.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

