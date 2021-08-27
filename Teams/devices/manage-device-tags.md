---
title: Gestire e filtrare i Microsoft Teams dispositivi
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
description: Informazioni su come gestire e filtrare i tag nei Microsoft Teams dispositivi.
ms.localizationpriority: medium
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: dec09762531b15e6889b2be77e7792d9313c606b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58596300"
---
# <a name="manage-microsoft-teams-device-tags"></a>Gestire i Microsoft Teams dei dispositivi

I tag dei dispositivi Microsoft Teams consentono di raggruppare, organizzare e gestire più facilmente i dispositivi distribuiti nell'organizzazione. Con l'interfaccia di amministrazione di Microsoft Teams, è possibile aggiungere uno o più tag ai dispositivi, usare i filtri per visualizzare i dispositivi che corrispondono al tag specificato e quindi eseguire azioni sui dispositivi che lo hanno.

È possibile aggiungere un tag di dispositivo a più tipi di dispositivo. Tuttavia, quando si apre un riquadro dei dispositivi nell'interfaccia di amministrazione, vengono restituiti solo i dispositivi di quel tipo. Ad esempio, è possibile assegnare il tag "Aziendale" sia ai telefoni che ai Teams Rooms dispositivi. Se si cerca il tag "Aziendale" in **Telefoni** dispositivi  >  , vengono restituiti solo i telefoni. Analogamente, se si cerca il tag "Aziendale" **in** Dispositivi Teams Rooms , vengono restituiti solo Teams Rooms  >  dispositivi.

Per gestire i tag dei dispositivi, è necessario essere un amministratore globale, un amministratore Teams Service o un amministratore Teams Dispositivo. Per altre informazioni sui ruoli di amministratore, vedere Usare [Microsoft Teams di amministratore per gestire Teams](../using-admin-roles.md).

> [!IMPORTANT]
> I tag del dispositivo vengono assegnati all'account della risorsa connesso a un dispositivo. Se si disconnette un account della risorsa da un dispositivo e quindi lo si usa per accedere a un altro dispositivo, i tag del dispositivo vengono applicati al nuovo dispositivo.

## <a name="create-remove-or-rename-device-tags"></a>Creare, rimuovere o rinominare tag di dispositivo

Usando il pannello di gestione dei tag del dispositivo, è possibile:

- Visualizza tutti i tag del dispositivo.
- Crea facilmente più tag dispositivo e quindi assegnali ai dispositivi in un secondo momento. I tag possono contenere fino a 25 caratteri.
- Rimuovere i tag del dispositivo che non sono più necessari. Prima di rimuovere un tag di dispositivo, è necessario rimuoverlo da tutti i dispositivi a cui è stato aggiunto.
- Rinominare i tag dei dispositivi. Quando si rinomina un tag di dispositivo, la modifica viene riflessa in tutti i dispositivi a cui è stato aggiunto. I tag possono contenere fino a 25 caratteri.

1. Accedere all'Microsoft Teams di amministrazione https://admin.teams.microsoft.com visitando .
2. Passare a **Dispositivi** e quindi scegliere un riquadro del dispositivo, ad esempio **Telefoni.**
3. Selezionare **Azioni** nell'angolo in alto a destra della pagina e selezionare **Tutti i tag dispositivo.**
4. Per creare un tag del dispositivo, selezionare **+ Aggiungi**, specificare un valore per il tag del dispositivo e selezionare **l'icona** Salva.
5. Per rimuovere un tag del dispositivo, selezionare i puntini di sospensione **...** accanto al tag del dispositivo da rimuovere e quindi **scegliere Elimina**.
    > [!NOTE]
    > Se provi a rimuovere un tag del dispositivo che è stato aggiunto ai dispositivi, riceverai un messaggio che chiede se vuoi rimuoverlo da tutti i dispositivi. Se si vuole eseguire questa operazione e continuare a rimuovere il tag del dispositivo, selezionare **Rimuovi contrassegno dispositivi.**
6. Per rinominare un tag di dispositivo, selezionare i puntini di sospensione **...** accanto al contrassegno del dispositivo da rinominare e selezionare **Modifica**. Specificare un nuovo valore per il tag del dispositivo e selezionare **l'icona** Salva.

## <a name="add-or-remove-tags-on-a-single-device"></a>Aggiungere o rimuovere tag in un singolo dispositivo

Quando si aggiungono tag a un dispositivo, è possibile selezionare un tag esistente o crearne uno nuovo. I tag possono contenere fino a 25 caratteri.

1. Accedere all'Microsoft Teams di amministrazione https://admin.teams.microsoft.com visitando .
2. Passare a **Dispositivi** e quindi scegliere il riquadro del dispositivo che contiene il dispositivo in cui si vogliono aggiungere o rimuovere tag.
3. Inserire un segno di spunta accanto al dispositivo in cui si vogliono aggiungere o rimuovere tag e selezionare **Gestisci tag.**
4. Se si vuole aggiungere un tag:
    1. Iniziare a digitare il nome del tag da aggiungere.
    2. Se il tag esiste già, selezionarlo nell'elenco dei tag restituiti.
    3. Se il tag non esiste, selezionare **Aggiungi " " come nuovo \<tag name> tag**. I tag possono contenere fino a 25 caratteri.
5. Se si vuole rimuovere un tag, selezionare **X** accanto al tag da rimuovere.
6. Ripetere i passaggi precedenti per aggiungere o rimuovere altri tag.
7. Selezionare **Applica**.

## <a name="add-or-remove-tags-on-multiple-devices"></a>Aggiungere o rimuovere tag in più dispositivi

Quando si aggiungono tag a un dispositivo, è possibile selezionare un tag esistente o crearne uno nuovo. I tag possono contenere fino a 25 caratteri. Se si vuole rimuovere un tag da più dispositivi, è necessario selezionare l'utente Teams associato al dispositivo e rimuovere il tag dall'utente.

1. Accedere all'Microsoft Teams di amministrazione https://admin.teams.microsoft.com visitando .
2. Passare a **Dispositivi** e quindi scegliere il riquadro dei dispositivi che contiene i dispositivi in cui si vogliono aggiungere o rimuovere tag.
3. Inserire un segno di spunta accanto ai dispositivi in cui si vogliono aggiungere o rimuovere tag e selezionare **Gestisci contrassegni.**
4. Se si vuole aggiungere un tag:
    1. Iniziare a digitare il nome del tag da aggiungere in Gestisci tag per tutti i **dispositivi Teams utenti**.
    2. Se il tag esiste già, selezionarlo nell'elenco dei tag restituiti.
    3. Se il tag non esiste, selezionare **Aggiungi " " come nuovo \<tag name> tag**.
5. Per rimuovere un tag:
    1. Espandere **Seleziona Teams utenti**.
    2. Espandere **\<x> i** tag sotto il nome dell Teams utente da cui si vogliono rimuovere i tag.
    3. Selezionare **X** accanto al contrassegno da rimuovere.
6. Ripetere i passaggi precedenti per aggiungere o rimuovere altri tag.
7. Selezionare **Applica**.

## <a name="use-filters-to-return-devices-with-a-specific-tag"></a>Usare i filtri per restituire i dispositivi con un tag specifico

Se sono stati aggiunti tag di dispositivo ai dispositivi, è possibile usarli per filtrare l'elenco dei dispositivi in modo da restituire solo i dispositivi a cui è stato aggiunto un tag specificato. Questa opzione può risultare utile se si vogliono solo visualizzare tutti i dispositivi in una chat room specifica, tutti i dispositivi di un determinato tipo o qualsiasi altro criterio usato per l'aggiunta di tag. È anche possibile eseguire azioni in blocco sui dispositivi restituiti, ad esempio l'applicazione di aggiornamenti in onde o l'impostazione di criteri di configurazione diversi a seconda dei gruppi di dispositivi identificati con i tag dei dispositivi.

1. Accedere all'Microsoft Teams di amministrazione https://admin.teams.microsoft.com visitando .
2. Passare a **Dispositivi** e quindi scegliere il riquadro dei dispositivi che contiene i dispositivi da filtrare.
3. Selezionare **l'icona** Filtro.
4. Se si vuole specificare un solo tag o se si vogliono trovare dispositivi che hanno tutti i tag specificati, selezionare Soddisfa **tutte queste condizioni.**
5. Se si vogliono trovare dispositivi che corrispondono a uno o più tag di dispositivo, selezionare **Corrisponde a una di queste condizioni.**
6. Selezionare il **campo Contrassegno** e quindi specificare un nome di tag dispositivo nel **campo Immettere un** valore.
7. Se si vogliono aggiungere altri tag per i dispositivi, selezionare **Aggiungi altro** e ripetere il passaggio 6 per ogni tag da aggiungere.
8. Selezionare **Applica**.

Dopo aver filtrato i dispositivi nell'elenco dei dispositivi, è possibile eseguire azioni su di essi come si farebbe normalmente. Ad esempio, è possibile selezionarli e quindi assegnare configurazioni, modificarne le impostazioni (se sono Teams Rooms dispositivi) e così via. Al termine, è possibile rimuovere il filtro selezionando la  **X** accanto alla  voce Filtro contrassegni o selezionando Cancella tutto sul lato destro dell'elenco.
