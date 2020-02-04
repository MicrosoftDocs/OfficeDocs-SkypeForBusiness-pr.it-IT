---
title: 'Lync Server 2013: uso di Microsoft SQL Server 2008 R2 come database di Operations Manager di System Center'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Microsoft SQL Server 2008 R2 as your System Center Operations Manager database
ms:assetid: 0efe76da-8854-499e-bdc7-3623244a8e85
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687969(v=OCS.15)
ms:contentKeyID: 49733555
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27516e7ca6c3fb70a01b7c1d245054d515ae351b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744056"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-microsoft-sql-server-2008-r2-as-your-system-center-operations-manager-database-for-lync-server-2013"></a>Uso di Microsoft SQL Server 2008 R2 come database di Operations Manager di System Center per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-07-29_

Per usare SQL Server 2008 R2 come database back-end, completare la procedura descritta in questo argomento.

<div>

## <a name="configuring-sql-server-2008-r2-and-sql-server-reporting-services"></a>Configurazione di SQL Server 2008 R2 e SQL Server Reporting Services

Prima di iniziare l'installazione di System Center Operations Manager, è necessario apportare due modifiche a SQL Server 2008 R2 e alla configurazione di SQL Server Reporting Services. Queste modifiche sono necessarie solo se si usa SQL Server 2008 R2 come database di Operations Manager. Eseguire innanzitutto le operazioni seguenti nel computer che ospita il database di Operations Manager:

1.  Fare clic sul pulsante **Start** e quindi su **Esegui**.

2.  Nella finestra di dialogo **Esegui** Digitare **C:\\Program Files\\Microsoft SQL Server\\ MSRS10\_50. ARCHINST\\Reporting Services\\ReportServer** e quindi premere INVIO.

3.  Nella cartella **ReportServer** aprire il file **RSReportServer. config** nel blocco note o in qualsiasi altro editor di testo.

4.  Accanto all'inizio del file verrà visualizzata una serie di nodi "Aggiungi chiave". Trovare la voce che inizia ** \<Add Key = "SecureConnectionLevel"** e impostare il valore su **0**:
    
        <Add Key="SecureConnectionLevel" Value="0"/>

5.  Salvare il file **RSReportServer. config** e quindi chiudere l'editor di testo.

Dopo l'aggiornamento del file di configurazione del server di report, è necessario assegnare il certificato corretto a SQL Server Reporting Services. per farlo:

1.  Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft SQL Server 2008 R2**, fare clic su **strumenti di configurazione**e quindi su **Gestione configurazione di Reporting Services**.

2.  Nella finestra di dialogo **connessione configurazione Reporting Services** verificare che il nome del server sia visualizzato nella casella **nome server** . Selezionare l'istanza di SQL Server che ospiterà il database di Operations Manager, ad esempio **ARCHINST**, nell'elenco a discesa **istanza del server di report** e quindi fare clic su **Connetti**.

3.  In Gestione configurazione di Reporting Services fare clic su **URL servizio Web**.

4.  Nella pagina **URL servizio Web** selezionare il certificato da usare per Reporting Services dall'elenco a discesa **certificati SSL** e quindi fare clic su **applica**. Dopo alcuni secondi verrà visualizzata una coppia di URL elencati in **URL servizio Web**ReportServer.

5.  Fare clic su entrambi gli URL per verificare che sia possibile accedere a SQL Server Reporting Services.

6.  Chiudere Gestione configurazione di Reporting Services.

</div>

<div>

## <a name="creating-a-system-center-operations-manager-database-for-use-with-sql-server-2008-r2"></a>Creazione di un database di System Center Operations Manager da usare con SQL Server 2008 R2

Se si vuole configurare System Center Operations Manager per l'uso di un database di SQL Server 2008 R2, sarà necessario "manualmente" creare il database di Operations Manager nel computer in cui è installato SQL Server 2008 R2. Di nuovo, questi passaggi non sono necessari se si usa SQL Server 2005 o SQL Server 2008 come database back-end.

Per creare manualmente un database di Operations Manager, eseguire le operazioni seguenti:

1.  Nel supporto di configurazione di System Center Operations Manager 2007 R2, nella cartella\\SupportTools amd64, fare doppio clic su **DBCreateWizard. exe**.

2.  Nella schermata **Introduzione alla configurazione** guidata database della configurazione guidata database fare clic su **Avanti**.

3.  Nella pagina **informazioni database** uscire da tutte le impostazioni e quindi fare clic su **Avanti**

4.  Nella pagina **Configurazione gruppo di gestione** Digitare un nome per il gruppo di gestione, ad esempio **il monitoraggio di Lync Server**, nella casella **nome gruppo** di gestione e quindi fare clic su **Avanti**.

5.  Nella pagina **report di errore di Operations Manager** fare clic su **Avanti**.

6.  Nella pagina di **Riepilogo** fare clic su **fine**.

</div>

<div>

## <a name="creating-a-system-center-operations-manager-data-warehouse-for-use-with-sql-server-2008-r2"></a>Creazione di un data warehouse di System Center Operations Manager da usare con SQL Server 2008 R2

Microsoft Lync Server 2013 viene fornito con tre nuovi report di Operations Manager di System Center:

  - **Report disponibilità scenario finale**   questo report descrive in dettaglio la disponibilità/uptime dei servizi principali di Lync Server, ad esempio registrazione o presenza.

  - **Report capacità con**   le informazioni sui contatori delle prestazioni, questo report Mostra le tendenze per i componenti di sistema, ad esempio la disponibilità della memoria e l'uso del processore

  - **Report componente questo**   report elenca i generatori di avvisi principali raggruppati in base al componente Lync Server.

Per usare questi nuovi report, è necessario installare un data warehouse di System Center Operations Manager. Un data warehouse consente l'archiviazione a lungo termine dei dati delle operazioni. Per usare un data warehouse con SQL Server 2008 R2, è necessario eseguire la procedura seguente nel computer che ospita il database di SQL Server:

1.  Nel supporto di configurazione di System Center Operations Manager, nella cartella\\Setup\\SupportTools amd64, fare doppio clic su **DBCreateWizard. exe**.

2.  Nella schermata **Introduzione alla configurazione** guidata database della configurazione guidata database fare clic su **Avanti**.

3.  Nella pagina **informazioni database** selezionare **database warehouse dei dati di Operations Manager** dall'elenco a discesa **tipo di database** e quindi fare clic su **Avanti**.

4.  Nella pagina di **Riepilogo** fare clic su **fine**.

</div>

<div>

## <a name="installing-the-system-center-operations-manager-console"></a>Installazione della console di System Center Operations Manager

La console di Operations Manager è lo strumento principale usato per gestire System Center Operations Manager. Prima di installare la console di Operations Manager, verificare di avere installato una versione supportata di SQL Server insieme a SQL Server Reporting Services. Si consiglia inoltre di eseguire Gestione configurazione di Reporting Services di SQL Server per verificare che il servizio Reporting sia stato installato e configurato correttamente.

Per installare la console di System Center Operations Manager:

1.  Nel supporto di configurazione di System Center Operations Manager fare doppio clic su **SetupOM. exe**.

2.  Nella configurazione di System Center Operations Manager 2007 R2 fare clic su **Controlla prerequisiti**.

3.  Nel Visualizzatore prerequisiti di System Center Operations Manager selezionare i componenti di System Center da installare: (**Server**; **Console**; e **PowerShell**), quindi fare clic su **Controlla**. Verificare che non siano stati segnalati problemi di blocco e quindi fare clic su **Chiudi**. Se è stato segnalato un problema di blocco, correggere il problema e quindi fare clic su **Verifica** per eseguire di nuovo il test dei prerequisiti.

4.  In configurazione di System Center Operations Manager fare clic su **Installa Operations Manager**.

5.  Nella configurazione guidata di System Center Operations Manager, nella pagina **Introduzione alla configurazione guidata di System Center Operations Manager** , fare clic su **Avanti**.

6.  Nella pagina **contratto di licenza con l'utente finale** selezionare **Accetto i termini del contratto di licenza** e quindi fare clic su **Avanti**.

7.  Nella pagina di **registrazione del prodotto** Digitare il proprio nome nella casella **nome utente** e nome dell'organizzazione nella casella **organizzazione** . Digitare il codice Product Key di System Center Operations Manager nella casella **immettere il codice CD di 25 cifre** e quindi fare clic su **Avanti**.

8.  Nella pagina **configurazione personalizzata** selezionare le opzioni di System Center da installare e quindi fare clic su **Avanti**. È consigliabile selezionare **server di gestione**, **interfacce utente**e **console Web** per l'installazione. Il **database** non deve essere selezionato e non deve essere installato.

9.  Nella pagina dell' **istanza del server di database SC** verificare che nella casella **Server System Center database** sia visualizzato il nome del computer in cui sono installati i database di Operations Manager. Fare clic su **Avanti**.

10. Nella pagina **account azione del server di gestione** selezionare **dominio o account del computer locale** e quindi immettere i valori appropriati nelle caselle **account utente**, **password**e **dominio o computer locale** . Fare clic su **Avanti**.

11. Nella pagina **account del servizio SDK e configurazione** selezionare **dominio o account del computer locale** e quindi immettere i valori appropriati nelle caselle **account utente**, **password**e **dominio o computer locale** . Fare clic su **Avanti**.

12. Nella pagina **report di errore di Operations Manager** fare clic su **Avanti**.

13. Nella pagina del **programma Analisi utilizzo software** fare clic su **Avanti**.

14. Nella pagina **pronto per l'installazione del programma** fare clic su **Installa**.

15. Nella pagina **completamento della configurazione di System Center Operations Manager** deselezionare la **chiave di crittografia backup** e **avviare le caselle** di controllo della console e quindi fare clic su **fine**.

16. Nella configurazione di System Center Operations Manager fare clic su **Esci**.

</div>

<div>

## <a name="installing-system-center-reporting-services"></a>Installazione di System Center Reporting Services

Dopo l'installazione e la configurazione della console di System Center Operations Manager, è necessario installare System Center Reporting Services. Se si usa SQL Server 2008 R2 come database back-end di Operations Manager, ciò significa che è necessario prima apportare una modifica temporanea al gruppo di sicurezza associato a SQL Server Reporting Services. Se si usa SQL Server 2008 R2, è necessario eseguire le operazioni seguenti:

1.  Fare clic sul pulsante **Start**, scegliere **strumenti di amministrazione**e quindi fare clic su **Gestione server**.

2.  In Server Manager espandere **configurazione**, espandere **utenti e gruppi locali**e quindi fare clic su **gruppi**.

3.  Individuare il gruppo seguente, in cui ATL-SC-001 rappresenta il nome del computer e ARCHINST rappresenta l'istanza di SQL Server per il database System Center: **SQLServerReportServerUser $ ATL-SC-001 $\_MSRS10 50. ARCHINST**.

4.  Fare clic con il pulsante destro del mouse sul gruppo e quindi scegliere **Rinomina**. Rinominare il gruppo eliminando ** \_50** dal nome del gruppo. Ad esempio: **SQLServerReportServerUser $ ATL-SC-001 $ MSRS10. ARCHINST**.

5.  Chiudere Server Manager.

A questo punto si è pronti per installare System Center Reporting Services. Procedi come segue.

1.  Nel supporto di configurazione di System Center Operations Manager 2007 R2 fare doppio clic su **SetupOM. exe**.

2.  Nella configurazione di System Center Operations Manager 2007 R2 fare clic su **Installa report di Operations Manager**.

3.  Nella pagina Configurazione guidata report di Operations Manager 2007 R2, nella pagina **installazione report di Operations Manager** , fare clic su **Avanti**.

4.  Nella pagina **contratto di licenza con l'utente finale** selezionare **Accetto i termini del contratto di licenza** e quindi fare clic su **Avanti**.

5.  Nella pagina di **registrazione del prodotto** verificare che il nome e il nome dell'organizzazione vengano visualizzati nelle caselle **nome utente** e **organizzazione** e quindi fare clic su **Avanti**.

6.  Nella pagina **configurazione personalizzata** fare clic su **server di report** e selezionare **questo componente e tutti i componenti dipendenti verranno installati nell'unità disco locale**. Fare clic su **data warehouse** e selezionare **questo componente non sarà disponibile**e quindi fare clic su **Avanti**.

7.  Nella pagina **Connetti alla pagina server di gestione radice** Digitare il nome del server di gestione radice di Operations Manager nella casella **Server** di gestione radice e quindi fare clic su **Avanti**.

8.  Nella pagina **Connect to the Operations Manager data warehouse** Digitare l'istanza di SQL Server in cui si trova il data warehouse nella casella **istanza di SQL Server** . Se il data warehouse si trova nell'istanza predefinita, digitare semplicemente il nome del server, ad esempio: ATL-SQL-001. Verificare che il nome del database **OperationsManagerDW** sia visualizzato nella casella **nome** e che la porta **1433** venga visualizzata nella casella **porta di SQL Server** . Fare clic su **Avanti**.

9.  Nella pagina **istanza di Reporting di SQL Server** selezionare il server di report di SQL Server nell'elenco a discesa **immettere il server di SQL Server Reporting Services** e quindi fare clic su **Avanti**.

10. Nella pagina **account di scrittura data warehouse** immettere il nome e la password dell'utente a cui assegnare inizialmente le autorizzazioni di scrittura per il data warehouse nelle caselle **account utente** e **password** . Selezionare il dominio dell'utente nell'elenco a discesa **Domain** e quindi fare clic su **Avanti**.

11. Nella pagina **account Reader dati** immettere il nome e la password dell'account utente da usare quando SQL Reporting Services esegue una query nel data warehouse nelle caselle **account utente** e **password** . Selezionare il dominio dell'account dall'elenco a discesa **Domain** e quindi fare clic su **Avanti**.

12. Nella pagina **report dati operativi** fare clic su **Avanti**.

13. Nella pagina **Microsoft Update** fare clic su **Avanti**.

14. Nella pagina **pronto per l'installazione del programma** fare clic su **Installa**.

15. Nella pagina **completamento della configurazione guidata componenti di report di Operations Manager** fare clic su **fine**.

16. Nella configurazione di System Center Operations Manager 2007 R2 fare clic su **Esci**.

Dopo aver installato System Center Reporting, usare la procedura seguente per reimpostare il nome del gruppo di sicurezza associato ai report di SQL Server. Anche in questo caso, questa procedura è obbligatoria solo se si usa SQL Server:

1.  Fare clic sul pulsante **Start**, scegliere **strumenti di amministrazione**e quindi fare clic su **Gestione server**.

2.  In Server Manager espandere **configurazione**, espandere **utenti e gruppi locali**e quindi fare clic su **gruppi**.

3.  Individuare il gruppo seguente, in cui ATL-SC-001 rappresenta il nome del computer e ARCHINST rappresenta l'istanza di SQL Server per i database di archiviazione e monitoraggio: **SQLServerReportServerUser $ ATL-SC-001 $ MSRS10. ARCHINST**.

4.  Fare clic con il pulsante destro del mouse sul gruppo e quindi scegliere **Rinomina**. Rinominare il gruppo aggiungendo ** \_50** alla fine del nome del gruppo, a destra prima del nome dell'istanza di SQL Server. Ad esempio: **SQLServerReportServerUser $ ATL-SC-001 $ MSRS10\_50. ARCHINST**.

5.  Chiudere Server Manager.

Se la console operativa di System Center è aperta, sarà necessario chiudere l'applicazione e quindi riavviarla. Se non si esegue questa operazione, la scheda **report** non verrà visualizzata nell'interfaccia utente della console operatore. Tieni presente che, dopo aver riavviato la prima volta la console operativa, potrebbero essere necessari alcuni minuti prima che tutti i report di monitoraggio vengano visualizzati nella scheda **report** .

</div>

</div>

<span> </span>

</div>

</div>

</div>

