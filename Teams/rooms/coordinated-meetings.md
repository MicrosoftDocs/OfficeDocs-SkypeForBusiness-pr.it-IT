---
title: Configurare riunioni coordinate con le sale di Microsoft teams e Surface Hub
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
description: Configurare i dispositivi di teams Rooms e Surface hub per partecipare alle riunioni quando un dispositivo o l'altro si unisce a una riunione.
ms.openlocfilehash: c1200b4e949cb866440907f8577f61f4528630e2
ms.sourcegitcommit: 20258b691ffc559b1656fd1e57f67f5c3a9e29e1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/15/2020
ms.locfileid: "46761443"
---
# <a name="set-up-coordinated-meetings-with-microsoft-teams-rooms-and-surface-hub"></a>Configurare riunioni coordinate con le sale di Microsoft teams e Surface Hub

Se si dispone di uno o più dispositivi di Microsoft teams rooms o di Surface Hub in una sala riunioni, è possibile configurare riunioni coordinate. Riunioni coordinate consente di configurare i dispositivi delle sale team e i relativi hub in modo che quando si partecipa a una riunione su un dispositivo, anche gli altri dispositivi della sala vengano uniti alla stessa riunione. È possibile configurare le telecamere, gli altoparlanti e i microfoni in modo che gli utenti che offrono l'esperienza migliore siano abilitati, mentre altri sono disabilitati. In questo caso, i partecipanti al rumore eco e feedback temuto possono provare quando si aggiungono più dispositivi a una riunione.

Per configurare riunioni coordinate, è necessario assicurarsi che i dispositivi di teams Rooms e i relativi hub siano già correttamente configurati per partecipare alle riunioni. Soprattutto, ogni dispositivo deve avere una propria cassetta postale della sala di scambio. Per informazioni su come configurarle, vedere gli articoli seguenti:

- [Distribuire Microsoft Teams Rooms](../rooms/rooms-deploy.md)
- [Creare un account di dispositivo Surface Hub 2S](https://docs.microsoft.com/surface-hub/surface-hub-2s-account)

Dopo aver confermato che i dispositivi teams Rooms e gli hub Surface possono accettare automaticamente le riunioni e partecipare correttamente, è possibile configurare riunioni coordinate.

La procedura seguente deve essere completata per ogni sala riunioni separatamente. I dispositivi in una sala riunioni non devono essere configurati per riunioni coordinate con dispositivi in altre sale riunioni.

## <a name="step-1-plan-your-coordinated-meeting-experience"></a>Passaggio 1: pianificare l'esperienza di riunione coordinata

Prima di apportare modifiche alla configurazione, è necessario decidere quali dispositivi faranno ciò che in ogni sala riunioni. Per una determinata sala riunioni, è necessario decidere quale dispositivo avrà il microfono, la fotocamera e la lavagna attivi. La configurazione dei dispositivi dipende dall'ambiente specifico, ma ecco alcuni consigli generali per iniziare:

- **Microfono** Dispositivo teams rooms
- **Fotocamera** Dispositivo teams Rooms (attivato per impostazione predefinita) e Surface Hub (disattivato per impostazione predefinita, ma consentito per i partecipanti)
- **Lavagna** Hub Surface

> [!IMPORTANT]
> Verificare che il microfono sia abilitato solo su un dispositivo. Se si Abilita il dispositivo su più dispositivi, si verificherà l'eco audio e il feedback.

## <a name="step-2-get-your-devices-upns"></a>Passaggio 2: ottenere i UPN dei dispositivi

Quando si configura un'esperienza di riunione coordinata in una sala riunioni, è necessario comunicare ai dispositivi sale di teams e agli hub Surface in quella sala i dispositivi con cui coordinare. A questo scopo, Aggiungi il nome dell'entità utente (UPN) dei dispositivi con cui deve coordinare la configurazione. Se non si conosce il UPN per ogni dispositivo che si vuole configurare per le riunioni coordinate, è possibile trovarle usando l'interfaccia di amministrazione di Microsoft 365. 

Per accedere all'interfaccia di amministrazione di Microsoft 365 è necessario che venga assegnato un ruolo di amministratore. Per altre informazioni, vedere [informazioni sui ruoli di amministratore](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).

Per ottenere il UPN dei dispositivi di teams Rooms e di Surface Hub, eseguire le operazioni seguenti:

1. Accedere all'interfaccia di amministrazione di Microsoft 365 visitando https://admin.microsoft.com
2. Accedere a **Users**utenti  >  **attivi** degli utenti
3. Trovare il nome del dispositivo teams rooms o dell'hub Surface nella colonna **nome visualizzato** (è possibile usare la casella di **ricerca** se sono presenti molti utenti)
4. Trovare l'UPN nella colonna **username** (sembrerà simile a alias@contoso.com o alias@contoso.onmicrosoft.com)
5. Ripetere questa operazione per ogni dispositivo che parteciperà alle riunioni coordinate

## <a name="step-3-create-a-deployment-worksheet"></a>Passaggio 3: creare un foglio di lavoro di distribuzione

Dopo aver pianificato l'esperienza di riunione coordinata e aver raccolto un elenco dei dispositivi di UPN, è consigliabile creare un foglio di lavoro di distribuzione. Un foglio di lavoro di distribuzione consente di visualizzare la configurazione che si vuole impostare in tutti i dispositivi, in modo da convalidare le scelte e verificare la possibilità di errori.

In un'app foglio di calcolo aggiungere righe per le seguenti nella prima colonna:

| Impostazione                | Descrizione      |
|------------------------|-----------------|
| **Impostazione predefinita audio**      | Determina il dispositivo in cui il microfono sarà attivo all'avvio di una riunione. Questo campo può essere impostato su un solo dispositivo (in genere un dispositivo sale di Teams) `true` mentre il resto dei dispositivi deve avere questo campo impostato su per `false` evitare l'eco audio e il feedback.          |
| **Audio abilitato**      | Determina se i partecipanti a una riunione possono attivare o disattivare il microfono. I dispositivi su cui è impostato l'impostazione **predefinita** per `false` l'audio devono avere questa impostazione in `false` modo che i partecipanti non possano accidentalmente attivare un microfono e causare l'eco audio o il feedback.<p>Se il **valore predefinito** è impostato su `true` , questa impostazione viene ignorata e i partecipanti possono disattivare o riattivare l'audio del microfono.          |
| **Video predefinito**      | Determina il dispositivo in cui la videocamera sarà attiva all'avvio di una riunione. Per un'esperienza ottimale, è consigliabile impostare solo il dispositivo teams Rooms `true` mentre tutti gli altri dispositivi sono impostati su `false` .          |
| **Video abilitato**      | Determina se i partecipanti a una riunione possono attivare o disattivare la videocamera. Puoi impostare questa operazione `true` su qualsiasi altro dispositivo nei partecipanti agli eventi che vogliono condividere diverse prospettive video, ad esempio se un partecipante usa la lavagna di Surface Hub. Se non si vuole che i partecipanti spengano o spengano una videocamera in un dispositivo, impostarlo su `false` .<p> Se il **video predefinito** è impostato su `true` , questa impostazione viene ignorata e i partecipanti possono attivare o disattivare la fotocamera.         |
| **Impostazione predefinita per la lavagna** | Determina se il dispositivo teams Rooms visualizzerà una lavagna condivisa da uno dei partecipanti alla riunione. Ti consigliamo di impostare questa impostazione su `false` se hai un hub Surface e se non ne hai una `true` . Questa impostazione non ha alcun effetto sugli hub di Surface. I mozzi della superficie visualizzeranno sempre una lavagna condivisa dai partecipanti alla riunione.         |
| **Account attendibili**   | Questo è un elenco delimitato da virgole di UPN per ogni dispositivo della sala teams o hub Surface che il dispositivo deve accettare le richieste di partecipazione alle riunioni o alle quali devono essere inviate le richieste di partecipazione alle riunioni. |

Nelle colonne successive aggiungere tutti i dispositivi teams Rooms e Surface Hub. In ogni colonna compilare i valori che corrispondono all'esperienza desiderata per la sala riunioni. Ecco un esempio con un dispositivo teams Rooms e un hub Surface:

- Dispositivo Teams
  - L'audio e **il** video vengono attivati all'avvio di una riunione. I partecipanti **possono** attivare o disattivare l'audio e il video.
  - La visualizzazione di una lavagna condivisa è disattivata.
- Hub Surface
  - L'audio è **disattivato all'avvio** di una riunione. I partecipanti **non possono** attivare o disattivare l'audio.
  - Il video viene **disattivato all'avvio** di una riunione. I partecipanti **possono** attivare o disattivare il video.

| Impostazione                | Sala Teams      | Hub Surface      |
|------------------------|-----------------|------------------|
| **Impostazione predefinita audio**      | `true`          | `false`          |
| **Audio abilitato**      | `true`          | `false`          |
| **Video predefinito**      | `true`          | `false`          |
| **Video abilitato**      | `true`          | `true`           |
| **Impostazione predefinita per la lavagna** | `false`         | Non applicabile   |
| **Account attendibili**   | hub@contoso.com | room@contoso.com |

## <a name="step-4-configure-teams-rooms-device"></a>Passaggio 4: configurare il dispositivo sale Teams

È possibile configurare riunioni coordinate in un dispositivo di teams Rooms usando il touchscreen del dispositivo oppure, se è necessario configurare molti dispositivi e si vuole farlo da una posizione centrale, è possibile usare un file di configurazione XML.

Usare il foglio di lavoro creato nel passaggio precedente per facilitare la configurazione dei dispositivi.

### <a name="use-the-teams-rooms-devices-touch-screen"></a>Usare il touch screen del dispositivo teams rooms

Per configurare riunioni coordinate in un dispositivo, eseguire le operazioni seguenti:

1. Selezionare **... Altre**  >  **Impostazioni**
2. Immettere la password di amministratore e selezionare **Sì**
3. Selezionare **riunioni coordinate**
4. In **Opzioni**impostare **riunione coordinata** su attivato
5. Se nel foglio di lavoro è presente l' **impostazione predefinita** per l'audio `true` , imposta il **microfono del dispositivo su attivato** , altrimenti lascialo fuori
6. Se nel foglio di lavoro è **abilitato l'audio** `true` , selezionare **Consenti agli utenti di partecipare a una riunione** in **attivare il microfono del dispositivo**. Questa opzione non può essere disattivata se **attiva il microfono del dispositivo** è impostato su attivato.
7. Se nel foglio di lavoro è presente l' **impostazione predefinita** per il video `true` , impostare **attiva la fotocamera del dispositivo** , altrimenti lasciarla fuori
8. Se il **video è abilitato** nel foglio di lavoro `true` , selezionare Consenti agli utenti di **partecipare a una riunione** in **attivare la fotocamera del dispositivo**. Questa opzione non può essere disattivata se **attiva la fotocamera del dispositivo** è impostata su attivato.
9. Se il foglio di lavoro **predefinito è lavagna** `true` , impostare **attiva lavagna su questo dispositivo** su attivato, altrimenti lasciarlo spento
10. In **account di dispositivo attendibili**Digitare ogni UPN elencato in **account attendibili** nel foglio di lavoro. Separare più UPN con virgole.
11. Selezionare **Salva ed esci**

Dopo aver selezionato **Salva ed esci**, il dispositivo verrà riavviato e sarà pronto per partecipare a riunioni coordinate.

### <a name="use-the-teams-rooms-xml-configuration-file"></a>Usare il file di configurazione XML sale Teams

Le riunioni coordinate possono essere configurate usando il file di configurazione XML del dispositivo sale teams `SkypeSettings.xml` . Il `SkypeSettings.xml` file non è un file statico. Quando si avvia il dispositivo sale teams, viene controllato il `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` nome di un file `SkypeSettings.xml` . Se il file esiste, il dispositivo legge e applica la configurazione specificata nel file. Dopo aver completato l'applicazione della configurazione, il file viene eliminato. Per altre informazioni sul `SkypeSettings.xml` file, vedere [gestire le impostazioni della console con un file di configurazione XML](../rooms/xml-config-file.md#manage-console-settings-with-an-xml-configuration-file).

Di seguito è riportata la sintassi delle impostazioni delle riunioni coordinate nel file di configurazione:

```xml
<CoordinatedMeetings enabled="true">
    <Settings>
        <Audio default="true" enabled="true"/>
        <Video default="true" enabled="true"/>
        <Whiteboard default="false"/>
    </Settings>
    <TrustedAccounts>hub@contoso.com</TrustedAccounts>
</CoordinatedMeetings>
```

Per configurare riunioni coordinate in un dispositivo, eseguire le operazioni seguenti:

1. In un editor di file di testo, come il codice di Visual Studio o il blocco note, incollare l'XML precedente in un nuovo file
2. Imposta ogni elemento XML sul corrispondente `true` o sul `false` valore nel foglio di calcolo. Ad esempio, se l' **impostazione predefinita** è l'audio `true` , imposta `<Audio default="true">` .
3. Assicurarsi di passare `TrustedAccounts` all'elenco di UPN
4. Salvare il file con il nome `SkypeSettings.xml`
5. Posizionare il file nella cartella del dispositivo teams Rooms `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` . Puoi eseguire questa operazione in pochi modi:
    - **Copiare il file nel dispositivo teams Rooms** È necessario abilitare la condivisione dei file e creare una condivisione di rete prima di poter copiare i file nel dispositivo. Dopo aver eseguito questa operazione, è possibile connettersi a condivisione di rete e copiare il file nel dispositivo. Per altre informazioni, vedere [manutenzione e operazioni di Microsoft teams Rooms](../rooms/rooms-operations.md).
    - **Usare criteri di gruppo** Creare criteri di gruppo per copiare il file nel dispositivo. Per altre informazioni, vedere [Cenni preliminari sui criteri di gruppo](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831791(v=ws.11)).
    - **Scaricare il file nel dispositivo teams Rooms** È possibile accedere al dispositivo usando la modalità amministratore e quindi copiare il file nel dispositivo da una condivisione di rete o da un'unità USB. Per altre informazioni, vedere [passaggio alla modalità amministratore](../rooms/rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running).
6. Riavviare il dispositivo. Questa operazione può essere eseguita in un paio di modi:
    - **PowerShell remoto** È possibile eseguire il comando Shutdown nel dispositivo usando una sessione remota di PowerShell. Per altre informazioni, vedere [gestione remota tramite PowerShell](../rooms/rooms-operations.md).
    - **Eseguire Restart-computer** È possibile eseguire il `Restart-Computer` cmdlet nel computer locale e specificare il nome del computer del dispositivo che si vuole riavviare. Per altre informazioni, vedere [Restart-computer](https://docs.microsoft.com/powershell/module/microsoft.powershell.management/restart-computer?view=powershell-7).

## <a name="step-5-configure-surface-hub"></a>Passaggio 5: configurare il mozzo della superficie

Puoi usare Windows Configuration designer per creare un pacchetto di provisioning che puoi usare per applicare le impostazioni di coordinamento delle riunioni agli hub di Surface. Verrà incollato il file XML creato in precedenza in Windows Configuration designer per creare il pacchetto di provisioning.

### <a name="create-coordinated-meetings-xml-configuration-file-for-surface-hub"></a>Creare un file di configurazione XML per riunioni coordinate per Surface Hub

Windows Configuration designer e Microsoft Intune vengono usati per applicare la configurazione coordinata delle riunioni agli hub di Surface. La configurazione viene definita tramite XML. Prima di procedere, è necessario creare il codice XML che verrà applicato.

Di seguito è riportata la sintassi del file di configurazione XML delle riunioni coordinate.

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

Per preparare il codice XML per Windows Configuration designer o Microsoft Intune, eseguire le operazioni seguenti:

1. In un editor di file di testo, come il codice di Visual Studio o il blocco note, incollare l'XML precedente in un nuovo file
2. Imposta ogni elemento XML sul corrispondente `true` o sul `false` valore nel foglio di calcolo. Ad esempio, se l' **impostazione predefinita** è l'audio `true` , imposta `<Audio default="true">` .
3. Assicurarsi di passare `TrustedAccounts` all'elenco di UPN
4. Windows Configuration designer richiede che l'XML sia su una singola riga. Rimuovere tutte le interruzioni di riga tra ogni riga in modo che l'aspetto XML sia simile al seguente:

    ```xml
    <SurfaceHubSettings><BluetoothAdvertisementEnabled>true</BluetoothAdvertisementEnabled>...
    ```

5. Salvare il file nel computer

Dopo aver creato il file di configurazione XML, eseguire la procedura descritta in [gestire le impostazioni di Microsoft teams in Surface Hub](surface-hub-manage-config.md) per applicarlo agli hub Surface.