---
title: Esperienze connesse facoltative di Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: ''
ms.localizationpriority: high
search.appverid: MET150
description: Questo articolo illustra le esperienze connesse facoltative che verranno visualizzate in Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 03c23ccc1e9d24733f083c3e1d780b38138d366e
ms.sourcegitcommit: 46dbff43eec9631863b74b2b49c9a29c6497d8e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/20/2022
ms.locfileid: "67396267"
---
# <a name="overview-of-optional-connected-experiences-in-microsoft-teams"></a>Panoramica delle esperienze connesse facoltative in Microsoft Teams

Se si ha un account aziendale o dell'istituto di istruzione, l'amministratore dell'organizzazione può aver offerto agli utenti la possibilità di usare uno o più servizi cloud opzionali (detti anche **esperienze connesse facoltative**) durante l'utilizzo di Microsoft Teams, ad esempio GIPHY o il servizio di anteprima URL. Questi servizi basati sul cloud sono facoltativi. La scelta di usarli o meno dipende dall'utente. Vengono offerti all'utente in base a condizioni diverse dalle [Condizioni del servizio online Microsoft](https://www.microsoft.com/licensing/product-licensing/products), come descritto separatamente per ogni servizio facoltativo. Questo articolo illustra i servizi basati su cloud per Teams.

Se l'amministratore ha offerto la possibilità di usare le esperienze connesse facoltative in Teams, si può passare a **Impostazioni** > **Privacy** in Teams e scegliere se si vogliono usare le esperienze connesse facoltative.

> [!NOTE]
> Gli amministratori possono concedere o limitare la possibilità degli utenti di usare le esperienze connesse facoltative. A questo scopo, possono usare il [servizio di criteri cloud di Office](/deployoffice/overview-office-cloud-policy-service) e configurare l'impostazione dei criteri *Consenti l'uso di altre esperienze connesse facoltative in Office*. Questa è la stessa impostazione criterio che controlla se le esperienze connesse opzionali sono disponibili agli utenti nelle app di Office (come Word, Excel, and PowerPoint) presenti in Microsoft 365 Apps for enterprise.

## <a name="giphy"></a>GIPHY

GIPHY è un servizio cloud opzionale che consente di usare GIF nelle chat di Teams. Se si usa La **ricerca** **GIF** >  di **Teams** > , i termini di ricerca vengono inviati a GIPHY. Queste esperienze, se sono consentite dall'amministratore e dopo aver scelto di usarle, sono soggette all'[Informativa sulla privacy](https://support.giphy.com/hc/articles/360032872931-GIPHY-Privacy-Policy) e alle [Condizioni d'uso](https://support.giphy.com/hc/articles/360020027752-GIPHY-User-Terms-of-Service) di GIPHY.

:::image type="content" source="media/giphy-menu.png" alt-text="Menu che mostra il pulsante di selezione Giphy e la casella di testo per la digitazione di informazioni per recuperare una o più immagini Giphy":::

## <a name="url-preview-service"></a>Servizio Anteprima URL

Il servizio Anteprima URL genera automaticamente un frammento di contenuto di anteprima e allega l'URL sotto il frammento quando un utente invia una stringa di URL. Questo servizio invierà una richiesta all'URL del servizio mentre l'utente digita il messaggio. Se l'URL del servizio non contiene dati di schema.org, invierà una richiesta di ricerca in Bing per ottenere i dati necessari per generare il frammento di anteprima. Le esperienze che si basano su Bing sono concesse in licenza all'utente ai sensi delle condizioni del [Contratto di Servizi Microsoft](https://www.microsoft.com/servicesagreement) e coperte dall'informativa [sulla privacy](https://privacy.microsoft.com/privacystatement). Tutti gli URL forniti a Microsoft Teams durante l'uso di questi servizi possono essere inviati a Microsoft Bing. Non sono collegati a te dall'organizzazione bing.

:::image type="content" source="media/url-preview.png" alt-text="Schermata che mostra un esempio di anteprima dell'URL per la Home page Microsoft in una casella di testo.":::

## <a name="teams-apps-link-previews"></a>Anteprime dei collegamenti alle app di Teams

Il servizio di anteprima del collegamento dell'app Teams genera un frammento di anteprima della scheda adattiva dell'app e lo allega sotto l'URL quando un utente invia una stringa di URL mappata all'app in Teams Store. Questo servizio invierà una richiesta all'URL del servizio mentre l'utente digita il messaggio.

## <a name="teams-device-store-checkout"></a>Cassa nello store dei dispositivi di Teams  

Lo store dei dispositivi di Teams si trova nell'interfaccia di amministrazione di Teams e consente l'individuazione e l'acquisto di dispositivi certificati per Teams. Per abilitare la transazione, l'archivio dispositivi di Teams condivide informazioni di base sull'utente e sull'azienda, tra cui l'indirizzo e-mail dell'utente, i GUID dell'utente e i GUID del tenant, con UnifiedCommunications.com. Questa esperienza, se consentita **dall'impostazione Consenti l'uso di altre esperienze connesse facoltative nei** criteri di Office , è soggetta alle condizioni del servizio e all'informativa sulla privacy di UnifiedCommunications.com.

:::image type="content" source="media/teams-device-store-buttons.png" alt-text="Screenshot di una parte della pagina store dei dispositivi di Teams con le opzioni di cassa fornite da UnifiedCommunications.com, una società di terze parti che consente l'acquisto di dispositivi dall'interfaccia di amministrazione di Teams.":::

Per altre informazioni su Teams Device Store, vedere: [Acquistare dispositivi nello store dei dispositivi di Teams](devices/device-store.md)

## <a name="related-articles"></a>Articoli correlati

- [Panoramica dei controlli dei criteri per Teams](policy-control-overview.md)
- [Privacy e Microsoft Teams](teams-privacy.md)
- [Panoramica delle esperienze connesse facoltative in Office](/deployoffice/privacy/optional-connected-experiences)
- [Dati di servizio obbligatori per Office](/deployoffice/privacy/required-service-data)
- [Impostazioni di Privacy account](https://support.microsoft.com/office/3e7bc183-bf52-4fd0-8e6b-78978f7f121b)
