---
title: Configurare riunioni coordinate con Le sale di Microsoft Teams e Surface Hub
ms.author: dstrome
author: dstrome
ms.reviewer: rahulmi
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
localization_priority: Normal
description: Configurare i dispositivi di Teams Rooms e Surface Hub per partecipare alle riunioni quando un dispositivo o l'altro partecipa a una riunione.
ms.openlocfilehash: cfd8bd423d8f7765a973d55e42d64773a06bba32
ms.sourcegitcommit: bd13aecbb25c14e17d1b64343df6d80c90b2aa45
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/19/2020
ms.locfileid: "46803938"
---
# <a name="set-up-coordinated-meetings-with-microsoft-teams-rooms-and-surface-hub"></a>Configurare riunioni coordinate con Le sale di Microsoft Teams e Surface Hub

Se si hanno uno o più dispositivi Microsoft Teams Room o Surface Hub in una sala riunioni, è possibile configurare riunioni coordinate. Riunioni coordinate consente di configurare i dispositivi delle sale di Teams e i Surface Hub in modo che, quando si partecipa a una riunione su un dispositivo, alla stessa riunione si uniranno anche gli altri dispositivi della sala. È possibile configurare le videocamere, gli altoparlanti e i microfoni in modo che quelli che offrono ai partecipanti la migliore esperienza siano abilitati, mentre gli altri sono disabilitati. In questo modo si evita che i partecipanti possano avere l'eco temuta e il rumore di feedback durante l'aggiunta di più dispositivi a una riunione.

Per configurare riunioni coordinate, è necessario assicurarsi che i dispositivi Della sala di Teams e Surface Hub siano già configurati correttamente per partecipare alle riunioni. E soprattutto, ogni dispositivo deve avere una propria cassetta postale della sala di Exchange. Per informazioni su come configurarle, vedere gli articoli seguenti:

- [Distribuire Microsoft Teams Rooms](../rooms/rooms-deploy.md)
- [Creare l'account del dispositivo Surface Hub 2S](https://docs.microsoft.com/surface-hub/surface-hub-2s-account)

Dopo aver confermato che i dispositivi Sala di Teams e Surface Hub possono accettare automaticamente le riunioni e parteciparvi correttamente, è possibile configurare riunioni coordinate.

I passaggi seguenti devono essere completati separatamente per ogni sala riunioni. I dispositivi presenti in una sala riunioni non devono essere impostati per le riunioni coordinate con i dispositivi presenti in altre sale riunioni.

## <a name="step-1-plan-your-coordinated-meeting-experience"></a>Passaggio 1: Pianificare l'esperienza della riunione coordinata

Prima di apportare modifiche alla configurazione, è necessario decidere quali dispositivi dovranno eseguire le attività in ogni sala riunioni. Ciò significa che per una determinata sala riunioni è necessario decidere quale dispositivo avrà il microfono, la fotocamera e la lavagna attivi. La modalità di configurazione dei dispositivi dipende dall'ambiente specifico, ma ecco alcuni consigli generali da cui iniziare:

- **Microfono** Dispositivo Teams Rooms
- **Fotocamera** Dispositivo Sale di Teams (attivato per impostazione predefinita) e Surface Hub (disattivato per impostazione predefinita, ma consentito dai partecipanti)
- **Lavagna** Surface Hub

> [!IMPORTANT]
> Assicurati di abilitare il microfono su un solo dispositivo. Se la abiliti in più dispositivi, riscontri eco audio e feedback.

## <a name="step-2-get-your-devices-upns"></a>Passaggio 2: Ottenere gli UPN dei dispositivi

Quando si configura un'esperienza di riunione coordinata in una sala riunioni, è necessario indicare ai dispositivi della sala riunioni di Teams e ai Surface Hub della sala con quali dispositivi coordinarsi. A questo scopo, aggiungere il nome dell'entità utente (UPN) dei dispositivi con cui deve coordinarsi alla configurazione. Se non si conoscono gli UPN di ognuno dei dispositivi da configurare per riunioni coordinate, è possibile trovarli tramite l'interfaccia di amministrazione di Microsoft 365. 

Per accedere all'interfaccia di amministrazione di Microsoft 365, è necessario avere un ruolo di amministratore. Per altre informazioni, vedere [Informazioni sui ruoli di amministratore.](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)

Per ottenere gli UPN dei dispositivi Sala di Teams e Surface Hub, eseguire le operazioni seguenti:

1. Accedi all'interfaccia di amministrazione di Microsoft 365 visitando https://admin.microsoft.com .
2. Passare a **Utenti**  >  **attivi.**
3. Trovare il nome del dispositivo Sale di  Teams o Surface Hub  nella colonna Nome visualizzato (è possibile usare la casella di ricerca se gli utenti sono numerosi).
4. Trovare l'UPN nella **colonna Nome** utente (sarà simile a alias@contoso.com o alias@contoso.onmicrosoft.com).
5. Ripetere l'operazione per ogni dispositivo che parteciperà a riunioni coordinate.

## <a name="step-3-create-a-deployment-worksheet"></a>Passaggio 3: Creare un foglio di lavoro per la distribuzione

Dopo aver pianificato l'esperienza della riunione coordinata e raccolto un elenco degli UPN dei dispositivi, è una buona idea creare un foglio di lavoro di distribuzione. Un foglio di lavoro di distribuzione consente di visualizzare la configurazione da impostare in tutti i dispositivi, consentendo di convalidare le scelte effettuate e verificare la presenza di errori.

In un'app foglio di calcolo aggiungere nella prima colonna le righe seguenti:

| Impostazione                | Descrizione      |
|------------------------|-----------------|
| **Audio predefinito**      | Determina il dispositivo in cui il microfono sarà attivo all'avvio di una riunione. Questo campo può essere impostato su un solo dispositivo (in genere un dispositivo Teams Room), mentre per gli altri dispositivi deve essere impostato questo campo per evitare eco `true` `false` audio e feedback.          |
| **Audio abilitato**      | Determina se i partecipanti a una riunione possono attivare o disattivare il microfono. Per i **dispositivi** per cui è impostata l'impostazione predefinita audio, questa impostazione deve essere impostata in modo che i partecipanti non possano attivare accidentalmente un microfono e causare `false` `false` eco audio o feedback.<p>Se **l'opzione Audio** predefinita è impostata su , questa impostazione viene ignorata e i partecipanti possono disattivare o `true` riattivare l'audio del microfono.          |
| **Impostazione predefinita del video**      | Determina il dispositivo in cui la videocamera sarà attiva all'avvio di una riunione. Per un'esperienza ottimale, è consigliabile impostare solo il dispositivo Sale di `true` Teams, mentre tutti gli altri dispositivi sono impostati su `false` .          |
| **Video abilitato**      | Determina se i partecipanti a una riunione possono attivare o disattivare la videocamera. Puoi impostare questa opzione su qualsiasi altro dispositivo nell'evento in cui i partecipanti vogliono condividere prospettive video diverse (ad esempio se un partecipante usa la lavagna `true` di Surface Hub). Se non si vuole che i partecipanti accendono o spegnino la fotocamera in un dispositivo, impostare questa opzione su `false` .<p> Se **l'impostazione predefinita** è Video, questa impostazione viene ignorata e i partecipanti possono attivare o `true` disattivare la videocamera.         |
| **Impostazione predefinita della lavagna** | Determina se nel dispositivo Sale di Teams verrà visualizzata una lavagna condivisa da uno dei partecipanti alla riunione. È consigliabile impostare questa opzione se si ha un Surface Hub e se non `false` `true` se ne ha uno. Questa impostazione non ha alcun effetto su Surface Hub. Surface Hub visualizza sempre una lavagna condivisa dai partecipanti alla riunione.         |
| **Lavagna abilitata** | Determina se i partecipanti a una riunione possono attivare o disattivare la lavagna. Se non si vuole che i partecipanti accendono o disaccendono la lavagna in un dispositivo, impostare questa opzione su `false` . <p>Se **l'impostazione predefinita** di Whiteboard è , questa impostazione viene ignorata e i partecipanti possono attivare o `true` disattivare la lavagna.
| **Account attendibili**   | Si tratta di un elenco separato da virgole di UPN per ogni dispositivo Teams Room o Surface Hub da cui il dispositivo deve accettare le convocazioni di partecipazione alle riunioni o a cui devono essere inviate le convocazioni di partecipazione. |

Nelle colonne successive, aggiungere ogni dispositivo di Teams Room e Surface Hub. In ogni colonna compilare i valori che corrispondono all'esperienza desiderata per la sala riunioni. Ecco un esempio con un dispositivo Sale di Teams e un Surface Hub:

- Dispositivo Teams
  - Audio e video sono **attivati all'avvio** di una riunione. I partecipanti **possono attivare** o disattivare audio e video.
  - La visualizzazione di una lavagna condivisa è disattivata.
- Surface Hub
  - L'audio viene **disattivato all'avvio** di una riunione. I partecipanti non possono attivare o disattivare **l'audio.**
  - Il video viene **disattivato all'avvio** di una riunione. I partecipanti **possono attivare** o disattivare il video.

| Impostazione                | Teams Room      | Surface Hub      |
|------------------------|-----------------|------------------|
| **Audio predefinito**      | `true`          | `false`          |
| **Audio abilitato**      | `true`          | `false`          |
| **Impostazione predefinita del video**      | `true`          | `false`          |
| **Video abilitato**      | `true`          | `true`           |
| **Impostazione predefinita della lavagna** | `false`         | `false`          |
| **Account attendibili**   | hub@contoso.com | room@contoso.com |

## <a name="step-4-configure-teams-rooms-device"></a>Passaggio 4: Configurare il dispositivo Sale di Teams

È possibile configurare riunioni coordinate in un dispositivo Teams Room usando il touchscreen del dispositivo oppure, se è necessario configurare molti dispositivi e si vuole farlo da una posizione centralizzata, è possibile usare un file di configurazione XML.

Usare il foglio di lavoro creato nel passaggio precedente per facilitare la configurazione dei dispositivi.

### <a name="use-the-teams-rooms-devices-touch-screen"></a>Usare il touchscreen del dispositivo Teams Rooms

Per configurare riunioni coordinate su un dispositivo, eseguire le operazioni seguenti:

1. **Seleziona... Altre**  >  **impostazioni.**
2. Immettere la password dell'amministratore e selezionare **Sì.**
3. Selezionare **Riunioni coordinate.**
4. In **Opzioni,** impostare **Riunione coordinata** _su On._
5. Se **l'opzione Audio** predefinita nel foglio di lavoro è attivata, attivare il microfono del `true` dispositivo, altrimenti _lasciarlo disattivato._ 
6. Se **l'audio** è abilitato nel foglio di lavoro, selezionare Consenti alle persone di abilitare l'opzione quando si partecipa a una riunione in Attiva `true` **microfono del dispositivo.**  Questa opzione non può essere disattivata se **attiva** il microfono di questo dispositivo.
7. Se **il valore predefinito** di Video nel foglio di lavoro è , impostare attiva la fotocamera del dispositivo, altrimenti `true` _lasciarla disattivata._ 
8. Se **il video è** abilitato nel foglio di lavoro, selezionare Consenti alle persone di abilitare `true` **l'opzione** quando si partecipa **a** una riunione in Attiva fotocamera del dispositivo. Questa opzione non può essere disattivata se attiva la **fotocamera** del _dispositivo._
9. Se **l'impostazione predefinita** di Whiteboard nel foglio di lavoro è , impostare attiva la lavagna nel dispositivo, altrimenti `true`   _lasciarla disattivata._
10. In **Account attendibili per dispositivi** digitare ogni UPN elencato in Account **attendibili** nel foglio di lavoro. Separare più UPN con virgole.
11. Selezionare **Salva e esci.**

Dopo aver selezionato **Salva e chiuso,** il dispositivo verrà riavviato e sarà pronto per partecipare alle riunioni coordinate.

### <a name="use-the-teams-rooms-xml-configuration-file"></a>Usare il file di configurazione XML di Teams Rooms

Le riunioni coordinate possono essere impostate usando il file di configurazione XML del dispositivo Teams `SkypeSettings.xml` Rooms. Il `SkypeSettings.xml` file non è un file statico. All'avvio, il dispositivo Teams Rooms lo controlla `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` per cercare un file `SkypeSettings.xml` denominato. Se il file esiste, il dispositivo legge e applica la configurazione specificata nel file. Al termine dell'applicazione della configurazione, il file viene eliminato. Per altre informazioni sul `SkypeSettings.xml` file, vedere Gestire le impostazioni [della console con un file di configurazione XML.](../rooms/xml-config-file.md#manage-console-settings-with-an-xml-configuration-file)

Di seguito è riportata la sintassi delle impostazioni di Riunioni coordinate nel file di configurazione:

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

Per configurare riunioni coordinate su un dispositivo, eseguire le operazioni seguenti:

1. In un editor di file di testo, ad esempio Visual Studio Code o Blocco note, incollare il codice XML precedente in un nuovo file.

2. Impostare ognuno degli elementi XML sul valore corrispondente `true` o sul valore nel foglio di `false` calcolo. Ad esempio, se **l'impostazione predefinita di Audio** `true` è , impostare `<Audio default="true">` .

3. Assicurarsi di passare `TrustedAccounts` all'elenco di UPN.

4. Salvare il file con il nome `SkypeSettings.xml` .

5. Inserire il file nella cartella del dispositivo Teams `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` Rooms. Questa operazione può essere possibile in diversi modi:

    - **Copiare il file nel dispositivo Teams Rooms** Sarà necessario abilitare la condivisione file e creare una condivisione di rete prima di poter copiare i file nel dispositivo. A questo scopo, è possibile connettersi alla condivisione di rete e copiare il file nel dispositivo. Per altre informazioni, vedere Manutenzione e operazioni [delle sale di Microsoft Teams.](../rooms/rooms-operations.md)
    - **Usare Criteri di gruppo** Creare criteri di gruppo per copiare il file nel dispositivo. Per altre informazioni, vedere [Panoramica di Criteri di gruppo.](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831791(v=ws.11))
    - **Scaricare il file nel dispositivo Teams Rooms** È possibile accedere al dispositivo usando la modalità di amministrazione e quindi copiare il file nel dispositivo da una condivisione di rete o da un'unità USB. Per altre informazioni, vedere [Passaggio alla modalità amministratore.](../rooms/rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running)
    
6. Riavviare il dispositivo. Questa operazione può essere possibile in due modi:

    - **PowerShell remoto** È possibile eseguire il comando Arresta nel dispositivo usando una sessione remota di PowerShell. Per altre informazioni, vedere [Gestione remota con PowerShell.](../rooms/rooms-operations.md)
    - **Esegui riavvio del computer** È possibile eseguire il cmdlet nel computer locale e specificare il nome del computer del dispositivo `Restart-Computer` da riavviare. Per altre informazioni, vedere [Riavviare il computer.](https://docs.microsoft.com/powershell/module/microsoft.powershell.management/restart-computer?view=powershell-7)

## <a name="step-5-configure-surface-hub"></a>Passaggio 5: Configurare Surface Hub

Puoi usare Progettazione configurazione di Windows per creare un pacchetto di provisioning che puoi usare per applicare le impostazioni di Riunioni coordinate a Surface Hub. Incollare il file XML creato in precedenza in Progettazione configurazione di Windows per creare il pacchetto di provisioning.

### <a name="create-coordinated-meetings-xml-configuration-file-for-surface-hub"></a>Creare un file di configurazione XML per riunioni coordinate per Surface Hub

Sia Progettazione configurazione di Windows che Microsoft Intune vengono usati per applicare la configurazione di Riunioni coordinate a Surface Hub. La configurazione viene definita tramite XML. Prima di procedere, è necessario creare il codice XML che verrà applicato.

Di seguito è riportata la sintassi del file di configurazione XML di Riunioni coordinate.

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

Eseguire le operazioni seguenti per preparare il codice XML per Progettazione configurazione di Windows o Microsoft Intune:

1. In un editor di file di testo, ad esempio Visual Studio Code o Blocco note, incollare il codice XML precedente in un nuovo file.

2. Impostare ognuno degli elementi XML sul valore corrispondente `true` o sul valore nel foglio di `false` calcolo. Ad esempio, se **l'impostazione predefinita di Audio** `true` è , impostare `<Audio default="true">` .

3. Assicurarsi di passare `TrustedAccounts` all'elenco di UPN.

4. Progettazione configurazione di Windows richiede che il codice XML sia su una sola riga. Rimuovere tutte le interruzioni di riga tra ogni riga in modo che il codice XML sia simile al seguente:

    ```xml
    <SurfaceHubSettings><BluetoothAdvertisementEnabled>true</BluetoothAdvertisementEnabled>...
    ```

5. Salvare il file nel computer.

Dopo aver creato il file di configurazione XML, usa la procedura descritta in Gestire le impostazioni di Microsoft Teams in [Surface Hub](surface-hub-manage-config.md) per applicarlo a Surface Hub.
