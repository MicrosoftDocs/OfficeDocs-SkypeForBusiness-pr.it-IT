---
title: Gestire e filtrare i tag dei dispositivi di Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: kelsawi
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Devices
f1.keywords:
- CSH
description: Informazioni su come gestire e filtrare i tag nei dispositivi Microsoft Teams.
ms.localizationpriority: medium
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1a372aacb7a8917dc169855fd671b1382d390f32
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2022
ms.locfileid: "67271351"
---
# <a name="manage-microsoft-teams-device-tags"></a>Gestire i tag dei dispositivi di Microsoft Teams

I tag dei dispositivi in Microsoft Teams consentono di raggruppare, organizzare e gestire più facilmente i dispositivi distribuiti nell'organizzazione. Con l'interfaccia di amministrazione di Microsoft Teams, è possibile aggiungere uno o più tag ai dispositivi, usare i filtri per visualizzare i dispositivi che corrispondono al tag specificato e quindi eseguire azioni sui dispositivi che hanno quel tag.

Puoi aggiungere un tag dispositivo a più tipi di dispositivo. Tuttavia, quando si apre un riquadro di dispositivi nell'interfaccia di amministrazione, vengono restituiti solo i dispositivi di quel tipo. Ad esempio, è possibile assegnare il tag "Aziendale" sia ai telefoni che ai dispositivi Teams Rooms. Se si cerca il tag "Aziendale" nei **telefoni** **dei dispositivi** >  di Teams, vengono restituiti solo i telefoni. Analogamente, se si cerca il tag "Aziendale" in **Dispositivi di** >  Teams **Teams Rooms**, vengono restituiti solo Teams Rooms dispositivi.

Per gestire i tag dei dispositivi, è necessario essere un amministratore globale, un amministratore del servizio teams o un amministratore di dispositivi di Teams. Per altre informazioni sui ruoli di amministratore, vedere [Usare i ruoli di amministratore di Microsoft Teams per gestire Teams](../using-admin-roles.md).

> [!IMPORTANT]
> I tag dispositivo vengono assegnati all'account della risorsa connesso a un dispositivo. Se si disconnette un account di risorse da un dispositivo e quindi lo si usa per accedere a un altro dispositivo, i tag del dispositivo vengono applicati al nuovo dispositivo.

## <a name="create-remove-or-rename-device-tags"></a>Creare, rimuovere o rinominare i tag del dispositivo

Utilizzando il pannello di gestione dei tag del dispositivo, è possibile:

- Visualizza tutti i tag del dispositivo.
- Crea più tag di dispositivo facilmente e assegnali ai dispositivi in un secondo momento. I tag possono avere un massimo di 25 caratteri.
- Rimuovi i tag del dispositivo che non sono più necessari. Prima di poter rimuovere un tag dispositivo, dovrai rimuoverlo da tutti i dispositivi a cui è stato aggiunto.
- Rinomina i tag del dispositivo. Quando si rinomina un tag dispositivo, la modifica viene riportata in tutti i dispositivi a cui è stato aggiunto. I tag possono avere un massimo di 25 caratteri.

1. Accedere all'interfaccia di amministrazione di Microsoft Teams visitando https://admin.teams.microsoft.com.
2. Passare a **Dispositivi di Teams** e quindi scegliere un riquadro dei dispositivi, ad esempio **Telefoni**.
3. Seleziona **Azioni** nell'angolo in alto a destra della pagina e seleziona **Tutti i tag dei dispositivi**.
4. Per creare un tag dispositivo, seleziona **+ Aggiungi**, specifica un valore per il tag dispositivo e seleziona l'icona **Salva** .
5. Per rimuovere un tag dispositivo, seleziona i puntini di sospensione **...** accanto al tag dispositivo che vuoi rimuovere e seleziona **Elimina**.
    > [!NOTE]
    > Se tenti di rimuovere un tag dispositivo che è stato aggiunto ai dispositivi, riceverai un messaggio in cui ti viene chiesto se vuoi rimuoverlo da tutti i dispositivi. Se vuoi eseguire questa operazione e continuare a rimuovere il tag del dispositivo, seleziona **Rimuovi tag dispositivi**.
6. Per rinominare un tag dispositivo, seleziona i puntini di sospensione **...** accanto al tag dispositivo che vuoi rinominare e seleziona **Modifica**. Fornisci un nuovo valore per il tag del dispositivo e seleziona l'icona **Salva** .

## <a name="add-or-remove-tags-on-a-single-device"></a>Aggiungere o rimuovere tag in un singolo dispositivo

Quando aggiungi tag a un dispositivo, puoi selezionare un tag esistente o crearne uno nuovo. I tag possono avere un massimo di 25 caratteri.

1. Accedere all'interfaccia di amministrazione di Microsoft Teams visitando https://admin.teams.microsoft.com.
2. Passare a **Dispositivi di Teams** e quindi scegliere il riquadro del dispositivo che contiene il dispositivo su cui si vogliono aggiungere o rimuovere tag.
3. Posiziona un segno di spunta accanto al dispositivo su cui vuoi aggiungere o rimuovere i tag e seleziona **Gestisci contrassegni**.
4. Se si vuole aggiungere un tag:
    1. Iniziare a digitare il nome del tag da aggiungere.
    2. Se il tag esiste già, selezionarlo nell'elenco di tag restituiti.
    3. Se il tag non esiste, seleziona **Aggiungi "\<tag name>" come nuovo tag**. I tag possono avere un massimo di 25 caratteri.
5. Se si vuole rimuovere un contrassegno, selezionare **X** accanto al contrassegno da rimuovere.
6. Ripetere i passaggi precedenti per aggiungere o rimuovere altri contrassegni.
7. Selezionare **Applica**.

## <a name="add-or-remove-tags-on-multiple-devices"></a>Aggiungere o rimuovere tag in più dispositivi

Quando aggiungi tag a un dispositivo, puoi selezionare un tag esistente o crearne uno nuovo. I tag possono avere un massimo di 25 caratteri. Se si vuole rimuovere un tag da più dispositivi, è necessario selezionare l'utente di Teams associato al dispositivo e rimuovere il tag dall'utente.

1. Accedere all'interfaccia di amministrazione di Microsoft Teams visitando https://admin.teams.microsoft.com.
2. Passare a **Dispositivi di Teams** e quindi scegliere il riquadro dei dispositivi che contiene i dispositivi in cui si vogliono aggiungere o rimuovere tag.
3. Posiziona un segno di spunta accanto ai dispositivi su cui vuoi aggiungere o rimuovere tag e seleziona **Gestisci contrassegni**.
4. Se si vuole aggiungere un tag:
    1. Iniziare a digitare il nome del tag da aggiungere in **Gestisci tag per tutti i dispositivi degli utenti di Teams**.
    2. Se il tag esiste già, selezionarlo nell'elenco di tag restituiti.
    3. Se il tag non esiste, seleziona **Aggiungi "\<tag name>" come nuovo tag**.
5. Se si vuole rimuovere un contrassegno:
    1. Espandere **Seleziona utenti di Teams**.
    2. Espandi **\<x> i tag** sotto il nome dell'utente di Teams da cui vuoi rimuovere i tag.
    3. Selezionare **X** accanto al contrassegno da rimuovere.
6. Ripetere i passaggi precedenti per aggiungere o rimuovere altri contrassegni.
7. Selezionare **Applica**.

## <a name="use-filters-to-return-devices-with-a-specific-tag"></a>Usare i filtri per restituire dispositivi con un tag specifico

Se hai aggiunto tag ai tuoi dispositivi, puoi usarli per filtrare l'elenco dei dispositivi e restituire solo i dispositivi a cui è stato aggiunto un tag specificato. Questo può essere utile se si vogliono visualizzare tutti i dispositivi in una stanza specifica, tutti i dispositivi di un determinato tipo o qualsiasi altro criterio usato per l'aggiunta dei tag. È anche possibile eseguire azioni in blocco sui dispositivi restituiti, ad esempio l'applicazione di aggiornamenti in onde o l'impostazione di criteri di configurazione diversi a seconda dei gruppi di dispositivi identificati tramite tag di dispositivo.

1. Accedere all'interfaccia di amministrazione di Microsoft Teams visitando https://admin.teams.microsoft.com.
2. Passare a **Dispositivi di Teams** e quindi scegliere il riquadro dei dispositivi che contiene i dispositivi da filtrare.
3. Selezionare l'icona **Filtro** .
4. Se vuoi specificare solo un singolo tag o se vuoi trovare dispositivi con tutti i tag specificati, seleziona **Confronta tutte queste condizioni**.
5. Se vuoi trovare dispositivi che corrispondono a uno o più tag di dispositivo, seleziona **Applica una di queste condizioni**.
6. Selezionare il campo **Tag** e quindi specificare il nome di un tag dispositivo nel campo **Immettere un valore** .
7. Se vuoi aggiungere altri tag del dispositivo, seleziona **Aggiungi altro** e ripeti il passaggio 6 per ogni tag che vuoi aggiungere.
8. Selezionare **Applica**.

Dopo aver filtrato i dispositivi nell'elenco dei dispositivi, puoi eseguire azioni su di essi come di consueto. Ad esempio, puoi selezionarle e assegnare configurazioni, modificarne le impostazioni (se sono Teams Rooms dispositivi) e così via. Al termine, è possibile rimuovere il filtro selezionando la **X**  accanto alla voce di filtro **Contrassegna** o selezionando **Cancella tutto** sul lato destro dell'elenco.
