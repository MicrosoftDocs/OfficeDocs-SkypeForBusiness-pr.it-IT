---
title: Registrare un dispositivo Teams Room nei servizi gestiti
author: donnah007
ms.author: v-donnahill
manager: serdars
ms.date: 07/22/2022
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Onboarding Teams Rooms dispositivi ai servizi gestiti
f1keywords: ''
ms.openlocfilehash: 124d301a37fde8802b60f3e59ad5f1a1dd19862c
ms.sourcegitcommit: f5d784df59a8010b390691bbb20c4ea66c46280b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/26/2022
ms.locfileid: "67005436"
---
# <a name="enroll-device-into-managed-service"></a>Registrare il dispositivo nel servizio gestito

La distribuzione richiede l'onboarding Microsoft Teams Rooms dispositivi ai servizi gestiti Microsoft Teams Rooms. L'agente del servizio di monitoraggio può essere usato con periferiche e sistemi Microsoft Teams Room (MTR) certificati.

## <a name="prerequisites"></a>Prerequisiti

Seguire queste procedure per configurare l'hardware prima di tentare il processo di registrazione:

### <a name="adding-proxy-settings-optional"></a>Aggiunta di impostazioni proxy (facoltativo)

1. Accedere come amministratore eseguendo [operazioni come utente Amministrazione del dispositivo MTR](#performing-operations-as-the-admin-user-of-the-mtr-device).
1. Nel campo Windows ***Search** _ (sezione in basso a sinistra dello schermo) immettere _ *cmd** (premere a lungo lo schermo o selezionare a destra e scegliere **_Esegui come amministratore_**).
1. Eseguire il comando seguente (le virgolette doppie alla fine del comando sono importanti):

   - Se si usa un singolo ***server proxy***: `bitsadmin /Util /SetIEProxy LOCALSYSTEM MANUAL_PROXY <proxyserver>:<port> ""`

     *Esempio:*

     ```DOS
     bitsadmin /Util /SetIEProxy LOCALSYSTEM MANUAL_PROXY contosoproxy.corp.net:8080 ""
     ```

   - Se si usa un file ***pac*** : `bitsadmin /Util /SetIEProxy LOCALSYSTEM AUTOSCRIPT <pac file url>`

     *Esempio:*

     ```DOS
     bitsadmin /Util /SetIEProxy LOCALSYSTEM AUTOSCRIPT `http://contosoproxy.corp.net/proxy.pac`
     ```

### <a name="enabling-tpm-settings"></a>Abilitazione delle impostazioni TPM

> [!NOTE]
> Il TPM deve essere abilitato per la registrazione nel servizio gestito.

Se TPM su un dispositivo Intel NUC è disabilitato, abilita TPM su questi dispositivi come indicato di seguito:

1. Collega la tastiera a un dispositivo NUC.
1. Riavvia il dispositivo.
1. Per visualizzare la schermata del BIOS, premi rapidamente **F2**.
1. Seleziona **Avanzate**.
1. Seleziona **Sicurezza**.
1. Sul lato destro sotto Le funzionalità di sicurezza abilita **Intel Platform Trust Technology**.
1. Per salvare le impostazioni, premere **F10**.
1. Nella casella di conferma selezionare **Sì**.

## <a name="performing-operations-as-the-admin-user-of-the-mtr-device"></a>Esecuzione di operazioni come utente Amministrazione del dispositivo MTR

Alcune procedure di configurazione/installazione richiedono l'accesso al dispositivo come amministratore.

Per accedere al dispositivo come amministratore (amministratore locale):

1. Assicurati di riagganciare le chiamate in corso e torna alla schermata iniziale.
1. Nell'interfaccia utente di Microsoft Teams Room, selezionare  **Altro**, quindi selezionare **Impostazioni**, in cui viene richiesta la password dell'amministratore locale nel dispositivo (la password predefinita è **_sfb_**).
1. Seleziona **Impostazioni**, quindi  **Impostazioni di Windows**  per accedere a Windows come amministratore locale.

1. Nell'elenco degli utenti visualizzato nella schermata di accesso di Windows seleziona  **Amministratore** (o il rispettivo amministratore locale del dispositivo).

> [!NOTE]
> Se il computer fa *parte di un dominio*, scegliere **Altro utente**, quindi utilizzare **.\admin** o il nome utente dell'amministratore locale configurato nel dispositivo come nome utente.

Per tornare all'app Microsoft Teams Rooms dopo aver eseguito le attività amministrative necessarie:

1. Dal ***menu Start*** di Windows disconnettiti dall'account Amministrazione.
1. Torna a Microsoft Teams Rooms selezionando l'icona dell'account utente all'estrema sinistra dello schermo e quindi selezionando **Skype**.

> [!NOTE]
> Se l'utente Skype non è elencato, seleziona Altro utente, immetti ***.\skype*** come nome utente, quindi accedi.

## <a name="urls-required-for-communication"></a>URL necessari per la comunicazione

 > [!NOTE]
 > Tutto il traffico di rete tra l'agente dei dispositivi MTR e il portale del servizio Microsoft Teams Rooms - Servizi gestiti è SSL sulla porta 443 *.*  Vedere [Office 365 URL e intervalli di indirizzi IP - Microsoft 365 Enterprise | Microsoft Docs](/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide&preserve-view=true).

Gli host seguenti devono essere consentiti se il **traffic allowlist** è abilitato all'interno dell'ambiente aziendale:

agent.rooms.microsoft.com<br>
global.azure-devices-provisioning.net<br>
gj3ftstorage.blob.core.windows.net<br>
mmrstgnoamiot.azure-devices.net<br>
mmrstgnoamstor.blob.core.windows.net<br>
mmrprodapaciot.azure-devices.net<br>
mmrprodapacstor.blob.core.windows.net<br>
mmrprodemeaiot.azure-devices.net<br>
mmrprodemeastor.blob.core.windows.net<br>
mmrprodnoamiot.azure-devices.net<br>
mmrprodnoamstor.blob.core.windows.net

## <a name="enrollment-process"></a>Processo di registrazione

Il processo di registrazione prevede questi passaggi:

1. Sulla barra di spostamento sinistra del portale [http://portal.rooms.microsoft.com](https://portal.rooms.microsoft.com/)Microsoft Teams Rooms - Servizi gestiti espandere **Impostazioni** e selezionare **Generale**.
1. In *Registra una sala* selezionare **Scarica programma di installazione**  per scaricare il software dell'agente di monitoraggio.
1. **Opzionale:** Configurare le impostazioni proxy per l'agente; vedere [Aggiunta di impostazioni proxy (facoltativo).](#adding-proxy-settings-optional)
1. Installare il programma di installazione dell'agente (scaricato nel passaggio 2) nelle unità MTR, eseguendo il file MSI in locale su un dispositivo MTR o tramite il normale mezzo di pubblicazione di applicazioni MSI in massa nei dispositivi all'interno dell'ambiente (Criteri di gruppo e così via).
1. La sala verrà visualizzata nel portale entro 5-10 minuti. In caso contrario, contatta managedroomsupport@microsoft.com.

   ![Screenshot delle impostazioni e dei tasti di autoregistrazione.](../media/software-installation-005new.png)

> [!NOTE]
> Se è necessario installare l'agente senza che l'app Teams nel programma MTR sia in grado di accedere a Teams, è possibile usare il codice di registrazione come processo facoltativo. Vai a '?'  (Guida) nell'angolo in alto a destra del portale, quindi seleziona "Chiave di download (facoltativa)". Durante l'installazione dell'agente, inserisci la "chiave di autoregistrazione" (precedentemente scaricata dal portale) nella directory **C:\Rigel** del dispositivo.

## <a name="installation"></a>Installazione

Dopo aver scaricato il programma di installazione da Microsoft (dal portale o utilizzando l'URL AKA.ms indicato in precedenza), decomprimere il contenuto per accedere al file **ManagedRoomsInstaller.msi**.

Esistono due modalità di installazione: 1) installazione singola macchina locale e 2) modalità di distribuzione di massa (in genere tramite Intune di metodo simile). È consigliabile l'installazione individuale per computer non appartenenti a un dominio o per computer in cui non è possibile eseguire i programmi di installazione MSI in remoto.

A causa dei vari modi in cui i clienti possono eseguire applicazioni MSI in modalità di distribuzione di massa questo documento illustra solo l'installazione in modalità singola e in blocco su dispositivi registrati Intune.

### <a name="individual-device-installation"></a>Installazione di singoli dispositivi

1. Accedi al dispositivo come amministratore. Assicurati che vengano seguite *le operazioni eseguite come utente Amministrazione del dispositivo*.

1. Copiare il **ManagedRoomsInstaller.msi** file nel dispositivo MTR.

   Quando si esegue il ***ManagedRoomsInstaller.msi*** è visualizzata la schermata del Contratto di licenza.

1. Dopo aver letto il contratto, seleziona ***Accetto i termini del Contratto di licenza** _ e premi _*Installa**.

    Viene avviata l'installazione del software di monitoraggio Microsoft Teams Rooms - Servizi gestiti. Viene visualizzata una richiesta di elevazione (eseguita come amministratore).

1. Seleziona **Sì**.

    L'installazione continuerà. Durante la procedura di installazione, viene aperta una finestra della console e viene avviata la fase finale dell'installazione software di monitoraggio di Microsoft Teams Rooms - Servizi gestiti.

    > [!NOTE]
    > Non chiudere la finestra. Una volta completata l'installazione, la procedura guidata visualizza un pulsante "Fine".

### <a name="intune-enrolled-device-bulk-deployment"></a>distribuzione in blocco del dispositivo registrata Intune

I componenti seguenti sono prerequisiti per il completamento dell'installazione: 

- **registrazione Intune**: Teams Rooms nei dispositivi Windows devono essere già registrati in Intune.
  Per altre informazioni su come registrare Teams Rooms nei dispositivi Windows in Intune, vedere [Registrazione di Microsoft Teams Rooms nei dispositivi Windows con Microsoft Endpoint Manager - Microsoft Tech Community](https://techcommunity.microsoft.com/t5/intune-customer-success/enrolling-microsoft-teams-rooms-on-windows-devices-with/ba-p/3246986)
- **Gruppo di Azure AD con tutti i Teams Rooms dei dispositivi Windows come membri**: un gruppo creato in Azure AD che include tutti i Teams Rooms nei dispositivi Windows che devono far parte del servizio Microsoft Teams Rooms Premium. Questo gruppo verrà utilizzato per la distribuzione dell'agente MTRP.
  
> [!NOTE]
> A questo scopo, è consigliabile usare i gruppi dinamici in Azure AD, per altre informazioni vedere [Registrazione di Microsoft Teams Rooms nei dispositivi Windows con Microsoft Endpoint Manager - Microsoft Tech Community](https://techcommunity.microsoft.com/t5/intune-customer-success/enrolling-microsoft-teams-rooms-on-windows-devices-with/ba-p/3246986)
- Scarica il **programma di installazione** **dell'agente MTRP**: scarica il file ZIP dell'agente ed <https://aka.ms/serviceportalagentmsi> estrai il contenuto del file ZIP (ManagedRoomsInstaller.msi) in una cartella temporanea locale.

**Per eseguire l'installazione con Intune**

1. Accedere [all'interfaccia di amministrazione di Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
1. Seleziona **App** > **Tutte le app** > **Aggiungi**.
1. Nel riquadro **Seleziona tipo di app** , in **Altri** tipi di app, seleziona **App line-of-business**.
1. Fare clic su **Seleziona**. Vengono visualizzati i passaggi per **l'aggiunta dell'app** . 
1. Nel riquadro **Aggiungi app** fare clic su **Seleziona file del pacchetto dell'app**.
   1. Nel riquadro File **pacchetto app** selezionare  **Sfoglia**. Seleziona quindi il **ManagedRoomsInstaller.msi** file scaricato in precedenza (fai riferimento alla sezione dei prerequisiti).
   1. Al termine, selezionare **OK** nel riquadro file del **pacchetto** dell'app per aggiungere l'app.
1. Nella pagina **Informazioni app** eseguire le modifiche seguenti:
   1. Editore: immettere **Microsoft Corporation**.
   1. Ignora versione dell'app: seleziona **Sì**.

      > [!NOTE]
      > L'agente MTRP si sta auto-aggiornando; quindi, è consigliabile ignorare esplicitamente la versione dell'app (qualsiasi versione di base può essere aggiornata automaticamente).

   1. (Facoltativo) Categoria: selezionare **Gestione computer**.
   
1. Fare clic su **Avanti** per visualizzare la pagina **Attività** .
   1. Nella sezione **Obbligatorio** fare clic su **+ aggiungi gruppo** per assegnare un gruppo di dispositivi per l'installazione dell'agente.
   1. Nel riquadro **Seleziona gruppo** digitare il nome del gruppo nella casella di ricerca (fare riferimento ai prerequisiti sopra) e fare clic sul **gruppo** desiderato e fare clic su **Seleziona**.
      Per altre informazioni, vedere [Aggiungere gruppi per organizzare utenti e dispositivi](https://go.microsoft.com/fwlink/?linkid=2202166) e [Assegnare app ai gruppi con Microsoft Intune](https://go.microsoft.com/fwlink/?linkid=2202270).
1. Fare clic su **Avanti** per visualizzare la pagina **Revisione e crea** .
1. Esaminare i valori e le impostazioni immessi per l'app. Al termine, fare clic su **Crea** per aggiungere l'app a Intune.

Una volta completato il processo, i dispositivi inizieranno a installare l'agente MTRP dopo alcuni minuti.

> [!NOTE]
> Dopo l'installazione, l'agente MTRP potrebbe richiedere fino a otto ore per eseguire un aggiornamento automatico alla versione più recente e diventare elencato nel portale MTRP.
Per velocizzare la registrazione automatica nel portale MTRP, è consigliabile riavviare il dispositivo MTR dopo la distribuzione dell'agente.

## <a name="completing-enrollment"></a>Completamento della registrazione

Al termine dell'installazione, attendi 5-10 minuti, quindi aggiorna il portale per visualizzare il dispositivo nell'elenco, indicato come stato *onboarding* .

Nello stato *onboarding* , lo stato della chat room viene visualizzato e aggiornato, ma non genera avvisi né crea ticket di indagine.

Scegliere la sala e selezionare **Registra**  per iniziare a ricevere avvisi di incidenti, ticket di indagine o per segnalare un evento imprevisto.

Per eventuali domande o problemi, apri un evento imprevisto segnalato dal cliente nel portale o contatta managedroomsupport@microsoft.com.

### <a name="unenrolling-and-uninstalling-monitoring-software"></a>Annullamento della registrazione e disinstallazione del software di monitoraggio

Per annullare la registrazione del dispositivo, rimuovi l'agente di monitoraggio dal dispositivo MTR come indicato di seguito:

1. Nel dispositivo monitorato, accedi al dispositivo come amministratore. Assicurarsi di seguire i passaggi descritti in *Eseguire operazioni come utente Amministrazione del dispositivo*.
1. Scaricare lo script di reimpostazione da [aka.ms/MTRPDeviceOffBoarding](https://aka.ms/MTRPDeviceOffBoarding).
1. Estrarre lo script in un punto qualsiasi del dispositivo e copiare il percorso.
1. Apri PowerShell come amministratore: nel campo Windows ***Search** _ (sezione in basso a sinistra dello schermo), immetti "Powershell" e fai clic con il pulsante destro del mouse su _*_Windows PowerShell_**.
1. Seleziona *"Esegui come amministratore"* e accetta la richiesta di controllo dell'account utente.
1. Immettere *Set-ExecutionPolicy –ExecutionPolicy RemoteSigned* , quindi premere **Y** al prompt successivo.
1. Incollare o digitare il percorso completo dello script di offboarding decompresso nella finestra di PowerShell e premere **INVIO**.

   Esempio:

   ```powershell
   C:\Users\admin\Downloads\MTRP\_Device\_Offboarding\MTRP\_Device\_Offboarding.ps1
   ```

   Questo comando reimposta il dispositivo agli aggiornamenti MTR standard dell'utente e rimuove i file e l'agente di monitoraggio MTRP.

1. Nel menu a sinistra nel portale Microsoft Teams Rooms - Servizi gestiti selezionare **Sale**.
1. Nell'elenco delle sale fornite scegliere la chat room da annullare e selezionare **Annulla registrazione** per interrompere la ricezione di avvisi o ticket d'indagine oppure per segnalare un evento imprevisto per la sala.

## <a name="troubleshooting-table"></a>Tabella di risoluzione dei problemi

> [!NOTE]
> Tutti gli Microsoft Teams Rooms : gli errori di monitoraggio dei servizi gestiti vengono registrati in uno specifico file di registro eventi denominato **Sale gestite Microsoft**.

***Percorso del file di log di runtime dell'applicazione*** =

C:\Windows\ServiceProfiles\LocalService\AppData\Local\ServicePortalAgent\ app-x.x\ServicePortalAgent\ServicePortal\_Verbose\_LogFile.log, dove **x.x.x** è il numero di versione dell'app.

|Sintomo|Procedura consigliata|
|---|---|
|Viene visualizzato un messaggio di errore che indica: </p><p> ***ERRORE: eseguire l'applicazione con** _ <br> _ *_elevated privileges_**|Esegui l'applicazione con privilegi di escalation e riprova.|
|||
|Viene visualizzato un messaggio di errore che indica: </p><p> ***Impossibile trovare i dati TPM***|Assicurati che nel BIOS del dispositivo sia attivato TPM (Trusted Platform Module). Questo si trova in genere nelle impostazioni di sicurezza del BIOS del dispositivo.|
|||
|Viene visualizzato un messaggio di errore: </p><p> ***ERRORE: Account utente locale denominato "Amministrazione" o "Skype" non trovato***|Assicurarsi che gli account utente siano presenti nel dispositivo certificato Microsoft Teams Room Systems.|
|||
|Vengono visualizzati messaggi di stato di errore non inclusi in precedenza.|Fornisci una copia del log di installazione all'agente di supporto di Sistema di Microsoft Teams.|
