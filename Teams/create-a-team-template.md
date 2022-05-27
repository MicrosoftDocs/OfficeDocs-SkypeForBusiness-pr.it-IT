---
title: Creare un modello di team personalizzato in Microsoft Teams
author: LanaChin
ms.author: v-lanachin
manager: samanro
ms.reviewer: aaglick
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Informazioni su come creare un modello di team personalizzato in Microsoft Teams.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6b313df288488de22e99943120ffd0fd94d34210
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675568"
---
# <a name="create-a-custom-team-template-in-microsoft-teams"></a>Creare un modello di team personalizzato in Microsoft Teams

**I modelli personalizzati non sono ancora supportati per i clienti EDU.**

Un modello di team personalizzato è una struttura di team predefinita con un set di canali, schede e app. È possibile sviluppare un modello che consente di creare rapidamente lo spazio di collaborazione giusto. Il modello di team personalizzato usa le impostazioni preferite.  

<br>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4P5rx]


Per iniziare:

1. Passare all'interfaccia di amministrazione di Teams.

2. Nel riquadro di spostamento sinistro espandere **Teams** >  **Modelli diTeam**.

3. Selezionare **Aggiungi**.

    ![Immagine della finestra di dialogo Modelli di team con Aggiungi evidenziato.](media/team-templates-new.png)

4. Nella sezione **Modelli di team** selezionare **Crea un nuovo modello**.

5. Nella sezione **Impostazioni modello** completare i campi seguenti e quindi selezionare **Avanti**:
    - Nome modello
    - Descrizioni brevi e lunghe del modello
    - Visibilità delle impostazioni locali  

    ![Immagine della finestra di dialogo di denominazione delle impostazioni dei modelli di team.](media/template-add-a-name.png)

6. Nella sezione **Canali, schede e app** aggiungi tutti i canali e le app di cui il team ha bisogno.

    1. Nella sezione **Canali** selezionare **Aggiungi**.
    2. Nella finestra di dialogo **Aggiungi** assegnare un nome al canale.
    3. Aggiungere una descrizione.
    4. Decidere se il canale deve essere visualizzato per impostazione predefinita.
    5. Cercare il nome di un'app da aggiungere al canale.
    6. Al termine, selezionare **Applica** .

    ![Immagine della schermata Dei modelli di team per canali, schede e app.](media/template-channels-tabs-apps.png)

8. Al termine, selezionare **Invia** .

Il nuovo modello viene visualizzato nell'elenco **Modelli di team** . Il modello può essere usato per creare un team in Teams.

> [!Note]
> Possono essere richieste fino a 24 ore prima che gli utenti dei team vedano una modifica del modello personalizzato nella raccolta.

## <a name="customizing-website-tab-apps"></a>Personalizzazione delle app della scheda Sito Web

> [!Note]
> Questa funzionalità è in anteprima

È consigliabile specificare gli URL per le schede dei siti Web per i canali nei modelli di team personalizzati. Gli utenti finali che creano team con modelli avranno schede di siti Web preimpostate nell'URL del sito specificato.

Per iniziare:

1. Creare un nuovo modello di team o modificare un modello di team esistente.

2. Nella sezione Canali aggiungi un nuovo canale o seleziona un canale esistente e seleziona **Modifica**.

3. Nella sezione **Aggiungere un'app per questo modello** aggiungere un'app sito Web.

    ![aggiungere un'app per l'opzione del modello.](media/add-an-app-template.png)

4. Selezionare l'icona di modifica e immettere l'URL desiderato.

    ![aggiungi un URL dell'app.](media/add-url-app-template.png)

5. Seleziona **Salva** per le modifiche dell'app della scheda e quindi seleziona **Applica** per salvare le modifiche.

## <a name="known-issues"></a>Problemi noti

**Problema**: se è stato creato un team da un modello personalizzato che conteneva altre schede personalizzate, è possibile che vengano visualizzate schede vuote al posto delle app di schede personalizzate. Le schede predefinite, ad esempio **Post**, **File** e **Wiki**, verranno visualizzate come previsto.

**Soluzione**: per risolvere il problema, rimuovere la scheda personalizzata e aggiungere una nuova scheda con la stessa app. Se non si hanno le autorizzazioni per rimuovere la scheda personalizzata e aggiungere una nuova scheda, contattare il proprietario del team per assistenza.

Stiamo lavorando a una correzione per i team futuri creati da modelli personalizzati.

**Problema**: quando si usa Teams nel browser, alcuni siti Web non supportano il rendering all'interno di una scheda Teams.

![messaggio di errore del browser.](media/browser-error-message.png)

**Soluzione**: se hai problemi a visualizzare il contenuto della scheda del sito Web, verrai reindirizzato ad aprire la scheda in una pagina Web separata o ad aprire Teams nell'app desktop per visualizzare l'app della scheda del sito Web.

## <a name="related-topics"></a>Argomenti correlati

- [Attività iniziali con i modelli di team nell'interfaccia di amministrazione](get-started-with-teams-templates-in-the-admin-console.md)
- [Creare un modello da un team esistente](create-template-from-existing-team.md)
- [Creare un modello di team da un modello di team esistente](create-template-from-existing-template.md)
