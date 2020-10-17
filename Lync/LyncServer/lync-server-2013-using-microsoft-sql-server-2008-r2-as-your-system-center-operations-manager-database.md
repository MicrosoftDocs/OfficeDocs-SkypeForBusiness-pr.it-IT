---
title: 'Lync Server 2013: utilizzo di Microsoft SQL Server 2008 R2 come database di System Center Operations Manager'
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
ms.openlocfilehash: 51dbff3748f342bd630c33fc867a4249b386c00c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518823"
---
# <a name="using-microsoft-sql-server-2008-r2-as-your-system-center-operations-manager-database-for-lync-server-2013"></a>Utilizzo di Microsoft SQL Server 2008 R2 come database di System Center Operations Manager per Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-07-29_

Per utilizzare SQL Server 2008 R2 come database back-end, completare la procedura descritta in questo argomento.

<div>

## <a name="configuring-sql-server-2008-r2-and-sql-server-reporting-services"></a>Configurazione di SQL Server 2008 R2 e SQL Server Reporting Services

Prima di iniziare a installare System Center Operations Manager, è necessario apportare due modifiche alla configurazione di SQL Server 2008 R2 e SQL Server Reporting Services. Queste modifiche sono necessarie solo se si utilizza SQL Server 2008 R2 come database di Operations Manager. In primo luogo, eseguire le operazioni seguenti nel computer che ospiterà il database di Operations Manager:

1.  Fare clic sul pulsante **Start**, quindi scegliere **Esegui**.

2.  Nella finestra di dialogo **Esegui** Digitare **C: \\ Program Files \\ Microsoft SQL Server \\ MSRS10 \_ 50. ARCHINST \\ Reporting Services \\ ReportServer** e quindi premere INVIO.

3.  Nella cartella **ReportServer** aprire il file **rsreportserver.config** nel Blocco note o in un altro editor di testo.

4.  Quasi all'inizio del file è presente una serie di nodi "Add Key". Individuare la voce che inizia con l' ** \< aggiunta di Key = "SecureConnectionLevel"** e impostare il valore su **0**:
    
        <Add Key="SecureConnectionLevel" Value="0"/>

5.  Salvare il file **rsreportserver.config** e chiudere l'editor di testo.

Dopo avere aggiornato il file di configurazione del server di report, è necessario assegnare il certificato corretto a SQL Server Reporting Services. A questo scopo:

1.  Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft SQL Server 2008 R2**, **strumenti di configurazione**e quindi fare clic su **Gestione configurazione Reporting Services**.

2.  Nella finestra di dialogo **Connessione configurazione Reporting Services** verificare che nella casella **Nome server** sia presente il nome del server. Selezionare l'istanza di SQL Server che ospiterà il database di Operations Manager (ad esempio, **ARCHINST**) dall'elenco a discesa **istanza del server di report** e quindi fare clic su **Connetti**.

3.  In Gestione configurazione Reporting Services fare clic su **URL servizio Web**.

4.  Nella pagina **URL servizio Web** selezionare il certificato da utilizzare per l'istanza di Reporting Services nell'elenco a discesa **Certificato SSL**, quindi fare clic su **Applica**. Dopo alcuni secondi comparirà una coppia di URL in **URL servizio Web ReportServer**.

5.  Fare clic su entrambi gli URL per verificare di poter accedere a SQL Server Reporting Services.

6.  Chiudere Gestione configurazione Reporting Services.

</div>

<div>

## <a name="creating-a-system-center-operations-manager-database-for-use-with-sql-server-2008-r2"></a>Creazione di un database System Center Operations Manager per l'utilizzo con SQL Server 2008 R2

Se si desidera configurare System Center Operations Manager per l'utilizzo di un database di SQL Server 2008 R2, è necessario creare manualmente il database di Operations Manager nel computer in cui è in esecuzione SQL Server 2008 R2. (Di nuovo, questi passaggi non sono necessari se si utilizza SQL Server 2005 o SQL Server 2008 come database back-end).

Per creare manualmente un database di Operations Manager, eseguire le operazioni seguenti:

1.  Nel supporto di installazione di System Center Operations Manager 2007 R2, nella \\ cartella SupportTools amd64 fare doppio clic su **DBCreateWizard.exe**.

2.  Nella pagina iniziale della **Configurazione guidata database** fare clic su **Avanti**.

3.  Nella pagina **Informazioni database** lasciare invariate tutte le impostazioni e fare clic su **Avanti**

4.  Nella pagina **Configurazione gruppo di gestione** Digitare un nome per il gruppo di gestione, ad esempio **il monitoraggio di Lync Server**, nella casella **nome gruppo di gestione** e quindi fare clic su **Avanti**.

5.  Nella pagina **Segnalazioni errori di Operations Manager** fare clic su **Avanti**.

6.  Nella pagina **Riepilogo** fare clic su **Fine**.

</div>

<div>

## <a name="creating-a-system-center-operations-manager-data-warehouse-for-use-with-sql-server-2008-r2"></a>Creazione di un data warehouse di System Center Operations Manager per l'utilizzo con SQL Server 2008 R2

Microsoft Lync Server 2013 viene fornito con tre nuovi report di System Center Operations Manager:

  - Report di disponibilità dello **scenario end to end**     Questo rapporto descrive in dettaglio la disponibilità/tempo di uptime per i servizi chiave di Lync Server, ad esempio la registrazione o la presenza.

  - **Rapporto capacità**     Utilizzando le informazioni sui contatori delle prestazioni, questo rapporto illustra le tendenze per i componenti di sistema, ad esempio la disponibilità della memoria e l'utilizzo del processore

  - **Report componente**     In questo report sono elencati i generatori di avvisi principali raggruppati in base al componente Lync Server.

Per utilizzare questi nuovi rapporti, è necessario installare un data warehouse di System Center Operations Manager. (Un data warehouse fornisce l'archiviazione a lungo termine dei dati delle operazioni). Per utilizzare un data warehouse con SQL Server 2008 R2, è necessario eseguire i passaggi seguenti nel computer che ospita il database di SQL Server:

1.  Nel supporto di installazione di System Center Operations Manager, nella \\ cartella Setup SupportTools \\ amd64 fare doppio clic su **DBCreateWizard.exe**.

2.  Nella pagina iniziale della **Configurazione guidata database** fare clic su **Avanti**.

3.  Nella pagina **Informazioni database** selezionare **Database data warehouse di Operations Manager** nell'elenco a discesa **Tipo database**, quindi fare clic su **Avanti**.

4.  Nella pagina **Riepilogo** fare clic su **Fine**.

</div>

<div>

## <a name="installing-the-system-center-operations-manager-console"></a>Installazione della console di System Center Operations Manager

La console di Operations Manager è lo strumento principale utilizzato per gestire System Center Operations Manager. Prima di installare la console di Operations Manager, verificare di aver installato una versione supportata di SQL Server insieme a SQL Server Reporting Services. È inoltre consigliabile eseguire Gestione configurazione Reporting Services di SQL Server per verificare che Reporting Service sia installato e configurato correttamente.

Per installare la console di System Center Operations Manager:

1.  Nel supporto di installazione di System Center Operations Manager fare doppio clic su **SetupOM.exe**.

2.  Nel programma di installazione di System Center Operations Manager 2007 R2 fare clic su **Controlla prerequisiti**.

3.  Nel Visualizzatore prerequisiti di System Center Operations Manager selezionare i componenti di System Center da installare: (**Server**; **Console**; e **PowerShell**), quindi fare clic su **Controlla**. Verificare che non siano stati riscontrati problemi gravi e quindi fare clic su **Chiudi**. Se viene segnalato un problema grave, correggerlo e fare clic su **Controlla** per ripetere il test dei prerequisiti.

4.  Nel programma di installazione di System Center Operations Manager fare clic su **Installa Operations Manager**.

5.  Nell'installazione guidata di System Center Operations Manager, nella pagina **installazione guidata di System Center Operations Manager** fare clic su **Avanti**.

6.  Nella pagina **Contratto di licenza con l'utente finale** selezionare **Accetto i termini del Contratto di licenza** e fare clic su **Avanti**.

7.  Nella pagina **Registrazione prodotto** digitare il proprio nome nella casella **Nome utente** e il nome dell'organizzazione nella casella **Organizzazione**. Digitare il codice Product Key di System Center Operations Manager nella casella **immettere il codice CD di 25 cifre** e quindi fare clic su **Avanti**.

8.  Nella pagina **Installazione personalizzata** selezionare le opzioni di System Center da installare, quindi fare clic su **Avanti**. È consigliabile selezionare **Server di gestione**, **Interfacce utente** e **Console Web** per l'installazione, ma non selezionare e installare **Database**.

9.  Nella pagina dell' **istanza del server database SC** verificare che il nome del computer in cui sono installati i database di Operations Manager sia visualizzato nella casella **server database System Center** . Fare clic su **Avanti**.

10. Nella pagina **Account azione server di gestione** selezionare **Dominio o account computer locale** e immettere i valori appropriati nelle caselle **Account utente**, **Password** e **Dominio o computer locale**. Fare clic su **Avanti**.

11. Nella pagina **SDK e account servizio di configurazione** selezionare **Dominio o account computer locale** e immettere i valori appropriati nelle caselle **Account utente**, **Password** e **Dominio o computer locale**. Fare clic su **Avanti**.

12. Nella pagina **Segnalazioni errori di Operations Manager** fare clic su **Avanti**.

13. Nella pagina **Analisi utilizzo software** fare clic su **Avanti**.

14. Nella pagina **Installazione del programma** fare clic su **Avanti**.

15. Nella pagina finale dell'**Installazione di System Center Operations Manager** deselezionare le caselle di controllo **Backup chiave di crittografia** e **Avvia console**, quindi fare clic su **Fine**.

16. Nel programma di installazione di System Center Operations Manager fare clic su **Esci**.

</div>

<div>

## <a name="installing-system-center-reporting-services"></a>Installazione di System Center Reporting Services

Dopo aver installato e configurato la console di System Center Operations Manager, è necessario installare System Center Reporting Services. Se si utilizza SQL Server 2008 R2 come database back-end di Operations Manager, significa che è innanzitutto necessario apportare una modifica temporanea al gruppo di sicurezza associato a SQL Server Reporting Services. Se si utilizza SQL Server 2008 R2, è necessario eseguire le operazioni seguenti:

1.  Fare clic su **Start**, scegliere **Strumenti di amministrazione**, quindi **Server Manager**.

2.  In Server Manager espandere **Configurazione** e **Utenti e gruppi locali**, quindi fare clic su **Gruppi**.

3.  Individuare il gruppo seguente, in cui ATL-SC-001 rappresenta il nome del computer e ARCHINST rappresenta l'istanza di SQL Server per il database System Center: **SQLServerReportServerUser $ ATL-SC-001 $ MSRS10 \_ 50. ARCHINST**.

4.  Fare clic con il pulsante destro del mouse sul gruppo e quindi scegliere **Rinomina**. Rinominare il gruppo eliminando ** \_ 50** dal nome del gruppo. Ad esempio: **SQLServerReportServerUser $ ATL-SC-001 $ MSRS10. ARCHINST**.

5.  Chiudere Server Manager.

A questo punto è possibile installare System Center Reporting Services. Procedere nel modo seguente:

1.  Nel supporto di installazione di System Center Operations Manager 2007 R2 fare doppio clic su **SetupOM.exe**.

2.  In System Center Operations Manager 2007 R2 Setup fare clic su **Install Operations Manager Reporting**.

3.  Nell'installazione guidata di Reporting System Center Operations Manager 2007 R2, nella pagina **installazione report di Operations Manager** fare clic su **Avanti**.

4.  Nella pagina **Contratto di licenza con l'utente finale** selezionare **Accetto i termini del Contratto di licenza** e fare clic su **Avanti**.

5.  Nella pagina **Registrazione prodotto** verificare che nelle caselle **Nome utente** e **Organizzazione** siano presenti il proprio nome e il nome dell'organizzazione, quindi fare clic su **Avanti**.

6.  Nella pagina **Installazione personalizzata** fare clic su **Server di report** e selezionare **Il componente e tutti i componenti secondari verranno installati sul disco rigido locale**. Fare clic su **Data warehouse** e selezionare **Il componente non sarà disponibile**, quindi fare clic su **Avanti**.

7.  Nella pagina **Connetti al server di gestione principale** digitare il nome del server di gestione principale di Operations Manager nella casella **Server di gestione principale** e fare clic su **Avanti**.

8.  Nella pagina **Connetti al data warehouse Operations Manager**, nella casella **Istanza di SQL Server**, digitare l'istanza di SQL Server in cui si trova il data warehouse (se il data warehouse si trova nell'istanza predefinita, è sufficiente digitare il nome del server, ad esempio atl-sql-001). Verificare che nella casella **Nome** sia riportato il nome **OperationsManagerDW** e che nella casella **Porta SQL Server** sia presente **1433**. Fare clic su **Avanti**.

9.  Nella pagina **Istanza di SQL Server Reporting Services** selezionare il server di report di SQL Server nell'elenco a discesa **Immettere il server SQL Server Reporting Services** e fare clic su **Avanti**.

10. Nella pagina **Account scrittura data warehouse**, nelle caselle **Account utente** e **Password** immettere il nome e la password dell'utente a cui assegnare inizialmente le autorizzazioni di scrittura per il data warehouse. Selezionare il dominio dell'utente nell'elenco a discesa **Dominio** e fare clic su **Avanti**.

11. Nella pagina **Account lettore dati**, nelle caselle **Account utente** e **Password** immettere il nome utente e la password dell'account utente da utilizzare per le query di SQL Reporting Services sul data warehouse. Selezionare il dominio dell'account nell'elenco a discesa **Dominio** e fare clic su **Avanti**.

12. Nella pagina **Rapporti dati operativi** fare clic su **Avanti**.

13. Nella pagina **Microsoft Update**fare clic su **Avanti**.

14. Nella pagina **Installazione del programma** fare clic su **Avanti**.

15. Nella pagina **Completamento dell'installazione guidata componenti di report di Operations Manager** fare clic su **Fine**.

16. In System Center Operations Manager 2007 R2 Setup fare clic su **Esci**.

Dopo aver installato i report di System Center, utilizzare la procedura seguente per reimpostare il nome del gruppo di sicurezza associato ai report di SQL Server. Questa procedura è di nuovo obbligatoria solo se si utilizza SQL Server:

1.  Fare clic su **Start**, scegliere **Strumenti di amministrazione**, quindi **Server Manager**.

2.  In Server Manager espandere **Configurazione** e **Utenti e gruppi locali**, quindi fare clic su **Gruppi**.

3.  Individuare il gruppo seguente, in cui ATL-SC-001 rappresenta il nome del computer e ARCHINST rappresenta l'istanza di SQL Server per i database di archiviazione e monitoraggio: **SQLServerReportServerUser $ ATL-SC-001 $ MSRS10. ARCHINST**.

4.  Fare clic con il pulsante destro del mouse sul gruppo e quindi scegliere **Rinomina**. Rinominare il gruppo aggiungendo ** \_ 50** alla fine del nome del gruppo, subito prima del nome dell'istanza di SQL Server. Ad esempio: **SQLServerReportServerUser $ ATL-SC-001 $ MSRS10 \_ 50. ARCHINST**.

5.  Chiudere Server Manager.

Se la Console operatore di System Center è aperta, è necessario chiudere l'applicazione e riavviarla, altrimenti la scheda **Report** non comparirà nell'interfaccia utente della Console operatore. Tenere presente che, dopo il primo riavvio della Console operatore, è possibile che siano necessari alcuni minuti perché vengano visualizzati tutti i report di monitoraggio nella scheda **Report**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

