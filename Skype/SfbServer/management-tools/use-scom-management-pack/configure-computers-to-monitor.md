---
title: Configurare i Skype for Business Server computer da monitorare
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: b24ea184-4b3e-4277-a244-157afb4b368b
description: "Riepilogo: installare i file dell'agente Operations Manager nel computer Skype for Business Server 2015 da monitorare e configurare il computer in modo che funzioni come proxy System Center locale."
ms.openlocfilehash: aa876d18ad597c911c7b0c9bea373a10c33f6858
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60778116"
---
# <a name="configure-the-skype-for-business-server-computers-to-monitor"></a>Configurare i Skype for Business Server computer da monitorare

**Riepilogo:** Installare i file dell'agente Operations Manager nel computer Skype for Business Server 2015 da monitorare e configurare il computer in modo che agirà come proxy System Center 2015.

Ogni Skype for Business Server 2015 che si desidera monitorare deve essere in grado di segnalare autonomamente l'esistenza al server di gestione. Per abilitare questo processo, è necessario installare i file dell'agente Operations Manager in ognuno dei computer da monitorare. Dopo aver installato i file dell'agente, è necessario configurare il computer in modo che agirà come proxy System Center proxy. Prima di eseguire queste procedure, assicurarsi di aver installato e Skype for Business Server in questi computer.

## <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network"></a>Installazione di un certificato in un nodo Watcher posizionato all'esterno del perimetro della rete
<a name="watcher_node_outside"> </a>

System Center Gli agenti di Operations Manager in esecuzione in una rete perimetrale (ad esempio un server perimetrale di Skype for Business Server), all'esterno dell'organizzazione (ad esempio un nodo External Synthetic Transaction Watcher) o attraverso un limite di trust di Active Directory, possono richiedere la configurazione di un server gateway di System Center Operations Manager. Questo ruolo del server consente agli agenti che non hanno una relazione di trust con il server di gestione radice di generare avvisi. Per informazioni dettagliate, [vedere Managing Gateway Servers in Operations Manager 2012](/previous-versions/system-center/system-center-2012-R2/hh212823(v=sc.12)).

Se si distribuisce un agente in una di queste posizioni, sarà inoltre necessario richiedere e configurare un certificato che consenta al nodo Watcher di inviare avvisi a System Center Operations Manager. Per semplificare questo processo, il team di Operations Manager ha creato un set di utilità che consente di richiedere e installare il tipo di certificato corretto nel computer del nodo di controllo. Per informazioni dettagliate e per scaricare queste utilità, vedere [Obtaining Certificates for Non-Domain Joined Agents Made Easy With Certificate Generation Wizard](https://techcommunity.microsoft.com/t5/system-center-blog/obtaining-certificates-for-non-domain-joined-agents-made-easy/ba-p/340467).

### <a name="installing-the-operation-manager-agent-files"></a>Installazione dei file dell'agente Operations Manager

1. Nel supporto System Center di installazione fare doppio clic su **Setup.exe**.

2. Nell'System Center guidata di Operation Manager fare clic su **Installa agente Operations Manager** da Installa agente in Installazioni facoltative

3. Nella pagina System Center installazione guidata di System Center Operations Manager fare clic su **Avanti.**

4. Nella pagina Cartella di destinazione selezionare la cartella in cui verranno installati i file dell'agente Operations Manager e fare clic su **Avanti.**

5. Nella pagina Configurazione gruppo di gestione selezionare Specifica **informazioni gruppo di gestione e** fare clic su **Avanti.**

6. Nella pagina Configurazione gruppo di gestione digitare il nome del gruppo di gestione di Operations Manager nella casella **Nome gruppo di gestione** e quindi digitare il nome host del server Operations Manager (ad esempio, atl-scom-001) nella casella **Server di gestione**. Se è stato modificato il numero di porta utilizzato da Operations Manager, immettere il nuovo numero di porta nella casella **Porta server di** gestione. In caso contrario, lasciare la porta sul valore predefinito 5723 e quindi fare clic su **Avanti.**

7. Nella pagina Account azione agente selezionare **Sistema locale** e fare clic su **Avanti.**

8. Nella pagina Microsoft Update selezionare **Non si desidera utilizzare Microsoft Update** e fare clic su **Avanti.**

9. Nella pagina Inizio installazione fare clic su **Installa**.

10. Nella pagina Completamento dell'Installazione guidata di System Center Operations Manager fare clic su **Fine**.

11. Fare clic su **Exit**.

Per System Center 2012, è possibile verificare che l'agente sia stato creato facendo clic sul pulsante **Start**, scegliendo Tutti i programmi **,** facendo clic su System Center Operations Manager **2012** e quindi su **Operations 2012 Manager Shell**. Nella casella shell di Operations Manager digitare il comando Windows PowerShell seguente e quindi premere INVIO:
```PowerShell
Get-SCOMAgent
```

Verrà visualizzato un elenco di tutti gli agenti di Operations Manager.
## <a name="configuring-the-skype-for-business-server-computer-to-participate-in-system-center-discovery"></a>Configurazione del computer Skype for Business Server per partecipare all'System Center individuazione
<a name="watcher_node_outside"> </a>

Per assicurarsi che il nuovo agente di Skype for Business Server partecipi al processo di individuazione per System Center Operations Manager, è necessario completare la procedura seguente in ogni computer in cui è stata installata la console di System Center Operations Manager:

1. Nella scheda Amministrazione fare clic su **Gestito tramite agente**.

2. Fare clic **su Individuazione guidata** e completare la procedura guidata per il computer da individuare.

3. Riavviare il servizio Agente integrità. Il riavvio del servizio forza l'individuazione del nuovo computer. Se non si riavvia il servizio, potrebbero essere necessario fino a 4 ore prima che il nuovo computer venga individuato da System Center Operations Manager.

4. Verificare che nel registro eventi di Operations Manager non siano stati registrati eventi di errore.

5. Il computer in cui l'agente viene inserito correttamente verrà visualizzato nell'elenco "Gestito dall'agente" e il computer in cui l'agente è stato installato manualmente verrà visualizzato in "Gestione in sospeso", fare clic sul nome del computer e approvare.

6. Fare clic con il pulsante destro del mouse sul nome del computer e scegliere **Proprietà**. Nella scheda Sicurezza della finestra di dialogo Proprietà selezionare **Consenti a questo agente di funzionare come proxy e individuare oggetti gestiti sugli altri computer**, quindi fare clic su **OK**.