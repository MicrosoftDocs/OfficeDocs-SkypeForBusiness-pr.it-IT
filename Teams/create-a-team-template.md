---
title: Creare un modello di team personalizzato in Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: aaglick
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Informazioni su come creare un modello di team personalizzato in Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f22b2c53ab6f3c3c90e1720313c135c2106b1a49
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196530"
---
# <a name="create-a-custom-team-template-in-microsoft-teams"></a>Creare un modello di team personalizzato in Microsoft Teams

**I modelli personalizzati non sono ancora supportati per i clienti dell'EDU.**

Un modello di team personalizzato è una struttura del team predefinita con un set di canali, schede e app. È possibile sviluppare un modello che consente di creare rapidamente lo spazio di collaborazione giusto. Il modello di team personalizzato usa le impostazioni preferite.  

Per iniziare:

1. Accedere all'interfaccia di amministrazione di Teams.

2. Nel riquadro di spostamento sinistro espandere **i modelli team** di  >  **Teams.**

3. Fare clic su **Aggiungi**.

![Immagine della finestra di dialogo Modelli di Team con Aggiungi evidenziato.](media/team-templates-new.png)

4. Nella sezione **Modelli del** team selezionare Crea un **nuovo modello.**

5. Nella sezione **Impostazioni modello** completare i campi seguenti e quindi fare clic su **Avanti:**
    - Nome modello
    - Descrizioni brevi e lunghe del modello
    - Visibilità delle impostazioni locali  

![Immagine della finestra di dialogo di denominazione delle impostazioni dei modelli di team.](media/template-add-a-name.png)

6. Nella sezione **canali, schede e app,** aggiungi i canali e le app di cui ha bisogno il tuo team.

    1. Nella sezione **Canali** fare clic su **Aggiungi.**
    2. Nella finestra **di dialogo** Aggiungi assegnare un nome al canale.
    3. Aggiungere una descrizione.
    4. Decidere se il canale deve essere visualizzato per impostazione predefinita.
    5. Cercare il nome di un'app che si vuole aggiungere al canale.
    6. Al **termine,** fare clic su Applica.

![Immagine della schermata canali, schede e app dei modelli del team.](media/template-channels-tabs-apps.png)

8. Al **termine, fare** clic su Invia.

Il nuovo modello viene visualizzato nell'elenco **dei modelli del** team. Il modello può essere usato per creare un team in Teams.

> [!Note]
> La visualizzazione di un modello personalizzato nella raccolta può richiedere fino a 24 ore.

## <a name="known-issues"></a>Problemi noti 

**Problema:** se è stato creato un team da un modello personalizzato che conteneva altre schede personalizzate, al posto delle app scheda personalizzate potrebbero essere visualizzate schede vuote. Le schede predefinite (ad esempio **Post,** **File** e **Wiki)** verranno visualizzate come previsto.

**Soluzione:** se è stato creato un team da un modello personalizzato contenente altre schede personalizzate, è possibile che al posto delle app schede personalizzate venga visualizzata una scheda vuota. Le schede predefinite (ad esempio Post, File e Wiki) verranno visualizzate come previsto.

Per risolvere il problema, rimuovere la scheda personalizzata e aggiungere una nuova scheda con la stessa app. Se non si hanno le autorizzazioni necessarie per rimuovere la scheda personalizzata e aggiungere una nuova scheda, contattare il proprietario del team per chiedere di farlo.

Stiamo lavorando a una correzione per i futuri team creati da modelli personalizzati.

## <a name="related-topics"></a>Argomenti correlati

- [Introduzione ai modelli di team nell'interfaccia di amministrazione](get-started-with-teams-templates-in-the-admin-console.md)
- [Creare un modello da un team esistente](create-template-from-existing-team.md)
- [Creare un modello di team da un modello di team esistente](create-template-from-existing-template.md)
