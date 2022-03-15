---
title: Configurare riunioni coordinate con Microsoft Teams Rooms e Surface Hub
ms.author: czawideh
author: cazawideh
ms.reviewer: rahulmi
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Configurare Teams Rooms dispositivi e Surface Hub partecipare alle riunioni quando un dispositivo o l'altro partecipa a una riunione.
ms.openlocfilehash: 5c52b1f6465db57613f45401c425a05286503454
ms.sourcegitcommit: a894e9397050e09bfaab02e700e943a3bbeb1302
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2022
ms.locfileid: "63503703"
---
# <a name="set-up-coordinated-meetings-with-microsoft-teams-rooms-and-surface-hub"></a>Configurare riunioni coordinate con Microsoft Teams Rooms e Surface Hub

Se hai uno o più dispositivi Microsoft Teams Rooms o Surface Hub in una sala riunioni, puoi configurare Riunioni coordinate. Riunioni coordinate consente di configurare i dispositivi Teams Rooms e Surface Hub in modo che, quando si partecipa a una riunione su un dispositivo, anche gli altri dispositivi della sala si uniranno alla stessa riunione. È possibile configurare le fotocamere, gli altoparlanti e i microfoni in modo che quelli che offrono ai partecipanti l'esperienza migliore siano abilitati mentre gli altri sono disabilitati. In questo modo si evitano i temuti e i rumori di feedback che i partecipanti possono sperimentare quando aggiungono più dispositivi a una riunione.

Per configurare riunioni coordinate, è necessario assicurarsi che i dispositivi Teams Rooms e Surface Hub siano già configurati correttamente per partecipare alle riunioni. Soprattutto, ogni dispositivo deve avere una propria cassetta postale Exchange sala. Per informazioni su come configurarle, vedere gli articoli seguenti:

- [Distribuire Microsoft Teams Rooms](../rooms/rooms-deploy.md)
- [Creare un Surface Hub dispositivo 2S](/surface-hub/surface-hub-2s-account)

Dopo aver confermato che i dispositivi Teams Rooms e Surface Hub possono accettare automaticamente le riunioni e partecipare correttamente, è possibile configurare riunioni coordinate.

I passaggi seguenti devono essere completati separatamente per ogni sala riunioni.

## <a name="step-1-plan-your-coordinated-meeting-experience"></a>Passaggio 1: Pianificare l'esperienza di riunione coordinata

Prima di apportare modifiche alla configurazione, è necessario decidere quali dispositivi dovranno eseguire in ogni sala riunioni. Ovvero, per una determinata sala riunioni, è necessario decidere quale dispositivo avrà il microfono, la fotocamera e la lavagna attivi. La modalità di configurazione dei dispositivi dipende dall'ambiente specifico, ma ecco alcuni consigli generali per iniziare:

- **Dispositivo Teams Rooms** microfono
- **Dispositivo** Teams Rooms fotocamera (attivato per impostazione predefinita) e Surface Hub (disattivato per impostazione predefinita, ma consentito ai partecipanti)
- **Whiteboard Surface Hub**

> [!IMPORTANT]
> Assicurarsi di abilitare il microfono solo in un dispositivo. Se lo abiliti in più dispositivi, si verificano l'eco audio e il feedback.

## <a name="step-2-get-your-devices-upns"></a>Passaggio 2: Ottenere gli UPN dei dispositivi

Quando si configura un'esperienza di riunione coordinata in una sala riunioni, è necessario indicare ai dispositivi Teams Rooms e ai Surface Hub della sala con quali dispositivi coordinarsi. Questa operazione viene eseguita aggiungendo il nome dell'entità utente (UPN) dei dispositivi con cui deve coordinarsi alla configurazione. Se non si conoscono gli UPN per ognuno dei dispositivi da configurare per le riunioni coordinate, è possibile trovarli usando il interfaccia di amministrazione di Microsoft 365. 

È necessario avere un ruolo di amministratore per accedere al interfaccia di amministrazione di Microsoft 365. Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](/microsoft-365/admin/add-users/about-admin-roles).

Per ottenere gli UPN dei dispositivi Teams Rooms e Surface Hub, eseguire le operazioni seguenti:To get the UPNs of your Teams Rooms devices and Surface Hubs, do the following:

1. Accedere al interfaccia di amministrazione di Microsoft 365 visitando https://admin.microsoft.com.
2. Passare a **UtentiAttivati** > .
3. Trovare il nome del dispositivo Teams Rooms o del Surface Hub nella colonna Nome visualizzato (è possibile  usare la casella di ricerca se si hanno  molti utenti).
4. Trovare l'UPN nella **colonna Nome** utente (sarà simile a alias@contoso.com o alias@contoso.onmicrosoft.com).
5. Ripetere l'operazione per ogni dispositivo che parteciperà alle riunioni coordinate.

## <a name="step-3-create-a-deployment-worksheet"></a>Passaggio 3: Creare un foglio di lavoro di distribuzione

Dopo aver pianificato l'esperienza di riunione coordinata e aver raccolto un elenco degli UPN dei dispositivi, è buona idea creare un foglio di lavoro per la distribuzione. Un foglio di lavoro di distribuzione consente di visualizzare la configurazione che si vuole impostare in tutti i dispositivi, consentendo di convalidare le scelte e verificare la presenza di errori.

In un'app foglio di calcolo aggiungere le righe per le righe seguenti nella prima colonna:

| Impostazione                | Descrizione      |
|------------------------|-----------------|
| **Audio predefinito**      | Determina il dispositivo in cui il microfono sarà attivo all'avvio di una riunione. Questo campo può essere impostato su `true` `false` un solo dispositivo,in genere un dispositivo di Teams Rooms, mentre il resto dei dispositivi deve avere questo campo impostato su per evitare l'eco audio e il feedback.          |
| **Audio abilitato**      | Determina se i partecipanti a una riunione possono attivare o disattivare il microfono. Nei dispositivi in cui **è impostata** `false` `false` l'impostazione predefinita Audio questa impostazione deve essere impostata su in modo che i partecipanti non possano attivare accidentalmente un microfono e causare eco audio o feedback.<p>Se **l'opzione Audio** predefinita è impostata su `true`, questa impostazione viene ignorata e i partecipanti possono disattivare o riattivare l'audio del microfono.          |
| **Impostazione predefinita video**      | Determina il dispositivo in cui la fotocamera sarà attiva all'avvio di una riunione. Per un'esperienza ottimale, è consigliabile impostare solo il dispositivo Teams Rooms `true` mentre tutti gli altri dispositivi sono impostati su `false`.          |
| **Video abilitato**      | Determina se i partecipanti a una riunione possono attivare o disattivare la fotocamera. È possibile impostare questa `true` opzione su qualsiasi altro dispositivo dell'evento in cui i partecipanti vogliono condividere prospettive video diverse, ad esempio se un partecipante usa la lavagna Surface Hub video. Se non si vuole che i partecipanti accendono o spegnino una fotocamera in un dispositivo, impostare questa opzione su `false`.<p> Se **l'impostazione predefinita** video è impostata su `true`, questa impostazione viene ignorata e i partecipanti possono attivare o disattivare la fotocamera.         |
| **Impostazione predefinita lavagna** | Determina se il Teams Rooms dispositivo visualizza una lavagna condivisa da uno dei partecipanti alla riunione. È consigliabile impostare questa opzione su se `false` si ha un `true` Surface Hub e se non se ne ha uno. Questa impostazione non ha alcun effetto sui Surface Hub. I Surface Hub visualizzano sempre una lavagna condivisa dai partecipanti alla riunione.         |
| **Lavagna abilitata** | Determina se i partecipanti a una riunione possono attivare o disattivare la lavagna. Se non si vuole che i partecipanti accertino o distorsino la lavagna in un dispositivo, impostare questa opzione su `false`. <p>Se **l'impostazione predefinita di** Lavagna è impostata su `true`, questa impostazione viene ignorata e i partecipanti possono attivare o disattivare la lavagna.
| **Account attendibili**   | Si tratta di un elenco separato da virgole di UPN per ogni dispositivo sala Teams o Surface Hub da cui il dispositivo deve accettare le convocazioni di partecipazione alle riunioni o a cui devono essere inviate le convocazioni di partecipazione alla riunione. |

Nelle colonne successive aggiungere ogni dispositivo Teams Rooms Surface Hub. In ogni colonna compilare i valori che corrispondono all'esperienza desiderata per la sala riunioni. Ecco un esempio con un dispositivo Teams Rooms e uno Surface Hub:

- Teams dispositivo
  - L'audio e il video sono **attivati** all'avvio di una riunione. I partecipanti **possono attivare** o disattivare audio e video.
  - La visualizzazione di una lavagna condivisa è disattivata.
- Surface Hub
  - L'audio viene **disattivato all'avvio** di una riunione. I partecipanti **non possono attivare o disattivare l'audio** .
  - Il video viene **disattivato all'avvio** di una riunione. I partecipanti **possono attivare** o disattivare il video.

| Impostazione                | Teams room      | Surface Hub      |
|------------------------|-----------------|------------------|
| **Audio predefinito**      | `true`          | `false`          |
| **Audio abilitato**      | `true`          | `false`          |
| **Impostazione predefinita video**      | `true`          | `false`          |
| **Video abilitato**      | `true`          | `true`           |
| **Impostazione predefinita lavagna** | `false`         | `false`          |
| **Account attendibili**   | hub@contoso.com | room@contoso.com |

## <a name="step-4-configure-teams-rooms-device"></a>Passaggio 4: Configurare Teams Rooms dispositivo

È possibile configurare riunioni coordinate in un dispositivo Teams Rooms usando il touchscreen del dispositivo oppure, se è necessario configurare molti dispositivi e si vuole farlo da una posizione centrale, è possibile usare un file di configurazione XML.

Usare il foglio di lavoro creato nel passaggio precedente per configurare i dispositivi.

### <a name="use-the-teams-rooms-devices-touch-screen"></a>Usare il Teams Rooms touchscreen del dispositivo

Per configurare riunioni coordinate in un dispositivo, eseguire le operazioni seguenti:

1. Selezionare **... Altro** >  **Impostazioni**.
2. Immettere la password dell'amministratore e selezionare **Sì**.
3. Selezionare **Riunioni coordinate**.
4. In **Opzioni** impostare **Riunione coordinata** su _on_.
5. Se **Audio predefinito nel** foglio di lavoro `true`è , impostare **Attiva** microfono del dispositivo su Attiva, altrimenti lasciarlo _disattivato_.
6. Se **l'opzione Audio** abilitata nel `true`foglio di lavoro è , selezionare Consenti alle persone di abilitare quando si partecipa **a** una riunione in **Attiva microfono del dispositivo**. Questa opzione non può essere disattivata se **attiva** il microfono di questo dispositivo.
7. Se **l'impostazione Predefinita** video nel foglio `true`di lavoro è , impostare Attiva fotocamera **del** dispositivo su attivata, altrimenti lasciarla _disattivata_.
8. Se **l'opzione Video** abilitato nel foglio di `true`lavoro è , selezionare Consenti alle persone di abilitare la partecipazione **a** una riunione in **Attiva fotocamera del dispositivo**. Questa opzione non può essere disattivata se **l'opzione** Attiva fotocamera del dispositivo è _attivata_.
9. Se **l'impostazione predefinita di** `true`Whiteboard nel foglio di lavoro è , impostare Attiva **lavagna** su questo dispositivo su _attiva_, altrimenti lasciarla _disattivata_.
10. In **Account dispositivo attendibili** digitare ogni UPN elencato in **Account attendibili** nel foglio di lavoro. Separare più UPN con virgole.
11. Selezionare **Salva e esci**.

Dopo aver selezionato **Salva e esci**, il dispositivo verrà riavviato e sarà pronto per partecipare alle riunioni coordinate.

### <a name="use-the-teams-rooms-xml-configuration-file"></a>Usare il file Teams Rooms di configurazione XML

Le riunioni coordinate possono essere impostate usando il file Teams Rooms di configurazione `SkypeSettings.xml` XML del dispositivo. Il `SkypeSettings.xml` file non è un file statico. All'avvio Teams Rooms dispositivo, viene verificato `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` se è presente un file denominato `SkypeSettings.xml`. Se il file esiste, il dispositivo legge e applica la configurazione specificata nel file. Al termine dell'applicazione della configurazione, il file viene eliminato. Per altre informazioni sul `SkypeSettings.xml` file, vedere [Gestire le impostazioni della console con un file di configurazione XML](../rooms/xml-config-file.md#manage-console-settings-with-an-xml-configuration-file).

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

Per configurare riunioni coordinate in un dispositivo, eseguire le operazioni seguenti:

1. In un editor di file di testo, ad esempio Visual Studio Code o Blocco note, incollare il codice XML precedente in un nuovo file.

2. Impostare ognuno degli elementi XML sul valore o `true` corrispondente `false` nel foglio di calcolo. Ad esempio, se **l'impostazione predefinita audio** è `true`, impostare `<Audio default="true">`.

3. Assicurarsi di passare all'elenco `TrustedAccounts` di UPN.

4. Salvare il file con il nome `SkypeSettings.xml`.

5. Inserire il file nella Teams Rooms del dispositivo`C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState`. È possibile eseguire questa operazione in diversi modi:

    - **Copiare il file nel dispositivo Teams Rooms** è necessario abilitare la condivisione file e creare una condivisione di rete prima di poter copiare i file nel dispositivo. Dopo aver fatto ciò, è possibile connettersi alla condivisione di rete e copiare il file nel dispositivo. Per altre informazioni, vedere Microsoft Teams Rooms [manutenzione e operazioni](../rooms/rooms-operations.md).
    - **Usare Criteri di gruppo** Creare criteri di gruppo per copiare il file nel dispositivo. Per altre informazioni, vedere Panoramica [di Criteri di gruppo](/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831791(v=ws.11)).
    - **Scaricare il file nel dispositivo Teams Rooms** È possibile accedere al dispositivo usando la modalità di amministrazione e quindi copiare il file nel dispositivo da una condivisione di rete o da un'unità USB. Per altre informazioni, vedere [Passaggio alla modalità di amministrazione](../rooms/rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running).
    
6. Riavviare il dispositivo. È possibile eseguire questa operazione in due modi:

    - **PowerShell remoto** È possibile eseguire il comando Arresta nel dispositivo usando Remote PowerShell. Per altre informazioni, vedere [Gestione remota con PowerShell](../rooms/rooms-operations.md).
    - **Esegui Restart-Computer** È possibile eseguire il `Restart-Computer` cmdlet nel computer locale e specificare il nome del computer del dispositivo da riavviare. Per altre informazioni, vedere [Restart-Computer](/powershell/module/microsoft.powershell.management/restart-computer?view=powershell-7).

## <a name="step-5-configure-surface-hub"></a>Passaggio 5: Configurare Surface Hub

È possibile usare Windows Configuration Designer per creare un pacchetto di provisioning che è possibile usare per applicare le impostazioni delle riunioni di coordinamento ai Surface Hub. Incollare il file XML creato in precedenza in Progettazione Windows configurazione per creare il pacchetto di provisioning.

### <a name="create-coordinated-meetings-xml-configuration-file-for-surface-hub"></a>Creare un file di configurazione XML per riunioni coordinate per Surface Hub

Sia Windows Configuration Designer che Microsoft Intune vengono usati per applicare la configurazione Riunioni coordinate ai Surface Hub. La configurazione viene definita tramite XML. Prima di procedere, è necessario creare il codice XML che verrà applicato.

Di seguito è riportata la sintassi del file di configurazione XML Delle riunioni coordinate.

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

Eseguire le operazioni seguenti per preparare il codice XML per progettazione Windows configurazione o Microsoft Intune:

1. In un editor di file di testo, ad esempio Visual Studio Code o Blocco note, incollare il codice XML precedente in un nuovo file.

2. Impostare ognuno degli elementi XML sul valore o `true` corrispondente `false` nel foglio di calcolo. Ad esempio, se **l'impostazione predefinita audio** è `true`, impostare `<Audio default="true">`.

3. Assicurarsi di passare all'elenco `TrustedAccounts` di UPN.

4. Windows Progettazione configurazione richiede che il codice XML sia su una singola riga. Rimuovere tutte le interruzioni di riga tra ogni riga in modo che il codice XML sia simile al seguente:

    ```xml
    <SurfaceHubSettings><BluetoothAdvertisementEnabled>true</BluetoothAdvertisementEnabled>...
    ```

5. Salvare il file nel computer.

Dopo aver creato il file di configurazione XML, seguire la [procedura descritta in](surface-hub-manage-config.md) Gestire le impostazioni di Microsoft Teams in Surface Hub per applicarlo ai Surface Hub.