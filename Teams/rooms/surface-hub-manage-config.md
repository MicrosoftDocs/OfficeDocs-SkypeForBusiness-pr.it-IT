---
title: Gestire la configurazione di Microsoft Teams in Surface Hub
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
description: Gestire le impostazioni di Microsoft Teams in Surface Hub con Microsoft Intune e Windows Configuration Designer
ms.openlocfilehash: 3e254d7f7afbd918e8279d2dc7b100ebbfdc3daf
ms.sourcegitcommit: 20258b691ffc559b1656fd1e57f67f5c3a9e29e1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/15/2020
ms.locfileid: "46761444"
---
# <a name="manage-microsoft-teams-settings-on-surface-hub"></a>Gestire le impostazioni di Microsoft Teams in Surface Hub

È possibile gestire le impostazioni di Microsoft Teams in Surface Hub usando Progettazione configurazione di Windows o Microsoft Intune in Microsoft Endpoint Manager. Per apportare modifiche alle impostazioni di Teams è necessario conoscere Progettazione configurazione di Windows o Microsoft Intune. Per altre informazioni su queste opzioni, vedere gli articoli seguenti:

- [Creare un pacchetto di provisioning per Windows 10](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-create-package)
- [Che cos'è la gestione di dispositivi Microsoft Intune?](https://docs.microsoft.com/mem/intune/remote-actions/device-management)

Progettazione configurazione di Windows è una buona opzione se hai solo pochi dispositivi Surface Hub e puoi accedervi facilmente. Se si dispone di molti Surface Hub o se si tratta di dispositivi in posizioni remote, usare Microsoft Intune in Microsoft Endpoint Manager se è stato distribuito nell'organizzazione. Indipendentemente dal metodo scelto, è necessario creare un file di configurazione XML per apportare modifiche alle impostazioni di Teams in Surface Hub.

## <a name="teams-configuration-file-syntax"></a>Sintassi del file di configurazione di Teams

La configurazione di Teams in Surface Hub viene definita usando un file XML. Il file XML contiene tutte le impostazioni che possono essere usate per controllare il funzionamento di Teams. Sia Progettazione configurazione di Windows che Microsoft Intune usano la stessa sintassi XML. Ecco un esempio del file XML di configurazione di Teams:

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
| Nessuno                    | `<SurfaceHubSettings>`                    |           | Contiene tutti gli elementi di configurazione per la configurazione di Teams in Surface Hub.                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| `<SurfaceHubSettings>`  | `<BluetoothAdvertisementEnabled>`         |           | Determina se Surface Hub annuncia che è disponibile per le Bluetooth esterne.<br>Valori accettati: `true` , `false`                                                                                                                                                                                                                                                                                                                                                                                         |
| `<SurfaceHubSettings>`  | `<AutoAcceptProximateMeetingInvitations>` |           | Determina se Teams accetta automaticamente le riunioni basate sulla prossimità.<br>Valori accettati: `true` , `false`                                                                                                                                                                                                                                                                                                                                                                                                     |
| `<SurfaceHubSettings>`  | `<CoordinatedMeetings>`                   |           | Contiene tutti gli elementi di configurazione per le riunioni coordinate.                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|                         |                                           | `enabled` | Determina se Teams è configurato per partecipare a riunioni coordinate con altri dispositivi.<br>Valori accettati: `true` , `false`                                                                                                                                                                                                                                                                                                                                                                                |
| `<CoordinatedMeetings>` | `<TrustedAccounts>`                       |           | Si tratta di un elenco separato da virgole di UPN per ogni dispositivo Teams Room o Surface Hub da cui il dispositivo deve accettare le convocazioni di partecipazione alle riunioni o a cui devono essere inviate le convocazioni di partecipazione.<br>Valori accettati: stringa                                                                                                                                                                                                                                                                                                                         |
| `<CoordinatedMeetings>` | `<Settings>`                              |           | Contiene elementi di configurazione audio e video di configurazione per riunioni coordinate                                                                                                                                                                                                                                                                                                                                                                                                                               |
| `<Settings>`            | `<Audio>`                                 |           | Controlla la configurazione audio per Teams in Surface Hub.                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|                         |                                           | `default` | Determina il dispositivo in cui il microfono sarà attivo all'avvio di una riunione. Questo campo può essere impostato su un solo dispositivo (in genere un dispositivo Teams Room), mentre per gli altri dispositivi deve essere impostato questo campo per evitare eco `true` `false` audio e feedback.<br>Valori accettati: `true` , `false`                                                                                                                                                                                                           |
|                         |                                           | `enabled` | Determina se i partecipanti a una riunione possono attivare o disattivare il microfono. Per i **dispositivi** per cui è impostata l'impostazione predefinita audio, questa impostazione deve essere impostata in modo che i partecipanti non possano attivare accidentalmente un microfono e causare `false` `false` eco audio o feedback.<p>Se **l'opzione Audio** predefinita è impostata su , questa impostazione viene ignorata e i partecipanti possono disattivare o `true` riattivare l'audio del microfono.<br>Valori accettati: `true` , `false`                                                                               |
| `<Settings>`            | `<Video>`                                 |           | Controlla la configurazione video per Teams in Surface Hub.                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|                         |                                           | `default` | Determina il dispositivo in cui la videocamera sarà attiva all'avvio di una riunione. Per un'esperienza ottimale, è consigliabile impostare solo il dispositivo Sale di `true` Teams, mentre tutti gli altri dispositivi sono impostati su `false` .<br>Valori accettati: `true` , `false`                                                                                                                                                                                                                                                                  |
|                         |                                           | `enabled` | Determina se i partecipanti a una riunione possono attivare o disattivare la videocamera. Puoi impostare questa opzione su qualsiasi altro dispositivo nell'evento in cui i partecipanti vogliono condividere prospettive video diverse (ad esempio se un partecipante usa la lavagna `true` di Surface Hub). Se non si vuole che i partecipanti accendono o spegnino la fotocamera in un dispositivo, impostare questa opzione su `false` .<p> Se **l'impostazione predefinita** è Video, questa impostazione viene ignorata e i partecipanti possono attivare o `true` disattivare la videocamera.<br>Valori accettati: `true` , `false` |

## <a name="apply-teams-settings-to-surface-hub"></a>Applicare le impostazioni di Teams a Surface Hub

Applicare o aggiornare le impostazioni di configurazione di Teams in Surface Hub usando Progettazione configurazione di Windows o Microsoft Intune in Microsoft Endpoint Manager.

### <a name="use-windows-configuration-designer"></a>Usare Progettazione configurazione di Windows

Puoi usare Progettazione configurazione di Windows per creare un pacchetto di provisioning che puoi usare per applicare le impostazioni di Teams a Surface Hub. Incollare il file XML creato in precedenza in Progettazione configurazione di Windows per creare il pacchetto di provisioning.

> [!IMPORTANT]
> Se hai già applicato la configurazione di Teams a Surface Hub usando un pacchetto di provisioning e vuoi cambiarlo, devi prima rimuovere il pacchetto di provisioning esistente. Per altre informazioni, vedi [Rimuovere un pacchetto di provisioning creato da Progettazione configurazione Di Windows.](#remove-a-provisioning-package-created-by-windows-configuration-designer)

Per creare il pacchetto di provisioning in Progettazione configurazione di Windows, eseguire le operazioni seguenti:

1. Installare Progettazione configurazione di Windows da Windows Store nel computer locale e aprirlo
2. Seleziona **Provisioning dispositivi Surface Hub** e quindi Passa **all'editor avanzato**
3. Nella schermata successiva espandere **WindowsTeamSettings**  >  **Teams** e selezionare **Configurazioni**
4. Nel campo accanto a **Configurazioni nel** riquadro centrale incollare la singola riga di XML creata sopra
5. Seleziona **Esporta pacchetto** di  >  **provisioning**
6. Fornisci un nome per il pacchetto di provisioning in **Nome** e seleziona **Avanti**  >  
7. Specifica una posizione in cui salvare il pacchetto di provisioning e seleziona **Avanti**
8. Seleziona **Build** per creare il pacchetto di provisioning e quindi **fine**

Infine, dopo aver creato il pacchetto di provisioning, fai quanto segue per applicare il pacchetto di provisioning a Surface Hub:

1. Salvare il pacchetto di provisioning creato in precedenza in un'unità USB
2. Inserire l'unità USB in Surface Hub
3. In Surface Hub apri il menu Start, seleziona Tutte le **app** e quindi **seleziona Impostazioni**
4. Fornisci il nome utente e la password dell'amministratore, quindi seleziona **Sì**
5. Vai a **Surface Hub,** **Gestione dispositivi,** **Aggiungi o rimuovi un pacchetto di provisioning,** quindi **aggiungi un pacchetto**
6. In **Seleziona un pacchetto,** seleziona **Aggiungi** accanto al pacchetto di provisioning e quindi riavvia Il tuo Surface Hub

### <a name="use-microsoft-intune"></a>Usare Microsoft Intune

Se i Surface Hub vengono gestiti con Microsoft Intune in Microsoft Endpoint Management, è possibile usarlo per applicare le impostazioni di Teams ai Surface Hub. È necessario creare un nuovo profilo di configurazione e quindi incollare al suo interno il file XML creato in precedenza.

> [!IMPORTANT]
> I Surface Hub devono essere in un gruppo di dispositivi in modo che Microsoft Intune possa identificare i dispositivi a cui applicare il profilo di configurazione. Per informazioni su come creare un gruppo di dispositivi, vedere [Aggiungere gruppi per organizzare utenti e dispositivi.](https://docs.microsoft.com/mem/intune/fundamentals/groups-add)

Per creare un profilo di configurazione per applicare le impostazioni di Teams a Surface Hub, procedere come segue:

1. Accedi a Microsoft Endpoint Manager visitando https://endpoint.microsoft.com/
2. Passare ai **profili di** configurazione  >  **dei dispositivi** e selezionare Crea **profilo**
3. In **Piattaforma** selezionare **Windows 10 e versioni successive**
4. In **Profilo** selezionare **Personalizzato** e quindi fare clic su **Crea**
5. Nella scheda **Informazioni di base,** in **Nome,** specificare un nome descrittivo per il profilo di configurazione e selezionare **Avanti**
6. Nella scheda **Impostazioni di** configurazione selezionare **Aggiungi**
7. Nel riquadro **Aggiungi riga** eseguire le operazioni seguenti:
    1. Specificare un nome descrittivo e, facoltativamente, una descrizione dell'impostazione di Teams da aggiungere
    2. In **URI OMA** immettere `./Vendor/MSFT/SurfaceHub/InBoxApps/Teams/Configurations`
    3. In **Tipo di dati** selezionare Stringa **(file XML)**
    4. Aprire il browser di file, selezionare il file XML creato in precedenza e quindi fare clic su **Apri**
8. Selezionare **Aggiungi** e quindi **Avanti**
9. Nella scheda **Attività,** assicurarsi che Assegna **a** sia impostato su **Gruppi selezionati**
10. In **Gruppi selezionati,** seleziona **Seleziona gruppi da includere** e scegli il gruppo che contiene i tuoi Surface Hub, quindi **seleziona**
11. Selezionare **Avanti,** **Avanti**
12. In Revisione **+ crea** seleziona **Crea**

## <a name="remove-teams-settings-from-a-surface-hub"></a>Rimuovere le impostazioni di Teams da Surface Hub

Rimuovere le impostazioni di configurazione di Teams in Surface Hub usando Windows Configuration Designer o Microsoft Intune in Microsoft Endpoint Manager.

### <a name="remove-a-provisioning-package-created-by-windows-configuration-designer"></a>Rimuovere un pacchetto di provisioning creato da Progettazione configurazione di Windows

Se hai applicato le impostazioni di Teams a un Surface Hub usando un pacchetto di provisioning creato da Windows Configuration Designer, usa la procedura seguente per rimuovere il pacchetto e le relative impostazioni:

1. In Surface Hub apri il menu Start, seleziona Tutte le **app** e quindi **seleziona Impostazioni**
2. Fornisci il nome utente e la password dell'amministratore, quindi seleziona **Sì**
3. Vai a **Surface Hub,** **Gestione dispositivi e** quindi aggiungi o rimuovi un pacchetto di **provisioning**
4. Accanto al pacchetto di provisioning che vuoi rimuovere, seleziona **Rimuovi**
5. Passare a **Surface Hub** e quindi a App **& funzionalità**
6. Trovare **Microsoft Teams per Surface Hub** e quindi selezionare Opzioni **avanzate**
7. Seleziona **Reimposta,** quindi reimposta **di** nuovo
8. Riavviare Surface Hub

### <a name="remove-settings-applied-by-microsoft-intune"></a>Rimuovere le impostazioni applicate da Microsoft Intune

Se sono state applicate le impostazioni di Teams a un Surface Hub usando Microsoft Intune in Microsoft Endpoint Management, usare la procedura seguente per rimuovere il profilo di configurazione e le relative impostazioni:

1. Accedi a Microsoft Endpoint Manager visitando https://endpoint.microsoft.com/
2. Passare ai profili **di configurazione**  >  **dei dispositivi**
3. Selezionare il profilo di configurazione che contiene le impostazioni della riunione coordinata da rimuovere
4. Nella pagina dei dettagli del profilo di configurazione selezionare **Elimina** e quindi **OK**

Dopo aver rimosso il profilo di configurazione che conteneva le impostazioni della riunione coordinata per Surface Hub, usare la procedura seguente per reimpostare l'app Teams in Surface Hub:

1. In Surface Hub apri il menu Start, seleziona Tutte le **app** e quindi **seleziona Impostazioni**
2. Fornisci il nome utente e la password dell'amministratore, quindi seleziona **Sì**
3. Passare a **Surface Hub** e quindi a App **& funzionalità**
4. Trovare **Microsoft Teams per Surface Hub** e quindi selezionare Opzioni **avanzate**
5. Seleziona **Reimposta,** quindi reimposta **di** nuovo
6. Riavviare Surface Hub