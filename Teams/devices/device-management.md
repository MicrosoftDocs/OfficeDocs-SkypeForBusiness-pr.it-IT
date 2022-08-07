---
title: Gestire i dispositivi in Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: kelsawi
ms.collection:
- M365-collaboration
- m365initiative-deployteams
- Teams_ITAdmin_Devices
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.managedevices.overview
- ms.teamsadmincenter.devicemanagement.overview
description: Informazioni su come gestire i dispositivi usati con Teams nell'organizzazione.
ms.localizationpriority: medium
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5dc65025ed255dff1685f7aa30a555facdd3f11c
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2022
ms.locfileid: "67270841"
---
# <a name="microsoft-teams-managing-your-devices"></a>Microsoft Teams: Gestione dei dispositivi 

È possibile gestire i dispositivi usati con Microsoft Teams nell'organizzazione dall'interfaccia di amministrazione di Microsoft Teams. È possibile visualizzare e gestire l'inventario dei dispositivi per l'organizzazione ed eseguire attività come l'aggiornamento, il riavvio e il monitoraggio della diagnostica per i dispositivi. È anche possibile creare e assegnare profili di configurazione a un dispositivo o a gruppi di dispositivi.

Per gestire i dispositivi, ad esempio modificare la configurazione dei dispositivi, riavviare i dispositivi, gestire gli aggiornamenti o visualizzare l'integrità dei dispositivi e delle periferiche, è necessario essere assegnati a uno dei ruoli di amministratore di Microsoft 365 seguenti:

- Amministratore globale di Microsoft 365
- Amministratore del servizio Teams
- Amministratore dei dispositivi di Teams

Per altre informazioni sui ruoli di amministratore in Teams, vedere [Usare i ruoli di amministratore di Teams per gestire Teams](../using-admin-roles.md).

## <a name="what-devices-can-you-manage"></a>Quali dispositivi puoi gestire?

Puoi gestire qualsiasi dispositivo certificato per Teams e registrato. Un dispositivo viene registrato automaticamente la prima volta che un utente accede a Teams sul dispositivo. Per un elenco dei dispositivi certificati che possono essere gestiti, vedi:

- [Microsoft Teams Rooms](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=20)
- [Telefoni da conferenza](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=73)
- [Telefoni da tavolo](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=34)
- [Visualizzazioni di Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=34)
- [Pannelli di Teams](teams-panels.md)

Per gestire i dispositivi, nel riquadro di spostamento sinistro [dell'interfaccia di amministrazione di Microsoft Teams](https://admin.teams.microsoft.com) passare a **Dispositivi di Teams** e quindi selezionare il tipo di dispositivo. Ogni tipo di dispositivo ha la rispettiva sezione, che consente di gestirli separatamente.

## <a name="manage-teams-rooms-on-windows-devices"></a>Gestire Teams Rooms nei dispositivi Windows

È possibile usare l'interfaccia di amministrazione di Teams per visualizzare e gestire in remoto i Teams Rooms nei dispositivi Windows dell'intera organizzazione. L'interfaccia di amministrazione di Teams consente di vedere a colpo d'occhio quali dispositivi sono integri e che richiedono attenzione e consente di concentrarsi su dispositivi specifici per visualizzare informazioni dettagliate sull'integrità dei dispositivi, sulle prestazioni delle riunioni, sulla qualità delle chiamate e sulle periferiche. 

Ecco alcune operazioni che puoi eseguire per gestire i dispositivi Teams Rooms. Teams Rooms dispositivi sono disponibili [nell'interfaccia di amministrazione di Microsoft Teams](https://admin.teams.microsoft.com) in **Dispositivi** >  di Teams **Teams Rooms in Windows**.

Per informazioni dettagliate su come gestire i dispositivi Teams Rooms, vedere [Gestire Microsoft Teams Rooms](../rooms/rooms-manage.md).

| Per eseguire questa operazione...                          | Esegui questa operazione                                                                                                                                                                                                                                                                                                                                                                          |
|----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Modificare le impostazioni in uno o più dispositivi | Seleziona uno o più dispositivi > **Modifica impostazioni**. Se si selezionano più dispositivi, i valori modificati sostituiranno i valori in tutti i dispositivi selezionati.                                                                                                                                                                                                                       |
| Riavviare i dispositivi                        | Seleziona uno o più dispositivi > **Riavvia**. Quando riavvii un dispositivo, puoi scegliere se riavviare immediatamente il dispositivo o selezionare **Pianifica riavvio** per riavviare il dispositivo a una data e un'ora specifiche. La data e l'ora selezionate sono locali per il dispositivo da riavviare.                                                                                            |
| Visualizzare l'attività della riunione                  | Seleziona il nome di un dispositivo per aprire i dettagli del dispositivo > **Attività**. Quando apri la scheda **Attività** , puoi vedere tutte le riunioni a cui ha partecipato il dispositivo. Questa visualizzazione di riepilogo mostra l'ora di inizio della riunione, il numero di partecipanti, la durata e la qualità complessiva della chiamata.                                                                                        |
| Visualizzare i dettagli della riunione                   | Seleziona il nome di un dispositivo per aprire i dettagli del dispositivo > **Attività** > seleziona una riunione. Quando apri i dettagli di una riunione, puoi vedere tutti i partecipanti alla riunione, per quanto tempo hanno partecipato alla chiamata, i tipi di sessione di Teams e la loro qualità della chiamata individuale. Per visualizzare informazioni tecniche sulla chiamata di un partecipante, selezionare l'ora di inizio della chiamata del partecipante. |

## <a name="manage-phones-teams-rooms-on-android-teams-displays-and-teams-panels"></a>Gestire telefoni, Teams Rooms sui pannelli Android, Teams e Teams 

Nell'interfaccia di amministrazione di Teams è possibile visualizzare e gestire telefoni, Teams Rooms su Android, schermi di Teams e pannelli teams registrati in Teams nell'organizzazione. Le informazioni visualizzate per ogni dispositivo includono il nome del dispositivo, il produttore, il modello, l'utente, lo stato, l'azione, l'ultima visualizzazione e la cronologia. È possibile personalizzare la visualizzazione in modo da visualizzare le informazioni più adatte alle proprie esigenze.

I telefoni, i Teams Rooms su Android, gli schermi di Teams e i pannelli teams vengono registrati automaticamente in Microsoft Intune se ci si è iscritti. Dopo la registrazione di un dispositivo, la conformità del dispositivo viene confermata e al dispositivo vengono applicati criteri di accesso condizionale.

Ecco alcuni esempi di come gestire telefoni, Teams Rooms su schermi Android, Teams e pannelli Teams nell'organizzazione.  

| Per eseguire questa operazione...                           | Esegui questa operazione                                                                                                                                                                                                                                                                                                      |
|-----------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Modificare le informazioni sul dispositivo               | Seleziona un dispositivo > **Modifica**. È possibile modificare dettagli come il nome del dispositivo, il tag risorsa e aggiungere note.                                                                                                                                                                                                              |
| Gestire gli aggiornamenti software                 | Seleziona un dispositivo > **Update**. Puoi visualizzare l'elenco degli aggiornamenti software e firmware disponibili per il dispositivo e scegliere gli aggiornamenti da installare. Per altre informazioni sull'aggiornamento dei dispositivi, vedere [Aggiornare i dispositivi di Teams in remoto](remote-update.md)                                                          |
| Aggiornare i telefoni di Teams agli schermi di Teams  | Nella pagina **Telefoni IP** selezionare uno o più telefoni teams > **Aggiorna**. Questa opzione è disponibile solo per i telefoni che supportano l'aggiornamento agli schermi di Teams. Per altre informazioni, vedere [Aggiornare i telefoni di Teams agli schermi di Teams](upgrade-phones-to-displays.md).                                                      |
| Assegnare o modificare criteri di configurazione | Seleziona uno o più dispositivi > **Assegna configurazione**.                                                                                                                                                                                                                                                       |
| Aggiungere o rimuovere tag dispositivo               | Seleziona uno o più dispositivi > **Gestisci tag**. Per altre informazioni sui tag dei dispositivi, vedere [Gestire i tag dei dispositivi di Teams](manage-device-tags.md).                                                                                                                                                                 |
| Riavviare i dispositivi                         | Seleziona uno o più dispositivi > **Riavvia**.                                                                                                                                                                                                                                                                    |
| Filtrare i dispositivi usando i tag del dispositivo        | Seleziona l'icona del filtro, seleziona il campo **Tag** , specifica un tag dispositivo in base al quale filtrare e seleziona **Applica**. Per altre informazioni sul filtro dei dispositivi tramite tag di dispositivo, vedere [Usare i filtri per restituire i dispositivi con un tag specifico](manage-device-tags.md#use-filters-to-return-devices-with-a-specific-tag). |
| Visualizzare la cronologia e la diagnostica dei dispositivi     | Nella colonna **Cronologia** fai clic sul collegamento **Visualizza** per un dispositivo per visualizzare la cronologia degli aggiornamenti e i dettagli diagnostici.                                                                                                                                                                                         |

### <a name="use-configuration-profiles-in-teams"></a>Usare i profili di configurazione in Teams

Usare i profili di configurazione per gestire le impostazioni e le funzionalità per i diversi dispositivi Teams nell'organizzazione, tra cui Teams Rooms su Android, schermi di Teams, telefono Teams e pannelli teams. È possibile creare o caricare profili di configurazione per includere le impostazioni e le funzionalità da abilitare o disabilitare e quindi assegnare un profilo a un dispositivo o a un set di dispositivi. 

#### <a name="create-a-configuration-profile"></a>Creare un profilo di configurazione

Per creare un profilo di configurazione per un tipo di dispositivo di Teams:

1. Nella barra di spostamento sinistra, passare a **Dispositivi di Teams** > selezionare il tipo di dispositivo teams > **profili di configurazione**. Ad esempio, selezionare **Teams Devices** > **Teams panel** > **Profili di configurazione** per creare un nuovo profilo di configurazione per i pannelli di Teams.
2. Fare clic su **Aggiungi**.
3. Immettere un nome per il profilo e facoltativamente aggiungere una descrizione descrittiva.
4. Specificare le impostazioni desiderate per il profilo e quindi fare clic su **Salva**.
   Il profilo di configurazione appena creato viene visualizzato nell'elenco dei profili.

#### <a name="assign-a-configuration-profile"></a>Assegnare un profilo di configurazione
Dopo aver creato un profilo di configurazione per un tipo di dispositivo di Teams, assegnarlo a uno o più dispositivi.

1. Nella barra di spostamento sinistra, passare a **Dispositivi di Teams** > selezionare il tipo di dispositivo di Teams. Ad esempio, per assegnare un profilo di configurazione a un dispositivo dei pannelli di Teams, selezionare **i pannelli Teams** **Dispositivi** >  di Teams.
2. Seleziona uno o più dispositivi e quindi fai clic su **Assegna configurazione**.  
3. Nel riquadro **Assegna configurazione** cercare profilo di configurazione da assegnare ai dispositivi selezionati.
4. Fare clic su **Applica**.
   Per i dispositivi a cui è stato applicato il criterio di configurazione, la colonna **Azione** visualizza **Aggiornamento configurazione** e la colonna **Profilo di configurazione** visualizza il nome del profilo di configurazione.
