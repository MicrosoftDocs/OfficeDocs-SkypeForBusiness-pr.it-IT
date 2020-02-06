---
title: Configurare i computer di Skype for Business Server che verranno monitorati
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 11/7/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: "Riepilogo: installare i file dell'agente di Operations Manager nel computer Skype for Business Server 2019 per il monitoraggio e configurare il computer in modo che funga da proxy del centro di sistema."
ms.openlocfilehash: 162b2dc0b50b7da5246d69d64b0bdb307212c139
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799646"
---
# <a name="configure-the-skype-for-business-server-computers-that-will-be-monitored"></a>Configurare i computer di Skype for Business Server che verranno monitorati

**Riepilogo:** Installare i file dell'agente Operations Manager nel computer Skype for Business Server 2019 per il monitoraggio e configurare il computer in modo che funga da proxy del centro di sistema.

Ogni computer Skype for Business Server 2019 che si vuole monitorare deve essere in grado di auto-segnalare la propria esistenza al server di gestione. Per abilitare questo processo, è necessario installare i file dell'agente di Operations Manager in ognuno dei computer da monitorare. Dopo aver installato i file dell'agente, è necessario configurare il computer per fungere da proxy centro di sistema. Prima di eseguire queste procedure, assicurati di aver installato e configurato prima Skype for Business Server in questi computer.

## <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network"></a>Installazione di un certificato in un nodo Watcher situato all'esterno della rete perimetrale
<a name="watcher_node_outside"> </a>

Gli agenti di System Center Operations Manager eseguiti in una rete perimetrale (ad esempio Skype for Business Server Edge Server), all'esterno dell'organizzazione, ad esempio un nodo di Watcher delle transazioni sintetiche esterne o in un limite di attendibilità di Active Directory, potrebbero richiedere configurazione di un server gateway di System Center Operations Manager. Questo ruolo del server consente agli agenti che non hanno una relazione di trust con il server di gestione radice di generare avvisi. Per informazioni dettagliate, vedere [gestione dei server gateway in Operations Manager 2012](https://technet.microsoft.com/en-us/library/hh212823.aspx).

Se si distribuisce un agente in una di queste posizioni, sarà anche necessario richiedere e configurare un certificato che consenta al nodo Watcher di inviare avvisi a System Center Operations Manager. Per semplificare questo processo, il team di Operations Manager ha creato un set di utilità che consentono di richiedere e installare il tipo corretto di certificato nel computer del nodo Watcher. Per informazioni dettagliate e per scaricare queste utilità, vedere [ottenere certificati per gli agenti non appartenenti a un dominio semplificati con la generazione guidata certificati](https://go.microsoft.com/fwlink/p/?LinkID=267421&amp;amp;clcid=0x409).

### <a name="installing-the-operation-manager-agent-files"></a>Installazione dei file dell'agente di Operation Manager

1. Nel supporto di configurazione di System Center fare doppio clic su **Setup. exe**.

2. Nella configurazione guidata di System Center Operation Manager fare clic su **Installa agente di Operations Manager**dall'agente di installazione in installazioni facoltative

3. Nella configurazione guidata di System Center, nella pagina Introduzione alla configurazione guidata di System Center Operations Manager, fare clic su **Avanti**.

4. Nella pagina cartella di destinazione selezionare la cartella in cui verranno installati i file dell'agente Operations Manager e fare clic su **Avanti**.

5. Nella pagina Configurazione gruppo di gestione selezionare **specifica informazioni gruppo di gestione** e fare clic su **Avanti**.

6. Nella pagina Configurazione gruppo di gestione digitare il nome del gruppo gestione Operations Manager nella casella **nome gruppo di gestione** e quindi digitare il nome host del server Operations Manager, ad esempio ATL-SCOM-001, nella casella **server di gestione** . Se è stato modificato il numero di porta usato da Operations Manager, immettere il nuovo numero di porta nella casella **porta del server di gestione** . In caso contrario, lascia la porta al valore predefinito di 5723 e quindi fai clic su **Avanti**.

7. Nella pagina account azione agente selezionare **sistema locale** e fare clic su **Avanti**.

8. Nella pagina Microsoft Update selezionare **non si vuole usare Microsoft Update** e fare clic su **Avanti**.

9. Nella pagina pronto per l'installazione fare clic su **Installa**.

10. Nella pagina completamento della configurazione guidata di System Center Operations Manager fare clic su **fine**.

11. Fare clic su **Esci**.

Per System Center 2012, è possibile verificare che l'agente sia stato creato facendo clic sul pulsante **Start**, scegliendo **tutti i programmi**, facendo clic su **System Center Operations Manager 2012**e quindi scegliendo **Operations 2012 Manager Shell**. In Operations Manager Shell digitare il comando di Windows PowerShell seguente e quindi premere INVIO:
```PowerShell
Get-SCOMAgent
```

Verrà visualizzato un elenco di tutti gli agenti di Operations Manager.
## <a name="configuring-the-skype-for-business-server-computer-to-participate-in-system-center-discovery"></a>Configurazione del computer Skype for Business Server per partecipare a System Center Discovery
<a name="watcher_node_outside"> </a>

Per assicurarsi che il nuovo agente di Skype for Business Server partecipi al processo di individuazione di System Center Operations Manager, è necessario completare la procedura seguente in ogni computer in cui è stata installata la console di System Center Operations Manager:

1. Nella scheda Amministrazione fare clic su **agente gestito**.

2. Fare clic su **Individuazione guidata** e completare la procedura guidata per scoprire il computer.

3. Riavviare il servizio Agente integrità. Il riavvio del servizio forzerà l'individuazione del nuovo computer. Se il servizio non viene riavviato, potrebbero essere necessarie fino a 4 ore prima che il nuovo computer venga individuato da System Center Operations Manager.

4. Verificare che non siano stati registrati eventi di errore nel log eventi di Operations Manager.

5. Il computer in cui l'agente viene inserito correttamente verrà visualizzato nella sezione "agente gestito" e il computer in cui è stato installato l'agente manualmente verrà visualizzato in "gestione in sospeso", fare clic sul nome del computer e approvare.

6. Fare clic con il pulsante destro del mouse sul nome del computer e quindi scegliere **Proprietà**. Nella scheda sicurezza della finestra di dialogo Proprietà selezionare **Consenti all'agente di fungere da proxy e individuare gli oggetti gestiti in altri computer**e quindi fare clic su **OK**.


