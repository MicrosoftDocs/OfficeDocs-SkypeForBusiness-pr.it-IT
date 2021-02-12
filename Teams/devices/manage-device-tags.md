---
title: Gestire e filtrare i tag per i dispositivi di Microsoft Teams
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
description: Informazioni su come gestire e filtrare i tag nei dispositivi Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: d29bc28de39c8d145914d3bddab4ed949ad0a338
ms.sourcegitcommit: b255db7ef816d1884c9c71af86a901bd83a1d9ab
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962897"
---
# <a name="manage-microsoft-teams-device-tags"></a>Gestire i tag per i dispositivi di Microsoft Teams

I tag dei dispositivi in Microsoft Teams consentono di raggruppare, organizzare e gestire più facilmente i dispositivi distribuiti nell'organizzazione. Con l'interfaccia di amministrazione di Microsoft Teams, è possibile aggiungere uno o più tag ai dispositivi, usare i filtri per visualizzare i dispositivi che corrispondono al tag specificato e quindi eseguire le azioni sui dispositivi che hanno quel tag.

È possibile aggiungere un tag dispositivo a più di un tipo di dispositivo. Tuttavia, quando si apre un riquadro dei dispositivi nell'interfaccia di amministrazione, vengono restituiti solo i dispositivi di questo tipo. Ad esempio, è possibile assegnare il tag "Aziendale" sia ai telefoni che ai dispositivi di Teams Room. Se si cerca il contrassegno "Aziendale" mentre si utilizza **Dispositivi**  >  **telefoni,** vengono restituiti solo i telefoni. Allo stesso modo, se si cerca il tag "Aziendale" **nelle** sale di Teams per dispositivi, vengono restituiti solo i dispositivi di Sale di  >  Teams.

Per gestire i tag per i dispositivi, è necessario essere un amministratore globale, un amministratore dei servizi di Teams o un amministratore di dispositivi di Teams. Per altre informazioni sui ruoli di amministratore, vedere Usare i ruoli di amministratore [di Microsoft Teams per gestire Teams.](../using-admin-roles.md)

> [!IMPORTANT]
> I tag dispositivo vengono assegnati all'account delle risorse connesso a un dispositivo. Se si disconnette un account di risorsa da un dispositivo e quindi lo si usa per accedere a un altro dispositivo, i tag dispositivo vengono applicati al nuovo dispositivo.

## <a name="create-remove-or-rename-device-tags"></a>Creare, rimuovere o rinominare tag per i dispositivi

Nel pannello di gestione dei tag di dispositivo è possibile:

- Vedi tutti i tag per i dispositivi.
- Creare più tag di dispositivo con facilità e quindi assegnarli ai dispositivi in un secondo momento. I tag possono essere fino a 25 caratteri.
- Rimuovere i tag per i dispositivi non più necessari. Prima di poter rimuovere un tag per il dispositivo, è necessario rimuoverlo da tutti i dispositivi a cui è stato aggiunto.
- Rinominare i tag per i dispositivi. Quando si rinomina un tag per il dispositivo, la modifica viene riflessa in tutti i dispositivi a cui è stata aggiunta. I tag possono essere fino a 25 caratteri.

1. Accedi all'interfaccia di amministrazione di Microsoft Teams visitando https://admin.teams.microsoft.com .
2. Passare a **Dispositivi e** quindi scegliere un riquadro di dispositivi, ad esempio **Telefoni.**
3. Selezionare **Azioni** nell'angolo in alto a destra della pagina e selezionare **Tutti i tag di dispositivo.**
4. Per creare un tag per il dispositivo, seleziona **+ Aggiungi,** fornisci un valore per il tag del dispositivo e seleziona l'icona Salva. 
5. Per rimuovere un tag del dispositivo, seleziona i puntini di **sospensione...** accanto al tag del dispositivo che vuoi rimuovere, quindi **scegli Elimina.**
    > [!NOTE]
    > Se si prova a rimuovere un contrassegno per il dispositivo aggiunto ai dispositivi, si riceverà un messaggio che chiede se si vuole rimuoverlo da tutti i dispositivi. Se vuoi eseguire questa operazione e continuare a rimuovere il tag del dispositivo, seleziona **Rimuovi contrassegno per i dispositivi.**
6. Per rinominare un tag del dispositivo, seleziona i puntini di **sospensione...** accanto al tag del dispositivo che vuoi rinominare, quindi **seleziona Modifica.** Fornisci un nuovo valore per il tag del dispositivo e seleziona **l'icona** Salva.

## <a name="add-or-remove-tags-on-a-single-device"></a>Aggiungere o rimuovere tag in un singolo dispositivo

Quando si aggiungono contrassegni a un dispositivo, è possibile selezionare un contrassegno esistente o crearne uno nuovo. I tag possono essere fino a 25 caratteri.

1. Accedi all'interfaccia di amministrazione di Microsoft Teams visitando https://admin.teams.microsoft.com .
2. Passare a **Dispositivi** e quindi scegliere il riquadro del dispositivo che contiene il dispositivo in cui aggiungere o rimuovere i tag.
3. Inserire un segno di spunta accanto al dispositivo in cui si vogliono aggiungere o rimuovere contrassegni e **selezionare Gestisci contrassegni.**
4. Se si vuole aggiungere un contrassegno:
    1. Iniziare a digitare il nome del tag da aggiungere.
    2. Se il contrassegno esiste già, selezionarlo nell'elenco di contrassegni restituiti.
    3. Se il tag non esiste, selezionare **Aggiungi " " come nuovo \<tag name> tag.** I tag possono essere fino a 25 caratteri.
5. Per rimuovere un contrassegno, selezionare **la X** accanto al contrassegno da rimuovere.
6. Ripetere i passaggi precedenti per aggiungere o rimuovere altri contrassegni.
7. Selezionare **Applica.**

## <a name="add-or-remove-tags-on-multiple-devices"></a>Aggiungere o rimuovere tag in più dispositivi

Quando si aggiungono contrassegni a un dispositivo, è possibile selezionare un contrassegno esistente o crearne uno nuovo. I tag possono essere fino a 25 caratteri. Se si vuole rimuovere un tag da più dispositivi, è necessario selezionare l'utente di Teams associato al dispositivo e rimuovere il tag dall'utente.

1. Accedi all'interfaccia di amministrazione di Microsoft Teams visitando https://admin.teams.microsoft.com .
2. Passare a **Dispositivi** e quindi scegliere il riquadro dei dispositivi che contiene i dispositivi in cui aggiungere o rimuovere i tag.
3. Inserire un segno di spunta accanto ai dispositivi in cui si vogliono aggiungere o rimuovere contrassegni e selezionare **Gestisci contrassegni.**
4. Se si vuole aggiungere un contrassegno:
    1. Iniziare a digitare il nome del tag da aggiungere in **Gestisci tag per tutti i dispositivi degli utenti di Teams.**
    2. Se il contrassegno esiste già, selezionarlo nell'elenco di contrassegni restituiti.
    3. Se il tag non esiste, selezionare **Aggiungi " " come nuovo \<tag name> tag.**
5. Per rimuovere un contrassegno:
    1. Espandere **Seleziona utenti di Teams.**
    2. Espandere **\<x> i** tag sotto il nome dell'utente di Teams da cui rimuovere i tag.
    3. Selezionare **la X** accanto al contrassegno da rimuovere.
6. Ripetere i passaggi precedenti per aggiungere o rimuovere altri contrassegni.
7. Selezionare **Applica.**

## <a name="use-filters-to-return-devices-with-a-specific-tag"></a>Usare i filtri per restituire i dispositivi con un tag specifico

Se sono stati aggiunti tag per i dispositivi, è possibile usarli per filtrare l'elenco di dispositivi in modo da restituire solo i dispositivi per cui è stato aggiunto un tag specificato. Ciò può risultare utile se si vogliono solo visualizzare tutti i dispositivi di una sala specifica, tutti i dispositivi di un determinato tipo o qualsiasi altro criterio usato per aggiungere i contrassegni. È anche possibile eseguire azioni in blocco sui dispositivi restituiti, ad esempio applicare aggiornamenti per onde o impostare criteri di configurazione diversi a seconda dei gruppi di dispositivi identificati con tag di dispositivo.

1. Accedi all'interfaccia di amministrazione di Microsoft Teams visitando https://admin.teams.microsoft.com .
2. Passare a **Dispositivi** e quindi scegliere il riquadro dei dispositivi che contiene i dispositivi da filtrare.
3. Selezionare **l'icona del** filtro.
4. Se si vuole specificare un solo tag o se si vogliono trovare dispositivi che hanno tutti i tag specificati, selezionare **Soddisfano tutte le condizioni.**
5. Se si vogliono trovare dispositivi che corrispondono a uno o più tag di dispositivo, selezionare **Soddisfa una di queste condizioni.**
6. Selezionare il **campo Tag** e quindi specificare un nome di tag di dispositivo nel campo **Immettere un** valore.
7. Se si vogliono aggiungere altri tag per i dispositivi, selezionare **Aggiungi altri** contrassegni e ripetere il passaggio 6 per ogni contrassegno da aggiungere.
8. Selezionare **Applica.**

Dopo aver filtrato i dispositivi nell'elenco di dispositivi, è possibile eseguire azioni su di essi come di consueto. Ad esempio, è possibile selezionarle e quindi assegnare configurazioni, modificarne le impostazioni (se si tratta di dispositivi Teams Room) e così via. Al termine, è possibile rimuovere il filtro selezionando la  **X** accanto alla  voce Filtro contrassegni o selezionando Cancella tutto sul lato destro dell'elenco.
