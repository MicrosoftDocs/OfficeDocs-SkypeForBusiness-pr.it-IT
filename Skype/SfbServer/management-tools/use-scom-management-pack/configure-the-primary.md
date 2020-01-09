---
title: Configurare il server di gestione primario
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c7e21cce-1dd2-489a-a2eb-f632799f7523
description: 'Riepilogo: configurare il server di gestione principale, installare System Center Operations Manager e importare Management Pack per Skype for Business Server 2015.'
ms.openlocfilehash: adee7ef72e6b59854e2b458aa33fdb4880923eed
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992463"
---
# <a name="configure-the-primary-management-server"></a>Configurare il server di gestione primario

**Riepilogo:** Configurare il server di gestione principale, installare System Center Operations Manager e importare Management Pack per Skype for Business Server 2015.

Per sfruttare al meglio le nuove funzionalità di monitoraggio dell'integrità incluse in Skype for Business Server 2015, è prima di tutto necessario designare un computer per fungere da server di gestione principale. È quindi necessario installare System Center Operations Manager 2012 SP1 o R2 o System Center Operations Manager 2007 R2 in tale computer. Inoltre, devi prima installare una versione supportata di SQL Server in modo che funzioni come database back-end di Operations Manager.

Quando si installa System Center Operations Manager, sarà necessario installare tutti i componenti di tale prodotto, tra cui:

- Database operativo

- Server

- Console

- Cmdlet di Windows PowerShell

- Console Web

- Reporting

- Data warehouse

> [!IMPORTANT]
> Per installare System Center Operations Manager 2012 è necessario installare "[Microsoft Report Viewer 2010 Redistributable Package](https://www.microsoft.com/en-us/download/details.aspx?id=6442)".

Per informazioni dettagliate su questi prodotti e sulla relativa installazione, vedere i collegamenti seguenti:

- [System Center Operations Manager 2012](https://go.microsoft.com/fwlink/p/?linkid=257527)

- [System Center Operations Manager 2007](https://technet.microsoft.com/en-us/library/bb735860.aspx)

Tieni presente che puoi avere un solo server di gestione radice per la distribuzione di Skype for Business Server.

## <a name="importing-the-skype-for-business-server-2015-management-packs"></a>Importazione dei Management Pack di Skype for Business Server 2015

Per estendere le funzionalità di System Center Operations Manager, è possibile installare Management Pack, ovvero il software che stabilisce quali elementi possono essere monitorati da System Center Operations Manager, come devono essere monitorati gli elementi e come devono essere attivati gli avvisi e segnalato. Skype for Business Server 2015 include due Management Pack di System Center Operations Manager che fornisce le funzionalità seguenti:

- **Il componente e l'User Management Pack** (Microsoft.ls.2015.Monitoring.ComponentAndUser.MP) registra i problemi di Skype for Business Server registrati nei registri eventi, registrati dai contatori delle prestazioni, oppure registrati nei database dei dettagli delle chiamate (CDRs) o nei dati QoE (Quality of Experience). Per problemi critici, System Center Operations Manager può essere configurato per comunicare immediatamente agli amministratori tramite posta elettronica, messaggi istantanei o messaggi SMS. (SMS o Short Message Service) è la tecnologia usata per inviare SMS da un dispositivo mobile a un altro.

    > [!NOTE]
    >  Per informazioni dettagliate sulla configurazione della notifica di Operations Manager, vedere [configurazione della notifica](https://go.microsoft.com/fwlink/p/?LinkID=268785&amp;amp;clcid=0x409).

- **Active Monitoring Management Pack** (Microsoft.ls.2015.Monitoring.ActiveMonitoring.MP) verifica in modo proattivo i componenti principali di Skype for Business Server, ad esempio l'accesso al sistema, lo scambio di messaggi istantanei o la chiamata a un telefono che si trova nella rete PSTN (Public Switched Telephone Network). Questi test vengono condotti usando i cmdlet di transazione sintetica di Skype for Business Server. Ad esempio, il cmdlet **Test-CsIM** viene usato per simulare una conversazione di messaggistica istantanea tra una coppia di utenti di test. Se la conversazione simulata non riesce, viene generato un avviso.

L'importazione dei Management Pack è un passaggio cruciale. Se i Management Pack non vengono importati, non sarà possibile usare Operations Manager per monitorare gli eventi di Skype for Business Server o eseguire transazioni sintetiche di Skype for Business Server.

Il Management Pack per i componenti e gli utenti viene usato per monitorare solo Skype for Business Server 2015. Se si è in uno scenario di coesistenza in cui sono installati sia Skype for Business Server 2015 che Lync Server 2013, è necessario continuare a usare i Management Pack di Lync Server 2013 per i computer di Lync Server 2013.

> [!NOTE]
> I Management Pack per Skype for Business Server 2015 includono il componente Skype for Business Server 2015 e il Management Pack utenti di Skype for Business Server 2015 Active Monitoring Management Pack.

È possibile usare uno degli strumenti seguenti per importare i Management Pack:

- **System Center Operations Manager** Con questo metodo, puoi usare Operations Manager per aggiungere il monitoraggio per Skype for Business Server.

- **Shell di Operations Manager** È possibile usare la shell di Operations Manager per importare direttamente o per risolvere eventuali problemi che si verificano quando si importano i Management Pack tramite la console di System Center Operations Manager.

### <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a>Importazione di Management Pack tramite System Center Operations Manager

1. Scaricare il file SkypeForBusiness2015ManagementPacks. msi dai download di Microsoft Web e installare MSI.

2. In System Center Operations Manager fare clic su **Amministrazione**.

3. Nel riquadro Amministrazione fare clic con il pulsante destro del mouse su **Management Pack**e quindi scegliere **Importa Management Pack**.

4. Nella finestra di dialogo **Seleziona Management Pack** fare clic su **Aggiungi**e quindi su **Aggiungi da disco**.

5. Nella finestra di dialogo **connessione Catalogo online** fare clic su **No**.

6. Nella finestra **di dialogo Seleziona Management Pack da importare** individuare e selezionare i file Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp e Microsoft.ls.2015.Monitoring.ComponentAndUser.MP e quindi fare clic su **Apri**. Per selezionare più file nella finestra di dialogo, fare clic sul primo file e quindi tenere premuto il tasto CTRL e fare clic sui file successivi.

7. Nella finestra di dialogo **Seleziona Management Pack** fare clic su **Installa**. Se viene visualizzato un messaggio di errore e l'installazione non riesce, significa in genere che i file del Management Pack si trovano in una cartella protetta dal controllo dell'account utente di Windows. In questo caso, copiare i file in un'altra cartella e quindi riavviare il processo di importazione e installazione.

8. Nella finestra di dialogo **Seleziona Management Pack** fare clic su **Chiudi**. Il processo di importazione e installazione potrebbe richiedere diversi minuti per il completamento.

## <a name="importing-the-management-packs-by-using-the-operations-manager-shell"></a>Importazione di Management Pack tramite la shell di Operations Manager

In generale, è più semplice importare i Management Pack tramite la console di Operations Manager. Tuttavia, se si verifica un errore e l'importazione non riesce, la console non sempre fornisce rapporti di errore adeguati. In base al confronto, Operations Manager Shell offre informazioni dettagliate. Se si usa Operations Manager e si verificano problemi durante l'importazione di un Management Pack, importare il pacchetto tramite Operations Manager Shell. Le informazioni fornite da Operations Manager Shell consentono di determinare il motivo per cui l'importazione non è riuscita.

1. Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Microsoft System Center 2012**, fare clic su **Operations Manager**e quindi su **Operations Manager Shell**.

2. In Operations Manager Shell digitare il comando seguente al prompt dei comandi, usando il percorso effettivo della copia del file Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp e quindi premere INVIO:

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp"
   ```

3. Dopo aver importato il primo Management Pack, ripetere il processo usando il percorso per la copia del file Microsoft.LS.2015.Monitoring.ComponentAndUser.mp:

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2015.Monitoring.ComponentAndUser.mp"
   ```
