---
title: Configurare il server di gestione primario
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
ms.assetid: c7e21cce-1dd2-489a-a2eb-f632799f7523
description: 'Riepilogo: configurare il server di gestione principale, installare System Center Operations Manager e importare Management Pack per Skype for Business Server 2015.'
ms.openlocfilehash: be7e484814e241b4aebb042a23497ed4806693e0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814866"
---
# <a name="configure-the-primary-management-server"></a>Configurare il server di gestione primario

**Riepilogo:** Configurare il server di gestione principale, installare System Center Operations Manager e importare Management Pack per Skype for Business Server 2015.

Per sfruttare al meglio le nuove funzionalità di monitoraggio dello stato incluse in Skype for Business Server 2015, è necessario prima di tutto designare un computer che funga da server di gestione primario. È quindi necessario installare System Center Operations Manager 2012 SP1 o R2 o System Center Operations Manager 2007 R2 nel computer in questione. Inoltre, è necessario innanzitutto installare una versione supportata di SQL Server per funzionare come database back-end di Operations Manager.

Quando si installa System Center Operations Manager, sarà necessario installare tutti i componenti del prodotto, tra cui:

- Database operativo

- Server

- Console

- Cmdlet di Windows PowerShell

- Console Web

- Creazione di report

- Data warehouse

> [!IMPORTANT]
> Prima di installare System Center Operations Manager 2012, è necessario che sia installato "[Microsoft Report Viewer 2010 Redistributable Package](https://www.microsoft.com/download/details.aspx?id=6442)".

Per informazioni dettagliate su questi prodotti e sull'installazione, vedere i seguenti collegamenti:

- [System Center Operations Manager 2012](https://go.microsoft.com/fwlink/p/?linkid=257527)

- [System Center Operations Manager 2007](https://technet.microsoft.com/library/bb735860.aspx)

Tenere presente che è possibile disporre di un solo server di gestione radice per la distribuzione di Skype for Business Server.

## <a name="importing-the-skype-for-business-server-2015-management-packs"></a>Importazione dei Management Pack di Skype for Business Server 2015

È possibile estendere le funzionalità di System Center Operations Manager installando Management Pack, ovvero software che determina quali elementi possono essere monitorati dal System Center Operations Manager, come devono essere monitorati gli elementi e come devono essere attivati e segnalati gli avvisi. Skype for Business Server 2015 include due Management Pack di System Center Operations Manager che offrono le seguenti funzionalità:

- **Il componente e l'User Management Pack** (Microsoft.ls.2015.Monitoring.ComponentAndUser.MP) tiene traccia dei problemi di Skype for Business Server registrati nei registri eventi, registrati dai contatori delle prestazioni, o sono stati registrati nei database di registrazione dettagli chiamata (CDRs) o nella qualità di esperienza (QoE). Per i problemi critici, System Center Operations Manager può essere configurato per informare immediatamente gli amministratori tramite la posta elettronica, il messaggio istantaneo o la messaggistica SMS. (SMS o Short Message Service) è la tecnologia utilizzata per inviare messaggi di testo da un dispositivo mobile a un altro.

    > [!NOTE]
    >  Per informazioni dettagliate sulla configurazione della notifica di Operations Manager, vedere [Configuring Notification](https://go.microsoft.com/fwlink/p/?LinkID=268785&amp;amp;clcid=0x409).

- **Active Monitoring Management Pack** (Microsoft.ls.2015.Monitoring.ActiveMonitoring.MP) verifica in modo proattivo i componenti principali di Skype for Business Server, ad esempio l'accesso al sistema, lo scambio di messaggi istantanei o la chiamata a un telefono che si trova nella rete PSTN (Public Switched Telephone Network). Questi test vengono eseguiti utilizzando i cmdlet per le transazioni sintetiche di Skype for Business Server. Il cmdlet **Test-CsIM** ad esempio viene utilizzato per simulare una conversazione istantanea tra due utenti di test. Se la conversazione simulata ha esito negativo, viene generato un avviso.

L'importazione dei Management Pack è un passaggio cruciale. Se i Management Pack non vengono importati, non sarà possibile utilizzare Operations Manager per monitorare gli eventi di Skype for Business Server o eseguire transazioni sintetiche di Skype for Business Server.

Il componente e il Management Pack utente vengono utilizzati per monitorare solo Skype for Business Server 2015. Se si è in uno scenario di coesistenza in cui sono installati sia Skype for Business Server 2015 che Lync Server 2013, è consigliabile continuare a utilizzare Lync Server 2013 Management Pack per i computer Lync Server 2013.

> [!NOTE]
> I Management Pack per Skype for Business Server 2015 includono il componente Skype for Business Server 2015 e il Management Pack di utenti e Skype for Business Server 2015 Active Monitoring Management Pack.

È possibile utilizzare uno degli strumenti per importare i pacchetti di gestione:

- **System Center Operations Manager** Con questo metodo, è possibile utilizzare Operations Manager per aggiungere il monitoraggio per Skype for Business Server.

- **Shell di Operations Manager** È possibile utilizzare la shell di Operations Manager per importare direttamente o per risolvere eventuali problemi che si verificano quando si importano i Management Pack tramite la console di System Center Operations Manager.

### <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a>Importazione dei Management Pack tramite System Center Operations Manager

1. Scaricare il SkypeForBusiness2015ManagementPacks.msi dai download di Microsoft Web e installare MSI.

2. In System Center Operations Manager fare clic su **Amministrazione**.

3. Nel riquadro Amministrazione, fare clic con il tasto destro del mouse su **Management Pack**, e quindi su **Importa Management Pack**.

4. Nella finestra di dialogo **Seleziona Management Pack**, fare clic su **Aggiungi** e quindi su **Aggiungi da disco**.

5. Nella finestra di dialogo **connessione Catalogo online** fare clic su **No**.

6. Nella finestra di dialogo **Seleziona Management Pack da importare** individuare e selezionare i file Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp e Microsoft.ls.2015.Monitoring.ComponentAndUser.MP e quindi fare clic su **Apri**. Per selezionare più file nella finestra di dialogo, fare clic sul primo file, quindi tenere premuto il tasto CTRL e fare clic sui file successivi.

7. Nella finestra di dialogo **Seleziona Management Pack**, fare clic su **Installa**. Se compare un messaggio di errore e l'installazione ha esito negativo, molto probabilmente i file dei pacchetti di gestione si trovano in una cartella protetta da Controllo account utente di Windows. In tal caso, copiare i file in una cartella diversa e quindi riavviare il processo di importazione e installazione.

8. Nella finestra di dialogo **Seleziona Management Pack**, fare clic su **Chiudi**. Il processo di importazione e installazione potrebbe richiedere alcuni minuti per il completamento.

## <a name="importing-the-management-packs-by-using-the-operations-manager-shell"></a>Importazione dei Management Pack tramite la shell di Operations Manager

In generale, è più facile importare i Management Pack tramite la console di Operations Manager. Tuttavia, se si verifica un errore e l'importazione ha esito negativo, la console non fornisce sempre segnalazioni di errori adeguate. In base al confronto, Operations Manager Shell fornisce informazioni dettagliate. Se si utilizza Operations Manager e si verificano problemi durante l'importazione di un Management Pack, importare il pacchetto tramite la shell di Operations Manager. Le informazioni fornite dalla shell di Operations Manager consentono di determinare il motivo per cui l'importazione ha avuto esito negativo.

1. Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft System Center 2012**, fare clic su **Operations Manager** e quindi fare clic su **Operations Manager Shell**.

2. In Operations Manager Shell, digitare il comando seguente al prompt dei comandi, utilizzando il percorso effettivo della copia del file Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp e quindi premere INVIO:

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp"
   ```

3. Dopo aver importato il primo Management Pack, ripetere il processo utilizzando il percorso della copia del file Microsoft.LS.2015.Monitoring.ComponentAndUser.mp:

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2015.Monitoring.ComponentAndUser.mp"
   ```
