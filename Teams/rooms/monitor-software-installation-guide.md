---
title: Microsoft Teams Rooms software
author: donnah007
ms.author: v-donnahill
manager: serdars
ms.reviewer: ''
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
description: Onboarding di Teams Rooms dispositivi ai servizi gestiti
f1keywords: ''
ms.openlocfilehash: 70209bcd60740f1d1e19b45b215b921396a6f0fd
ms.sourcegitcommit: a969502c0a5237caf041d7726f4f1edefdd75b44
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2022
ms.locfileid: "61767560"
---
# <a name="monitor-device-software-installation"></a>Monitorare l'installazione del software del dispositivo

La distribuzione richiede l'onboarding Microsoft Teams Rooms dispositivi nei Microsoft Teams Rooms gestiti. L'agente del servizio di monitoraggio è per l'uso con sistemi Microsoft Teams room (MTR) certificati e periferiche.

## <a name="performing-operations-as-the-admin-user-of-the-mtr-device"></a>Esecuzione di operazioni come utente amministratore del dispositivo MTR

Alcune procedure di configurazione/installazione richiedono l'accesso al dispositivo come amministratore.

Per accedere al dispositivo come amministratore (amministratore locale):

1. Assicurarsi di riagganciare le chiamate in corso e tornare alla schermata iniziale.
1. Nell'interfaccia utente della chat room Microsoft Teams selezionare Altro **,** quindi selezionare Impostazioni , in cui viene richiesta la password di amministratore locale nel dispositivo (la password predefinita è **_sfb)._** 
1. Selezionare **Impostazioni**, quindi **selezionare** Windows Impostazioni per accedere Windows come amministratore locale.  

1. Nell'elenco degli utenti visualizzato nella schermata di Windows di accesso selezionare **Amministratore** (o il rispettivo amministratore locale del dispositivo).

> [!NOTE]
> Se il computer *fa* parte di un dominio, scegliere Altro utente **,** quindi usare **.\admin** o il nome utente dell'amministratore locale configurato nel dispositivo come nome utente.  

Per tornare all'app Microsoft Teams room dopo aver eseguito le attività amministrative necessarie:

1. Dal Windows ***menu Start***, disconnettersi dall'account amministratore.
1. Tornare alla Microsoft Teams room selezionando l'icona dell'account utente all'estrema sinistra dello schermo e quindi **selezionando** Skype .

> [!NOTE]
> Se l Skype utente non è presente nell'elenco, seleziona Altro utente e immetti ***.\skype*** come nome utente e accedi.

## <a name="prerequisites"></a>Prerequisiti

Seguire queste procedure per configurare l'hardware prima di provare il processo di registrazione:

### <a name="adding-proxy-settings-optional"></a>Aggiunta di impostazioni proxy (facoltativo)

1. Accedere come amministratore seguendo [Esecuzione delle operazioni come utente amministratore del dispositivo MTR.](#performing-operations-as-the-admin-user-of-the-mtr-device)
1. Nel campo Windows ***Cerca** _ (sezione in basso a sinistra dello schermo), immettere _ *cmd** (premere a lungo lo schermo o selezionare a destra e scegliere Esegui **_come amministratore)._**  
1. Eseguire il comando seguente (le virgolette doppie alla fine del comando sono importanti):
   - Se si usa un ***singolo server proxy***: bitsadmin /Util /SetIEProxy LOCALSYSTEM MANUAL PROXY : \_ <proxyserver> <port> ""

      *Esempio:* bitsadmin /Util /SetIEProxy LOCALSYSTEM MANUAL \_ PROXY contosoproxy.corp.net:8080 ""
      

   - Se si usa un file ***pac:*** bitsadmin /Util /SetIEProxy LOCALSYSTEM AUTOSCRIPT <pac file url> ""

      
      *Esempio:* bitsadmin /Util /SetIEProxy LOCALSYSTEM AUTOSCRIPT `http://contosoproxy.corp.net/proxy.pac` ""
      

### <a name="enabling-tpm-settings"></a>Abilitazione delle impostazioni TPM

Se il TPM in un dispositivo Intel NUC è disabilitato, abilitare il TPM in questi dispositivi nel modo seguente:  

1. Collegare la tastiera a un dispositivo NUC.  
1. Riavvia il dispositivo.  
1. Per visualizzare la schermata del BIOS, premere **rapidamente F2**.  
1. Seleziona **Avanzate**.  
1. Selezionare **Sicurezza**.  
1. Sul lato destro, sotto Funzionalità di sicurezza, abilitare **Intel Platform Trust Technology.**  
1. Per salvare le impostazioni, premere **F10.**  
1. Nella casella di conferma selezionare **Sì.**  

## <a name="urls-required-for-communication"></a>URL obbligatori per la comunicazione

 > [!NOTE]
 > Tutto il traffico di rete tra l'agente dei dispositivi MTR e il portale del servizio Microsoft Teams Rooms - Servizi gestiti è SSL sulla porta 443.  Vedere [Office 365 URL e intervalli di indirizzi IP - Microsoft 365 Enterprise | Documenti Microsoft](/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide&preserve-view=true).

Gli host seguenti devono essere consentiti se l'elenco degli indirizzi consentiti **per il** traffico è abilitato all'interno dell'ambiente aziendale:

agent.rooms.microsoft.com<br>
global.azure-devices-provisioning.net<br>
gj3ftstorage.blob.core.windows.net<br>
iothubsgagwt5wgvwg6.azure-devices.net<br>
blobssgagwt5wgvwg6.blob.core.windows.net<br>
mmrstgnoamiot.azure-devices.net<br>
mmrstgnoamstor.blob.core.windows.net<br>
mmrprodapaciot.azure-devices.net<br>
mmrprodapacstor.blob.core.windows.net<br>
mmrprodemeaiot.azure-devices.net<br>
mmrprodemeastor.blob.core.windows.net<br>
mmrprodnoamiot.azure-devices.net<br>
mmrprodnoamstor.blob.core.windows.net

## <a name="process"></a>Processo

Il processo di registrazione prevede alcuni passaggi:  

1. Sulla barra di spostamento sinistra del portale Microsoft Teams Rooms - Servizi gestiti espandere Impostazioni [http://portal.rooms.microsoft.com](https://portal.rooms.microsoft.com/) e selezionare **Generale.**   
1. In *Chiavi di autoregistrazione* selezionare **Scarica collegamento ipertestuale del programma di** installazione per scaricare il https://aka.ms/serviceportalagentmsi software dell'agente di monitoraggio.
1. Selezionare **Scarica chiave**. Inserire il file di chiave **nella cartella C:\Rigel** in ogni dispositivo che si sta registrando.  
1. **Facoltativo:** Configurare le impostazioni del proxy per l'agente. vedere [Aggiunta di impostazioni proxy (facoltativo).](#adding-proxy-settings-optional)
1. Installare il programma di installazione dell'agente (scaricato nel passaggio 2) nelle unità MTR, eseguendo il file MSI localmente in un dispositivo MTR o tramite il normale mezzo per pubblicare le applicazioni MSI in massa nei dispositivi all'interno dell'ambiente (Criteri di gruppo e così via).  
1. La chat room viene visualizzata nel portale entro 5-10 minuti. In caso contrario, contattare managedroomsupport@microsoft.com.  

![Figura 5](../media/software-installation-005.jpg)

## <a name="installation"></a>Installazione

Dopo aver scaricato il programma di installazione da Microsoft (dal portale o usando l'URL AKA.ms indicato sopra), decomprimerne il contenuto per accedere al file **ManagedRoomsInstaller.msi**.

Esistono due modalità di installazione, ovvero l'installazione di singoli computer locali e la modalità di distribuzione di massa (in genere tramite criteri di gruppo con metodo simile). È consigliabile eseguire l'installazione individuale per computer non aggiunti a un dominio o per computer in cui non è possibile eseguire programmi di installazione MSI in remoto.  

A causa dei diversi modi in cui i clienti possono eseguire applicazioni MSI in modalità di distribuzione di massa, questo documento illustra solo l'installazione in modalità singola.  

 > [!NOTE]
 > Il flusso del programma di installazione è lo stesso, indipendentemente dalla modalità in esecuzione. L'unica piccola differenza è che l'installazione non richiede all'utente di premere i pulsanti avanti e chiudi in modalità di distribuzione di massa.  

## <a name="individual-devicemdashdomain-joined-walkthrough"></a>Procedura dettagliata &mdash; per singoli dispositivi aggiunti a un dominio

1. Accedere al dispositivo come amministratore: assicurarsi che siano seguite le operazioni eseguite come utente amministratore *dei* passaggi del dispositivo.

1. Copiare i file seguenti nel dispositivo MTR:

   - Inserire la "chiave di autoregistrazione" (scaricata in precedenza dal portale) nella directory **C:\Rigel** del dispositivo.
   - Copiare **ilManagedRoomsInstaller.msi** (precedentemente scaricato dal portale o dal AKA.MS) nel dispositivo.

1. Durante **l'esecuzione delManagedRoomsInstaller.msi** _, verrà visualizzata la schermata Contratto di licenza. Dopo aver letto il contratto, verificare _*_che accetti i termini_*_ del Contratto di licenza e premere il pulsante _ *Installa**.  

    Viene avviata l'installazione Microsoft Teams Rooms software di monitoraggio dei servizi gestiti. Viene visualizzata una richiesta di elevazione (esegui come amministratore).
 1. Selezionare ***Sì***.

    L'installazione continuerà. Durante la procedura di installazione si apre una finestra della console che inizia la fase finale del Microsoft Teams Rooms - Installazione del software di monitoraggio dei servizi gestiti.  

    > [!NOTE]
    > Non chiudere la finestra. Al termine dell'installazione, la procedura guidata visualizza il pulsante "Fine".

## <a name="completing-enrollment"></a>Completamento della registrazione

Al termine dell'installazione, attendere 5-10 minuti e aggiornare il portale e il dispositivo verrà elencato, segnalato come stato *onboarding.*

Nello *stato Onboarding* lo stato della chat room viene visualizzato e aggiornato, ma non genera avvisi né crea ticket di indagine.

Scegliere la chat room e selezionare **Registra**  per iniziare a ricevere avvisi di incidente, ticket di indagine o per segnalare un incidente.

Per eventuali domande o problemi, aprire un evento imprevisto segnalato dal cliente nel portale o contattare managedroomsupport@microsoft.com.

### <a name="unenrolling-and-uninstalling-monitoring-software"></a>Annullamento della registrazione e disinstallazione del software di monitoraggio

Per annullare la registrazione del dispositivo, rimuovere l'agente di monitoraggio dal dispositivo MTR nel modo seguente:

1. Nel dispositivo monitorato accedere al dispositivo come amministratore. Assicurarsi di seguire la procedura descritta in Esecuzione di operazioni come *utente amministratore del dispositivo.*
1. Scaricare lo script di reimpostazione [da aka.ms/MTRPDeviceOffBoarding](https://aka.ms/MTRPDeviceOffBoarding).
1. Estrarre lo script in un punto qualsiasi del dispositivo e copiare il percorso.
1. Aprire PowerShell come amministratore: nel campo Windows ***Search** _ (sezione in basso a sinistra dello schermo), immettere 'Powershell' e fare clic con il pulsante destro del mouse su _*_Windows PowerShell_**.
1. Selezionare *"Esegui come amministratore" e* accettare la richiesta di controllo dell'account utente.
1. Immettere *Set-ExecutionPolicy –ExecutionPolicy RemoteSigned* , quindi premere **Y** al prompt successivo.  
1. Incollare o digitare il percorso completo dello script di offboarding decompresso nella finestra di PowerShell e premere **INVIO.**

   Ad esempio:

   *C:\Users\admin\Downloads\MTRP \_ Device \_ Offboarding\MTRP \_ Device \_Offboarding.ps1*  

   In questo modo il dispositivo viene reimpostato con gli aggiornamenti MTR standard dell'utente e vengono rimossi l'agente di monitoraggio MTRP e i file.

1. Nel menu a sinistra nel portale Microsoft Teams Rooms - Servizi gestiti selezionare **Sale.**  
1. Nell'elenco delle chat room disponibili scegliere la chat  room da annullare la registrazione e selezionare Annulla registrazione per interrompere la visualizzazione di avvisi di eventi imprevisti o ticket di indagine o per segnalare un evento imprevisto per la chat room.

## <a name="troubleshooting-table"></a>Tabella di risoluzione dei problemi

> [!NOTE]
> Tutti Microsoft Teams Rooms: gli errori di monitoraggio dei servizi gestiti vengono registrati in un file di log eventi specifico denominato **Microsoft Managed Rooms.** 

### <a name="application-runtime-log-file-location-"></a>***Percorso del file di log di Application Runtime*** =  

C:\Windows\ServiceProfiles\LocalService\AppData\Local\ServicePortalAgent\ app-x.x.x\ServicePortalAgent\ServicePortal \_ Verbose \_ LogFile.log, dove **x.x.x** è il numero di versione dell'app.

|**Sintomo**  |**Procedura consigliata**  |
| :- | :- |
|<p>Viene visualizzato un messaggio di errore che indica   </p><p>***ERRORE: Eseguire l'applicazione con** _ </p><p>_ *_privilegi elevati_**  </p>|Eseguire l'applicazione con privilegi elevati e riprovare  |
|  |  |
|<p>Viene visualizzato un messaggio di errore che indica   </p><p>***Non è possibile trovare dati TPM***  </p>|Verificare che il TPM (Trusted Platform Module) del dispositivo sia attivato nel BIOS. Questo problema si trova in genere nelle impostazioni di sicurezza del BIOS del dispositivo  |
|  |  |
|<p>Viene visualizzato un messaggio di errore  </p><p>` `***ERRORE: account utente locale denominato "Amministratore" o "Skype" non trovato***  </p>|Verificare che gli account utente siano presenti nel dispositivo Microsoft Teams room.  |
|  |  |
|Vengono visualizzati messaggi di stato di errore non coperti in precedenza  |Fornisci una copia del log di installazione all'agente Microsoft Teams di sistema. |
