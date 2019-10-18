---
title: Gestire i dispositivi in Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 11/12/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: kelsawi
ms.collection:
- M365-collaboration
f1keywords:
- ms.teamsadmincenter.managedevices.overview
- ms.teamsadmincenter.devicemanagement.overview
description: Informazioni su come gestire i dispositivi usati con i team dell'organizzazione.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: d1473acc92113cc8788ae5cc27eecc11ad909124
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2019
ms.locfileid: "37571792"
---
# <a name="manage-your-devices-in-microsoft-teams"></a>Gestire i dispositivi in Microsoft Teams

::: zone target="docs"
Come amministratore, puoi gestire tutti i dispositivi usati con i team dell'organizzazione dall'interfaccia di amministrazione di Microsoft teams. È possibile visualizzare e gestire l'inventario dei dispositivi per l'organizzazione e svolgere attività come l'aggiornamento, il riavvio e il monitoraggio della diagnostica per i dispositivi. È anche possibile creare e assegnare profili di configurazione a un dispositivo o a un gruppo di dispositivi. 

## <a name="what-devices-can-you-manage"></a>Quali dispositivi è possibile gestire?
I dispositivi devono essere certificati per i team e registrati in teams. Un dispositivo viene automaticamente registrato la prima volta che un utente accede a teams nel dispositivo. Per un elenco dei dispositivi certificati che è possibile gestire, vedere [telefoni per conferenze](https://products.office.com/en-us/microsoft-teams/across-devices/devices/category?devicetype=16) e [telefoni da tavolo](https://products.office.com/en-us/microsoft-teams/across-devices/devices/category?devicetype=34).

> [!NOTE]
> Se si dispone di Microsoft Intune, i dispositivi vengono registrati automaticamente in Intune. Dopo che un dispositivo è stato registrato, la conformità del dispositivo viene confermata e i criteri di accesso condizionale vengono applicati al dispositivo. 

## <a name="manage-devices-in-teams"></a>Gestire i dispositivi in teams

![Icona che mostra il logo](media/teams-logo-30x30.png) di Microsoft teams **con l'interfaccia di amministrazione di Microsoft teams**

1. Nella barra di spostamento sinistra passa a **dispositivi** > per la**gestione dei dispositivi**.
2. Selezionare **tutti i dispositivi**.  

::: zone-end

 Da qui è possibile visualizzare e gestire tutti i dispositivi registrati in teams dell'organizzazione. Le informazioni che verranno visualizzate per ogni dispositivo includono il nome del dispositivo, il produttore, il modello, l'utente, lo stato, l'azione, l'ultima volta e la cronologia. È possibile personalizzare la visualizzazione per visualizzare le informazioni adatte alle proprie esigenze.

 Ecco alcuni esempi di come è possibile gestire i dispositivi teams nell'organizzazione.  
    
|Per eseguire questa operazione...  |Operazione da eseguire |
|---------|---------|
|Modificare le informazioni sul dispositivo   | Selezionare un dispositivo > **modifica**. È possibile modificare i dettagli, ad esempio nome dispositivo, informazioni utente, tag asset e Aggiungi note.     |
|Gestire gli aggiornamenti software   |Selezionare un dispositivo > **aggiornamento**. È possibile visualizzare l'elenco degli aggiornamenti software e firmware disponibili per il dispositivo e scegliere gli aggiornamenti da installare.    |
|Riavviare un dispositivo   |Selezionare un dispositivo > **riavviare**.          |
|Visualizzare la cronologia dei dispositivi  | Selezionare un dispositivo > **cronologia**. È possibile visualizzare la cronologia degli aggiornamenti per il dispositivo.     |
|Visualizzazione diagnostica  | Selezionare un dispositivo > **diagnostica**.        |

## <a name="use-configuration-profiles-in-teams"></a>Usare i profili di configurazione in teams

Usare i profili di configurazione per gestire le impostazioni e le funzionalità per i dispositivi teams nell'organizzazione. È possibile creare o caricare profili di configurazione per includere le impostazioni e le caratteristiche da abilitare o disabilitare e quindi assegnare un profilo a un dispositivo o a un gruppo di dispositivi. 

### <a name="create-a-configuration-profile"></a>Creare un profilo di configurazione

::: zone target="docs"

![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) Uso dell'interfaccia di amministrazione di Microsoft teams & Skype for business

1. Nella barra di spostamento sinistra passa a **dispositivi** > per la**gestione dei dispositivi**.

::: zone-end

2. Selezionare **profili di configurazione**e quindi selezionare **nuovo profilo di configurazione**.
3. Immettere un nome per il profilo e, se si vuole, aggiungere una descrizione amichevole.
4. Specificare le impostazioni desiderate per il profilo e quindi fare clic su **Salva**.

### <a name="assign-a-configuration-profile"></a>Assegnare un profilo di configurazione

::: zone target="docs"

![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) Uso dell'interfaccia di amministrazione di Microsoft teams & Skype for business

1. Nella barra di spostamento sinistra passa a **dispositivi** > per la**gestione dei dispositivi**.

::: zone-end

2. Selezionare **profilo di configurazione**e quindi in **assegnata al** profilo che si vuole assegnare fare clic sul collegamento.  
3. Nel riquadro **assegna dispositivi a un profilo di configurazione** cercare e selezionare i dispositivi che si desidera assegnare.
4. Fai clic su **Salva**.
