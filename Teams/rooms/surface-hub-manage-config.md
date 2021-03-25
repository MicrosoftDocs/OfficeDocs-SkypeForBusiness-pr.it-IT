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
description: Gestire le impostazioni di Microsoft Teams in Surface Hub usando Microsoft Intune e Progettazione configurazione di Windows
ms.openlocfilehash: 9c16fa4875febd3c9e0a8457626db5e09bf90545
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117384"
---
# <a name="manage-microsoft-teams-settings-on-surface-hub"></a>Gestire le impostazioni di Microsoft Teams in Surface Hub

È possibile gestire le impostazioni di Microsoft Teams in un Surface Hub usando Progettazione configurazione di Windows o Microsoft Intune in Microsoft Endpoint Manager. Per apportare modifiche alle impostazioni di Teams, è necessaria la conoscenza di Windows Configuration Designer o Microsoft Intune. Per altre informazioni su queste opzioni, vedere gli articoli seguenti:

- [Creare un pacchetto di provisioning per Windows 10](/windows/configuration/provisioning-packages/provisioning-create-package)
- [Che cos'è la gestione dei dispositivi di Microsoft Intune?](/mem/intune/remote-actions/device-management)

Progettazione configurazione di Windows è una buona opzione se si hanno solo pochi dispositivi Surface Hub e si può accedervi facilmente. Se si hanno molti Surface Hub o se sono in posizioni remote, usare Microsoft Intune in Microsoft Endpoint Manager se è distribuito nell'organizzazione. Indipendentemente dal metodo scelto, è necessario creare un file di configurazione XML per apportare modifiche alle impostazioni di Teams in Surface Hub.

## <a name="teams-configuration-file-syntax"></a>Sintassi del file di configurazione di Teams

La configurazione di Teams in un Surface Hub viene definita usando un file XML. Il file XML contiene tutte le impostazioni che possono essere usate per controllare il funzionamento di Teams. Sia Progettazione configurazione di Windows che Microsoft Intune usano la stessa sintassi XML. Ecco un esempio del file XML di configurazione di Teams:

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
| Nessuno                    | `<SurfaceHubSettings>`                    |           | Contiene tutti gli elementi di configurazione per la configurazione di Teams in un Surface Hub.                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| `<SurfaceHubSettings>`  | `<BluetoothAdvertisementEnabled>`         |           | Determina se Surface Hub annuncia che è disponibile per Bluetooth connessioni.<br>Valori accettati: `true` , `false`                                                                                                                                                                                                                                                                                                                                                                                         |
| `<SurfaceHubSettings>`  | `<AutoAcceptProximateMeetingInvitations>` |           | Determina se Teams accetterà automaticamente riunioni basate sulla prossimità.<br>Valori accettati: `true` , `false`                                                                                                                                                                                                                                                                                                                                                                                                     |
| `<SurfaceHubSettings>`  | `<CoordinatedMeetings>`                   |           | Contiene tutti gli elementi di configurazione per le riunioni coordinate.                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|                         |                                           | `enabled` | Determina se Teams è configurato per partecipare a riunioni coordinate con altri dispositivi.<br>Valori accettati: `true` , `false`                                                                                                                                                                                                                                                                                                                                                                                |
| `<CoordinatedMeetings>` | `<TrustedAccounts>`                       |           | Si tratta di un elenco separato da virgole di UPN per ogni dispositivo Teams Room o Surface Hub da cui il dispositivo deve accettare le convocazioni di partecipazione alle riunioni o a cui devono essere inviate le convocazioni di partecipazione alla riunione.<br>Valori accettati: stringa                                                                                                                                                                                                                                                                                                                         |
| `<CoordinatedMeetings>` | `<Settings>`                              |           | Contiene gli elementi di configurazione audio e video per le riunioni coordinate                                                                                                                                                                                                                                                                                                                                                                                                                               |
| `<Settings>`            | `<Audio>`                                 |           | Controlla la configurazione audio per Teams in un Surface Hub.                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|                         |                                           | `default` | Determina il dispositivo in cui il microfono sarà attivo all'avvio di una riunione. Questo campo può essere impostato su un solo dispositivo (in genere un dispositivo Teams Rooms), mentre il resto dei dispositivi deve avere questo campo impostato su per evitare l'eco audio e `true` `false` il feedback.<br>Valori accettati: `true` , `false`                                                                                                                                                                                                           |
|                         |                                           | `enabled` | Determina se i partecipanti a una riunione possono attivare o disattivare il microfono. Per i **dispositivi** in cui è impostata l'impostazione predefinita Audio, questa impostazione deve essere impostata su in modo che i partecipanti non possano attivare accidentalmente un microfono e causare eco `false` `false` audio o feedback.<p>Se **l'opzione Audio** predefinita è impostata su , questa impostazione viene ignorata e i partecipanti possono disattivare o `true` riattivare l'audio del microfono.<br>Valori accettati: `true` , `false`                                                                               |
| `<Settings>`            | `<Video>`                                 |           | Controlla la configurazione video per Teams in un Surface Hub.                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|                         |                                           | `default` | Determina il dispositivo in cui la fotocamera sarà attiva all'avvio di una riunione. Per un'esperienza ottimale, è consigliabile impostare solo il dispositivo Teams Rooms su `true` mentre tutti gli altri dispositivi sono impostati su `false` .<br>Valori accettati: `true` , `false`                                                                                                                                                                                                                                                                  |
|                         |                                           | `enabled` | Determina se i partecipanti a una riunione possono attivare o disattivare la fotocamera. È possibile impostare questa opzione su qualsiasi altro dispositivo nell'evento in cui i partecipanti vogliono condividere prospettive video diverse, ad esempio se un partecipante usa la `true` lavagna di Surface Hub. Se non si vuole che i partecipanti accendono o spegnino una fotocamera in un dispositivo, impostare questa opzione su `false` .<p> Se **l'impostazione predefinita** video è impostata su , questa impostazione viene ignorata e i partecipanti possono attivare o disattivare `true` la fotocamera.<br>Valori accettati: `true` , `false` |

## <a name="apply-teams-settings-to-surface-hub"></a>Applicare le impostazioni di Teams a Surface Hub

Applicare o aggiornare le impostazioni di configurazione di Teams in Surface Hub usando Progettazione configurazione di Windows o Microsoft Intune in Microsoft Endpoint Manager.

### <a name="use-windows-configuration-designer"></a>Usare Progettazione configurazione di Windows

È possibile usare Progettazione configurazione di Windows per creare un pacchetto di provisioning che è possibile usare per applicare le impostazioni di Teams ai Surface Hub. Incollare il file XML creato in precedenza in Progettazione configurazione di Windows per creare il pacchetto di provisioning.

> [!IMPORTANT]
> Se hai già applicato la configurazione di Teams a Surface Hub usando un pacchetto di provisioning e vuoi cambiarla, devi prima rimuovere il pacchetto di provisioning esistente. Per altre informazioni, vedere [Rimuovere un pacchetto di provisioning creato da Progettazione configurazione di Windows.](#remove-a-provisioning-package-created-by-windows-configuration-designer)

Eseguire le operazioni seguenti per creare il pacchetto di provisioning in Progettazione configurazione di Windows:

1. Installare Progettazione configurazione di Windows da Windows Store nel computer locale e aprirlo
2. Seleziona **Provisioning dei dispositivi Surface Hub** e quindi passa **all'editor avanzato**
3. Nella schermata successiva espandere **WindowsTeamSettings**  >  **Teams** e selezionare **Configurazioni**
4. Nel campo accanto a **Configurazioni** nel riquadro centrale incollare la singola riga di CODICE XML creata in precedenza
5. Selezionare **Esporta**  >  **pacchetto di provisioning**
6. Specificare un nome per il pacchetto di provisioning in **Nome** e selezionare   >  **Avanti**
7. Specificare un percorso in cui salvare il pacchetto di provisioning e selezionare **Avanti**
8. Selezionare **Genera** per creare il pacchetto di provisioning e quindi **fine**

Infine, dopo aver creato il pacchetto di provisioning, eseguire le operazioni seguenti per applicare il pacchetto di provisioning a Surface Hub:

1. Salvare il pacchetto di provisioning creato in precedenza in un'unità USB
2. Inserire l'unità USB in Surface Hub
3. In Surface Hub apri il menu Start, seleziona **Tutte le app** e quindi seleziona **Impostazioni**
4. Specificare il nome utente e la password dell'amministratore e quindi selezionare **Sì**
5. Passare a **Surface Hub**, **Gestione dispositivi**, Aggiungere o rimuovere un pacchetto **di provisioning** e quindi aggiungere **un pacchetto**
6. In **Seleziona un pacchetto** seleziona **Aggiungi** accanto al pacchetto di provisioning e quindi riavvia Surface Hub

### <a name="use-microsoft-intune"></a>Usare Microsoft Intune

Se i surface hub vengono gestiti con Microsoft Intune in Microsoft Endpoint Management, è possibile usarlo per applicare le impostazioni di Teams ai Surface Hub. Si creerà un nuovo profilo di configurazione e quindi incollare al suo interno il file XML creato in precedenza.

> [!IMPORTANT]
> I Surface Hub devono essere in un gruppo di dispositivi in modo che Microsoft Intune possa identificare i dispositivi a cui applicare il profilo di configurazione. Per informazioni su come creare un gruppo di dispositivi, vedere [Aggiungere gruppi per organizzare utenti e dispositivi.](/mem/intune/fundamentals/groups-add)

Eseguire le operazioni seguenti per creare un profilo di configurazione per applicare le impostazioni di Teams ai Surface Hub:

1. Accedere a Microsoft Endpoint Manager visitando https://endpoint.microsoft.com/
2. Passare a **Profili di**  >  **configurazione dispositivi** e selezionare Crea **profilo**
3. In **Piattaforma** selezionare **Windows 10 e versioni successive**
4. In **Profilo** selezionare **Personalizzato** e quindi fare clic su **Crea**
5. Nella scheda **Nozioni di** base, in **Nome,** specificare un nome descrittivo per il profilo di configurazione e selezionare **Avanti**
6. Nella scheda **Impostazioni di** configurazione selezionare **Aggiungi**
7. Nel riquadro **Aggiungi riga** eseguire le operazioni seguenti:
    1. Specificare un nome descrittivo e, facoltativamente, una descrizione dell'impostazione di Teams che si sta aggiungendo
    2. In **OMA-URI** immettere `./Vendor/MSFT/SurfaceHub/InBoxApps/Teams/Configurations`
    3. In **Tipo di dati** selezionare Stringa **(file XML)**
    4. Aprire il browser dei file, selezionare il file XML creato in precedenza e **quindi apri**
8. Selezionare **Aggiungi** e quindi **Avanti**
9. Nella scheda **Attività verificare** che l'opzione Assegna a **sia** impostata su **Gruppi selezionati**
10. In **Gruppi selezionati** seleziona Seleziona gruppi da **includere** e scegli il gruppo che contiene i tuoi Surface Hub, quindi seleziona **Seleziona**
11. Selezionare **Avanti**, **Avanti**
12. Nella scheda **Revisione + crea** selezionare **Crea**

## <a name="remove-teams-settings-from-a-surface-hub"></a>Rimuovere le impostazioni di Teams da un Surface Hub

Rimuovere le impostazioni di configurazione di Teams in Surface Hub usando Progettazione configurazione di Windows o Microsoft Intune in Microsoft Endpoint Manager.

### <a name="remove-a-provisioning-package-created-by-windows-configuration-designer"></a>Rimuovere un pacchetto di provisioning creato da Progettazione configurazione di Windows

Se hai applicato le impostazioni di Teams a un Surface Hub usando un pacchetto di provisioning creato da Progettazione configurazione di Windows, usa la procedura seguente per rimuovere il pacchetto e le relative impostazioni:

1. In Surface Hub apri il menu Start, seleziona **Tutte le app** e quindi seleziona **Impostazioni**
2. Specificare il nome utente e la password dell'amministratore e quindi selezionare **Sì**
3. Passare a **Surface Hub**, **Gestione dispositivi** e quindi aggiungere o rimuovere un pacchetto **di provisioning**
4. Accanto al pacchetto di provisioning da rimuovere, seleziona **Rimuovi**
5. Passare a **Surface Hub e** quindi alle funzionalità di & **app**
6. Trova **Microsoft Teams per Surface Hub** e quindi seleziona Opzioni **avanzate**
7. Seleziona **Reimposta** e quindi **reimposta di** nuovo
8. Riavvia Surface Hub

### <a name="remove-settings-applied-by-microsoft-intune"></a>Rimuovere le impostazioni applicate da Microsoft Intune

Se le impostazioni di Teams sono state applicate a un Surface Hub usando Microsoft Intune in Microsoft Endpoint Management, usare la procedura seguente per rimuovere il profilo di configurazione e le relative impostazioni:

1. Accedere a Microsoft Endpoint Manager visitando https://endpoint.microsoft.com/
2. Passare ai **profili di configurazione** dei  >  **dispositivi**
3. Selezionare il profilo di configurazione che contiene le impostazioni della riunione coordinata da rimuovere
4. Nella pagina dei dettagli del profilo di configurazione selezionare **Elimina** e quindi **OK**

Dopo aver rimosso il profilo di configurazione che conteneva le impostazioni della riunione coordinata per Surface Hub, usare la procedura seguente per reimpostare l'app Teams in Surface Hub:

1. In Surface Hub apri il menu Start, seleziona **Tutte le app** e quindi seleziona **Impostazioni**
2. Specificare il nome utente e la password dell'amministratore e quindi selezionare **Sì**
3. Passare a **Surface Hub e** quindi alle funzionalità di & **app**
4. Trova **Microsoft Teams per Surface Hub** e quindi seleziona Opzioni **avanzate**
5. Seleziona **Reimposta** e quindi **reimposta di** nuovo
6. Riavvia Surface Hub