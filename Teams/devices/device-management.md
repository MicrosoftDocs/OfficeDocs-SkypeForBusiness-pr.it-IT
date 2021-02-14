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

È possibile gestire i dispositivi usati con Microsoft Teams nell'organizzazione dall'interfaccia di amministrazione di Microsoft Teams. È possibile visualizzare e gestire l'inventario dei dispositivi per l'organizzazione ed eseguire attività come aggiornare, riavviare e monitorare la diagnostica per i dispositivi. È anche possibile creare e assegnare profili di configurazione a uno o più dispositivi.

Per gestire i dispositivi, ad esempio modificare la configurazione dei dispositivi, riavviare i dispositivi, gestire gli aggiornamenti o visualizzare l'integrità di dispositivi e periferiche, è necessario disporre di uno dei ruoli di amministratore di Microsoft 365 seguenti:

- Amministratore globale di Microsoft 365
- Amministratore del servizio Teams
- Amministratore dei dispositivi di Teams

Per altre informazioni sui ruoli di amministratore in Teams, vedere Usare i ruoli di [amministratore di Teams per gestire Teams.](../using-admin-roles.md)

## <a name="what-devices-can-you-manage"></a>Quali dispositivi è possibile gestire?

È possibile gestire qualsiasi dispositivo certificato e registrato in Teams. Un dispositivo viene registrato automaticamente la prima volta che un utente accede a Teams sul dispositivo. Per un elenco di dispositivi certificati che è possibile gestire, vedere:

- [Microsoft Teams Rooms](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=20)
- [Telefoni da conferenza](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=73)
- [Telefoni da tavolo](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=34)
- [Display di Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=34)
- [Barre di collaborazione](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=16)

Per gestire i dispositivi, nella barra di spostamento sinistra dell'interfaccia di amministrazione di [Microsoft Teams,](https://admin.teams.microsoft.com)accedi a **Dispositivi,** quindi seleziona il tipo di dispositivo. Ogni tipo di dispositivo ha una propria sezione, che consente di gestirli separatamente.

## <a name="manage-teams-rooms-devices"></a>Gestire i dispositivi di Teams Room

È possibile usare l'interfaccia di amministrazione di Teams per visualizzare e gestire in remoto i dispositivi di Sale di Teams nell'intera organizzazione. L'interfaccia di amministrazione di Teams consente di vedere facilmente, a colpo d'occhio, quali dispositivi sono integri e che necessitano di attenzione e consente di concentrarsi su dispositivi specifici per visualizzare informazioni dettagliate sull'integrità del dispositivo, le prestazioni delle riunioni, la qualità delle chiamate e le periferiche. 

Ecco alcune operazioni che è possibile eseguire per gestire i dispositivi di Teams Rooms. I dispositivi di Teams Rooms sono disponibili nell'interfaccia [di amministrazione di Microsoft Teams](https://admin.teams.microsoft.com) in Sale di Teams per   >  **dispositivi.**

Per informazioni dettagliate su come gestire i dispositivi delle sale di Teams, vedere [Gestire le sale di Microsoft Teams.](../rooms/rooms-manage.md)

| Per... | Operazione da eseguire|
|---------------|--------|
| Modificare le impostazioni in uno o più dispositivi | Selezionare uno o più dispositivi con > **Modifica impostazioni.** Se si selezionano più dispositivi, i valori da modificare sostituiranno i valori in tutti i dispositivi selezionati. |
| Riavvia i dispositivi | Selezionare uno o più dispositivi > **riavvio.** Quando si riavvia un dispositivo, è possibile scegliere  se riavviarlo immediatamente o selezionare Pianifica riavvio per riavviare il dispositivo a una data e un'ora specifiche. La data e l'ora selezionate sono locali per il dispositivo da riavviare.|
| Visualizzare le attività delle riunioni | Seleziona un nome di dispositivo per aprire i dettagli del dispositivo > **attività.** Quando si apre la **scheda** Attività, è possibile visualizzare tutte le riunioni a cui ha partecipato il dispositivo. Questa visualizzazione di riepilogo mostra l'ora di inizio della riunione, il numero di partecipanti, la durata e la qualità complessiva della chiamata.|
| Visualizzare i dettagli della riunione |  Selezionare un nome di dispositivo per aprire i dettagli del dispositivo > **attività** > una riunione. Quando apri i dettagli di una riunione, puoi vedere tutti i partecipanti alla riunione, la durata della chiamata, i tipi di sessione di Teams e la qualità delle singole chiamate. Se desideri visualizzare informazioni tecniche sulla chiamata di un partecipante, seleziona l'ora di inizio della chiamata del partecipante.|

## <a name="manage-phones-collaboration-bars-and-teams-displays"></a>Gestire telefoni, barre di collaborazione e schermi di Teams 

Nell'interfaccia di amministrazione di Teams è possibile visualizzare e gestire telefoni, barre di collaborazione e schermi di Teams registrati in Teams nell'organizzazione. Le informazioni visualizzate per ogni dispositivo includono il nome, il produttore, il modello, l'utente, lo stato, l'azione, l'ultima visualizzazione e la cronologia. È possibile personalizzare la visualizzazione per mostrare le informazioni più adatti alle proprie esigenze.

I telefoni, le barre di collaborazione e i display di Teams vengono registrati automaticamente in Microsoft Intune se ci si è iscritti. Dopo la registrazione di un dispositivo, la conformità del dispositivo viene confermata e i criteri di accesso condizionale vengono applicati al dispositivo.

Ecco alcuni esempi di come è possibile gestire i telefoni, le barre di collaborazione e i display di Teams nell'organizzazione.  

|Per...  |Operazione da eseguire |
|---------|---------|
| Modificare le informazioni sul dispositivo               | Selezionare un dispositivo > **Modifica.** È possibile modificare dettagli come il nome del dispositivo, un tag di risorsa e aggiungere note.     |
| Gestire gli aggiornamenti software                 | Selezionare un dispositivo > **Aggiorna.** Puoi visualizzare l'elenco degli aggiornamenti software e firmware disponibili per il dispositivo e scegliere gli aggiornamenti da installare. Per altre informazioni sull'aggiornamento dei dispositivi, vedere [Aggiornare i dispositivi di Teams in remoto](remote-update.md)   |
| Aggiornare i telefoni di Teams ai display di Teams                | Nella pagina **Telefoni IP** selezionare uno o più telefoni di Teams > **Aggiorna.** Questa opzione è disponibile solo per i telefoni che supportano l'aggiornamento ai display di Teams. Per altre informazioni, vedere [Aggiornare i telefoni di Teams ai display di Teams.](upgrade-phones-to-displays.md)   |
| Assegnare o modificare i criteri di configurazione | Selezionare uno o più dispositivi e > **la configurazione.**                                                                                                                                                                                                                   |
| Aggiungere o rimuovere tag per i dispositivi               | Selezionare uno o più dispositivi > **i tag.** Per altre informazioni sui tag per i dispositivi, vedere [Gestire i tag per i dispositivi di Teams.](manage-device-tags.md)                                                                                                      |
| Riavvia i dispositivi                         | Selezionare uno o più dispositivi > **riavvio.**                                                                                                                                                                                                                                |
| Filtrare i dispositivi usando i tag di dispositivo        | Selezionare l'icona del filtro, selezionare il **campo Tag,** specificare un tag di dispositivo in base a cui filtrare e selezionare **Applica.** Per altre informazioni su come filtrare i dispositivi usando i tag di dispositivo, vedere Usare i filtri [per restituire i dispositivi con un tag specifico.](manage-device-tags.md#use-filters-to-return-devices-with-a-specific-tag)|
| Visualizza cronologia dispositivi                     | Seleziona un dispositivo > **cronologia.** Puoi visualizzare la cronologia degli aggiornamenti per il dispositivo.                                                                                                                                                                                |
| Visualizzare la diagnostica                        | Selezionare un dispositivo > **diagnostica.**                                                                                                                                                                                                                            |
### <a name="use-configuration-profiles-in-teams"></a>Usare i profili di configurazione in Teams

Usare i profili di configurazione per gestire le impostazioni e le funzionalità per i telefoni di Teams e le barre di collaborazione nell'organizzazione. È possibile creare o caricare profili di configurazione per includere le impostazioni e le funzionalità da abilitare o disabilitare e quindi assegnare un profilo a uno o più dispositivi. 

#### <a name="create-a-configuration-profile"></a>Creare un profilo di configurazione

1. Nel riquadro di spostamento sinistro passare a **Profili di**  >  **configurazione dispositivi.**
2. Fare clic su **Aggiungi**.
3. Immettere un nome per il profilo e, se si vuole, aggiungere una descrizione descrittiva.
4. Specificare le impostazioni desiderate per il profilo e quindi fare clic su **Salva.**

#### <a name="assign-a-configuration-profile"></a>Assegnare un profilo di configurazione

1. Nel riquadro di spostamento sinistro passare a **Profili di**  >  **configurazione dispositivi.**
2. Selezionare il **profilo di configurazione** da assegnare e quindi fare clic su Assegna al **dispositivo.**  
3. Nel riquadro **Assegna dispositivi a un profilo di** configurazione, cerca e seleziona i dispositivi che vuoi assegnare.
4. Fare clic su **Salva**.

