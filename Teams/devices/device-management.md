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
description: Informazioni su come gestire i dispositivi usati con i team dell'organizzazione.
localization_priority: Normal
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: d6996b0980ae7305a7517a71645ba823a588e2f8
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/13/2020
ms.locfileid: "49033009"
---
# <a name="manage-your-devices-in-microsoft-teams"></a>Gestire i dispositivi in Microsoft Teams

È possibile gestire i dispositivi usati con Microsoft teams nell'organizzazione dall'interfaccia di amministrazione di Microsoft teams. È possibile visualizzare e gestire l'inventario dei dispositivi per l'organizzazione e svolgere attività come l'aggiornamento, il riavvio e il monitoraggio della diagnostica per i dispositivi. È anche possibile creare e assegnare profili di configurazione a un dispositivo o a un gruppo di dispositivi.

Per gestire i dispositivi, ad esempio la configurazione del dispositivo di modifica, riavviare i dispositivi, gestire gli aggiornamenti o visualizzare il dispositivo e l'integrità delle periferiche, è necessario assegnare uno dei ruoli di amministratore di Microsoft 365 seguenti:

- Amministratore globale di Microsoft 365
- Amministratore del servizio Teams
- Amministratore del dispositivo Teams

Per altre informazioni sui ruoli di amministratore in teams, vedere [usare i ruoli di amministratore dei team per gestire i team](../using-admin-roles.md).

## <a name="what-devices-can-you-manage"></a>Quali dispositivi è possibile gestire?

È possibile gestire tutti i dispositivi certificati e registrati in teams. Un dispositivo viene automaticamente registrato la prima volta che un utente accede a teams nel dispositivo. Per un elenco dei dispositivi certificati che è possibile gestire, vedere:

- [Microsoft Teams Rooms](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=20)
- [Telefoni per conferenze](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=73)
- [Telefoni da tavolo](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=34)
- [Mostra Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=34)
- [Barre di collaborazione](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=16)

Per gestire i dispositivi, nella barra di spostamento sinistra dell'interfaccia di [amministrazione di Microsoft teams](https://admin.teams.microsoft.com)passa a **dispositivi** e quindi seleziona il tipo di dispositivo. Ogni tipo di dispositivo ha una propria sezione, che consente di gestirli separatamente.

## <a name="manage-teams-rooms-devices"></a>Gestire i dispositivi di teams rooms

È possibile usare l'interfaccia di amministrazione di teams per visualizzare e gestire in remoto i dispositivi di teams rooms nell'organizzazione. L'interfaccia di amministrazione di teams semplifica la visualizzazione, a colpo d'occhio, dei dispositivi sani e che richiedono attenzione e consente di concentrarsi su dispositivi specifici per visualizzare informazioni dettagliate sull'integrità dei dispositivi, sulle prestazioni delle riunioni, sulla qualità delle chiamate e sulle periferiche. 

Ecco alcune operazioni che è possibile eseguire per gestire i dispositivi di teams rooms. I dispositivi teams Rooms si trovano nell'interfaccia di [amministrazione di Microsoft teams](https://admin.teams.microsoft.com) in **dispositivi**  >  **Teams Rooms**.

Per informazioni dettagliate su come gestire i dispositivi di teams rooms, vedere [gestire le sale di Microsoft teams](../rooms/rooms-manage.md).

| Per eseguire questa operazione... | Operazione da eseguire|
|---------------|--------|
| Modificare le impostazioni in uno o più dispositivi | Selezionare uno o più dispositivi > **Modifica impostazioni**. Se selezioni più dispositivi, i valori modificati sostituiranno i valori di tutti i dispositivi selezionati. |
| Riavviare i dispositivi | Selezionare uno o più dispositivi > **riavviare**. Quando si riavvia un dispositivo, è possibile scegliere se riavviare immediatamente il dispositivo o selezionare **Pianifica riavvio** per riavviare il dispositivo in base a una data e un'ora specifiche. La data e l'ora selezionate sono locali per il dispositivo da riavviare.|
| Visualizzare l'attività di riunione | Selezionare un nome di dispositivo per aprire i dettagli del dispositivo > **attività**. Quando si apre la scheda **attività** , è possibile visualizzare tutte le riunioni a cui ha partecipato il dispositivo. Questa visualizzazione riepilogo Mostra l'ora di inizio della riunione, il numero di partecipanti, la durata e la qualità complessiva delle chiamate.|
| Visualizzare i dettagli della riunione |  Selezionare un nome di dispositivo per aprire i dettagli del dispositivo > **attività** > selezionare una riunione. Quando si aprono i dettagli di una riunione, è possibile vedere tutti i partecipanti alla riunione, la durata della chiamata, i tipi di sessione di team e la qualità di chiamata individuale. Se si vogliono visualizzare informazioni tecniche sulla chiamata di un partecipante, selezionare l'ora di inizio della chiamata del partecipante.|

## <a name="manage-phones-collaboration-bars-and-teams-displays"></a>Gestire telefoni, barre di collaborazione e Team visualizzati 

Nell'interfaccia di amministrazione di teams è possibile visualizzare e gestire telefoni, barre di collaborazione e teams visualizzati registrati in teams dell'organizzazione. Le informazioni che verranno visualizzate per ogni dispositivo includono il nome del dispositivo, il produttore, il modello, l'utente, lo stato, l'azione, l'ultima volta e la cronologia. È possibile personalizzare la visualizzazione per visualizzare le informazioni adatte alle proprie esigenze.

I telefoni, le barre di collaborazione e le visualizzazioni team vengono automaticamente registrati in Microsoft Intune, se è stato effettuato l'accesso. Dopo che un dispositivo è stato registrato, la conformità del dispositivo viene confermata e i criteri di accesso condizionale vengono applicati al dispositivo.

Ecco alcuni esempi di come è possibile gestire telefoni, barre di collaborazione e teams visualizzati nell'organizzazione.  

|Per eseguire questa operazione...  |Operazione da eseguire |
|---------|---------|
| Modificare le informazioni sul dispositivo               | Selezionare un dispositivo > **modifica**. È possibile modificare i dettagli, ad esempio il nome del dispositivo, il tag asset e aggiungere note.     |
| Gestire gli aggiornamenti software                 | Selezionare un dispositivo > **aggiornamento**. È possibile visualizzare l'elenco degli aggiornamenti software e firmware disponibili per il dispositivo e scegliere gli aggiornamenti da installare. Per altre informazioni sull'aggiornamento dei dispositivi, vedere [aggiornare i dispositivi di teams in remoto](remote-update.md)   |
| Aggiornare i telefoni teams agli schermi Teams                | Nella pagina **telefoni IP** selezionare uno o più telefoni di Team > **aggiornamento**. Questa opzione è disponibile solo per i telefoni che supportano l'aggiornamento alle visualizzazioni teams. Per altre informazioni, vedere [aggiornare i telefoni teams agli schermi teams](upgrade-phones-to-displays.md).   |
| Assegnare o modificare i criteri di configurazione | Selezionare uno o più dispositivi > **assegnare la configurazione**.                                                                                                                                                                                                                   |
| Aggiungere o rimuovere tag per i dispositivi               | Selezionare uno o più dispositivi > **Gestisci contrassegni**. Per altre informazioni sui tag di dispositivo, vedere [gestire i tag del dispositivo teams](manage-device-tags.md).                                                                                                      |
| Riavviare i dispositivi                         | Selezionare uno o più dispositivi > **riavviare**.                                                                                                                                                                                                                                |
| Filtrare i dispositivi con i tag del dispositivo        | Selezionare l'icona del filtro, selezionare il campo **tag** , specificare un tag di dispositivo per filtrare e selezionare **applica**. Per altre informazioni su come filtrare i dispositivi usando i tag dei dispositivi, vedere [usare i filtri per restituire dispositivi con un tag specifico](manage-device-tags.md#use-filters-to-return-devices-with-a-specific-tag).|
| Visualizzare la cronologia dei dispositivi                     | Selezionare un dispositivo > **cronologia**. È possibile visualizzare la cronologia degli aggiornamenti per il dispositivo.                                                                                                                                                                                |
| Visualizzazione diagnostica                        | Selezionare un dispositivo > **diagnostica**.                                                                                                                                                                                                                            |
### <a name="use-configuration-profiles-in-teams"></a>Usare i profili di configurazione in teams

Usare i profili di configurazione per gestire le impostazioni e le funzionalità per i telefoni delle squadre e le barre di collaborazione nell'organizzazione. È possibile creare o caricare profili di configurazione per includere le impostazioni e le caratteristiche da abilitare o disabilitare e quindi assegnare un profilo a un dispositivo o a un gruppo di dispositivi. 

#### <a name="create-a-configuration-profile"></a>Creare un profilo di configurazione

1. Nella barra di spostamento sinistra passa a **Devices**  >  **profili di configurazione** dei dispositivi.
2. Fare clic su **Aggiungi**.
3. Immettere un nome per il profilo e, se si vuole, aggiungere una descrizione amichevole.
4. Specificare le impostazioni desiderate per il profilo e quindi fare clic su **Salva**.

#### <a name="assign-a-configuration-profile"></a>Assegnare un profilo di configurazione

1. Nella barra di spostamento sinistra passa a **Devices**  >  **profili di configurazione** dei dispositivi.
2. Selezionare il **profilo di configurazione** che si vuole assegnare e quindi fare clic su **assegna al dispositivo**.  
3. Nel riquadro **assegna dispositivi a un profilo di configurazione** cercare e selezionare i dispositivi che si desidera assegnare.
4. Fare clic su **Salva**.

