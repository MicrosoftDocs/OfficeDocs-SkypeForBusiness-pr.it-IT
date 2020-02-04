---
title: 'Lync Server 2013: importare i Management Pack di Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Importing the Lync Server 2013 management packs
ms:assetid: 846287e1-660f-453f-bdba-b2137b5f0ea1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205052(v=OCS.15)
ms:contentKeyID: 48184690
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1cc97cad4069c286f66707c34a9a1af7e87e97da
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763830"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="importing-the-lync-server-2013-management-packs"></a>Importazione dei Management Pack di Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-22_

Per estendere le funzionalità di System Center Operations Manager, è possibile installare Management Pack, ovvero software che indica quali elementi possono essere monitorati da System Center Operations Manager e come devono essere controllati gli elementi e come devono essere attivati gli avvisi e segnalato. Lync Server 2013 include due Management Pack di System Center Operations Manager che fornisce le funzionalità seguenti:

  - Il componente e User Management Pack (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) tiene traccia dei problemi di Lync Server registrati nei registri eventi, registrati da contatori delle prestazioni oppure registrati nei record dettagli chiamata (CDR) o nella qualità dell'esperienza (QoE) database. Per problemi critici, System Center Operations Manager può essere configurato per informare immediatamente gli amministratori tramite posta elettronica, messaggio istantaneo o messaggistica SMS (Short Message Service). SMS è la tecnologia usata per inviare SMS da un dispositivo mobile a un altro.
    
    <div>
    

    > [!NOTE]  
    > Per informazioni dettagliate sulla configurazione della notifica di Operations Manager, vedere la notifica di configurazione nella <A href="http://go.microsoft.com/fwlink/p/?linkid=268785">http://go.microsoft.com/fwlink/p/?LinkId=268785</A>Raccolta TechNet.

    
    </div>

  - Active Monitoring Management Pack (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) verifica in modo proattivo i componenti principali di Lync Server, ad esempio l'accesso al sistema, lo scambio di messaggi istantanei o l'esecuzione di chiamate a un telefono che si trova sul pubblico commutato rete telefonica (PSTN). Questi test vengono eseguiti usando i cmdlet di transazione sintetica di Lync Server. Ad esempio, puoi usare il cmdlet **Test-CsIM** per simulare una conversazione di messaggistica istantanea tra una coppia di utenti di test. Se la conversazione di messaggistica simulata non riesce, viene generato un avviso.

È necessario importare i Management Pack. Se non si importano i Management Pack, non è possibile usare Operations Manager per monitorare gli eventi di Lync Server o eseguire transazioni sintetiche di Lync Server.

Il Management Pack per il componente e l'utente viene usato solo per monitorare Lync Server 2013. In uno scenario di coesistenza, in cui sono installati sia Lync Server 2013 che Lync Server 2010, è necessario continuare a usare i Management Pack di Lync Server 2010 per i computer di Lync Server 2010.

<div>


> [!NOTE]  
> I Management Pack per Lync Server 2010 includono Lync Server 2010 Monitoring Management Pack e Lync Server 2010 Group Chat Monitoring Management Pack.



</div>

È possibile usare uno degli strumenti seguenti per importare i Management Pack:

  - **System Center Operations Manager**   con questo metodo, è possibile usare Operations Manager per aggiungere il monitoraggio per Lync Server.

  - **Operations Manager Shell**   è possibile usare la shell di Operations Manager per importare direttamente o per risolvere i problemi che si verificano quando si importano i Management Pack tramite la console di System Center Operations Manager.

<div>

## <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a>Importazione di Management Pack tramite System Center Operations Manager

1.  Scaricare i file Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp e Microsoft.LS.2013.Monitoring.ComponentAndUser.mp.

2.  In System Center Operations Manager fare clic su **Amministrazione**.

3.  Nel riquadro **Amministrazione** fare clic con il pulsante destro del mouse su **Management Pack**e quindi scegliere **Importa Management Pack**.

4.  Nella finestra di dialogo **Seleziona Management Pack** fare clic su **Aggiungi**e quindi su **Aggiungi da disco**.

5.  Nella finestra di dialogo **connessione Catalogo online** fare clic su **Annulla** per evitare che Operations Manager venga visualizzato online per verificare se esistono dipendenze per i Management Pack di Lync Server. Se si usa System Center Operations Manager 2012, fare clic su **No**.

6.  Nella finestra **di dialogo Seleziona Management Pack da importare** individuare e selezionare i file **Microsoft.ls.2013.Monitoring.ActiveMonitoring.MP** e **Microsoft.ls.2013.Monitoring.ComponentAndUser.MP** e quindi fare clic su **Apri**. Per selezionare più file nella finestra di dialogo, fare clic sul primo file, tenere premuto CTRL e quindi fare clic sul secondo file.

7.  Nella finestra di dialogo **Seleziona Management Pack** fare clic su **Installa**. Se viene visualizzato un messaggio di errore e l'installazione non riesce, significa in genere che i file del Management Pack si trovano in una cartella protetta dal controllo dell'account utente di Windows. In questo caso, copiare i file in un'altra cartella e quindi riavviare il processo di importazione e installazione.

8.  Nella finestra di dialogo **Seleziona Management Pack** fare clic su **Chiudi**. Tieni presente che il processo di importazione e installazione potrebbe richiedere diversi minuti per il completamento.

</div>

<div>

## <a name="importing-management-packs-by-using-the-operations-manager-shell"></a>Importazione di Management Pack tramite la shell di Operations Manager

In generale, è più semplice importare i Management Pack tramite Operations Manager. Tuttavia, se si verifica un errore e l'importazione non riesce, la console non sempre fornisce rapporti di errore adeguati. Tramite il confronto, la shell di Operations Manager offre informazioni dettagliate. Se si usa Operations Manager e si verificano problemi di importazione di un Management Pack, importare il pacchetto tramite Operations Manager Shell. La shell di Operations Manager offre ulteriori informazioni che potrebbero essere utili per determinare il motivo per cui l'importazione non è riuscita.

Se si usa System Center Operations Manager 2007 R2, eseguire la procedura seguente:

1.  Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, quindi **System Center Operations Manager 2007 R2**e quindi fare clic su **Operations Manager Shell**.

2.  In Operations Manager Shell digitare il comando seguente al prompt dei comandi, usando il percorso effettivo della copia del file Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp e quindi premere INVIO:
    
        MPImport.exe D:\MP\Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp

3.  Dopo aver importato il primo Management Pack, ripetere il processo usando il percorso della copia del file Microsoft.LS.2013.Monitoring.ComponentAndUser.mp:
    
        MPImport.exe D:\MP\Microsoft.LS.2013.Monitoring.ComponentAndUser.mp

4.  Chiudere la shell di Operations Manager.

Se si usa System Center Operations Manager 2012, eseguire questa procedura:

1.  Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Microsoft System Center 2012**, fare clic su **Operations Manager**e quindi su **Operations Manager Shell**.

2.  In Operations Manager Shell digitare il comando seguente al prompt dei comandi, usando il percorso effettivo della copia del file Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp e quindi premere INVIO:
    
        Import-SCOMManagementPack -FullName "D:\MP\ Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp"

3.  Dopo aver importato il primo Management Pack, ripetere il processo usando il percorso della copia del file Microsoft.LS.2013.Monitoring.ComponentAndUser.mp:
    
        Import-SCOMManagementPack -FullName "D:\MP\ Microsoft.LS.2013.Monitoring.ComponentAndUser.mp"

</div>

</div>

<span> </span>

</div>

</div>

</div>

