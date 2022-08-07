---
title: Gestire la configurazione di Microsoft Teams su Surface Hub
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
description: Gestire le impostazioni di Microsoft Teams su Surface Hub usando Microsoft Intune e Progettazione configurazione di Windows
ms.openlocfilehash: 6e99922ebb7bb30db1b5e94fd1a4d30b8ec653b8
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2022
ms.locfileid: "67272211"
---
# <a name="manage-microsoft-teams-settings-on-surface-hub"></a>Gestire le impostazioni di Microsoft Teams su Surface Hub

È possibile gestire le impostazioni di Microsoft Teams in un Surface Hub usando Progettazione configurazione di Windows o Microsoft Intune in Microsoft Endpoint Manager. La conoscenza di Progettazione configurazione di Windows o di Microsoft Intune è necessaria per apportare modifiche alle impostazioni di Teams. Per altre informazioni su queste opzioni, vedere gli articoli seguenti:

- [Creare un pacchetto di provisioning per Windows 10](/windows/configuration/provisioning-packages/provisioning-create-package)
- [Che cos'è Microsoft Intune gestione dei dispositivi?](/mem/intune/remote-actions/device-management)

Progettazione configurazione di Windows è una buona opzione se hai solo pochi dispositivi Surface Hub e puoi accedervi facilmente. Se hai molti Surface Hub o se si trovano in posizioni remote, usa Microsoft Intune in Microsoft Endpoint Manager se è stato distribuito nell'organizzazione. Indipendentemente dal metodo scelto, è necessario creare un file di configurazione XML per apportare modifiche alle impostazioni di Teams in Surface Hub.

## <a name="teams-configuration-file-syntax"></a>Sintassi del file di configurazione di Teams

La configurazione di Teams in un Surface Hub è definita con un file XML. Il file XML contiene tutte le impostazioni che possono essere usate per controllare il funzionamento di Teams. Progettazione configurazione di Windows e Microsoft Intune usare la stessa sintassi XML. Ecco un esempio del file XML di configurazione di Teams:

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

| Genitore                  | Elemento                                   | Attributo | Descrizione                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
|-------------------------|-------------------------------------------|-----------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Nessuno                    | `<SurfaceHubSettings>`                    |           | Contiene tutti gli elementi di configurazione per la configurazione di Teams in surface hub.                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| `<SurfaceHubSettings>`  | `<BluetoothAdvertisementEnabled>`         |           | Determina se Surface Hub annuncia che è disponibile per le connessioni Bluetooth.<br>Valori accettati: `true`, `false`                                                                                                                                                                                                                                                                                                                                                                                         |
| `<SurfaceHubSettings>`  | `<AutoAcceptProximateMeetingInvitations>` |           | Determina se Teams accetterà automaticamente le riunioni basate sulla prossimità.<br>Valori accettati: `true`, `false`                                                                                                                                                                                                                                                                                                                                                                                                     |
| `<SurfaceHubSettings>`  | `<CoordinatedMeetings>`                   |           | Contiene tutti gli elementi di configurazione per le riunioni coordinate.                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|                         |                                           | `enabled` | Determina se Teams è configurato per partecipare a riunioni coordinate con altri dispositivi.<br>Valori accettati: `true`, `false`                                                                                                                                                                                                                                                                                                                                                                                |
| `<CoordinatedMeetings>` | `<TrustedAccounts>`                       |           | Si tratta di un elenco separato da virgole di UPN per ogni dispositivo Teams Room o Surface Hub da cui il dispositivo deve accettare le convocazioni di partecipazione a riunioni o a cui devono essere inviate le convocazioni di partecipazione.<br>Valori accettati: stringa                                                                                                                                                                                                                                                                                                                         |
| `<CoordinatedMeetings>` | `<Settings>`                              |           | Contiene elementi di configurazione audio e video di configurazione per riunioni coordinate                                                                                                                                                                                                                                                                                                                                                                                                                               |
| `<Settings>`            | `<Audio>`                                 |           | Controlla la configurazione audio per Teams in un Surface Hub.                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|                         |                                           | `default` | Determina in quale dispositivo sarà attivo il microfono all'avvio di una riunione. Questo campo può essere impostato su `true` un solo dispositivo (in genere un dispositivo Teams Rooms), mentre per il resto dei dispositivi questo campo deve essere impostato su per `false` evitare eco audio e feedback.<br>Valori accettati: `true`, `false`                                                                                                                                                                                                           |
|                         |                                           | `enabled` | Determina se i partecipanti a una riunione possono attivare o disattivare il microfono. Per i dispositivi su cui è impostata `false` **l'impostazione audio predefinita**, questa impostazione deve essere impostata `false` su in modo che i partecipanti non possano attivare accidentalmente un microfono e causare eco audio o feedback.<p>Se **l'opzione Audio** è impostata su `true`, questa impostazione viene ignorata e i partecipanti possono disattivare o riattivare l'audio del microfono.<br>Valori accettati: `true`, `false`                                                                               |
| `<Settings>`            | `<Video>`                                 |           | Controlla la configurazione video per Teams in un Surface Hub.                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|                         |                                           | `default` | Determina in quale dispositivo la fotocamera sarà attiva all'avvio di una riunione. Per un'esperienza ottimale, è consigliabile impostare `true` solo il Teams Rooms dispositivo, mentre tutti gli altri dispositivi sono impostati su `false`.<br>Valori accettati: `true`, `false`                                                                                                                                                                                                                                                                  |
|                         |                                           | `enabled` | Determina se i partecipanti a una riunione possono attivare o disattivare la fotocamera. Puoi impostare questa `true` opzione su su qualsiasi altro dispositivo nei partecipanti all'evento che vogliono condividere prospettive video diverse (ad esempio se un partecipante usa la lavagna di Surface Hub). Se non si vuole che i partecipanti attivino o disattivino una fotocamera in un dispositivo, impostare questa `false`opzione su .<p> Se **l'impostazione predefinita video** è `true`, questa impostazione viene ignorata e i partecipanti possono attivare o disattivare la fotocamera.<br>Valori accettati: `true`, `false` |

## <a name="apply-teams-settings-to-surface-hub"></a>Applicare le impostazioni di Teams a Surface Hub

Applicare o aggiornare le impostazioni di configurazione di Teams su Surface Hub usando Progettazione configurazione di Windows o Microsoft Intune in Microsoft Endpoint Manager.

### <a name="use-windows-configuration-designer"></a>Usare Progettazione configurazione di Windows

È possibile usare Progettazione configurazione di Windows per creare un pacchetto di provisioning da usare per applicare le impostazioni di Teams a Surface Hub. Il file XML creato in precedenza verrà incollato in Progettazione configurazione di Windows per creare il pacchetto di provisioning.

> [!IMPORTANT]
> Se hai già applicato la configurazione di Teams a Surface Hub utilizzando un pacchetto di provisioning e vuoi modificarla, devi prima rimuovere il pacchetto di provisioning esistente. Per altre informazioni, vedere [Rimuovere un pacchetto di provisioning creato da Progettazione configurazione di Windows](#remove-a-provisioning-package-created-by-windows-configuration-designer).

Per creare il pacchetto di provisioning in Progettazione configurazione di Windows, eseguire le operazioni seguenti:

1. Installare Progettazione configurazione di Windows da Windows Store nel computer locale e aprirlo
2. Seleziona **Provisioning dei dispositivi Surface Hub** , quindi **Passa all'editor avanzato**
3. Nella schermata successiva espandere **WindowsTeamSettings** > **Teams** e selezionare **Configurazioni**
4. Nel campo accanto a **Configurazioni** nel riquadro centrale incollare la singola riga di CODICE XML creata sopra
5. Selezionare **Il****pacchetto di provisioning dell'esportazione** > 
6. Fornisci un nome per il pacchetto di provisioning in **Nome** e seleziona **Avanti Avanti** > 
7. Specificare un percorso in cui salvare il pacchetto di provisioning e selezionare **Avanti**
8. Seleziona **Compila** per creare il pacchetto di provisioning, quindi **Fine**

Infine, dopo aver creato il pacchetto di provisioning, esegui le operazioni seguenti per applicare il pacchetto di provisioning a Surface Hub:

1. Salva il pacchetto di provisioning creato in precedenza in un'unità USB
2. Inserire l'unità USB in Surface Hub
3. In Surface Hub apri il menu Start, seleziona **Tutte le app** e quindi seleziona **Impostazioni**
4. Fornisci il nome utente e la password dell'amministratore, quindi seleziona **Sì**
5. Vai a **Surface Hub**, **Gestione dispositivi**, **Aggiungi o rimuovi un pacchetto di provisioning** e quindi **Aggiungi un pacchetto**
6. In **Seleziona un pacchetto** seleziona **Aggiungi** accanto al pacchetto di provisioning, quindi riavvia Surface Hub

### <a name="use-microsoft-intune"></a>Usare Microsoft Intune

Se i Surface Hub sono gestiti tramite Microsoft Intune in Gestione endpoint Microsoft, è possibile usarlo per applicare le impostazioni di Teams a Surface Hub. Verrà creato un nuovo profilo di configurazione e quindi incollato il file XML creato in precedenza.

> [!IMPORTANT]
> I Surface Hub devono far parte di un gruppo di dispositivi in modo che il Microsoft Intune possa identificare a quali dispositivi applicare il profilo di configurazione. Per informazioni su come creare un gruppo di dispositivi, vedere [Aggiungere gruppi per organizzare utenti e dispositivi](/mem/intune/fundamentals/groups-add).

Per creare un profilo di configurazione per applicare le impostazioni di Teams a Surface Hub, eseguire le operazioni seguenti:

1. Accedi a Microsoft Endpoint Manager visitandohttps://endpoint.microsoft.com/
2. Passa a **Profili di configurazione** **dispositivi** >  e seleziona **Crea profilo**
3. In **Piattaforma** seleziona **Windows 10 e versioni successive**
4. In **Profilo** selezionare **Personalizzato** e quindi fare clic su **Crea**
5. Nella scheda **Nozioni di base** , in **Nome**, fornisci un nome descrittivo per il profilo di configurazione e seleziona **Avanti**
6. Nella scheda **Impostazioni di configurazione** seleziona **Aggiungi**
7. Nel riquadro **Aggiungi riga** eseguire le operazioni seguenti:
    1. Fornisci un nome descrittivo e, facoltativamente, una descrizione dell'impostazione di Teams che stai aggiungendo
    2. In **OMA-URI** immetti `./Vendor/MSFT/SurfaceHub/InBoxApps/Teams/Configurations`
    3. In **Tipo di dati** selezionare **Stringa (file XML)**
    4. Aprire il browser dei file, selezionare il file XML creato in precedenza e **scegliere Apri**
8. Seleziona **Aggiungi** e quindi **Avanti**
9. Nella scheda **Attività** assicurarsi che **Assegna a** sia impostato su **Gruppi selezionati**
10. In **Gruppi selezionati** seleziona **Seleziona gruppi da includere** e scegli il gruppo che contiene Surface Hub, quindi seleziona **Seleziona**
11. Seleziona **Avanti**, **Avanti**
12. In **Revisione + Crea** seleziona **Crea**

## <a name="remove-teams-settings-from-a-surface-hub"></a>Rimuovere le impostazioni di Teams da un Surface Hub

Rimuovere le impostazioni di configurazione di Teams in Surface Hub usando Progettazione configurazione di Windows o Microsoft Intune in Microsoft Endpoint Manager.

### <a name="remove-a-provisioning-package-created-by-windows-configuration-designer"></a>Rimuovere un pacchetto di provisioning creato da Progettazione configurazione di Windows

Se hai applicato le impostazioni di Teams a un Surface Hub usando un pacchetto di provisioning creato da Progettazione configurazione di Windows, utilizza la procedura seguente per rimuovere il pacchetto e le relative impostazioni:

1. In Surface Hub apri il menu Start, seleziona **Tutte le app** e quindi seleziona **Impostazioni**
2. Fornisci il nome utente e la password dell'amministratore, quindi seleziona **Sì**
3. Vai a **Surface Hub**, **Gestione dispositivi** e quindi **Aggiungi o rimuovi un pacchetto di provisioning**
4. Accanto al pacchetto di provisioning che vuoi rimuovere, seleziona **Rimuovi**
5. Vai a **Surface Hub** e quindi a **Funzionalità di & delle app**
6. Trova **Microsoft Teams per Surface Hub** e quindi seleziona **Opzioni avanzate**
7. Seleziona **Reimposta** e quindi **reimposta** di nuovo
8. Riavviare Surface Hub

### <a name="remove-settings-applied-by-microsoft-intune"></a>Rimuovere le impostazioni applicate da Microsoft Intune

Se sono stati applicate le impostazioni di Teams a un Surface Hub usando Microsoft Intune in Gestione endpoint Microsoft, usare la procedura seguente per rimuovere il profilo di configurazione e le relative impostazioni:

1. Accedi a Microsoft Endpoint Manager visitandohttps://endpoint.microsoft.com/
2. Passare ai **profili di configurazione** **dei dispositivi** > 
3. Selezionare il profilo di configurazione contenente le impostazioni riunione coordinata da rimuovere
4. Nella pagina dei dettagli del profilo di configurazione seleziona **Elimina** e quindi **OK**

Dopo aver rimosso il profilo di configurazione che conteneva le impostazioni riunione coordinata per Surface Hub, utilizza i passaggi seguenti per reimpostare l'app Teams su Surface Hub:

1. In Surface Hub apri il menu Start, seleziona **Tutte le app** e quindi seleziona **Impostazioni**
2. Fornisci il nome utente e la password dell'amministratore, quindi seleziona **Sì**
3. Vai a **Surface Hub** e quindi a **Funzionalità di & delle app**
4. Trova **Microsoft Teams per Surface Hub** e quindi seleziona **Opzioni avanzate**
5. Seleziona **Reimposta** e quindi **reimposta** di nuovo
6. Riavviare Surface Hub
