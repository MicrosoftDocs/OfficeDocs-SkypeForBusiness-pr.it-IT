---
title: Configurare i computer Skype for Business Server che verranno monitorati
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b24ea184-4b3e-4277-a244-157afb4b368b
description: "Riepilogo: installare i file dell'agente di Operations Manager sul computer Skype for Business Server 2015 per essere monitorati e configurare il computer affinché funga da proxy di centro di sistema."
ms.openlocfilehash: d3935f0f6c9ffb13ac18f544d7b4727199b6dbea
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814886"
---
# <a name="configure-the-skype-for-business-server-computers-that-will-be-monitored"></a>Configurare i computer Skype for Business Server che verranno monitorati

**Riepilogo:** Installare i file dell'agente di Operations Manager sul computer Skype for Business Server 2015 per essere monitorati e configurare il computer affinché funga da proxy di centro di sistema.

Ogni computer Skype for Business Server 2015 che si desidera monitorare deve essere in grado di autosegnalarne l'esistenza al server di gestione. Per abilitare questo processo, è necessario installare i file dell'agente Operations Manager su ciascuno dei computer da monitorare. Dopo l'installazione dei file dell'agente, è necessario configurare il computer affinché funga da proxy di centro di sistema. Prima di eseguire queste procedure, verificare di aver installato e configurato per la prima volta Skype for Business Server in questi computer.

## <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network"></a>Installazione di un certificato in un nodo Watcher posizionato all'esterno del perimetro della rete
<a name="watcher_node_outside"> </a>

Gli agenti di System Center Operations Manager in esecuzione in una rete perimetrale, ad esempio un server perimetrale di Skype for Business Server, all'esterno dell'organizzazione (ad esempio un nodo Watcher esterno di una transazione sintetica) o in un limite di attendibilità di Active Directory possono richiedere la configurazione di un server Gateway System Center Operations Manager. Questo ruolo del server consente agli agenti che non dispongono di una relazione di trust con il server di gestione radice di generare avvisi. Per informazioni dettagliate, vedere [Managing gateway Servers in Operations Manager 2012](https://technet.microsoft.com/library/hh212823.aspx).

Se si distribuisce un agente in una di queste posizioni, sarà inoltre necessario richiedere e configurare un certificato che consenta al nodo Watcher di inviare avvisi a System Center Operations Manager. Per semplificare questo processo, il team di Operations Manager ha creato un set di utilità che consente di richiedere e installare il tipo di certificato corretto nel computer del nodo di controllo. Per ulteriori informazioni e per scaricare queste utilità, vedere [ottenimento di certificati per gli agenti non appartenenti a un dominio semplificati con la generazione guidata certificati](https://go.microsoft.com/fwlink/p/?LinkID=267421&amp;amp;clcid=0x409).

### <a name="installing-the-operation-manager-agent-files"></a>Installazione dei file dell'agente Operations Manager

1. Nel supporto di installazione di System Center fare doppio clic su **Setup.exe**.

2. Nell'installazione guidata di System Center Operation Manager fare clic su **Install Operations Manager Agent** dall'agente di installazione in installazioni opzionali.

3. Nell'installazione guidata di System Center, nella pagina installazione guidata di System Center Operations Manager fare clic su **Avanti**.

4. Nella pagina cartella di destinazione, selezionare la cartella in cui verranno installati i file dell'agente Operations Manager e fare clic su **Avanti**.

5. Nella pagina Configurazione gruppo di gestione selezionare **specifica informazioni gruppo di gestione** e fare clic su **Avanti**.

6. Nella pagina Configurazione gruppo di gestione digitare il nome del gruppo di gestione di Operations Manager nella casella **Nome gruppo di gestione** e quindi digitare il nome host del server Operations Manager (ad esempio, atl-scom-001) nella casella **Server di gestione**. Se il numero di porta utilizzato da Operations Manager è stato modificato, immettere il nuovo numero di porta nella casella **porta del server di gestione** . In caso contrario, lasciare la porta al valore predefinito 5723 e quindi fare clic su **Avanti**.

7. Nella pagina account azione agente selezionare **sistema locale** e fare clic su **Avanti**.

8. Nella pagina Microsoft Update selezionare **non si desidera utilizzare Microsoft Update** e fare clic su **Avanti**.

9. Nella pagina Inizio installazione fare clic su **Installa**.

10. Nella pagina Completamento dell'Installazione guidata di System Center Operations Manager fare clic su **Fine**.

11. Fare clic su **Exit**.

Per System Center 2012, è possibile verificare che l'agente sia stato creato facendo clic sul pulsante **Start**, scegliendo **tutti i programmi**, facendo clic su **System Center Operations Manager 2012** e quindi scegliendo **Operations 2012 Manager Shell**. Nella shell di Operations Manager, digitare il comando di Windows PowerShell seguente e quindi premere INVIO:
```PowerShell
Get-SCOMAgent
```

Verrà visualizzato un elenco di tutti gli agenti di Operations Manager.
## <a name="configuring-the-skype-for-business-server-computer-to-participate-in-system-center-discovery"></a>Configurazione del computer con Skype for Business Server per partecipare a System Center Discovery
<a name="watcher_node_outside"> </a>

Per assicurarsi che il nuovo agente di Skype for Business Server partecipi al processo di individuazione per System Center Operations Manager, è necessario completare la procedura seguente in ogni computer in cui è stata installata la console di System Center Operations Manager:

1. Nella scheda Amministrazione fare clic su **Gestito tramite agente**.

2. Fare clic su **Individuazione guidata** e completare la procedura guidata per individuare il computer.

3. Riavviare il servizio dell'agente di integrità. Il riavvio del servizio costringerà l'individuazione del nuovo computer. Se il servizio non viene riavviato, potrebbe essere necessario fino a 4 ore prima che il nuovo computer venga individuato da System Center Operations Manager.

4. Verificare che non siano stati registrati eventi di errore nel registro eventi di Operations Manager.

5. Il computer in cui viene inserito l'agente verrà visualizzato nell'elenco "agente gestito" e il computer in cui è stato installato l'agente manualmente verrà visualizzato in "gestione in sospeso", fare clic sul nome del computer e approvare.

6. Fare clic con il pulsante destro del mouse sul nome del computer e scegliere **Proprietà**. Nella scheda Sicurezza della finestra di dialogo Proprietà selezionare **Consenti a questo agente di funzionare come proxy e individuare oggetti gestiti sugli altri computer**, quindi fare clic su **OK**.


