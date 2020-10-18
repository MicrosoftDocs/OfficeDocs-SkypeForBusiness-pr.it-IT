---
title: Configurazione di un nodo Watcher per l'utilizzo dell'autenticazione del server attendibile
description: Configurazione di un nodo Watcher per l'utilizzo dell'autenticazione basata su server attendibili.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a watcher node to use Trusted Server authentication
ms:assetid: 42d879ac-aa90-4ed6-b5e2-1e208711672a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204852(v=OCS.15)
ms:contentKeyID: 48184017
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 247d628f936808a01780c7adc497342baedbbecb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576312"
---
# <a name="configuring-a-watcher-node-in-lync-server-2013-to-use-trusted-server-authentication"></a>Configurazione di un nodo Watcher in Lync Server 2013 per l'utilizzo dell'autenticazione server attendibile

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-22_

Se il computer del nodo Watcher si trova all'interno della rete perimetrale, l'uso dell'autenticazione Server attendibile può ridurre notevolmente le attività di amministrazione richieste dal momento che implica il mantenimento di un singolo certificato anziché di numerose password per i vari account utente.

Il primo passaggio per la configurazione dell'autenticazione Server attendibile consiste nel creare un pool di applicazioni attendibili in cui ospitare il computer del nodo Watcher. Dopo aver creato il pool, è necessario configurare l'esecuzione delle transazioni sintetiche sul nodo Watcher come applicazione attendibile.

<div>


> [!NOTE]
> Un'applicazione attendibile è un'applicazione a cui viene assegnato lo stato attendibile per l'esecuzione come parte di Lync Server 2013, ma non si tratta di una parte incorporata del prodotto. Lo stato attendibile indica che all'applicazione non verrà richiesta l'autenticazione a ogni esecuzione.



</div>

Per creare un pool di applicazioni attendibili, aprire Lync Server 2013 Management Shell ed eseguire un comando simile al seguente:

    New-CsTrustedApplicationPool -Identity atl-watcher-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -ThrottleAsServer $True -TreatAsAuthenticated $True -OutboundOnly $False -RequiresReplication $True -ComputerFqdn atl-watcher-001.litwareinc.com -Site Redmond

<div>


> [!NOTE]
> Per informazioni dettagliate sui parametri utilizzati nel comando precedente, al prompt dei comandi di Lync Server Management Shell digitare quanto segue:<BR>Get-Help New-CsTrustedApplicationPool -Full | more



</div>

Dopo aver creato il pool di applicazioni attendibili, configurare il computer del nodo Watcher per l'esecuzione delle transazioni sintetiche come applicazione attendibile. A tale scopo, utilizzare il cmdlet **New-CsTrustedApplication** e un comando simile al seguente:

    New-CsTrustedApplication -ApplicationId STWatcherNode -TrustedApplicationPoolFqdn atl-watcher-001.litwareinc.com -Port 5061

Al termine del comando precedente e della creazione dell'applicazione attendibile, eseguire Enable-CsTopology per in modo che le modifiche diventino effettive:

    Enable-CsTopology

Dopo aver eseguito Enable-CsTopology, si consiglia di riavviare il computer.

Per verificare che la nuova applicazione attendibile sia stata creata, digitare quanto segue al prompt dei comandi di Lync Server Management Shell:

    Get-CsTrustedApplication -Identity "atl-watcher-001.litwareinc.com/urn:application:STWatcherNode"

<div>

## <a name="configuring-a-default-certificate-on-the-watcher-node"></a>Configurazione di un certificato predefinito sul nodo Watcher

Ogni nodo Watcher deve disporre di un certificato predefinito assegnato tramite la distribuzione guidata di Lync Server.

**Per assegnare un certificato predefinito**

1.  Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Lync Server**e quindi **distribuzione guidata di Lync Server**.

2.  Nella distribuzione guidata di Lync Server, fare clic su **Installa o aggiorna il sistema Lync Server** , quindi fare clic su **Esegui** nell'intestazione **richiesta, installazione o assegnazione**di un certificato.
    
    <div>
    

    > [!NOTE]
    > Se il pulsante <STRONG>Esegui</STRONG> è disabilitato, può essere necessario prima fare clic su <STRONG>Esegui</STRONG> al di sotto di <STRONG>Installazione dell'archivio di configurazione locale</STRONG>.

    
    </div>

3.  Eseguire una delle operazioni seguenti:
    
      - Se è già disponibile un certificato da poter utilizzare come predefinito, fare clic su **Predefinito** nella Configurazione guidata certificati e quindi fare clic su **Assegna**. Seguire i passaggi indicati nella procedura guidata Assegnazione certificato per assegnarlo.
    
      - Se è necessario richiedere un certificato da utilizzare come predefinito, fare clic su **Richiesta** e quindi seguire i passaggi indicati dalla procedura guidata Richiesta di certificato. Se si utilizzano i valori predefiniti per il certificato del server Web, si ottiene un certificato che può essere assegnato come predefinito.

</div>

<div>

## <a name="installing-and-configuring-a-watcher-node"></a>Installazione e configurazione di un nodo Watcher

Dopo aver riavviato il computer del nodo Watcher e aver configurato un certificato, è necessario eseguire il file Watchernode.msi. È necessario eseguire Watchernode.msi in un computer in cui sono installati sia i file dell'agente di Operations Manager che i componenti di base di Lync Server 2013.

**Per installare e configurare un nodo Watcher**

1.  Aprire Lync Server Management Shell facendo clic sul pulsante **Start**, scegliendo **tutti i programmi**, **Lync Server**e quindi **Lync Server Management Shell**.

2.  In Lync Server Management Shell, digitare il comando seguente e quindi premere INVIO (specificare il percorso effettivo della copia di Watchernode.msi):
    
        C:\Tools\Watchernode.msi Authentication=TrustedServer
    
    <div>
    

    > [!NOTE]
    > È anche possibile eseguire Watchernode.msi da una finestra di comando. Per aprire una finestra di comando, fare clic sul pulsante <STRONG>Start</STRONG>, fare clic con il pulsante destro del mouse su <STRONG>Prompt dei comandi</STRONG> e quindi scegliere <STRONG>Esegui come amministratore</STRONG>. Quando viene visualizzata la finestra di comando, digitare lo stesso comando precedente.

    
    </div>

Si noti che la coppia nome/valore del comando precedente Authentication=TrustedServer presenta la distinzione tra maiuscole e minuscole. Digitarla esattamente come mostrato. Il comando seguente non riesce in quanto non utilizza la corretta distinzione tra maiuscole e minuscole per le lettere:

C: \\ Tools \\Watchernode.msi Authentication = TrustedServer

È possibile utilizzare la modalità TrustedServer solo con i computer situati all'interno della rete perimetrale. Quando un nodo viene eseguito in modalità TrustedServer, gli amministratori non devono mantenere le password di prova degli utenti sul computer.

</div>

</div>

<span> </span>

</div>

</div>

</div>

