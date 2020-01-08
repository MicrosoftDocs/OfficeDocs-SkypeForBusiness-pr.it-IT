---
title: Configurazione di un nodo Watcher per l'uso dell'autenticazione trusted server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring a watcher node to use Trusted Server authentication
ms:assetid: 42d879ac-aa90-4ed6-b5e2-1e208711672a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204852(v=OCS.15)
ms:contentKeyID: 48184017
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6634fa55424190d2e0a05aece38d88977d2f6bca
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978581"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-in-lync-server-2013-to-use-trusted-server-authentication"></a>Configurazione di un nodo Watcher in Lync Server 2013 per l'uso dell'autenticazione server attendibile

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-22_

Se il computer del nodo Watcher si trova all'interno della rete perimetrale, l'autenticazione basata su server attendibile può ridurre notevolmente le imposte amministrative per il mantenimento di un singolo certificato anziché di numerose password degli account utente.

Il primo passaggio della configurazione dell'autenticazione del server attendibile consiste nel creare un pool di applicazioni attendibili per ospitare il computer del nodo Watcher. Dopo aver creato il pool di applicazioni attendibili, è necessario configurare le transazioni sintetiche nel nodo Watcher per l'esecuzione come applicazione attendibile.

<div>


> [!NOTE]
> Un'applicazione attendibile è un'applicazione a cui viene assegnato lo stato attendibile per l'esecuzione come parte di Lync Server 2013, ma questa non è una parte incorporata del prodotto. Lo stato attendibile indica che l'applicazione non verrà contestata per l'autenticazione ogni volta che viene eseguita.



</div>

Per creare un pool di applicazioni attendibili, aprire Lync Server 2013 Management Shell ed eseguire un comando simile al seguente:

    New-CsTrustedApplicationPool -Identity atl-watcher-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -ThrottleAsServer $True -TreatAsAuthenticated $True -OutboundOnly $False -RequiresReplication $True -ComputerFqdn atl-watcher-001.litwareinc.com -Site Redmond

<div>


> [!NOTE]
> Per informazioni dettagliate sui parametri usati nel comando precedente, digitare quanto segue al prompt di Lync Server Management Shell:<BR>Get-Help New-CsTrustedApplicationPool-Full | più



</div>

Dopo aver creato il pool di applicazioni attendibili, configurare il computer del nodo Watcher per eseguire transazioni sintetiche come applicazione attendibile. Questa operazione viene eseguita usando il cmdlet **New-CsTrustedApplication** e un comando simile al seguente:

    New-CsTrustedApplication -ApplicationId STWatcherNode -TrustedApplicationPoolFqdn atl-watcher-001.litwareinc.com -Port 5061

Quando il comando precedente viene completato e l'applicazione attendibile è stata creata, eseguire Enable-CsTopology per verificare che le modifiche abbiano effetto:

    Enable-CsTopology

Dopo aver eseguito Enable-CsTopology, è consigliabile riavviare il computer.

Per verificare che sia stata creata la nuova applicazione attendibile, digitare quanto segue al prompt di Lync Server Management Shell:

    Get-CsTrustedApplication -Identity "atl-watcher-001.litwareinc.com/urn:application:STWatcherNode"

<div>

## <a name="configuring-a-default-certificate-on-the-watcher-node"></a>Configurazione di un certificato predefinito nel nodo Watcher

Ogni nodo Watcher deve avere un certificato predefinito assegnato tramite la distribuzione guidata di Lync Server.

**Per assegnare un certificato predefinito**

1.  Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Lync Server**e quindi fare clic su **distribuzione guidata Lync Server**.

2.  Nella distribuzione guidata di Lync Server fare clic su **Installa o aggiorna Lync Server System** , quindi fare clic su **Esegui** sotto la richiesta di titolo **, installa o assegna certificato**.
    
    <div>
    

    > [!NOTE]
    > Se il pulsante <STRONG>Esegui</STRONG> è disabilitato, potrebbe essere necessario fare prima clic su <STRONG>Esegui</STRONG> in <STRONG>Installa archivio configurazione locale</STRONG>.

    
    </div>

3.  Esegui una delle operazioni seguenti:
    
      - Se si dispone già di un certificato che può essere usato come certificato predefinito, fare clic su **predefinito** nella procedura guidata certificato e quindi fare clic su **assegna**. Seguire i passaggi della procedura guidata assegnazione certificati per assegnare il certificato.
    
      - Se è necessario richiedere un certificato per l'uso del certificato predefinito, fare clic su **Richiedi** e quindi seguire i passaggi della richiesta guidata certificato per richiedere tale certificato. Se si usano i valori predefiniti per il certificato del server Web, si ottiene un certificato che è possibile assegnare come certificato predefinito.

</div>

<div>

## <a name="installing-and-configuring-a-watcher-node"></a>Installazione e configurazione di un nodo Watcher

Dopo aver riavviato il computer del nodo Watcher e configurato un certificato, è necessario eseguire il file WatcherNode. msi. È necessario eseguire WatcherNode. msi in un computer in cui sono installati sia i file dell'agente Operations Manager che i componenti principali di Lync Server 2013.

**Per installare e configurare un nodo Watcher**

1.  Aprire Lync Server Management Shell facendo clic sul pulsante **Start**, scegliendo **tutti i programmi**, facendo clic su **Lync Server**e quindi su **Lync Server Management Shell**.

2.  In Lync Server Management Shell digitare il comando seguente e quindi premere INVIO (specificare il percorso effettivo della copia di WatcherNode. msi):
    
        C:\Tools\Watchernode.msi Authentication=TrustedServer
    
    <div>
    

    > [!NOTE]
    > È anche possibile eseguire WatcherNode. msi da una finestra di comando. Per aprire una finestra di comando, fare clic su <STRONG>Start</STRONG>, fare clic con il pulsante destro del mouse su <STRONG>prompt dei comandi</STRONG>e quindi scegliere <STRONG>Esegui come amministratore</STRONG>. Quando viene visualizzata la finestra di comando, digitare lo stesso comando precedente.

    
    </div>

Tieni presente che la coppia nome/valore nel comando precedente Authentication = TrustedServer fa distinzione tra maiuscole e minuscole. È necessario digitarlo esattamente come illustrato. Il comando seguente non riesce perché non usa l'involucro lettera corretto:

C:\\strumenti\\di autenticazione WatcherNode. msi = TrustedServer

Puoi usare la modalità TrustedServer solo con i computer che si trovano all'interno della rete perimetrale. Quando un nodo Watcher viene eseguito in modalità TrustedServer, gli amministratori non devono gestire le password degli utenti di test nel computer.

</div>

</div>

<span> </span>

</div>

</div>

</div>

