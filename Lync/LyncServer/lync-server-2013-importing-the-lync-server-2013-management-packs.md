---
title: 'Lync Server 2013: importazione dei Lync Server 2013 Management Pack'
description: 'Lync Server 2013: importazione di Lync Server 2013 Management Pack.'
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
ms.openlocfilehash: c9615e559baf2f1c8b99015f1e407230559ff770
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547782"
---
# <a name="importing-the-lync-server-2013-management-packs"></a>Importazione dei Management Pack di Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-22_

È possibile estendere le funzionalità di System Center Operations Manager installando Management Pack, ovvero software che determina quali elementi possono essere monitorati dal System Center Operations Manager e in che modo tali elementi devono essere monitorati e come devono essere attivati e segnalati gli avvisi. Lync Server 2013 include due Management Pack di System Center Operations Manager che forniscono le funzionalità seguenti:

  - Il componente e l'User Management Pack (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) tiene traccia dei problemi di Lync Server registrati nei registri eventi, registrati dai contatori delle prestazioni o registrati nei database di registrazione dettagli chiamata (CDR) o in qualità di esperienza (QoE). Per i problemi critici, System Center Operations Manager può essere configurato per informare immediatamente gli amministratori tramite messaggi di posta elettronica, messaggi istantanei o SMS (Short Message Service). SMS è la tecnologia utilizzata per l'invio di messaggi di testo da un dispositivo mobile a un altro.
    
    <div>
    

    > [!NOTE]  
    > Per informazioni dettagliate sulla configurazione della notifica di Operations Manager, vedere la notifica di configurazione nella libreria TechNet all'indirizzo <A href="https://go.microsoft.com/fwlink/p/?linkid=268785">https://go.microsoft.com/fwlink/p/?LinkId=268785</A> .

    
    </div>

  - Active Monitoring Management Pack (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) verifica in modo proattivo i componenti chiave di Lync Server, ad esempio l'accesso al sistema, lo scambio di messaggi istantanei o l'esecuzione di chiamate a un telefono che si trova nella rete PSTN (Public Switched Telephone Network). Questi test vengono eseguiti utilizzando i cmdlet per le transazioni sintetiche di Lync Server. Ad esempio, è possibile utilizzare il cmdlet **Test-CsIM** per simulare una conversazione di messaggistica istantanea tra due utenti. Se la simulazione non ha esito positivo, viene generata un'allerta.

È necessario importare i pacchetti di gestione. Se non si importano i Management Pack, non è possibile utilizzare Operations Manager per monitorare gli eventi di Lync Server o eseguire transazioni sintetiche di Lync Server.

Il componente e il Management Pack dell'utente vengono utilizzati solo per il monitoraggio di Lync Server 2013. Se si è in uno scenario di coesistenza, in cui sono installati sia Lync Server 2013 che Lync Server 2010, è consigliabile continuare a utilizzare Lync Server 2010 Management Pack per i computer Lync Server 2010.

<div>


> [!NOTE]  
> I Management Pack per Lync Server 2010 includono Lync Server 2010 Monitoring Management Pack e Lync Server 2010 Group Chat Monitoring Management Pack.



</div>

È possibile utilizzare uno degli strumenti per importare i pacchetti di gestione:

  - **System Center Operations Manager**     Con questo metodo, è possibile utilizzare Operations Manager per aggiungere il monitoraggio per Lync Server.

  - Shell di Operations **Manager**     È possibile utilizzare la shell di Operations Manager per importare direttamente o per risolvere eventuali problemi che si verificano quando si importano i Management Pack tramite la console di System Center Operations Manager.

<div>

## <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a>Importazione dei Management Pack tramite System Center Operations Manager

1.  Scaricare i file Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp e Microsoft.LS.2013.Monitoring.ComponentAndUser.mp.

2.  In System Center Operations Manager fare clic su **Amministrazione**.

3.  Nel riquadro **Amministrazione**, fare clic con il tasto destro del mouse su **Management Pack**, e quindi su **Importa Management Pack**.

4.  Nella finestra di dialogo **Seleziona Management Pack**, fare clic su **Aggiungi** e quindi su **Aggiungi da disco**.

5.  Nella finestra di dialogo **connessione Catalogo online** fare clic su **Annulla** per evitare che Operations Manager venga visualizzato online per verificare se esistono dipendenze per i Management Pack di Lync Server. Se si utilizza System Center Operations Manager 2012, fare clic su **No**.

6.  Nella finestra di dialogo **Selezionare i Management Pack da importare**, localizzare e selezionare i file **Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp** e **Microsoft.LS.2013.Monitoring.ComponentAndUser.mp**, quindi fare clic su **Apri**. Per selezionare più file nella finestra di dialogo, fare clic sul primo file, tenere premuto il tasto Ctrl e quindi fare clic sul secondo file.

7.  Nella finestra di dialogo **Seleziona Management Pack**, fare clic su **Installa**. Se compare un messaggio di errore e l'installazione ha esito negativo, molto probabilmente i file dei pacchetti di gestione si trovano in una cartella protetta da Controllo account utente di Windows. In casi simili, copiare i file in una cartella diversa, quindi riavviare il processo di importazione e installazione.

8.  Nella finestra di dialogo **Seleziona Management Pack**, fare clic su **Chiudi**. Il processo di importazione e installazione potrebbe richiedere diversi minuti per essere completato.

</div>

<div>

## <a name="importing-management-packs-by-using-the-operations-manager-shell"></a>Importazione dei Management Pack tramite la shell di Operations Manager

In generale, è più facile importare i Management Pack tramite Operations Manager. Tuttavia, se si verifica un errore e l'importazione ha esito negativo, la console non fornisce sempre segnalazioni di errori adeguate. Tramite il confronto, la shell di Operations Manager fornisce informazioni dettagliate. Se si utilizza Operations Manager e si verificano problemi nell'importazione di un Management Pack, importare il pacchetto tramite la shell di Operations Manager. La shell di Operations Manager fornisce ulteriori informazioni che possono essere utili per determinare il motivo per cui l'importazione ha avuto esito negativo.

Se si utilizza System Center Operations Manager 2007 R2, eseguire la procedura seguente:

1.  Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **System Center Operations Manager 2007 R2**e quindi fare clic su **Operations Manager Shell**.

2.  Nella shell di Operations Manager, digitare il comando seguente al prompt dei comandi, utilizzando il percorso effettivo della copia del file Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp e quindi premere INVIO:
    
        MPImport.exe D:\MP\Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp

3.  Dopo avere importato il primo pacchetto di gestione, ripetere il processo utilizzando il percorso della copia del file Microsoft.LS.2013.Monitoring.ComponentAndUser.mp:
    
        MPImport.exe D:\MP\Microsoft.LS.2013.Monitoring.ComponentAndUser.mp

4.  Chiudere la shell di Operations Manager.

Se si utilizza System Center Operations Manager 2012, eseguire questa procedura in alternativa:

1.  Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft System Center 2012**, fare clic su **Operations Manager**e quindi fare clic su **Operations Manager Shell**.

2.  Nella shell di Operations Manager, digitare il comando seguente al prompt dei comandi, utilizzando il percorso effettivo della copia del file Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp e quindi premere INVIO:
    
        Import-SCOMManagementPack -FullName "D:\MP\ Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp"

3.  Dopo avere importato il primo pacchetto di gestione, ripetere il processo utilizzando il percorso della copia del file Microsoft.LS.2013.Monitoring.ComponentAndUser.mp:
    
        Import-SCOMManagementPack -FullName "D:\MP\ Microsoft.LS.2013.Monitoring.ComponentAndUser.mp"

</div>

</div>

<span> </span>

</div>

</div>

</div>

