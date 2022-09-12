---
title: Usare la personalizzazione delle app per personalizzare le app in base alle esigenze dell'organizzazione
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Informazioni su come modificare i metadati e l'aspetto di un'app per rinominarla per una migliore adozione nell'organizzazione.
ms.openlocfilehash: 0a1ae462933768e0c5a53db6c7379e5cd8b9bf05
ms.sourcegitcommit: 41a75f1ba5ceb09f8db7d468aa41b63a89ab9c30
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2022
ms.locfileid: "67647480"
---
# <a name="use-app-customization-to-update-branding-of-apps-in-your-organizations-teams-store"></a>Usare la personalizzazione delle app per aggiornare il branding delle app nello store teams dell'organizzazione

Gli amministratori di Microsoft Teams possono modificare l'aspetto di alcune app di Teams per offrire un'esperienza personalizzata di marchio agli utenti finali dell'organizzazione. Tali modifiche possono migliorare l'esperienza di Teams Store per gli utenti finali e aderire al branding dell'organizzazione. Ad esempio, gli amministratori possono modificare la descrizione e l'icona di un'app che rende più facile per gli utenti finali della propria organizzazione identificare l'app, comprenderne l'uso e per una maggiore rilevanza. Gli amministratori apportano queste modifiche modificando alcuni metadati o proprietà di un'app. Le modifiche sono disponibili solo all'interno dell'organizzazione. Questa funzionalità è chiamata personalizzazione dell'app.

Gli amministratori possono personalizzare le app solo se lo sviluppatore consente la personalizzazione dell'app. Mentre Teams offre un'opzione per personalizzare alcune proprietà, gli sviluppatori di app controllano le proprietà che possono effettivamente essere personalizzate da qualsiasi amministratore.

Gli amministratori possono personalizzare le proprietà seguenti.

* Nome breve
* Descrizione breve
* Descrizione completa
* URL dell'Informativa sulla privacy
* URL del sito Web
* URL delle Condizioni per l'utilizzo
* Icona dell'app
* Colore del contorno dell'icona
* Colore di evidenziazione

Per informazioni dettagliate su ognuno di questi campi di metadati, vedere [lo schema del manifesto di Teams](/microsoftteams/platform/resources/schema/manifest-schema) nella documentazione per sviluppatori di Teams.

> [!NOTE]
> La funzionalità di personalizzazione delle app non è disponibile per le app personalizzate. Gli amministratori non possono personalizzare alcuna app negli ambienti Government Community Cloud High (GCCH) e Department of Defense (DoD).

## <a name="verify-if-an-app-is-customizable"></a>Verifica se un'app è personalizzabile

Tutte le app non sono personalizzabili. Se uno sviluppatore di app consente di personalizzare l'app, solo allora è possibile utilizzare la funzionalità di personalizzazione dell'app per modificare l'aspetto dell'app. Per verificare se l'app di tua scelta è personalizzabile o meno, segui questi passaggi:

1. Accedere all'interfaccia di amministrazione di Teams e accedere alle app  > **di Teams****[Gestire le app](https://admin.teams.microsoft.com/policies/manage-apps)**.

1. Cerca nell'app che vuoi personalizzare usando il nome dell'app. Verificare nella colonna **Personalizzabile** se lo sviluppatore dell'app consente o meno di personalizzare l'app. Se la colonna non è visibile, selezionare Modifica colonne :::image type="icon" source="media/settings-icon-16px.svg"::: e impostare **l'opzione Personalizzabile** **su Attivato**.

   :::image type="content" source="media/customizable-apps-in-tac.png" alt-text="Lo screenshot mostra che la colonna personalizzabile nell'interfaccia di amministrazione consente di verificare se un'app è personalizzabile o meno.":::

Per trovare tutte le app personalizzabili in Teams Store, ordinare la colonna Personalizzabile.

## <a name="customize-the-details-of-an-app"></a>Personalizzare i dettagli di un'app

Per modificare l'aspetto di un'app così come appare in Teams Store dell'organizzazione, seguire questa procedura:

1. Accedere all'interfaccia di amministrazione di Teams e accedere alle app  > **di Teams****[Gestire le app](https://admin.teams.microsoft.com/policies/manage-apps)**.

1. Cerca nell'app che vuoi personalizzare usando il nome dell'app e assicurati che possa essere personalizzata.

1. Per aprire l'interfaccia utente per personalizzare singoli campi di metadati, eseguire una di queste operazioni:

   * Seleziona la riga di un'app e quindi seleziona **Personalizza** :::image type="icon" source="media/edit-pen-icon.png"::: nella barra degli strumenti nella pagina Gestisci app.

   * Seleziona il nome dell'app per aprire la pagina dei dettagli dell'app e quindi seleziona l'icona :::image type="icon" source="media/edit-pen-icon.png"::: di modifica in **Personalizzabile**.

   * Seleziona il nome dell'app, seleziona **Azioni** e **quindi Personalizza**.

     :::image type="content" source="media/customize-action-menu.png" alt-text="Lo screenshot mostra un'opzione per personalizzare un'app aprendo il menu Azioni e selezionando Personalizza opzione nella pagina dei dettagli dell'app." lightbox="media/customize-action-menu-expanded.png":::

1. Personalizzare uno o più campi disponibili. Uno sviluppatore di app può consentire la personalizzazione solo di alcuni dei campi dei metadati. Vedere [considerazioni e limitazioni dei campi personalizzabili](#considerations-and-limitations-of-app-customization).

   :::image type="content" source="media/customize-settings.png" alt-text="Lo screenshot mostra il nome e la descrizione nell'interfaccia utente personalizzata.":::

1. Dopo aver personalizzato l'app, selezionare **Applica**. Per verificare le modifiche apportate, vedere [visualizzare in anteprima i dettagli dell'app](#preview-app-details). Per annullare le modifiche, vedi [Reimpostare i dettagli dell'app ai valori predefiniti](#reset-app-details-to-default-values).

1. Selezionare **Pubblica** per pubblicare l'app personalizzata e visualizzarla elencata nella pagina **Gestisci app** .

<!---
   :::image type="content" source="media/customize-app-colors.png" alt-text="Screenshot showing the icon color options that can be customized.":::
--->

## <a name="preview-app-details"></a>Anteprima dei dettagli dell'app

Per visualizzare le modifiche dopo il salvataggio della personalizzazione, visualizzare la pagina dei dettagli dell'app.

1. Accedere all'interfaccia di amministrazione di Teams e accedere alle app  > **di Teams****[Gestire le app](https://admin.teams.microsoft.com/policies/manage-apps)**.

1. Per aprire la pagina dei dettagli dell'app, seleziona il nome dell'app.

1. Visualizzare i dettagli dell'app, incluso il nome dell'app originale nel campo **Nome breve dell'autore**. Il campo è visibile solo se è stato modificato il nome breve dell'app.

   :::image type="content" source="media/original-app-version.png" alt-text="Lo screenshot mostra il nome breve modificato di un'app.":::

Gli utenti di Teams possono vedere l'app personalizzata in Teams Store nel proprio client.

   :::image type="content" source="media/contoso-app.png" alt-text="Lo screenshot mostra un'app personalizzata nel client di Teams.":::

## <a name="considerations-and-limitations-of-app-customization"></a>Considerazioni e limitazioni sulla personalizzazione delle app

Considerare i dettagli seguenti sulla funzionalità di personalizzazione delle app:

* Si avrà una sola versione dell'app, poiché la personalizzazione delle funzionalità dell'app non crea una copia dell'app.

* Quando si personalizzano le app e qualsiasi descrizione correlata a un'app, assicurarsi di seguire le linee guida fornite dallo sviluppatore dell'app nella documentazione o nelle condizioni per l'utilizzo. Attenersi alle leggi sul copyright quando si usano immagini di terze parti.

* I dati di personalizzazione forniti dall'amministratore vengono archiviati nell'area geografica più vicina.

* L'utente è responsabile di garantire la validità dei collegamenti alle condizioni per l'utilizzo o all'informativa sulla privacy.

* Nel caso in cui lo sviluppatore dell'app non consenta più la personalizzazione di un campo, verrà visualizzato un messaggio nella pagina dei dettagli dell'app che informa l'amministratore riguardo ai campi che non possono più essere personalizzati. Tutte le modifiche apportate al campo verranno ripristinate ai valori originali.

* È consigliabile testare le modifiche alla personalizzazione delle app in un tenant di test di Teams prima di apportare queste modifiche nell'ambiente di produzione. Per ottenere un tenant di test, seguire le istruzioni in [Creare il tenant di test](/microsoftteams/platform/concepts/build-and-test/prepare-your-o365-tenant).

* La propagazione delle modifiche a tutti gli utenti può richiedere fino a 24 ore.

* Per rendere personalizzabile un'app, gli sviluppatori possono fornire una nuova versione dell'app. Si carica la nuova versione e si rimuove la versione precedente dell'app. Se hai personalizzato un'app e l'hai pubblicata, la nuova app personalizzata con la funzionalità di personalizzazione dell'app non sostituirà l'app corrente.

* Il [report sull’utilizzo dell’app](teams-analytics-and-reports/app-usage-report.md) visualizza il nome originale dell'app fornito dall'autore.

* La finestra di dialogo di consenso per l'autorizzazione di Microsoft Graph visualizza il nome originale dell'app fornito dall’autore. Consente di identificare accuratamente un'app, fornendo al contempo le autorizzazioni per l'app.

Di seguito sono riportate le limitazioni relative ai campi personalizzabili:

| Campo personalizzabile | Considerazione |
|:---|:---|
| Eventuali campi URL | Assicurarsi che gli URL validi e sicuri utilizzando `https`. |
| Descrizione breve | La descrizione breve deve essere inferiore a 80 caratteri e non ripetere il testo della descrizione completa. |
| Icona | Icona struttura trasparente in formato PNG con risoluzione di 32x32 pixel. |
| Icona a colori | Icona a colori completi in formato PNG con risoluzione di 192x192 pixel. |
| Colore di evidenziazione | Il colore deve corrispondere a quello dell'icona. |

## <a name="reset-app-details-to-default-values"></a>Reimpostare i dettagli dell'app sui valori predefiniti

È possibile reimpostare i dettagli dell'app sui valori originali forniti dallo sviluppatore dell'app. L'opzione è disponibile solo per app che si sceglie di personalizzare.

1. Nell'interfaccia di amministrazione di Teams, accedere a **App di Teams** > **[Gestisci app](https://admin.teams.microsoft.com/policies/manage-apps)**.

1. Per aprire la pagina dei dettagli dell'app, seleziona il nome dell'app.

1. Dal menu **Azioni** seleziona **Ripristina impostazione predefinita**.

   :::image type="content" source="media/reset-app-customization.png" alt-text="Lo screenshot mostra l'opzione di reimpostazione predefinita per un'app personalizzata.":::

## <a name="related-articles"></a>Articoli correlati

* [Personalizzare l'app store dell'organizzazione](customize-your-app-store.md)
* [Ridefinire l’identità di marchio delle app](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/rebrand-apps-to-your-own-organization-s-branding-with-app/ba-p/2376296)
