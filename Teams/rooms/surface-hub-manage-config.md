---
title: Gestire Microsoft Teams configurazione in Surface Hub
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
description: Gestire Microsoft Teams impostazioni di Surface Hub usando Microsoft Intune e Windows Configuration Designer
ms.openlocfilehash: 6bcf1d8780c1214637e1c12d5830edd3f2534ffd86898b14095f573bb08932b5
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54275992"
---
# <a name="manage-microsoft-teams-settings-on-surface-hub"></a>Gestire Microsoft Teams impostazioni di Surface Hub

È possibile gestire le Microsoft Teams in un Surface Hub usando Windows Configuration Designer o Microsoft Intune in Microsoft Endpoint Manager. Per apportare modifiche Windows impostazioni Microsoft Intune Teams configurazione. Per altre informazioni su queste opzioni, vedere gli articoli seguenti:

- [Creare un pacchetto di provisioning per Windows 10](/windows/configuration/provisioning-packages/provisioning-create-package)
- [Che cos'è Microsoft Intune gestione dei dispositivi?](/mem/intune/remote-actions/device-management)

Windows Progettazione configurazione è una buona opzione se si hanno solo pochi Surface Hub e si può accedervi facilmente. Se hai molti Surface Hub o se sono in posizioni remote, usa Microsoft Intune in Microsoft Endpoint Manager se è distribuito nell'organizzazione. Indipendentemente dal metodo scelto, è necessario creare un file di configurazione XML per apportare modifiche alle impostazioni Teams in Surface Hub.

## <a name="teams-configuration-file-syntax"></a>Teams sintassi del file di configurazione

Teams configurazione in un Surface Hub viene definita usando un file XML. Il file XML contiene tutte le impostazioni che possono essere usate per controllare Teams funzionamento. Sia Windows Progettazione configurazione che Microsoft Intune la stessa sintassi XML. Ecco un esempio di file XML di Teams di configurazione:

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
| Nessuno                    | `<SurfaceHubSettings>`                    |           | Contiene tutti gli elementi di configurazione Teams configurazione in un Surface Hub.                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| `<SurfaceHubSettings>`  | `<BluetoothAdvertisementEnabled>`         |           | Determina se Surface Hub annuncia che è disponibile per Bluetooth connessioni.<br>Valori accettati: `true` , `false`                                                                                                                                                                                                                                                                                                                                                                                         |
| `<SurfaceHubSettings>`  | `<AutoAcceptProximateMeetingInvitations>` |           | Determina se Teams accetta automaticamente riunioni basate sulla prossimità.<br>Valori accettati: `true` , `false`                                                                                                                                                                                                                                                                                                                                                                                                     |
| `<SurfaceHubSettings>`  | `<CoordinatedMeetings>`                   |           | Contiene tutti gli elementi di configurazione per le riunioni coordinate.                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|                         |                                           | `enabled` | Determina se Teams è configurato per partecipare a riunioni coordinate con altri dispositivi.<br>Valori accettati: `true` , `false`                                                                                                                                                                                                                                                                                                                                                                                |
| `<CoordinatedMeetings>` | `<TrustedAccounts>`                       |           | Si tratta di un elenco separato da virgole di UPN per ogni dispositivo sala Teams o Surface Hub da cui il dispositivo deve accettare le convocazioni di partecipazione alla riunione o a cui devono essere inviate le convocazioni di partecipazione alla riunione.<br>Valori accettati: stringa                                                                                                                                                                                                                                                                                                                         |
| `<CoordinatedMeetings>` | `<Settings>`                              |           | Contiene gli elementi di configurazione audio e video per le riunioni coordinate                                                                                                                                                                                                                                                                                                                                                                                                                               |
| `<Settings>`            | `<Audio>`                                 |           | Controlla la configurazione audio per Teams in un Surface Hub.                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|                         |                                           | `default` | Determina il dispositivo in cui il microfono sarà attivo all'avvio di una riunione. Questo campo può essere impostato su un solo dispositivo (in genere un dispositivo di Teams Rooms), mentre il resto dei dispositivi deve avere questo campo impostato su per evitare l'eco audio e `true` `false` il feedback.<br>Valori accettati: `true` , `false`                                                                                                                                                                                                           |
|                         |                                           | `enabled` | Determina se i partecipanti a una riunione possono attivare o disattivare il microfono. Per i **dispositivi** in cui è impostata l'impostazione predefinita Audio, questa impostazione deve essere impostata su in modo che i partecipanti non possano attivare accidentalmente un microfono e causare eco `false` `false` audio o feedback.<p>Se **l'opzione Audio** predefinita è impostata su , questa impostazione viene ignorata e i partecipanti possono disattivare o `true` riattivare l'audio del microfono.<br>Valori accettati: `true` , `false`                                                                               |
| `<Settings>`            | `<Video>`                                 |           | Controlla la configurazione video per Teams in un Surface Hub.                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|                         |                                           | `default` | Determina il dispositivo in cui la fotocamera sarà attiva all'avvio di una riunione. Per un'esperienza ottimale, è consigliabile impostare su solo il dispositivo Teams Rooms mentre tutti gli altri `true` dispositivi sono impostati su `false` .<br>Valori accettati: `true` , `false`                                                                                                                                                                                                                                                                  |
|                         |                                           | `enabled` | Determina se i partecipanti a una riunione possono attivare o disattivare la fotocamera. È possibile impostare questa opzione su qualsiasi altro dispositivo nell'evento in cui i partecipanti vogliono condividere prospettive video diverse, ad esempio se un partecipante usa la lavagna Surface Hub `true` video. Se non si vuole che i partecipanti accendono o spegnino una fotocamera in un dispositivo, impostare questa opzione su `false` .<p> Se **l'impostazione predefinita** video è impostata su , questa impostazione viene ignorata e i partecipanti possono attivare o disattivare `true` la fotocamera.<br>Valori accettati: `true` , `false` |

## <a name="apply-teams-settings-to-surface-hub"></a>Applicare Teams impostazioni di Surface Hub

Applicare o aggiornare le Teams di configurazione Surface Hub usando Windows Configuration Designer o Microsoft Intune in Microsoft Endpoint Manager.

### <a name="use-windows-configuration-designer"></a>Usare Windows Progettazione configurazione

È possibile usare Windows Configuration Designer per creare un pacchetto di provisioning che è possibile usare per applicare Teams impostazioni ai Surface Hub. Incollare il file XML creato in precedenza in Progettazione Windows configurazione per creare il pacchetto di provisioning.

> [!IMPORTANT]
> Se hai già applicato la configurazione Teams al tuo Surface Hub usando un pacchetto di provisioning e vuoi cambiarla, devi prima rimuovere il pacchetto di provisioning esistente. Per altre informazioni, vedere [Rimuovere un pacchetto di provisioning creato da Windows Configuration Designer.](#remove-a-provisioning-package-created-by-windows-configuration-designer)

Eseguire le operazioni seguenti per creare il pacchetto di provisioning in Windows Configuration Designer:

1. Installare Windows Configuration Designer da Windows Store nel computer locale e aprirlo
2. Selezionare **Provisioning Surface Hub dispositivi e** quindi passare **all'editor avanzato**
3. Nella schermata successiva espandere **WindowsTeamSettings**  >  **Teams** e selezionare **Configurazioni**
4. Nel campo accanto a **Configurazioni** nel riquadro centrale incollare la singola riga di CODICE XML creata in precedenza
5. Selezionare **Esporta**  >  **pacchetto di provisioning**
6. Specificare un nome per il pacchetto di provisioning in **Nome** e selezionare   >  **Avanti**
7. Specificare un percorso in cui salvare il pacchetto di provisioning e selezionare **Avanti**
8. Selezionare **Genera** per creare il pacchetto di provisioning e quindi **fine**

Infine, dopo aver creato il pacchetto di provisioning, eseguire le operazioni seguenti per applicare il pacchetto di provisioning al Surface Hub:

1. Salvare il pacchetto di provisioning creato in precedenza in un'unità USB
2. Inserire l'unità USB nel Surface Hub
3. Nel Surface Hub aprire il menu Start, selezionare Tutte le **app** e quindi selezionare **Impostazioni**
4. Specificare il nome utente e la password dell'amministratore e quindi selezionare **Sì**
5. Passare a **Surface Hub**, **Gestione dispositivi**, Aggiungere o rimuovere un pacchetto di **provisioning** e quindi aggiungere **un pacchetto**
6. In **Selezionare un pacchetto** selezionare **Aggiungi** accanto al pacchetto di provisioning e quindi riavviare il Surface Hub

### <a name="use-microsoft-intune"></a>Usare Microsoft Intune

Se i surface hub sono gestiti con Microsoft Intune in Microsoft Endpoint Management, puoi usarlo per applicare le impostazioni Teams a Surface Hub.If your Surface Hubs are managed using Microsoft Intune in Microsoft Endpoint Management, you can use it to apply Teams settings to your Surface Hubs. Si creerà un nuovo profilo di configurazione e quindi incollare al suo interno il file XML creato in precedenza.

> [!IMPORTANT]
> I Surface Hub devono essere in un gruppo di dispositivi in modo che il Microsoft Intune possa identificare i dispositivi a cui applicare il profilo di configurazione. Per informazioni su come creare un gruppo di dispositivi, vedere [Aggiungere gruppi per organizzare utenti e dispositivi.](/mem/intune/fundamentals/groups-add)

Eseguire le operazioni seguenti per creare un profilo di configurazione per applicare Teams impostazioni ai Surface Hub:

1. Accedi a Microsoft Endpoint Manager visitandohttps://endpoint.microsoft.com/
2. Passare a **Profili di**  >  **configurazione dispositivi** e selezionare Crea **profilo**
3. In **Piattaforma** selezionare Windows 10 **e versioni successive**
4. In **Profilo** selezionare **Personalizzato** e quindi fare clic su **Crea**
5. Nella scheda **Nozioni di** base, in **Nome,** specificare un nome descrittivo per il profilo di configurazione e selezionare **Avanti**
6. Nella scheda **Impostazioni di** configurazione selezionare **Aggiungi**
7. Nel riquadro **Aggiungi riga** eseguire le operazioni seguenti:
    1. Specificare un nome descrittivo e, facoltativamente, una descrizione dell'impostazione Teams che si sta aggiungendo
    2. In **OMA-URI** immettere `./Vendor/MSFT/SurfaceHub/InBoxApps/Teams/Configurations`
    3. In **Tipo di dati** selezionare Stringa **(file XML)**
    4. Aprire il browser dei file, selezionare il file XML creato in precedenza e **quindi apri**
8. Selezionare **Aggiungi** e quindi **Avanti**
9. Nella scheda **Attività verificare** che l'opzione Assegna a **sia** impostata su **Gruppi selezionati**
10. In **Gruppi selezionati** seleziona Seleziona gruppi da **includere** e scegli il gruppo che contiene i tuoi Surface Hub, quindi seleziona **Seleziona**
11. Selezionare **Avanti**, **Avanti**
12. Nella scheda **Revisione + crea** selezionare **Crea**

## <a name="remove-teams-settings-from-a-surface-hub"></a>Rimuovere Teams impostazioni da un Surface Hub

Rimuovere Teams di configurazione in Surface Hub usando Windows Configuration Designer o Microsoft Intune in Microsoft Endpoint Manager.

### <a name="remove-a-provisioning-package-created-by-windows-configuration-designer"></a>Rimuovere un pacchetto di provisioning creato da Windows Configuration Designer

Se sono state applicate Teams a un Surface Hub usando un pacchetto di provisioning creato da Windows Configuration Designer, usare la procedura seguente per rimuovere il pacchetto e le relative impostazioni:

1. Nel Surface Hub aprire il menu Start, selezionare Tutte le **app** e quindi selezionare **Impostazioni**
2. Specificare il nome utente e la password dell'amministratore e quindi selezionare **Sì**
3. Passare a **Surface Hub**, **Gestione dispositivi** e quindi aggiungere o rimuovere un pacchetto di **provisioning**
4. Accanto al pacchetto di provisioning da rimuovere, seleziona **Rimuovi**
5. Passare a **Surface Hub** e quindi alle **funzionalità di & app**
6. Trovare **Microsoft Teams per Surface Hub** e quindi selezionare Opzioni **avanzate**
7. Seleziona **Reimposta** e quindi **reimposta di** nuovo
8. Riavviare il Surface Hub

### <a name="remove-settings-applied-by-microsoft-intune"></a>Rimuovere le impostazioni applicate da Microsoft Intune

Se sono state applicate Teams a un Surface Hub usando Microsoft Intune in Microsoft Endpoint Management, usare la procedura seguente per rimuovere il profilo di configurazione e le relative impostazioni:

1. Accedi a Microsoft Endpoint Manager visitandohttps://endpoint.microsoft.com/
2. Passare ai **profili di configurazione** dei  >  **dispositivi**
3. Selezionare il profilo di configurazione che contiene le impostazioni della riunione coordinata da rimuovere
4. Nella pagina dei dettagli del profilo di configurazione selezionare **Elimina** e quindi **OK**

Dopo aver rimosso il profilo di configurazione che conteneva le impostazioni riunione coordinata per il Surface Hub, usare la procedura seguente per reimpostare l'app Teams nel Surface Hub:

1. Nel Surface Hub aprire il menu Start, selezionare Tutte le **app** e quindi selezionare **Impostazioni**
2. Specificare il nome utente e la password dell'amministratore e quindi selezionare **Sì**
3. Passare a **Surface Hub** e quindi alle **funzionalità di & app**
4. Trovare **Microsoft Teams per Surface Hub** e quindi selezionare Opzioni **avanzate**
5. Seleziona **Reimposta** e quindi **reimposta di** nuovo
6. Riavviare il Surface Hub