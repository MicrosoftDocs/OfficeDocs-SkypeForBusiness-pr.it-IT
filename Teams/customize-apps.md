---
title: Usare la personalizzazione delle app per personalizzare le app in base alle esigenze dell'organizzazione
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-apps
audience: Admin
ms.date: 09/20/2022
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Informazioni su come modificare i metadati e l'aspetto di un'app per rinominarla per una migliore adozione nell'organizzazione.
ms.openlocfilehash: f12e6ead6c0d031100bcf30783de980986a14563
ms.sourcegitcommit: c2d8c7f779f4f938f8355632ecfbfc9147b53bb2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2022
ms.locfileid: "68738732"
---
# <a name="use-app-customization-to-update-branding-of-apps-in-your-organizations-teams-store"></a>Usare la personalizzazione delle app per aggiornare il branding delle app nello store teams dell'organizzazione

Gli amministratori di Microsoft Teams possono modificare l'aspetto di alcune app di Teams per offrire un'esperienza personalizzata di marchio agli utenti finali dell'organizzazione. Tali modifiche possono migliorare l'esperienza di Teams Store per gli utenti finali e aderire al branding dell'organizzazione. Ad esempio, gli amministratori possono modificare la descrizione e l'icona di un'app. La personalizzazione semplifica agli utenti finali l'identificazione dell'app come strumento interno, la comprensione del caso d'uso specifico dell'organizzazione e l'uso sicuro. Gli amministratori apportano questi aggiornamenti modificando alcuni metadati o proprietà di un'app. Le modifiche sono disponibili solo all'interno dell'organizzazione. Questa funzionalità è chiamata personalizzazione dell'app.

Gli amministratori possono personalizzare le app solo se lo sviluppatore consente la personalizzazione dell'app. Mentre Teams offre un'opzione per personalizzare le proprietà seguenti, gli sviluppatori di app controllano quali proprietà possono effettivamente essere personalizzate da qualsiasi amministratore.

* Nome breve
* Descrizione breve
* Descrizione completa
* URL dell'Informativa sulla privacy
* URL del sito Web
* URL delle Condizioni per l'utilizzo
* Icona dell'app
* Colore del contorno dell'icona
* Colore di evidenziazione

Per informazioni dettagliate su ognuna di queste proprietà, vedere [lo schema del manifesto di Teams](/microsoftteams/platform/resources/schema/manifest-schema) nella documentazione per sviluppatori di Teams.

> [!NOTE]
> È necessario avere una licenza client di Teams per personalizzare le informazioni sulle app.

## <a name="verify-if-an-app-is-customizable"></a>Verifica se un'app è personalizzabile

Tutte le app non sono personalizzabili. Se uno sviluppatore di app consente la personalizzazione dell'app, solo allora puoi modificare l'aspetto dell'app. Per verificare se l'app di tua scelta è personalizzabile o meno, segui questi passaggi:

1. Accedere all'interfaccia di amministrazione di Teams e accedere alle app  > **di Teams****[Gestire le app](https://admin.teams.microsoft.com/policies/manage-apps)**.

1. Facoltativamente, se la colonna **Personalizzabile** non è visibile, selezionare Modifica colonne :::image type="icon" source="media/settings-icon-16px.svg"::: e impostare **l'opzione Personalizzabile** **su Attivato**.

1. Cerca nell'app che vuoi personalizzare usando il nome dell'app. Verificare nella colonna **Personalizzabile** se lo sviluppatore dell'app consente o meno di personalizzare l'app.

   :::image type="content" source="media/customizable-apps-in-tac.png" alt-text="Lo screenshot mostra che la colonna personalizzabile nell'interfaccia di amministrazione consente di verificare se un'app è personalizzabile o meno.":::

Per trovare tutte le app personalizzabili in Teams Store, ordinare la colonna **Personalizzabile** .

## <a name="customize-an-app"></a>Personalizzare un'app

Per modificare l'aspetto di un'app in Teams Store dell'organizzazione, seguire questa procedura:

1. Accedere all'interfaccia di amministrazione di Teams e accedere alle app  > **di Teams****[Gestire le app](https://admin.teams.microsoft.com/policies/manage-apps)**.

1. Cerca nell'app che vuoi personalizzare usando il nome dell'app e [assicurati che possa essere personalizzata](#verify-if-an-app-is-customizable).

1. Per aprire l'interfaccia utente per personalizzare singoli campi di metadati, eseguire una di queste operazioni:

   * Seleziona la riga di un'app e quindi seleziona **Personalizza** :::image type="icon" source="media/edit-pen-icon.png"::: nella barra degli strumenti nella pagina Gestisci app.

   * Seleziona il nome dell'app per aprire la pagina dei dettagli dell'app e quindi seleziona l'icona :::image type="icon" source="media/edit-pen-icon.png"::: di modifica in **Personalizzabile**.

   * Seleziona il nome dell'app per aprire la pagina dei dettagli dell'app e quindi seleziona **Azioni** > **Personalizza**.

     :::image type="content" source="media/customize-action-menu.png" alt-text="Lo screenshot mostra un'opzione per personalizzare un'app aprendo il menu Azioni e selezionando Personalizza opzione nella pagina dei dettagli dell'app." lightbox="media/customize-action-menu-expanded.png":::

1. Personalizzare uno o più campi disponibili. Vengono visualizzati solo i campi dei metadati che lo sviluppatore dell'app ha consentito di personalizzare. Per le limitazioni di alcuni campi, vedere [considerazioni e limitazioni dei campi personalizzabili](#considerations-and-limitations-of-app-customization).

   :::image type="content" source="media/customize-settings.png" alt-text="Lo screenshot mostra il nome e la descrizione nell'interfaccia utente personalizzata.":::

1. Dopo aver personalizzato l'app, selezionare **Applica**. Per verificare le modifiche apportate, vedere [visualizzare in anteprima i dettagli dell'app](#preview-app-customizations). Per annullare le modifiche, vedi [Reimpostare i dettagli dell'app ai valori predefiniti](#reset-app-details-to-default-values).

1. Selezionare **Pubblica** per pubblicare l'app personalizzata nello store dell'organizzazione.

L'app è elencata nella pagina **Gestisci app** e in Teams Store e client (disponibile tramite web, mobile o desktop client) con i dettagli aggiornati. La visualizzazione della modifica potrebbe richiedere alcune ore.

## <a name="preview-app-customizations"></a>Anteprima delle personalizzazioni delle app

Per visualizzare le modifiche dopo il salvataggio delle personalizzazioni, visualizzare la pagina dei dettagli dell'app.

1. Accedere all'interfaccia di amministrazione di Teams e accedere alle app  > **di Teams****[Gestire le app](https://admin.teams.microsoft.com/policies/manage-apps)**.

1. Per aprire la pagina dei dettagli dell'app, seleziona il nome dell'app.

1. Visualizzare i dettagli dell'app, incluso il nome dell'app originale nel campo **Nome breve dell'autore**. Il campo è visibile solo se è stato modificato il nome breve dell'app.

   :::image type="content" source="media/original-app-version.png" alt-text="Lo screenshot mostra il nome breve modificato di un'app.":::

Dopo alcune ore, gli utenti di Teams possono vedere l'app personalizzata in Teams Store nel proprio client (web, mobile e desktop).

   :::image type="content" source="media/contoso-app.png" alt-text="Lo screenshot mostra un'app personalizzata nel client di Teams.":::

## <a name="considerations-and-limitations-of-app-customization"></a>Considerazioni e limitazioni sulla personalizzazione delle app

Considerare i dettagli seguenti sulla funzionalità di personalizzazione delle app:

* È possibile personalizzare solo [le app di terze parti](deploy-apps-microsoft-teams-landing-page.md#third-party-apps-created-by-independent-app-developers) e non [le app personalizzate](deploy-apps-microsoft-teams-landing-page.md#custom-apps-created-within-an-organization-for-internal-use).

* Non è possibile personalizzare alcuna app negli ambienti Government Community Cloud High (GCCH) e Department of Defense (DoD).

* Un'app può essere personalizzata solo se lo sviluppatore lo consente.

* Le modifiche alle app sono disponibili solo all'interno dell'organizzazione.

* Si avrà una sola versione dell'app, perché la personalizzazione dei dettagli dell'app non crea una copia dell'app.

* Quando si personalizzano le app e qualsiasi descrizione correlata a un'app, assicurarsi di seguire le linee guida fornite dagli sviluppatori di app nella documentazione o nelle condizioni per l'utilizzo. Attenersi alle leggi sul copyright quando si usano immagini di terze parti.

* Amministrazione dati di personalizzazione forniti vengono archiviati nell'area di archiviazione dei dati più vicina.

* L'utente è responsabile di garantire la validità dei collegamenti alle condizioni per l'utilizzo o all'informativa sulla privacy.

* Nel caso in cui lo sviluppatore di app non consenta più di personalizzare un campo, nella pagina dei dettagli dell'app viene visualizzato un messaggio che informa l'amministratore di un campo di questo tipo. Tutte le modifiche apportate al campo vengono ripristinate al valore originale.

* È consigliabile testare le modifiche alla personalizzazione delle app in un tenant di test di Teams prima di apportare queste modifiche nell'ambiente di produzione. Per ottenere un tenant di test, seguire le istruzioni in [Creare il tenant di test](/microsoftteams/platform/concepts/build-and-test/prepare-your-o365-tenant).

* Aggiornamenti richiedere fino a 24 ore per essere visualizzato nel client per tutti gli utenti e gli account amministratore.

* Affinché un'app esistente diventi personalizzabile, lo sviluppatore può fornire una nuova versione dell'app in Teams Store.

* Il [report utilizzo app](teams-analytics-and-reports/app-usage-report.md) visualizza il nome originale dell'app fornito dall'autore, anche se l'app personalizzata viene usata dagli utenti finali.

* La finestra di dialogo di consenso per l'autorizzazione di Microsoft Graph visualizza il nome originale dell'app fornito dall’autore. Consente di identificare accuratamente un'app, fornendo al contempo le autorizzazioni per l'app.

* La personalizzazione di un'app non modifica le funzionalità dell'app.

Di seguito sono riportate le limitazioni di alcuni campi personalizzabili:

| Campo personalizzabile | Considerazione |
|:---|:---|
| Eventuali campi URL | Assicurarsi che gli URL validi e sicuri utilizzando `https`. |
| Descrizione breve | La descrizione breve deve essere inferiore a 80 caratteri. Non ripetere il contenuto della descrizione completa. |
| Icona | Icona struttura trasparente in formato PNG con risoluzione di 32x32 pixel. |
| Icona a colori | Icona a colori completi in formato PNG con risoluzione di 192x192 pixel. |
| Colore di evidenziazione | Il colore deve corrispondere a quello dell'icona. |

## <a name="troubleshoot-app-customization"></a>Risolvere i problemi di personalizzazione delle app

| Errori e problemi | Possibile correzione o comprensione del problema |
| --- | --- |
| Gli aggiornamenti non sono disponibili per gli utenti finali. | Attendere alcune ore per la propagazione delle modifiche. |
| Non riesco a personalizzare un'app. | Verifica se [l'app è personalizzabile o meno](#verify-if-an-app-is-customizable).|
| Ho iniziato a personalizzare un'app ma non riesco a salvare o applicare le mie modifiche. | Attenersi alle limitazioni dei campi. Cerca gli errori nell'interfaccia utente e le [limitazioni della personalizzazione delle app](#considerations-and-limitations-of-app-customization) |
| La pagina Gestisci app non viene caricata correttamente. L'elenco delle app non viene visualizzato. | Amministrazione account in uso deve avere la licenza di Teams assegnata. |

<!--- Check ICM for error string. --->

## <a name="reset-app-details-to-default-values"></a>Reimpostare i dettagli dell'app sui valori predefiniti

È possibile reimpostare i dettagli dell'app sui valori originali forniti dallo sviluppatore dell'app. L'opzione è disponibile solo per app che si sceglie di personalizzare.

1. Nell'interfaccia di amministrazione di Teams, accedere a **App di Teams** > **[Gestisci app](https://admin.teams.microsoft.com/policies/manage-apps)**.

1. Per aprire la pagina dei dettagli dell'app, seleziona il nome dell'app.

1. Dal menu **Azioni** seleziona **Ripristina impostazione predefinita**.

   :::image type="content" source="media/reset-app-customization.png" alt-text="Lo screenshot mostra l'opzione di reimpostazione predefinita per un'app personalizzata.":::

## <a name="related-articles"></a>Articoli correlati

* [Personalizzare l'app store dell'organizzazione](customize-your-app-store.md)
* [Rebrand your apps community post](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/rebrand-apps-to-your-own-organization-s-branding-with-app/ba-p/2376296)
