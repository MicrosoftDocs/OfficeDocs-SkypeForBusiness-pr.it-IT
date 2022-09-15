---
title: Configurare riunioni coordinate con Microsoft Teams Rooms e Surface Hub
ms.author: dstrome
author: dstrome
ms.reviewer: rahulmi
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Configura Teams Rooms dispositivi e Surface Hub per partecipare alle riunioni quando un dispositivo o l'altro partecipa a una riunione.
ms.openlocfilehash: 759574015f2138476e0b03ef6fa85b8b105d81ef
ms.sourcegitcommit: 424b14534aa269bb408c97c368102a193b481656
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2022
ms.locfileid: "67706983"
---
# <a name="set-up-coordinated-meetings-with-microsoft-teams-rooms-and-surface-hub"></a>Configurare riunioni coordinate con Microsoft Teams Rooms e Surface Hub

Se disponi di uno o più dispositivi Microsoft Teams Rooms o Surface Hub in una sala riunioni, puoi configurare le riunioni coordinate. Riunioni coordinate consente di configurare i dispositivi Teams Rooms e Surface Hub in modo che, quando si partecipa a una riunione su un dispositivo, alla stessa riunione partecipi anche gli altri dispositivi della sala. Puoi configurare le fotocamere, gli altoparlanti e i microfoni in modo che quelli che offrono ai partecipanti l'esperienza migliore siano abilitati mentre gli altri vengono disabilitati. In questo modo si evita l'eco temuta e il rumore di feedback che i partecipanti possono avvertire quando aggiungono più dispositivi a una riunione.

Per configurare riunioni coordinate, è necessario verificare che i dispositivi Teams Rooms e Surface Hub siano già configurati correttamente per partecipare alle riunioni. Soprattutto, ogni dispositivo deve avere una propria cassetta postale della sala di Exchange. Per informazioni su come configurarli, vedere gli articoli seguenti:

- [Distribuire Microsoft Teams Rooms](../rooms/rooms-deploy.md)
- [Creare l'account del dispositivo Surface Hub 2S](/surface-hub/surface-hub-2s-account)

Dopo aver confermato che i dispositivi Teams Rooms e Surface Hub possono accettare automaticamente le riunioni e parteciparvi correttamente, è possibile configurare riunioni coordinate.

I passaggi seguenti devono essere completati separatamente per ogni sala riunioni.

## <a name="step-1-plan-your-coordinated-meeting-experience"></a>Passaggio 1: Pianificare l'esperienza di riunione coordinata

Prima di apportare modifiche alla configurazione, è necessario decidere quali dispositivi eseguire in ogni sala riunioni. Ovvero, per una determinata sala riunioni, è necessario decidere quale dispositivo avrà il microfono, la fotocamera e la lavagna attivi. La procedura per configurare i dispositivi dipende dall'ambiente specifico, ma ecco alcuni suggerimenti generali da cui iniziare:

- **Microfono** Teams Rooms dispositivo
- **Fotocamera** Teams Rooms dispositivo (attivata per impostazione predefinita) e Surface Hub (disattivata per impostazione predefinita, ma può essere attivata dai partecipanti)
- **Lavagna** Surface Hub

> [!IMPORTANT]
> Assicurati di abilitare il microfono su un solo dispositivo. Se l'opzione viene abilitata in più dispositivi, si verificherà un'eco audio e un feedback.

## <a name="step-2-get-your-devices-upns"></a>Passaggio 2: Ottenere gli UPN dei dispositivi

Quando configuri un'esperienza di riunione coordinata in una sala riunioni, devi comunicare ai dispositivi Teams Rooms e Surface Hub della sala con cui coordinarti. A questo scopo, aggiungere il nome dell'entità utente (UPN) dei dispositivi con cui deve coordinarsi alla configurazione. Se non si conoscono gli UPN per ognuno dei dispositivi da configurare per le riunioni coordinate, è possibile trovarli usando il interfaccia di amministrazione di Microsoft 365. 

È necessario avere un ruolo di amministratore per accedere al interfaccia di amministrazione di Microsoft 365. Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](/microsoft-365/admin/add-users/about-admin-roles).

Per ottenere gli UPN dei tuoi dispositivi Teams Rooms e Surface Hub, procedi come segue:

1. Accedi al interfaccia di amministrazione di Microsoft 365 visitando https://admin.microsoft.com.
2. Passare a **Utenti** > **attivi**.
3. Trova il nome del dispositivo Teams Rooms o di Surface Hub nella colonna **Nome visualizzato** (puoi usare la casella **di ricerca** se hai molti utenti).
4. Trovare l'UPN nella colonna **Nome utente** , ad esempio alias@contoso.com o alias@contoso.onmicrosoft.com.
5. Ripetere l'operazione per ogni dispositivo che parteciperà alle riunioni coordinate.

## <a name="step-3-create-a-deployment-worksheet"></a>Passaggio 3: Creare un foglio di lavoro per la distribuzione

Dopo aver pianificato l'esperienza di riunione coordinata e aver raccolto un elenco degli UPN dei dispositivi, è consigliabile creare un foglio di lavoro per la distribuzione. Un foglio di lavoro di distribuzione consente di visualizzare la configurazione da impostare in tutti i dispositivi, consentendo di convalidare le scelte effettuate e verificare la presenza di errori.

In un'app foglio di calcolo aggiungere le righe seguenti nella prima colonna:

| Impostazione                | Descrizione      |
|------------------------|-----------------|
| **Impostazione predefinita per l'audio**      | Determina in quale dispositivo sarà attivo il microfono all'avvio di una riunione. Questo campo può essere impostato su `true` un solo dispositivo (in genere un dispositivo Teams Rooms), mentre per il resto dei dispositivi questo campo deve essere impostato su per `false` evitare eco audio e feedback.          |
| **Audio abilitato**      | Determina se i partecipanti a una riunione possono attivare o disattivare il microfono. Per i dispositivi su cui è impostata `false` **l'impostazione audio predefinita**, questa impostazione deve essere impostata `false` su in modo che i partecipanti non possano attivare accidentalmente un microfono e causare eco audio o feedback.<p>Se **l'opzione Audio** è impostata su `true`, questa impostazione viene ignorata e i partecipanti possono disattivare o riattivare l'audio del microfono.          |
| **Impostazione predefinita per il video**      | Determina in quale dispositivo la fotocamera sarà attiva all'avvio di una riunione. Per un'esperienza ottimale, è consigliabile impostare `true` solo il Teams Rooms dispositivo, mentre tutti gli altri dispositivi sono impostati su `false`.          |
| **Video abilitato**      | Determina se i partecipanti a una riunione possono attivare o disattivare la fotocamera. Puoi impostare questa `true` opzione su su qualsiasi altro dispositivo nei partecipanti all'evento che vogliono condividere prospettive video diverse (ad esempio se un partecipante usa la lavagna di Surface Hub). Se non si vuole che i partecipanti attivino o disattivino una fotocamera in un dispositivo, impostare questa `false`opzione su .<p> Se **l'impostazione predefinita video** è `true`, questa impostazione viene ignorata e i partecipanti possono attivare o disattivare la fotocamera.         |
| **Impostazione predefinita lavagna** | Determina se il dispositivo Teams Rooms visualizzerà una lavagna condivisa da uno dei partecipanti alla riunione. Ti consigliamo di impostare questa opzione su `false` se hai un Surface Hub e `true` se non ne hai uno. Questa impostazione non ha alcun effetto su Surface Hub. Surface Hubs mostrerà sempre una lavagna condivisa dai partecipanti alla riunione.         |
| **Lavagna abilitata** | Determina se i partecipanti a una riunione possono attivare o disattivare la lavagna. Se non vuoi che i partecipanti attivino o disabilitino la lavagna in un dispositivo, imposta questa `false`opzione su . <p>Se **l'impostazione predefinita di Whiteboard** è `true`, questa impostazione viene ignorata e i partecipanti possono attivare o disattivare la lavagna.
| **Account attendibili**   | Si tratta di un elenco di UPN separati da virgole per ogni dispositivo Teams Rooms o Surface Hub da cui il dispositivo deve accettare convocazioni di partecipazione a riunioni o a cui devono essere inviate le convocazioni di partecipazione. |

Nelle colonne successive aggiungi ogni dispositivo Teams Rooms e Surface Hub. In ogni colonna immettere i valori che corrispondono all'esperienza desiderata per la sala riunioni. Ecco un esempio con un dispositivo Teams Rooms e un dispositivo Surface Hub:

- Dispositivo di Teams
  - L'audio e il video sono **attivati** all'avvio di una riunione. I partecipanti **possono** attivare o disattivare audio e video.
  - La visualizzazione di una lavagna condivisa è disattivata.
- Surface Hub
  - L'audio è **disattivato** all'avvio di una riunione. I partecipanti non possono attivare o disattivare **l'audio** .
  - Il video è **disattivato** all'avvio di una riunione. I partecipanti **possono** attivare o disattivare il video.

| Impostazione                | Sala riunioni di Teams      | Surface Hub      |
|------------------------|-----------------|------------------|
| **Impostazione predefinita per l'audio**      | `true`          | `false`          |
| **Audio abilitato**      | `true`          | `false`          |
| **Impostazione predefinita per il video**      | `true`          | `false`          |
| **Video abilitato**      | `true`          | `true`           |
| **Impostazione predefinita lavagna** | `false`         | `false`          |
| **Account attendibili**   | hub@contoso.com | room@contoso.com |

## <a name="step-4-configure-teams-rooms-device"></a>Passaggio 4: Configurare Teams Rooms dispositivo

È possibile configurare riunioni coordinate in un dispositivo Teams Rooms usando il touchscreen del dispositivo oppure, se è necessario configurare più dispositivi e si vuole farlo da una posizione centrale, è possibile usare un file di configurazione XML.

Usare il foglio di lavoro creato nel passaggio precedente per configurare i dispositivi.

### <a name="use-the-teams-rooms-devices-touch-screen"></a>Usare il touchscreen del dispositivo Teams Rooms

Per configurare riunioni coordinate in un dispositivo, eseguire le operazioni seguenti:

1. Seleziona **... Altre** > **impostazioni**.
2. Immettere la password dell'amministratore e selezionare **Sì**.
3. Selezionare **Riunioni coordinate**.
4. In **Opzioni** impostare **Riunione coordinata** _su attivato_.
5. Se **l'opzione Audio predefinita** nel foglio di lavoro è `true`, impostare **Attiva microfono del dispositivo** su Attivato, altrimenti _lasciarlo disattivato_.
6. Se **l'opzione Audio abilitato** nel foglio di lavoro è `true`, selezionare **Consenti agli utenti di abilitare la partecipazione a una riunione** in **Attiva il microfono del dispositivo**. Questa opzione non può essere disattivata se **l'opzione Attiva il microfono del dispositivo** è attivata.
7. Se **l'impostazione predefinita di Video** nel foglio di lavoro è `true`, impostare **Attiva la fotocamera del dispositivo** su Attivato, altrimenti _lasciarla disattivata_.
8. Se **l'opzione Video abilitato** nel foglio di lavoro è `true`, selezionare **Consenti agli utenti di abilitare la partecipazione a una riunione** in **Attiva la fotocamera del dispositivo**. Questa opzione non può essere disattivata se **l'opzione Attiva la fotocamera del dispositivo** è _attivata_.
9. Se **l'impostazione predefinita di Whiteboard** nel foglio di lavoro è `true`, impostare **Attiva lavagna nel dispositivo su** _Attivato_, altrimenti _lasciarla disattivata_.
10. In **Account di dispositivo attendibili** digitare ogni UPN elencato in **Account attendibili** nel foglio di lavoro. Separare più UPN con virgole.
11. Nel dispositivo attendibile disattivare la prossimità e il telecomando della sala. 
12. Seleziona **Salva e chiudi**.

Dopo aver selezionato **Salva e chiudi**, il dispositivo verrà riavviato e sarà pronto per partecipare alle riunioni coordinate.

### <a name="use-the-teams-rooms-xml-configuration-file"></a>Usare il file di configurazione XML Teams Rooms

Le riunioni coordinate possono essere configurate usando il file di configurazione XML del `SkypeSettings.xml` dispositivo Teams Rooms. Il `SkypeSettings.xml` file non è statico. Quando il dispositivo Teams Rooms viene avviato, cerca `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` un file denominato `SkypeSettings.xml`. Se il file esiste, il dispositivo legge e applica la configurazione specificata nel file. Al termine dell'applicazione della configurazione, il file viene eliminato. Per altre informazioni sul file, vedere Gestire le impostazioni della `SkypeSettings.xml` [console con un file di configurazione XML](../rooms/xml-config-file.md#manage-console-settings-with-an-xml-configuration-file).

Di seguito è riportata la sintassi delle impostazioni riunione coordinate nel file di configurazione:

```xml
<CoordinatedMeetings enabled="true">
    <Settings>
        <Audio default="true" enabled="true"/>
        <Video default="true" enabled="true"/>
        <Whiteboard default="false" enabled="false"/>
    </Settings>
    <TrustedAccounts>hub@contoso.com</TrustedAccounts>
</CoordinatedMeetings>
```

Per configurare riunioni coordinate in un dispositivo, eseguire le operazioni seguenti:

1. In un editor di file di testo, ad esempio Visual Studio Code o Blocco note, incollare il codice XML precedente in un nuovo file.

2. Impostare ognuno degli elementi XML sul valore corrispondente `true` o `false` nel foglio di calcolo. Ad esempio, se **l'impostazione predefinita audio** è `true`, impostare `<Audio default="true">`.

3. Assicurarsi di passare `TrustedAccounts` all'elenco di UPN.

4. Salvare il file con il nome `SkypeSettings.xml`.

5. Inserisci il file nella cartella del `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` dispositivo Teams Rooms. È possibile eseguire questa operazione in diversi modi:

    - **Copiare il file nel dispositivo Teams Rooms** È necessario abilitare la condivisione dei file e creare una condivisione di rete prima di poter copiare i file nel dispositivo. Dopo averlo fatto, puoi connetterti alla condivisione di rete e copiare il file nel dispositivo. Per altre informazioni, vedere [Microsoft Teams Rooms manutenzione e le operazioni](../rooms/rooms-operations.md).
    - **Usare un Criteri di gruppo** Creare criteri di gruppo per copiare il file nel dispositivo. Per altre informazioni, vedere [Panoramica Criteri di gruppo](/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831791(v=ws.11)).
    - **Scarica il file nel dispositivo Teams Rooms** Puoi accedere al dispositivo utilizzando la modalità Amministrazione e quindi copiare il file nel dispositivo da una condivisione di rete o un'unità USB. Per altre informazioni, vedere [Passaggio alla modalità Amministrazione](../rooms/rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running).
    
6. Riavvia il dispositivo. È possibile eseguire questa operazione in due modi:

    - **Remote PowerShell** È possibile eseguire il comando Arresta il sistema nel dispositivo usando una sessione remota di PowerShell. Per altre informazioni, vedere [Gestione remota con PowerShell](../rooms/rooms-operations.md).
    - **Eseguire il riavvio del computer** È possibile eseguire il cmdlet nel `Restart-Computer` computer locale e specificare il nome del computer del dispositivo da riavviare. Per ulteriori informazioni, vedi [Riavvia-Computer](/powershell/module/microsoft.powershell.management/restart-computer?view=powershell-7).

## <a name="step-5-configure-surface-hub"></a>Passaggio 5: Configurare Surface Hub

Puoi utilizzare Progettazione configurazione di Windows per creare un pacchetto di provisioning che puoi utilizzare per applicare le impostazioni riunioni coordinate a Surface Hub. Il file XML creato in precedenza verrà incollato in Progettazione configurazione di Windows per creare il pacchetto di provisioning.

### <a name="create-coordinated-meetings-xml-configuration-file-for-surface-hub"></a>Creare un file di configurazione XML per riunioni coordinate per Surface Hub

Sia Progettazione configurazione di Windows che Microsoft Intune vengono utilizzati per applicare la configurazione Riunioni coordinate a Surface Hub. La configurazione viene definita tramite XML. Prima di procedere, è necessario creare il codice XML che verrà applicato.

Di seguito è riportata la sintassi del file di configurazione XML Coordinated Meetings.

```xml
<SurfaceHubSettings>
    <BluetoothAdvertisementEnabled>true</BluetoothAdvertisementEnabled>
    <AutoAcceptProximateMeetingInvitations>true</AutoAcceptProximateMeetingInvitations>
    <CoordinatedMeetings enabled="true"> 
        <TrustedAccounts>room@contoso.com</TrustedAccounts>
        <Settings> 
            <Audio default="false" enabled="false" />
            <Video default="false" enabled="true" /> 
        </Settings> 
    </CoordinatedMeetings>
</SurfaceHubSettings>
```

Per preparare il file XML per Progettazione configurazione di Windows o per Microsoft Intune, eseguire le operazioni seguenti:

1. In un editor di file di testo, ad esempio Visual Studio Code o Blocco note, incollare il codice XML precedente in un nuovo file.

2. Impostare ognuno degli elementi XML sul valore corrispondente `true` o `false` nel foglio di calcolo. Ad esempio, se **l'impostazione predefinita audio** è `true`, impostare `<Audio default="true">`.

3. Assicurarsi di passare `TrustedAccounts` all'elenco di UPN.

4. Progettazione configurazione di Windows richiede che il codice XML sia su una singola riga. Rimuovere tutte le interruzioni di riga tra ogni riga in modo che il codice XML abbia l'aspetto seguente:

    ```xml
    <SurfaceHubSettings><BluetoothAdvertisementEnabled>true</BluetoothAdvertisementEnabled>...
    ```

5. Salvare il file nel computer.

Dopo aver creato il file di configurazione XML, usare la procedura descritta in [Gestire le impostazioni di Microsoft Teams in Surface Hub](surface-hub-manage-config.md) per applicarlo a Surface Hub.
