---
title: Configurare il server di gestione principale
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
description: 'Riepilogo: configurare il server di gestione principale, installare System Center Operations Manager e importare i Management Pack per Skype for Business Server 2019.'
ms.openlocfilehash: f7fd7350cb4cf5a9697e789806c963f4fbe46636
ms.sourcegitcommit: 6a87a4180519e493ac115c2faadb9ccae26d5a35
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/17/2021
ms.locfileid: "58372236"
---
# <a name="skype-for-business-server-configure-the-primary-management-server"></a>Skype for Business Server: Configurare il server di gestione principale

**Riepilogo:** Configurare il server di gestione principale, installare System Center Operations Manager e importare i Management Pack per Skype for Business Server 2019.

Per sfruttare al meglio le nuove funzionalità di monitoraggio dell'integrità incluse in Skype for Business Server 2019, è innanzitutto necessario designare un computer come server di gestione principale. È quindi necessario installare System Center Operations Manager 2012 SP1 o R2 o System Center Operations Manager 2007 R2 in tale computer. Inoltre, è necessario installare prima una versione supportata di SQL Server per funzionare come database back-end di Operations Manager.

Quando si installa System Center Operations Manager, è necessario installare tutti i componenti del prodotto, tra cui:

- Database operativo

- Server

- Console

- Cmdlet di Windows PowerShell

- Console Web

- Creazione di report

- Data warehouse

> [!IMPORTANT]
> Prima di installare Microsoft Report Viewer Operations Manager 2012, è necessario installare "Microsoft Report Viewer[2010 Redistributable](https://www.microsoft.com/download/details.aspx?id=6442)System Center Package".

Per informazioni dettagliate su questi prodotti e sulla relativa installazione, vedere i collegamenti seguenti:

- [System Center Operations Manager 2012](/previous-versions/system-center/system-center-2012-R2/hh205987(v=sc.12))

- [System Center Operations Manager 2007](https://technet.microsoft.com/library/bb735860.aspx)

Tenere presente che è possibile disporre di un solo server di gestione radice per Skype for Business Server distribuzione.

## <a name="importing-the-skype-for-business-server-2019-management-packs"></a>Importazione dei Management Pack Skype for Business Server 2019

È possibile estendere le funzionalità di System Center Operations Manager installando Management Pack, ovvero software che determina quali elementi System Center Operations Manager è in grado di monitorare, come devono essere monitorati e come devono essere attivati e segnalati gli avvisi. Skype for Business Server 2019 include due System Center Management Pack di Operations Manager che offrono le funzionalità seguenti:

- Component **and User Management Pack** (Microsoft.LS.2019.Monitoring.ComponentAndUser.mp) tiene traccia dei problemi di Skype for Business Server registrati nei registri eventi, registrati dai contatori delle prestazioni o registrati nei record dettagli chiamata (CDR) o nei database QoE (Quality of Experience). Per problemi critici, System Center Operations Manager può essere configurato in modo da inviare immediatamente una notifica agli amministratori tramite posta elettronica, messaggi istantanei o sms. SMS, o Servizio messaggi brevi, è la tecnologia utilizzata per inviare messaggi di testo da un dispositivo mobile a un altro.

    > [!NOTE]
    >  Per informazioni dettagliate sulla configurazione della notifica di Operations Manager, vedere [Configuring Notification.](/previous-versions/system-center/operations-manager-2007-r2/dd440890(v=technet.10))

- **Active Monitoring Management Pack** (Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp) testa in modo proattivo i principali componenti di Skype for Business Server, ad esempio l'accesso al sistema, lo scambio di messaggi istantanei o l'esecuzione di chiamate a un telefono situato sulla rete PSTN (Public Switched Telephone Network). Questi test vengono eseguiti utilizzando i cmdlet Skype for Business Server transazione sintetica. Il cmdlet **Test-CsIM** ad esempio viene utilizzato per simulare una conversazione istantanea tra due utenti di test. Se la conversazione simulata ha esito negativo, viene generato un avviso.

L'importazione dei Management Pack è un passaggio fondamentale. Se i Management Pack non vengono importati, non sarà possibile utilizzare Operations Manager per monitorare Skype for Business Server eventi o eseguire Skype for Business Server sintetiche.

Component and User Management Pack viene utilizzato per monitorare solo Skype for Business Server 2019. Se si è in uno scenario di coesistenza in cui sono installati sia Skype for Business Server 2019 che Skype for Business Server 2015, è consigliabile continuare a utilizzare i Management Pack di Skype for Business Server 2015 per i computer Skype for Business Server 2015.

> [!NOTE]
> I Management Pack per Skype for Business Server 2019 includono Skype for Business Server 2019 Component and User Management Pack e Skype for Business Server Active Monitoring Management Pack 2019.

È possibile utilizzare uno degli strumenti per importare i pacchetti di gestione:

- **System Center Operations Manager** Con questo metodo, si utilizza Operations Manager per aggiungere il monitoraggio per Skype for Business Server.

- **shell di Operations Manager** È possibile utilizzare il shell di Operations Manager per importare direttamente o per risolvere eventuali problemi riscontrati durante l'importazione dei Management Pack tramite la console di System Center Operations Manager.

### <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a>Importazione dei Management Pack tramite System Center Operations Manager

1. Scaricare il SkypeForBusiness2019ManagementPacks.msi dai download Web Microsoft e installare il file msi.

2. In System Center Operations Manager fare clic su **Amministrazione**.

3. Nel riquadro Amministrazione, fare clic con il tasto destro del mouse su **Management Pack**, e quindi su **Importa Management Pack**.

4. Nella finestra di dialogo **Seleziona Management Pack**, fare clic su **Aggiungi** e quindi su **Aggiungi da disco**.

5. Nella finestra **di dialogo Connessione** catalogo online fare clic su **No.**

6. Nella finestra **di dialogo Seleziona Management Pack** da importare individuare e selezionare i file Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp e Microsoft.LS.2019.Monitoring.ComponentAndUser.mp e quindi fare clic su **Apri**. Per selezionare più file nella finestra di dialogo, fare clic sul primo file e quindi tenere premuto CTRL e fare clic sui file successivi.

7. Nella finestra di dialogo **Seleziona Management Pack**, fare clic su **Installa**. Se compare un messaggio di errore e l'installazione ha esito negativo, molto probabilmente i file dei pacchetti di gestione si trovano in una cartella protetta da Controllo account utente di Windows. In questo caso, copiare i file in una cartella diversa e quindi riavviare il processo di importazione e installazione.

8. Nella finestra di dialogo **Seleziona Management Pack**, fare clic su **Chiudi**. Il completamento del processo di importazione e installazione potrebbe richiedere alcuni minuti.

## <a name="importing-the-management-packs-by-using-the-operations-manager-shell"></a>Importazione dei Management Pack tramite il shell di Operations Manager

In generale, è più semplice importare i Management Pack utilizzando la console di Operations Manager. Tuttavia, se si verifica un errore e l'importazione non riesce, la console non fornisce sempre segnalazioni di errori adeguate. In confronto, il shell di Operations Manager fornisce informazioni dettagliate. Se si utilizza Operations Manager e si verificano problemi durante l'importazione di un Management Pack, importarlo utilizzando il shell di Operations Manager. Le informazioni fornite da shell di Operations Manager consentono di determinare il motivo per cui l'importazione non è riuscita.

1. Fare clic sul pulsante **Start,** **scegliere** Tutti i programmi, **Microsoft System Center 2012,** **Operations Manager** e quindi fare clic su **shell di Operations Manager**.

2. In shell di Operations Manager digitare il comando seguente al prompt dei comandi, utilizzando il percorso effettivo della copia del file Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp e quindi premere INVIO:

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp"
   ```

3. Dopo aver importato il primo Management Pack, ripetere il processo utilizzando il percorso della copia del file Microsoft.LS.2019.Monitoring.ComponentAndUser.mp:

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2019.Monitoring.ComponentAndUser.mp"
   ```