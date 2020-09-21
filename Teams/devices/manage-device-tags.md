---
title: Gestire e filtrare i tag del dispositivo Microsoft Teams
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
description: Informazioni su come gestire e filtrare i tag nei dispositivi Microsoft teams.
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
# <a name="manage-microsoft-teams-device-tags"></a>Gestire i tag del dispositivo Microsoft Teams

I tag di dispositivo in Microsoft teams consentono di raggruppare, organizzare e gestire più facilmente i dispositivi distribuiti nell'organizzazione. Con l'interfaccia di amministrazione di Microsoft teams, è possibile aggiungere uno o più tag ai dispositivi, usare i filtri per visualizzare i dispositivi che corrispondono al tag specificato e quindi eseguire azioni sui dispositivi che dispongono di tale tag.

Puoi aggiungere un tag di dispositivo a più di un tipo di dispositivo. Tuttavia, quando si apre un riquadro dei dispositivi nell'interfaccia di amministrazione, vengono restituiti solo i dispositivi di quel tipo. Ad esempio, è possibile assegnare il tag "aziendale" sia ai dispositivi telefonici che alle sale di teams. Se si cerca il tag "aziendale" durante i telefoni dei **dispositivi**  >  **Phones**, vengono restituiti solo i telefoni. Allo stesso modo, se si cerca il tag "aziendale" in **dispositivi**  >  **Teams Rooms**, vengono restituiti solo i dispositivi sale teams.

Per gestire i tag del dispositivo, è necessario essere un amministratore globale, un amministratore del servizio Team o un amministratore del dispositivo teams. Per altre informazioni sui ruoli di amministratore, vedere [usare i ruoli di amministratore di Microsoft teams per gestire i team](../using-admin-roles.md).

> [!IMPORTANT]
> I tag di dispositivo vengono assegnati all'account della risorsa che ha eseguito l'accesso a un dispositivo. Se si firma un account di risorse fuori da un dispositivo e quindi lo si usa per accedere a altri dispositivi, i tag del dispositivo vengono applicati a un nuovo dispositivo.

## <a name="create-remove-or-rename-device-tags"></a>Creare, rimuovere o rinominare i tag del dispositivo

Usando il pannello di gestione dei tag per dispositivi è possibile:

- Vedere tutti i tag del dispositivo.
- Creare facilmente più tag di dispositivo e quindi assegnarli ai dispositivi in un secondo momento. I tag possono contenere fino a 25 caratteri.
- Rimuovere i tag di dispositivo non più necessari. Prima di poter rimuovere un tag di dispositivo, è necessario rimuoverlo da tutti i dispositivi a cui è stato aggiunto.
- Rinominare i tag del dispositivo. Quando si rinomina un tag di dispositivo, tale modifica viene applicata a tutti i dispositivi a cui è stato aggiunto. I tag possono contenere fino a 25 caratteri.

1. Accedere all'interfaccia di amministrazione di Microsoft teams visitando https://admin.teams.microsoft.com .
2. Passare a **dispositivi** e quindi scegliere un riquadro dispositivo, ad esempio **telefoni**.
3. Selezionare **azioni** nell'angolo in alto a destra della pagina e selezionare **tutti i tag per i dispositivi**.
4. Per creare un tag di dispositivo, selezionare **+ Aggiungi**, specificare un valore per il tag del dispositivo e selezionare l'icona **Salva** .
5. Per rimuovere un tag di dispositivo, selezionare i puntini di sospensione **...** accanto al tag del dispositivo che si vuole rimuovere e quindi selezionare **Elimina**.
    > [!NOTE]
    > Se si prova a rimuovere un tag di dispositivo aggiunto ai dispositivi, viene visualizzato un messaggio che chiede se si vuole rimuoverlo da tutti i dispositivi. Se si vuole eseguire questa operazione e continuare a rimuovere il tag del dispositivo, selezionare **dispositivi UNTAG**.
6. Per rinominare un tag di dispositivo, selezionare i puntini di sospensione **...** accanto al tag del dispositivo che si vuole rinominare e quindi selezionare **modifica**. Fornisci un nuovo valore per il tag del dispositivo e seleziona l'icona **Salva** .

## <a name="add-or-remove-tags-on-a-single-device"></a>Aggiungere o rimuovere tag in un singolo dispositivo

Quando si aggiungono tag a un dispositivo, è possibile selezionare un tag esistente o crearne uno nuovo. I tag possono contenere fino a 25 caratteri.

1. Accedere all'interfaccia di amministrazione di Microsoft teams visitando https://admin.teams.microsoft.com .
2. Passare a **dispositivi** e quindi scegliere il riquadro dispositivo che contiene il dispositivo in cui si vogliono aggiungere o rimuovere i tag.
3. Inserire un segno di spunta accanto al dispositivo a cui si vogliono aggiungere o rimuovere i tag e selezionare **Gestisci contrassegni**.
4. Se si vuole aggiungere un tag:
    1. Iniziare a digitare il nome del tag che si vuole aggiungere.
    2. Se il tag esiste già, selezionarlo nell'elenco dei tag restituiti.
    3. Se il tag non esiste, selezionare **Aggiungi " \<tag name> " come nuovo tag**. I tag possono contenere fino a 25 caratteri.
5. Se si vuole rimuovere un contrassegno, selezionare **X** accanto al contrassegno da rimuovere.
6. Ripetere i passaggi descritti sopra per aggiungere o rimuovere altri contrassegni.
7. Selezionare **applica**.

## <a name="add-or-remove-tags-on-multiple-devices"></a>Aggiungere o rimuovere tag in più dispositivi

Quando si aggiungono tag a un dispositivo, è possibile selezionare un tag esistente o crearne uno nuovo. I tag possono contenere fino a 25 caratteri. Se si vuole rimuovere un contrassegno da più dispositivi, è necessario selezionare l'utente del team associato al dispositivo e rimuovere il contrassegno dall'utente.

1. Accedere all'interfaccia di amministrazione di Microsoft teams visitando https://admin.teams.microsoft.com .
2. Passare a **dispositivi** e quindi scegliere il riquadro dispositivo che contiene i dispositivi a cui si vogliono aggiungere o rimuovere i tag.
3. Inserire un segno di spunta accanto ai dispositivi a cui si vogliono aggiungere o rimuovere i tag e selezionare **Gestisci contrassegni**.
4. Se si vuole aggiungere un tag:
    1. Iniziare a digitare il nome del tag che si vuole aggiungere in **Gestisci tag per tutti i dispositivi degli utenti di teams**.
    2. Se il tag esiste già, selezionarlo nell'elenco dei tag restituiti.
    3. Se il tag non esiste, selezionare **Aggiungi " \<tag name> " come nuovo tag**.
5. Se si vuole rimuovere un tag:
    1. Espandere **Seleziona utenti teams**.
    2. Espandi i ** \<x> tag** sotto il nome dell'utente di team da cui vuoi rimuovere i contrassegni.
    3. Selezionare **X** accanto al contrassegno che si vuole rimuovere.
6. Ripetere i passaggi descritti sopra per aggiungere o rimuovere altri contrassegni.
7. Selezionare **applica**.

## <a name="use-filters-to-return-devices-with-a-specific-tag"></a>Usare i filtri per restituire i dispositivi con un tag specifico

Se sono stati aggiunti tag di dispositivo ai dispositivi, è possibile usarli per filtrare l'elenco di dispositivi in cui vengono restituiti solo i dispositivi a cui è stato aggiunto un tag specificato. Può essere utile se si vogliono solo visualizzare tutti i dispositivi in una specifica sala, tutti i dispositivi di un determinato tipo o qualsiasi altro criterio usato per l'aggiunta dei tag. È anche possibile eseguire azioni in blocco sui dispositivi restituiti, ad esempio l'applicazione di aggiornamenti in onda o l'impostazione di criteri di configurazione diversi a seconda dei gruppi di dispositivi identificati usando i tag del dispositivo.

1. Accedere all'interfaccia di amministrazione di Microsoft teams visitando https://admin.teams.microsoft.com .
2. Passare a **dispositivi** e quindi scegliere il riquadro dispositivo che contiene i dispositivi che si desidera filtrare.
3. Selezionare l'icona del **filtro** .
4. Se si vuole specificare un singolo tag o se si vogliono trovare dispositivi con tutti i tag specificati, selezionare **Confronta tutte le condizioni**.
5. Se si vogliono trovare dispositivi che corrispondono a uno o più tag di dispositivo, selezionare **Confronta una di queste condizioni**.
6. Selezionare il campo **tag** e quindi specificare il nome di un tag di dispositivo nel campo **Immetti un valore** .
7. Per aggiungere altri tag di dispositivo, selezionare **Aggiungi altro** e ripetere il passaggio 6 per ogni tag che si vuole aggiungere.
8. Selezionare **applica**.

Dopo aver filtrato i dispositivi nell'elenco di dispositivi, è possibile eseguire azioni su di essi come si farebbe normalmente. Ad esempio, è possibile selezionarle e quindi assegnare le configurazioni, modificarne le impostazioni (se si tratta di dispositivi di teams rooms) e così via. Al termine, è possibile rimuovere il filtro selezionando la **X**  accanto alla voce del filtro **tag** o selezionando **Cancella tutto** sul lato destro dell'elenco.
