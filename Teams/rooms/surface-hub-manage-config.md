---
title: Gestire la configurazione di Microsoft teams in Surface Hub
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
description: Gestire le impostazioni di Microsoft teams in Surface Hub con Microsoft Intune e Windows Configuration designer
ms.openlocfilehash: 3e254d7f7afbd918e8279d2dc7b100ebbfdc3daf
ms.sourcegitcommit: 20258b691ffc559b1656fd1e57f67f5c3a9e29e1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/15/2020
ms.locfileid: "46761444"
---
# <a name="manage-microsoft-teams-settings-on-surface-hub"></a>Gestire le impostazioni di Microsoft teams in Surface Hub

Puoi gestire le impostazioni di Microsoft teams in un hub Surface usando Windows Configuration designer o Microsoft Intune in Microsoft Endpoint Manager. La conoscenza di Windows Configuration designer o Microsoft Intune è necessaria per apportare modifiche alle impostazioni del team. Per altre informazioni su queste opzioni, vedere gli articoli seguenti:

- [Creare un pacchetto di provisioning per Windows 10](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-create-package)
- [Che cos'è la gestione dei dispositivi di Microsoft Intune?](https://docs.microsoft.com/mem/intune/remote-actions/device-management)

Windows Configuration designer è una buona opzione se hai solo pochi dispositivi di Surface Hub ed è possibile accedervi facilmente. Se sono presenti molti Hub di Surface o se sono in posizioni remote, usare Microsoft Intune in Microsoft Endpoint Manager se è distribuito nell'organizzazione. Indipendentemente dal metodo scelto, è necessario creare un file di configurazione XML per apportare modifiche alle impostazioni del team in Surface Hub.

## <a name="teams-configuration-file-syntax"></a>Sintassi del file di configurazione Teams

La configurazione teams in un hub Surface viene definita usando un file XML. Il file XML contiene tutte le impostazioni che possono essere usate per controllare la modalità di funzionamento dei team. Windows Configuration designer e Microsoft Intune usano la stessa sintassi XML. Ecco un esempio del file XML di configurazione di teams:

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

La tabella seguente descrive tutte le impostazioni di configurazione disponibili nel file di configurazione:

| Padre                  | Elemento                                   | Attributo | Descrizione                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
|-------------------------|-------------------------------------------|-----------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Nessuno                    | `<SurfaceHubSettings>`                    |           | Contiene tutti gli elementi di configurazione per la configurazione teams in un hub Surface.                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| `<SurfaceHubSettings>`  | `<BluetoothAdvertisementEnabled>`         |           | Determina se Surface Hub annuncia che è disponibile per le connessioni Bluetooth.<br>Valori accettati: `true` , `false`                                                                                                                                                                                                                                                                                                                                                                                         |
| `<SurfaceHubSettings>`  | `<AutoAcceptProximateMeetingInvitations>` |           | Determina se i team accetteranno automaticamente riunioni basate su prossimità.<br>Valori accettati: `true` , `false`                                                                                                                                                                                                                                                                                                                                                                                                     |
| `<SurfaceHubSettings>`  | `<CoordinatedMeetings>`                   |           | Contiene tutti gli elementi di configurazione per le riunioni coordinate.                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|                         |                                           | `enabled` | Determina se i team sono configurati per partecipare a riunioni coordinate con altri dispositivi.<br>Valori accettati: `true` , `false`                                                                                                                                                                                                                                                                                                                                                                                |
| `<CoordinatedMeetings>` | `<TrustedAccounts>`                       |           | Questo è un elenco delimitato da virgole di UPN per ogni dispositivo della sala teams o hub Surface che il dispositivo deve accettare le richieste di partecipazione alle riunioni o alle quali devono essere inviate le richieste di partecipazione alle riunioni.<br>Valori accettati: stringa                                                                                                                                                                                                                                                                                                                         |
| `<CoordinatedMeetings>` | `<Settings>`                              |           | Contiene elementi di configurazione audio e video di configurazione per riunioni coordinate                                                                                                                                                                                                                                                                                                                                                                                                                               |
| `<Settings>`            | `<Audio>`                                 |           | Controlla la configurazione audio per i team in un hub Surface.                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|                         |                                           | `default` | Determina il dispositivo in cui il microfono sarà attivo all'avvio di una riunione. Questo campo può essere impostato su un solo dispositivo (in genere un dispositivo sale di Teams) `true` mentre il resto dei dispositivi deve avere questo campo impostato su per `false` evitare l'eco audio e il feedback.<br>Valori accettati: `true` , `false`                                                                                                                                                                                                           |
|                         |                                           | `enabled` | Determina se i partecipanti a una riunione possono attivare o disattivare il microfono. I dispositivi su cui è impostato l'impostazione **predefinita** per `false` l'audio devono avere questa impostazione in `false` modo che i partecipanti non possano accidentalmente attivare un microfono e causare l'eco audio o il feedback.<p>Se il **valore predefinito** è impostato su `true` , questa impostazione viene ignorata e i partecipanti possono disattivare o riattivare l'audio del microfono.<br>Valori accettati: `true` , `false`                                                                               |
| `<Settings>`            | `<Video>`                                 |           | Controlla la configurazione video per i team in un hub Surface.                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|                         |                                           | `default` | Determina il dispositivo in cui la videocamera sarà attiva all'avvio di una riunione. Per un'esperienza ottimale, è consigliabile impostare solo il dispositivo teams Rooms `true` mentre tutti gli altri dispositivi sono impostati su `false` .<br>Valori accettati: `true` , `false`                                                                                                                                                                                                                                                                  |
|                         |                                           | `enabled` | Determina se i partecipanti a una riunione possono attivare o disattivare la videocamera. Puoi impostare questa operazione `true` su qualsiasi altro dispositivo nei partecipanti agli eventi che vogliono condividere diverse prospettive video, ad esempio se un partecipante usa la lavagna di Surface Hub. Se non si vuole che i partecipanti spengano o spengano una videocamera in un dispositivo, impostarlo su `false` .<p> Se il **video predefinito** è impostato su `true` , questa impostazione viene ignorata e i partecipanti possono attivare o disattivare la fotocamera.<br>Valori accettati: `true` , `false` |

## <a name="apply-teams-settings-to-surface-hub"></a>Applicare le impostazioni Teams a Surface Hub

Applicare o aggiornare le impostazioni di configurazione di teams in Surface hub usando Windows Configuration designer o Microsoft Intune in Microsoft Endpoint Manager.

### <a name="use-windows-configuration-designer"></a>Usare Windows Configuration designer

Puoi usare Windows Configuration designer per creare un pacchetto di provisioning che puoi usare per applicare le impostazioni dei team agli hub Surface. Verrà incollato il file XML creato in precedenza in Windows Configuration designer per creare il pacchetto di provisioning.

> [!IMPORTANT]
> Se hai già applicato la configurazione teams al tuo hub Surface usando un pacchetto di provisioning e vuoi modificarlo, devi rimuovere prima il pacchetto di provisioning esistente. Per altre informazioni, vedere [rimuovere un pacchetto di provisioning creato da Windows Configuration designer](#remove-a-provisioning-package-created-by-windows-configuration-designer).

Per creare il pacchetto di provisioning in Windows Configuration designer, eseguire le operazioni seguenti:

1. Installare Windows Configuration designer da Windows Store nel computer locale e aprirlo
2. Selezionare **provisioning dispositivi hub Surface** e quindi **passare a Advanced editor**
3. Nella schermata successiva Espandi **WindowsTeamSettings**  >  **Teams** e seleziona **configurazioni**
4. Nel campo accanto a **configurazioni** nel riquadro centrale incollare la singola riga di codice XML creata sopra
5. Selezionare **Esporta**  >  **pacchetto di provisioning**
6. Specificare un nome per il pacchetto di provisioning in **nome** e selezionare **Avanti**  >  **Avanti**
7. Specificare un percorso in cui salvare il pacchetto di provisioning e selezionare **Avanti**
8. Selezionare **Compila** per creare il pacchetto di provisioning e quindi **completare**

Infine, dopo aver creato il pacchetto di provisioning, eseguire le operazioni seguenti per applicare il pacchetto di provisioning all'hub Surface:

1. Salvare il pacchetto di provisioning creato in precedenza su un'unità USB
2. Inserire l'unità USB nell'hub Surface
3. Nell'hub Surface aprire il menu Start, selezionare tutte le **app**e quindi selezionare **Impostazioni** .
4. Fornisci il nome utente e la password di amministratore e quindi scegli **Sì**
5. Accedere a **Surface Hub**, **Gestione dispositivi**, **aggiungere o rimuovere un pacchetto di provisioning**e quindi **aggiungere un pacchetto**
6. In **Seleziona un pacchetto**selezionare **Aggiungi** accanto al pacchetto di provisioning e quindi riavviare Surface Hub

### <a name="use-microsoft-intune"></a>Usare Microsoft Intune

Se gli hub di Surface vengono gestiti con Microsoft Intune in Microsoft Endpoint Management, è possibile usarli per applicare le impostazioni teams agli hub Surface. Sarà possibile creare un nuovo profilo di configurazione e quindi incollare il file XML creato in precedenza.

> [!IMPORTANT]
> Gli hub di Surface devono essere in un gruppo di dispositivi in modo che Microsoft Intune possa identificare i dispositivi a cui applicare il profilo di configurazione. Per informazioni su come creare un gruppo di dispositivi, vedere [aggiungere gruppi per organizzare utenti e dispositivi](https://docs.microsoft.com/mem/intune/fundamentals/groups-add).

Per creare un profilo di configurazione per applicare le impostazioni dei team agli hub di Surface, eseguire le operazioni seguenti:

1. Accedere a Microsoft Endpoint Manager visitando https://endpoint.microsoft.com/
2. Passare ai **Devices**  >  **profili di configurazione** dei dispositivi e selezionare **Crea profilo**
3. In **piattaforma**selezionare **Windows 10 e versioni successive**
4. In **profilo**selezionare **personalizzato**e quindi fare clic su **Crea**
5. Nella scheda **nozioni di base** , in **nome**, specificare un nome descrittivo per il profilo di configurazione e selezionare **Avanti** .
6. Nella scheda **impostazioni di configurazione** selezionare **Aggiungi**
7. Nel riquadro **Aggiungi riga** eseguire le operazioni seguenti:
    1. Specificare un nome descrittivo e, facoltativamente, una descrizione dell'impostazione teams che si sta aggiungendo
    2. In **OMA-URI**immettere `./Vendor/MSFT/SurfaceHub/InBoxApps/Teams/Configurations`
    3. In **tipo di dati**selezionare **stringa (file XML)**
    4. Aprire il browser file, selezionare il file XML creato in precedenza e **aprire**
8. Selezionare **Aggiungi** e quindi **Avanti**
9. Nella scheda **assegnazioni** verificare che l'opzione **assegna a** sia impostata su **gruppi selezionati**
10. In **gruppi selezionati**selezionare **Seleziona gruppi da includere** e scegliere il gruppo che contiene gli hub di Surface e quindi selezionare **Seleziona**
11. Selezionare **Avanti**, **Avanti**
12. Nella finestra **revisione + crea**selezionare **Crea**

## <a name="remove-teams-settings-from-a-surface-hub"></a>Rimuovere le impostazioni dei team da un hub Surface

Rimuovere le impostazioni di configurazione di teams in Surface hub usando Windows Configuration designer o Microsoft Intune in Microsoft Endpoint Manager.

### <a name="remove-a-provisioning-package-created-by-windows-configuration-designer"></a>Rimuovere un pacchetto di provisioning creato da Windows Configuration designer

Se si applicano le impostazioni di Teams a un hub Surface usando un pacchetto di provisioning creato da Windows Configuration designer, eseguire la procedura seguente per rimuovere il pacchetto e le relative impostazioni:

1. Nell'hub Surface aprire il menu Start, selezionare tutte le **app**e quindi selezionare **Impostazioni** .
2. Fornisci il nome utente e la password di amministratore e quindi scegli **Sì**
3. Accedere a **Surface Hub**, **Gestione dispositivi** e quindi **aggiungere o rimuovere un pacchetto di provisioning**
4. Accanto al pacchetto di provisioning che si vuole rimuovere, selezionare **Rimuovi**
5. Accedere a **Surface Hub** e quindi alle **funzionalità & delle app**
6. Trovare **Microsoft teams per Surface Hub** e quindi selezionare **Opzioni avanzate**
7. Selezionare **Reimposta**e quindi di nuovo **Reimposta**
8. Riavviare l'hub Surface

### <a name="remove-settings-applied-by-microsoft-intune"></a>Rimuovere le impostazioni applicate da Microsoft Intune

Se si applicano le impostazioni di Teams a un hub Surface con Microsoft Intune in Microsoft Endpoint Management, eseguire la procedura seguente per rimuovere il profilo di configurazione e le relative impostazioni:

1. Accedere a Microsoft Endpoint Manager visitando https://endpoint.microsoft.com/
2. Passare ai **Devices**  >  **profili di configurazione** dei dispositivi
3. Selezionare il profilo di configurazione che contiene le impostazioni di riunione coordinate che si desidera rimuovere
4. Nella pagina dettagli profilo di configurazione selezionare **Elimina** e quindi **OK**

Dopo aver rimosso il profilo di configurazione che conteneva le impostazioni di riunione coordinate per l'hub di Surface, eseguire la procedura seguente per reimpostare l'app teams nell'hub Surface:

1. Nell'hub Surface aprire il menu Start, selezionare tutte le **app**e quindi selezionare **Impostazioni** .
2. Fornisci il nome utente e la password di amministratore e quindi scegli **Sì**
3. Accedere a **Surface Hub** e quindi alle **funzionalità & delle app**
4. Trovare **Microsoft teams per Surface Hub** e quindi selezionare **Opzioni avanzate**
5. Selezionare **Reimposta**e quindi di nuovo **Reimposta**
6. Riavviare l'hub Surface