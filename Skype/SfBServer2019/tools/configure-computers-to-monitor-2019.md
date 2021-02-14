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
description: 'Riepilogo: installare i file agente di Operations Manager nel computer Skype for Business Server 2019 da monitorare e configurare il computer in modo che funzioni come proxy di System Center.'
ms.openlocfilehash: 08328e430acd4fa651fccd89b827d5c103066dd1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806076"
---
# <a name="configure-the-skype-for-business-server-computers-that-will-be-monitored"></a>Configurare i computer Skype for Business Server che verranno monitorati

**Riepilogo:** Installare i file agente di Operations Manager nel computer Skype for Business Server 2019 da monitorare e configurare il computer per agire come proxy di System Center.

Ogni computer Skype for Business Server 2019 che si desidera monitorare deve essere in grado di segnalare autonomamente l'esistenza al server di gestione. Per abilitare questo processo, è necessario installare i file agente di Operations Manager in ognuno dei computer da monitorare. Dopo aver installato i file agente, è necessario configurare il computer in modo che agirà come proxy di System Center. Assicurarsi di aver prima installato e configurato Skype for Business Server in questi computer prima di eseguire queste procedure.

## <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network"></a>Installazione di un certificato in un nodo Watcher posizionato all'esterno del perimetro della rete
<a name="watcher_node_outside"> </a>

Gli agenti di System Center Operations Manager in esecuzione in una rete perimetrale (ad esempio un server perimetrale Skype for Business Server), all'esterno dell'organizzazione (ad esempio un nodo External Synthetic Transaction Watcher) o attraverso un limite di trust di Active Directory, possono richiedere la configurazione di un server gateway di System Center Operations Manager. Questo ruolo del server consente agli agenti che non dispongono di una relazione di trust con il server di gestione radice di generare avvisi. Per informazioni dettagliate, [vedere Managing Gateway Servers in Operations Manager 2012.](https://technet.microsoft.com/library/hh212823.aspx)

Se si distribuisce un agente in una di queste posizioni, sarà inoltre necessario richiedere e configurare un certificato che consenta al nodo Watcher di inviare avvisi a System Center Operations Manager. Per semplificare questo processo, il team di Operations Manager ha creato un set di utilità che consente di richiedere e installare il tipo di certificato corretto nel computer del nodo di controllo. Per informazioni dettagliate e per scaricare queste utilità, vedere [Obtaining Certificates for Non-Domain Joined Agents Made Easy with Certificate Generation Wizard.](https://go.microsoft.com/fwlink/p/?LinkID=267421&amp;amp;clcid=0x409)

### <a name="installing-the-operation-manager-agent-files"></a>Installazione dei file dell'agente Operations Manager

1. Nel supporto di installazione di System Center fare doppio clic su **Setup.exe.**

2. Nell'installazione guidata di System Center Operation Manager fare clic **su Installa agente Operations Manager** dall'agente di installazione in Installazioni facoltative

3. Nella pagina Iniziale dell'installazione guidata di System Center Operations Manager fare clic su **Avanti.**

4. Nella pagina Cartella di destinazione selezionare la cartella in cui verranno installati i file dell'agente Operations Manager e fare clic su **Avanti.**

5. Nella pagina Configurazione gruppo di gestione selezionare Specifica informazioni gruppo **di gestione** e fare clic su **Avanti.**

6. Nella pagina Configurazione gruppo di gestione digitare il nome del gruppo di gestione di Operations Manager nella casella **Nome gruppo di gestione** e quindi digitare il nome host del server Operations Manager (ad esempio, atl-scom-001) nella casella **Server di gestione**. Se è stato modificato il numero di porta utilizzato da Operations Manager, immettere il nuovo numero di porta nella casella **Porta server di** gestione. In caso contrario, lasciare la porta sul valore predefinito 5723 e quindi fare clic su **Avanti.**

7. Nella pagina Account azione agente selezionare **Sistema** locale e fare clic su **Avanti.**

8. Nella pagina Microsoft Update selezionare **Non si vuole** usare Microsoft Update e fare clic su **Avanti.**

9. Nella pagina Inizio installazione fare clic su **Installa**.

10. Nella pagina Completamento dell'Installazione guidata di System Center Operations Manager fare clic su **Fine**.

11. Fare clic su **Exit**.

Per System Center 2012, è possibile verificare che l'agente sia stato creato facendo clic sul pulsante **Start,** scegliendo Tutti i **programmi,** **System Center Operations Manager 2012** e quindi facendo clic su **Operations 2012 Manager Shell.** In Operations Manager Shell digitare il comando Windows PowerShell seguente e quindi premere INVIO:
```PowerShell
Get-SCOMAgent
```

Verrà visualizzato un elenco di tutti gli agenti di Operations Manager.
## <a name="configuring-the-skype-for-business-server-computer-to-participate-in-system-center-discovery"></a>Configurazione del computer Skype for Business Server per partecipare all'individuazione di System Center
<a name="watcher_node_outside"> </a>

Per assicurarsi che il nuovo agente di Skype for Business Server partecipi al processo di individuazione per System Center Operations Manager, è necessario completare la procedura seguente in ogni computer in cui è stata installata la console di System Center Operations Manager:

1. Nella scheda Amministrazione fare clic su **Gestito tramite agente**.

2. Fare clic **su Individuazione guidata** e completare la procedura guidata per individuare il computer.

3. Riavviare il servizio Agente integrità. Il riavvio del servizio impone l'individuazione del nuovo computer. Se non si riavvia il servizio, potrebbero essere necessario fino a 4 ore prima che il nuovo computer venga individuato da System Center Operations Manager.

4. Verificare che nel registro eventi di Operations Manager non siano stati registrati eventi di errore.

5. Il computer in cui l'agente viene inserito correttamente verrà visualizzato nell'elenco "Agente gestito" e il computer in cui l'agente è stato installato manualmente verrà visualizzato in "Gestione in sospeso", fare clic sul nome del computer e approvare.

6. Fare clic con il pulsante destro del mouse sul nome del computer e scegliere **Proprietà**. Nella scheda Sicurezza della finestra di dialogo Proprietà selezionare **Consenti a questo agente di funzionare come proxy e individuare oggetti gestiti sugli altri computer**, quindi fare clic su **OK**.


