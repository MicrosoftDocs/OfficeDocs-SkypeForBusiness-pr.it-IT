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
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.managedevices.overview
- ms.teamsadmincenter.devicemanagement.overview
description: Informazioni su come gestire i dispositivi usati con i team dell'organizzazione.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: ef6412ff40d71a21f619b08ee5e334819d5470ca
ms.sourcegitcommit: a597b1572f1eca095144288446a2c038e5daa5f7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/10/2020
ms.locfileid: "42587292"
---
# <a name="manage-your-devices-in-microsoft-teams"></a>Gestire i dispositivi in Microsoft Teams

Come amministratore, puoi gestire i dispositivi usati con i team dell'organizzazione dall'interfaccia di amministrazione di Microsoft teams. È possibile visualizzare e gestire l'inventario dei dispositivi per l'organizzazione e svolgere attività come l'aggiornamento, il riavvio e il monitoraggio della diagnostica per i dispositivi. È anche possibile creare e assegnare profili di configurazione a un dispositivo o a un gruppo di dispositivi. 

## <a name="what-devices-can-you-manage"></a>Quali dispositivi è possibile gestire?
È possibile gestire tutti i dispositivi certificati e registrati in teams. Un dispositivo viene automaticamente registrato la prima volta che un utente accede a teams nel dispositivo. Per un elenco dei dispositivi certificati che è possibile gestire, vedere:

- [Telefoni per conferenze](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=16)
- [Telefoni da tavolo](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=34)
- Barre di collaborazione

I dispositivi vengono gestiti nell'interfaccia di [amministrazione di Microsoft teams](https://admin.teams.microsoft.com) in **dispositivi** nella barra di spostamento sinistra.

> [!NOTE]
> Se si dispone di Microsoft Intune, i dispositivi vengono registrati automaticamente in Intune. Dopo che un dispositivo è stato registrato, la conformità del dispositivo viene confermata e i criteri di accesso condizionale vengono applicati al dispositivo.

## <a name="manage-phones-and-collaboration-bars-in-teams"></a>Gestire i telefoni e le barre di collaborazione in teams

Anche se i telefoni e le barre di collaborazione sono gestiti nello stesso modo nell'interfaccia di amministrazione di Microsoft teams, hanno le rispettive sezioni nella barra di spostamento sinistra in **dispositivi**. In questo modo è possibile gestire separatamente ogni tipo di dispositivo.

Da qui è possibile visualizzare e gestire i telefoni e le barre di collaborazione iscritti ai team dell'organizzazione. Le informazioni che verranno visualizzate per ogni dispositivo includono il nome del dispositivo, il produttore, il modello, l'utente, lo stato, l'azione, l'ultima volta e la cronologia. È possibile personalizzare la visualizzazione per visualizzare le informazioni adatte alle proprie esigenze.

Ecco alcuni esempi di come è possibile gestire i dispositivi teams nell'organizzazione.  
    
|Per eseguire questa operazione...  |Operazione da eseguire |
|---------|---------|
|Modificare le informazioni sul dispositivo   | Selezionare un dispositivo > **modifica**. È possibile modificare i dettagli, ad esempio il nome del dispositivo, il tag asset e aggiungere note.     |
|Gestire gli aggiornamenti software   |Selezionare un dispositivo > **aggiornamento**. È possibile visualizzare l'elenco degli aggiornamenti software e firmware disponibili per il dispositivo e scegliere gli aggiornamenti da installare.    |
|Riavviare un dispositivo   |Selezionare un dispositivo > **riavviare**.          |
|Visualizzare la cronologia dei dispositivi  | Selezionare un dispositivo > **cronologia**. È possibile visualizzare la cronologia degli aggiornamenti per il dispositivo.     |
|Visualizzazione diagnostica  | Selezionare un dispositivo > **diagnostica**.        |

## <a name="use-configuration-profiles-in-teams"></a>Usare i profili di configurazione in teams

Usare i profili di configurazione per gestire le impostazioni e le funzionalità per i dispositivi teams nell'organizzazione. È possibile creare o caricare profili di configurazione per includere le impostazioni e le caratteristiche da abilitare o disabilitare e quindi assegnare un profilo a un dispositivo o a un gruppo di dispositivi. 

### <a name="create-a-configuration-profile"></a>Creare un profilo di configurazione

1. Nella barra di spostamento sinistra passa a **** > **profili di configurazione**dei dispositivi.
2. Fare clic su **Aggiungi**.
3. Immettere un nome per il profilo e, se si vuole, aggiungere una descrizione amichevole.
4. Specificare le impostazioni desiderate per il profilo e quindi fare clic su **Salva**.

### <a name="assign-a-configuration-profile"></a>Assegnare un profilo di configurazione

1. Nella barra di spostamento sinistra passa a **** > **profili di configurazione**dei dispositivi.
2. Selezionare il **profilo di configurazione** che si vuole assegnare e quindi fare clic su **assegna al dispositivo**.  
3. Nel riquadro **assegna dispositivi a un profilo di configurazione** cercare e selezionare i dispositivi che si desidera assegnare.
4. Fai clic su **Salva**.
