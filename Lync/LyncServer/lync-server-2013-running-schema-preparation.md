---
title: 'Lync Server 2013: esecuzione della preparazione dello schema'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Running schema preparation
ms:assetid: 9d02bdb1-ff29-417a-bcce-b068b31207d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412729(v=OCS.15)
ms:contentKeyID: 48184911
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 202052ce01bca6cdc11e8ed36dfede9afba74b8d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511103"
---
# <a name="running-active-directory-schema-preparation-in-lync-server-2013"></a>Esecuzione della preparazione dello schema di Active Directory in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-29_

È possibile utilizzare i cmdlet setup o Lync Server Management Shell per preparare lo schema di Active Directory. Il cmdlet che estende lo schema di Active Directory è **Install-CsAdServerSchema**.

<div>


> [!NOTE]  
> Il cmdlet di preparazione dello schema (<STRONG>Install-CsAdServerSchema</STRONG>) deve accedere al master dello schema, che richiede che il servizio Registro di sistema remoto sia in esecuzione e che la chiave del registro di sistema remota sia abilitata. Se il servizio Registro di sistema remoto non può essere abilitato sul master schema, è possibile eseguire il cmdlet localmente nel master schema. Per informazioni dettagliate sull'accesso remoto al registro di sistema, vedere l'articolo 314837 della Microsoft Knowledge Base "come gestire l'accesso remoto al registro di sistema" all'indirizzo <A href="https://go.microsoft.com/fwlink/p/?linkid=125769">https://go.microsoft.com/fwlink/p/?linkId=125769</A> .



</div>

Dopo aver completato la preparazione dello schema, verificare manualmente che la partizione dello schema sia stata replicata prima di procedere alla preparazione della foresta. Per informazioni dettagliate, vedere [Verifying Active Directory schema Replication in Lync Server 2013](lync-server-2013-verifying-schema-replication.md).

<div>

## <a name="to-use-setup-to-prepare-the-schema-of-the-current-forest"></a>Per utilizzare il programma di installazione per preparare lo schema della foresta corrente

1.  Accedere a un server nella foresta come membro del gruppo Schema Admins e con diritti di amministratore per il master schema.

2.  Dalla cartella o dal supporto di installazione di Lync Server 2013, eseguire Setup.exe per avviare la distribuzione guidata.

3.  Se viene chiesto di installare Microsoft Visual C++ Redistributable, fare clic su **Sì**.

4.  Nella finestra di dialogo installazione di Lync Server 2013 viene visualizzata una richiesta di installazione dei file di Lync Server. Scegliere il percorso predefinito o **Sfoglia** per selezionare il percorso desiderato e quindi fare clic su **Installa**.

5.  Nella pagina Contratto di Licenza selezionare **Accetto i termini del Contratto di Licenza** e quindi fare clic su **OK**.

6.  Il programma di installazione installa i componenti di base di Lync Server.

7.  Quando la distribuzione guidata è pronta, fare clic su **prepara Active Directory**e quindi attendere che venga determinato lo stato della distribuzione.

8.  Al **passaggio 1: preparare lo schema**, fare clic su **Esegui**.

9.  Nella pagina **Prepara schema** fare clic su **Avanti**.

10. Nella pagina **Esecuzione comandi in corso** ricercare **Stato attività: Operazione completata** e quindi fare clic su **Visualizza registro**.

11. Nella colonna **azione** espandere **preparazione schema**, cercare il **\<Success\>** risultato dell'esecuzione alla fine di ogni attività per verificare che la preparazione dello schema sia stata completata correttamente, chiudere il registro e quindi fare clic su **fine**.

12. Attendere il completamento della replica di Active Directory o forzare la replica.

13. Verificare manualmente che le modifiche allo schema siano state replicate in tutti gli altri controller di dominio. Per informazioni dettagliate, vedere [Verifying Active Directory schema Replication in Lync Server 2013](lync-server-2013-verifying-schema-replication.md).

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-schema-of-the-current-forest"></a>Per utilizzare i cmdlet per preparare lo schema della foresta corrente

1.  Accedere a un computer nella foresta con un account membro del gruppo Schema Admins e con diritti di amministratore per il master schema.

2.  Installare i componenti di base di Lync Server come indicato di seguito:
    
    1.  Dalla cartella o dal supporto di installazione di Lync Server 2013, eseguire Setup.exe per avviare la distribuzione guidata di Lync Server.
    
    2.  Se viene chiesto di installare Microsoft Visual C++ Redistributable, fare clic su **Sì**.
    
    3.  Nella finestra di dialogo installazione di Lync Server 2013 viene visualizzata una richiesta di installazione dei file di Lync Server. Scegliere il percorso predefinito o **Sfoglia** per selezionare il percorso desiderato e quindi fare clic su **Installa**.
    
    4.  Nella pagina Contratto di Licenza selezionare **Accetto i termini del Contratto di Licenza** e quindi fare clic su **OK**. Il programma di installazione installa i componenti di base di Lync Server 2013.

3.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

4.  Eseguire: 
    
        Install-CsAdServerSchema [-Ldf <directory where the .ldf file is located>] 
    
    Se non si specifica il parametro ldf, il valore predefinito è il percorso di installazione di Lync Server 2013 che viene letto dal registro di sistema.
    
    Ad esempio:
    
        Install-CsAdServerSchema -Ldf "C:\Program Files\Microsoft Lync Server 2013\Deployment\Setup"

5.  Utilizzare il cmdlet seguente per verificare la corretta esecuzione della preparazione dello schema.
    
        Get-CsAdServerSchema 
    
    Questo cmdlet restituisce il valore dello **stato della versione dello schema \_ \_ \_ corrente** se la preparazione dello schema ha avuto esito positivo.

6.  Attendere il completamento della replica di Active Directory o forzare la replica.

7.  Verificare manualmente che le modifiche allo schema siano state replicate in tutti gli altri controller di dominio. Per informazioni dettagliate, vedere [Verifying Active Directory schema Replication in Lync Server 2013](lync-server-2013-verifying-schema-replication.md).

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Verifica della replica dello schema di Active Directory in Lync Server 2013](lync-server-2013-verifying-schema-replication.md)  


[Preparazione dello schema di Active Directory in Lync Server 2013](lync-server-2013-preparing-the-active-directory-schema.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

