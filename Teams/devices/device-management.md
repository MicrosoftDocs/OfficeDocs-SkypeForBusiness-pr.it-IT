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
ms.openlocfilehash: 2baa4755f63bbb5867a1e259c9edc9a3aeca0718
ms.sourcegitcommit: ab9d27d7ddd1494539ae9424de200c9d0e76a9ec
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/28/2021
ms.locfileid: "59993211"
---
# <a name="manage-your-devices-in-microsoft-teams"></a>Gestire i dispositivi in Microsoft Teams

È possibile gestire i dispositivi usati con Microsoft Teams nell'organizzazione dall'Microsoft Teams di amministrazione. È possibile visualizzare e gestire l'inventario dei dispositivi per l'organizzazione ed eseguire attività come l'aggiornamento, il riavvio e il monitoraggio della diagnostica per i dispositivi. È anche possibile creare e assegnare profili di configurazione a un dispositivo o a gruppi di dispositivi.

Per gestire i dispositivi, ad esempio modificare la configurazione dei dispositivi, riavviare i dispositivi, gestire gli aggiornamenti o visualizzare l'integrità dei dispositivi e delle periferiche, è necessario avere uno dei ruoli di amministratore Microsoft 365 seguenti:

- Microsoft 365 Amministratore globale
- Teams Amministratore del servizio
- Teams Amministratore del dispositivo

Per altre informazioni sui ruoli di amministratore in Teams, vedere Usare i ruoli di Teams [di amministratore](../using-admin-roles.md)per gestire Teams .

## <a name="what-devices-can-you-manage"></a>Quali dispositivi è possibile gestire?

È possibile gestire qualsiasi dispositivo certificato e registrato in Teams. Un dispositivo viene registrato automaticamente la prima volta che un utente accede a Teams sul dispositivo. Per un elenco dei dispositivi certificati che è possibile gestire, vedere:

- [Barre di collaborazione](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=16)
- [Telefoni per conferenze](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=73)
- [Telefoni da tavolo](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=34)
- [Microsoft Teams Rooms](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=20)
- [Teams display](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=34)
- [Teams di lavoro](teams-panels.md)

Per gestire i dispositivi, nel riquadro di spostamento sinistro dell Microsoft Teams di [amministrazione](https://admin.teams.microsoft.com)passare a **Teams Dispositivi** e quindi selezionare il tipo di dispositivo. Ogni tipo di dispositivo ha una propria sezione, che consente di gestirli separatamente.

## <a name="manage-teams-rooms-devices"></a>Gestire Teams Rooms dispositivi

È possibile usare l'Teams di amministrazione per visualizzare e gestire in remoto i dispositivi Teams Rooms dell'organizzazione. L'interfaccia di amministrazione di Teams consente di vedere facilmente quali dispositivi sono integri e che necessitano di attenzione e consente di concentrarsi su dispositivi specifici per visualizzare informazioni dettagliate sull'integrità dei dispositivi, sulle prestazioni delle riunioni, sulla qualità delle chiamate e sulle periferiche. 

Ecco alcune operazioni che è possibile eseguire per gestire i dispositivi Teams Rooms mobili. Teams Rooms dispositivi sono disponibili [nell'interfaccia Microsoft Teams di amministrazione](https://admin.teams.microsoft.com) di Teams **dispositivi**  >  **Teams Rooms**.

Per informazioni dettagliate su come gestire i dispositivi Teams Rooms, vedere [Gestire Microsoft Teams Rooms](../rooms/rooms-manage.md).

| A questo scopo...                          | Eseguire questa operazione                                                                                                                                                                                                                                                                                                                                                                          |
|----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Modificare le impostazioni in uno o più dispositivi | Selezionare uno o più dispositivi > **Modifica impostazioni**. Se si selezionano più dispositivi, i valori che si modificano sostituiranno i valori in tutti i dispositivi selezionati.                                                                                                                                                                                                                       |
| Riavvia dispositivi                        | Selezionare uno o più dispositivi > **Riavvia**. Quando si riavvia un dispositivo, è possibile scegliere  se riavviarlo immediatamente o selezionare Pianifica riavvio per riavviare il dispositivo in una data e un'ora specifiche. La data e l'ora selezionate sono locali per il dispositivo da riavviare.                                                                                            |
| Visualizzare l'attività della riunione                  | Selezionare un nome di dispositivo per aprire i dettagli del dispositivo > **Attività.** Quando si apre la **scheda** Attività, è possibile visualizzare tutte le riunioni a cui ha partecipato il dispositivo. Questa visualizzazione di riepilogo mostra l'ora di inizio della riunione, il numero di partecipanti, la durata e la qualità complessiva della chiamata.                                                                                        |
| Visualizzare i dettagli della riunione                   | Selezionare un nome di dispositivo per aprire i dettagli del dispositivo > **attività >** selezionare una riunione. Quando apri i dettagli di una riunione, puoi vedere tutti i partecipanti alla riunione, la durata della chiamata, i tipi di sessione Teams e la qualità della chiamata individuale. Per visualizzare informazioni tecniche sulla chiamata di un partecipante, selezionare l'ora di inizio della chiamata del partecipante. |

## <a name="manage-phones-collaboration-bars-teams-displays-and-teams-panels"></a>Gestire telefoni, barre di collaborazione, Teams display e Teams pannelli 

Nell'Teams di amministrazione di Teams è possibile visualizzare e gestire telefoni, barre di collaborazione, schermi Teams e pannelli Teams registrati in Teams nell'organizzazione. Le informazioni visualizzate per ogni dispositivo includono il nome del dispositivo, il produttore, il modello, l'utente, lo stato, l'azione, l'ultima visualizzazione e la cronologia. È possibile personalizzare la visualizzazione in modo da visualizzare le informazioni che soddisfano le proprie esigenze.

Telefoni, barre di collaborazione, Teams display e Teams pannelli vengono registrati automaticamente in Microsoft Intune se ci si è iscritti. Dopo la registrazione di un dispositivo, la conformità del dispositivo viene confermata e i criteri di accesso condizionale vengono applicati al dispositivo.

Ecco alcuni esempi di come è possibile gestire telefoni, barre di collaborazione, Teams display e Teams pannelli nell'organizzazione.  

| A questo scopo...                           | Eseguire questa operazione                                                                                                                                                                                                                                                                                                      |
|-----------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Modificare le informazioni sul dispositivo               | Selezionare un dispositivo > **Modifica**. È possibile modificare i dettagli, ad esempio il nome del dispositivo, il tag della risorsa e aggiungere note.                                                                                                                                                                                                              |
| Gestire gli aggiornamenti software                 | Selezionare un dispositivo > **Aggiorna**. È possibile visualizzare l'elenco degli aggiornamenti del software e del firmware disponibili per il dispositivo e scegliere gli aggiornamenti da installare. Per altre informazioni sull'aggiornamento dei dispositivi, [vedere Aggiornare Teams dispositivi in remoto](remote-update.md)                                                          |
| Aggiornare Teams telefoni a Teams display  | Nella pagina **Telefoni IP** selezionare uno o più Teams telefoni > **Aggiorna**. Questa opzione è disponibile solo per i telefoni che supportano l'aggiornamento Teams display. Per altre informazioni, vedere [Aggiornare Teams telefoni a Teams schermi.](upgrade-phones-to-displays.md)                                                      |
| Assegnare o modificare i criteri di configurazione | Selezionare uno o più dispositivi > **Assegna configurazione**.                                                                                                                                                                                                                                                       |
| Aggiungere o rimuovere tag per i dispositivi               | Selezionare uno o più dispositivi > **Gestisci tag**. Per altre informazioni sui tag dei dispositivi, vedere [Gestire i tag Teams dispositivo](manage-device-tags.md).                                                                                                                                                                 |
| Riavvia dispositivi                         | Selezionare uno o più dispositivi > **Riavvia**.                                                                                                                                                                                                                                                                    |
| Filtrare i dispositivi usando i tag dei dispositivi        | Selezionare l'icona del filtro, selezionare il **campo Contrassegno,** specificare un tag di dispositivo in base a cui filtrare e selezionare **Applica**. Per altre informazioni sul filtro dei dispositivi con tag di dispositivo, vedere Usare i filtri per [restituire dispositivi con un tag specifico.](manage-device-tags.md#use-filters-to-return-devices-with-a-specific-tag) |
| Visualizzare la cronologia e la diagnostica dei dispositivi     | Nella colonna **Cronologia** fare clic sul **collegamento Visualizza** per un dispositivo per visualizzarne la cronologia degli aggiornamenti e i dettagli di diagnostica.                                                                                                                                                                                         |

### <a name="use-configuration-profiles-in-teams"></a>Usare i profili di configurazione in Teams

Usare i profili di configurazione per gestire le impostazioni e le funzionalità per i diversi dispositivi di Teams dell'organizzazione, tra cui barre di collaborazione, schermi Teams, Teams telefono e Teams pannelli. È possibile creare o caricare profili di configurazione per includere le impostazioni e le funzionalità da abilitare o disabilitare e quindi assegnare un profilo a un dispositivo o a un set di dispositivi. 

#### <a name="create-a-configuration-profile"></a>Creare un profilo di configurazione

Per creare un profilo di configurazione per un Teams tipo di dispositivo:

1. Nel riquadro di spostamento sinistro passare a Teams **dispositivi** > selezionare Teams tipo di dispositivo > **profili di configurazione**. Ad esempio, selezionare **Teams dispositivi Teams** profili di configurazione per creare un nuovo profilo di configurazione per Teams  >    >   pannelli.
2. Fare clic su **Aggiungi**.
3. Immettere un nome per il profilo e, facoltativamente, aggiungere una descrizione descrittiva.
4. Specificare le impostazioni desiderate per il profilo e quindi fare clic su **Salva.**
   Il profilo di configurazione appena creato viene visualizzato nell'elenco dei profili.

#### <a name="assign-a-configuration-profile"></a>Assegnare un profilo di configurazione
Dopo aver creato un profilo di configurazione per un tipo Teams dispositivo, assegnarlo a uno o più dispositivi.

1. Nel riquadro di spostamento sinistro passare a Teams **dispositivi** > selezionare il tipo Teams dispositivo. Ad esempio, per assegnare un profilo di configurazione a un dispositivo Teams, selezionare Teams **dispositivi** Teams  >  **pannelli.**
2. Selezionare uno o più dispositivi e quindi fare clic **su Assegna configurazione.**  
3. Nel riquadro **Assegna una configurazione** cercare il profilo di configurazione da assegnare ai dispositivi selezionati.
4. Fare clic **su Applica**.
   Per i dispositivi a cui sono  stati applicati i criteri  di configurazione, nella colonna Azione viene visualizzato l'aggiornamento della configurazione **e** nella colonna Profilo di configurazione viene visualizzato il nome del profilo di configurazione.
