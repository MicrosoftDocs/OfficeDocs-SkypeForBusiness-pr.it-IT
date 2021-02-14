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
description: 'Riepilogo: configurare il server di gestione principale, installare System Center Operations Manager e importare Management Pack per Skype for Business Server 2019.'
ms.openlocfilehash: 872459f99f2e620d3d34db1196a8618476650c98
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806066"
---
# <a name="configure-the-primary-management-server"></a>Configurare il server di gestione primario

**Riepilogo:** Configurare il server di gestione principale, installare System Center Operations Manager e importare Management Pack per Skype for Business Server 2019.

Per sfruttare al meglio le nuove funzionalità di monitoraggio dello stato incluse in Skype for Business Server 2019, è necessario innanzitutto designare un computer che agirà come server di gestione principale. È quindi necessario installare System Center Operations Manager 2012 SP1 o R2 o System Center Operations Manager 2007 R2 in tale computer. È inoltre necessario installare una versione supportata di SQL Server per funzionare come database back-end di Operations Manager.

Quando si installa System Center Operations Manager, sarà necessario installare tutti i componenti del prodotto, tra cui:

- Database operativo

- Server

- Console

- Cmdlet di Windows PowerShell

- Console Web

- Creazione di report

- Data warehouse

> [!IMPORTANT]
> È necessario[installare " Microsoft Report Viewer 2010 Redistributable Package"](https://www.microsoft.com/download/details.aspx?id=6442)prima di installare System Center Operations Manager 2012.

Per informazioni dettagliate su questi prodotti e sulla relativa installazione, vedere i collegamenti seguenti:

- [System Center Operations Manager 2012](https://go.microsoft.com/fwlink/p/?linkid=257527)

- [System Center Operations Manager 2007](https://technet.microsoft.com/library/bb735860.aspx)

Tieni presente che puoi avere un solo server di gestione radice per ogni distribuzione di Skype for Business Server.

## <a name="importing-the-skype-for-business-server-2019-management-packs"></a>Importazione dei Management Pack di Skype for Business Server 2019

È possibile estendere le funzionalità di System Center Operations Manager installando Management Pack, ovvero software che determina gli elementi che System Center Operations Manager può monitorare, come devono essere monitorati e come devono essere attivati e segnalati gli avvisi. Skype for Business Server 2019 include due Management Pack di System Center Operations Manager che offrono le seguenti funzionalità:

- Component **and User Management Pack** (Microsoft.LS.2019.Monitoring.ComponentAndUser.mp) tiene traccia dei problemi di Skype for Business Server registrati nei registri eventi, registrati dai contatori delle prestazioni o registrati nei database delle registrazioni dettagli chiamata (CDR) o QoE (Quality of Experience). Per problemi critici, System Center Operations Manager può essere configurato per inviare immediatamente una notifica agli amministratori tramite posta elettronica, messaggi istantanei o messaggi SMS. Sms, o Short Message Service, è la tecnologia utilizzata per inviare messaggi di testo da un dispositivo mobile a un altro.

    > [!NOTE]
    >  Per informazioni dettagliate sulla configurazione della notifica di Operations Manager, vedere [Configuring Notification.](https://go.microsoft.com/fwlink/p/?LinkID=268785&amp;amp;clcid=0x409)

- **Active Monitoring Management Pack** (Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp) verifica in modo proattivo i principali componenti di Skype for Business Server, ad esempio l'accesso al sistema, lo scambio di messaggi istantanei o l'esecuzione di chiamate a un telefono situato nella rete PSTN (Public Switched Telephone Network). Questi test vengono eseguiti utilizzando i cmdlet per le transazioni sintetiche di Skype for Business Server. Il cmdlet **Test-CsIM** ad esempio viene utilizzato per simulare una conversazione istantanea tra due utenti di test. Se la conversazione simulata non riesce, viene generato un avviso.

L'importazione dei Management Pack è un passaggio fondamentale. Se i Management Pack non vengono importati, non sarà possibile utilizzare Operations Manager per monitorare gli eventi di Skype for Business Server o eseguire transazioni sintetiche di Skype for Business Server.

Il Management Pack componenti e utenti viene utilizzato per monitorare solo Skype for Business Server 2019. In uno scenario di coesistenza in cui sono installati sia Skype for Business Server 2019 che Skype for Business Server 2015, è consigliabile continuare a usare i Management Pack di Skype for Business Server 2015 per i computer Skype for Business Server 2015.

> [!NOTE]
> I Management Pack per Skype for Business Server 2019 includono Skype for Business Server 2019 Component and User Management Pack e Skype for Business Server 2019 Active Monitoring Management Pack.

È possibile utilizzare uno degli strumenti per importare i pacchetti di gestione:

- **System Center Operations Manager** Con questo metodo, si usa Operations Manager per aggiungere il monitoraggio per Skype for Business Server.

- **Operations Manager Shell** È possibile utilizzare Operations Manager Shell per importare direttamente o per risolvere eventuali problemi riscontrati durante l'importazione dei Management Pack utilizzando la console di System Center Operations Manager.

### <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a>Importazione dei Management Pack tramite System Center Operations Manager

1. Scaricare il SkypeForBusiness2019ManagementPacks.msi dai download Web Microsoft e installare il file msi.

2. In System Center Operations Manager fare clic su **Amministrazione.**

3. Nel riquadro Amministrazione, fare clic con il tasto destro del mouse su **Management Pack**, e quindi su **Importa Management Pack**.

4. Nella finestra di dialogo **Seleziona Management Pack**, fare clic su **Aggiungi** e quindi su **Aggiungi da disco**.

5. Nella finestra **di dialogo Connessione catalogo** online fare clic su **No.**

6. Nella finestra di dialogo Seleziona **Management Pack** da importare individuare e selezionare i Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp e Microsoft.LS.2019.Monitoring.ComponentAndUser.mp e quindi fare clic su **Apri**. Per selezionare più file nella finestra di dialogo, fare clic sul primo file e quindi tenere premuto CTRL e fare clic sui file successivi.

7. Nella finestra di dialogo **Seleziona Management Pack**, fare clic su **Installa**. Se compare un messaggio di errore e l'installazione ha esito negativo, molto probabilmente i file dei pacchetti di gestione si trovano in una cartella protetta da Controllo account utente di Windows. In questo caso, copiare i file in una cartella diversa e quindi riavviare il processo di importazione e installazione.

8. Nella finestra di dialogo **Seleziona Management Pack**, fare clic su **Chiudi**. Il completamento del processo di importazione e installazione potrebbe richiedere alcuni minuti.

## <a name="importing-the-management-packs-by-using-the-operations-manager-shell"></a>Importazione dei Management Pack tramite Operations Manager Shell

In generale, è più semplice importare i Management Pack utilizzando la console di Operations Manager. Tuttavia, se si verifica un errore e l'importazione non riesce, la console non sempre fornisce segnalazioni di errori adeguate. Per confronto, Operations Manager Shell fornisce informazioni dettagliate. Se si utilizza Operations Manager e si verificano problemi durante l'importazione di un Management Pack, importare il pacchetto utilizzando La shell di Operations Manager. Le informazioni fornite da Operations Manager Shell consentono di determinare il motivo per cui l'importazione non è riuscita.

1. Fare **clic sul pulsante Start,** scegliere Tutti i programmi, Microsoft System Center **2012,** **Operations Manager** e quindi **Operations Manager Shell.** 

2. In Operations Manager Shell digitare il comando seguente al prompt dei comandi, utilizzando il percorso effettivo della copia del file Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp, quindi premere INVIO:

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp"
   ```

3. Dopo aver importato il primo Management Pack, ripetere il processo utilizzando il percorso della copia del file Microsoft.LS.2019.Monitoring.ComponentAndUser.mp:

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2019.Monitoring.ComponentAndUser.mp"
   ```
