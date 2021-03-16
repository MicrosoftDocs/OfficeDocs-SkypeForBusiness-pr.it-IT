---
title: Condividere con Teams
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
localization_priority: Normal
search.appverid: MET150
description: Informazioni sulla caratteristica Condividi in Teams, che consente agli utenti di condividere messaggi di posta elettronica e allegati di posta elettronica da Outlook a qualsiasi chat o canale in Teams.
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 80882bddae434b66f6a3e5988c08474859b37861
ms.sourcegitcommit: c6b630f9193d7f82f0416bd567a1de390d4b260f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2021
ms.locfileid: "50819449"
---
# <a name="share-to-teams-from-outlook"></a>Condividere in Teams da Outlook

Condividi in Teams da Outlook (Condividi in Teams) consente agli utenti di condividere messaggi di posta elettronica, inclusi gli allegati, da Outlook a qualsiasi chat o canale in Teams.

## <a name="outlook-add-in-for-share-to-teams"></a>Componente aggiuntivo Outlook per la condivisione in Teams 

La caratteristica Condividi in Teams richiede un componente aggiuntivo per Outlook. Questo componente aggiuntivo viene installato automaticamente ogni volta che un utente accede all'app Web teams o al client desktop di Teams.

> [!NOTE]
> Assicurarsi di esaminare i componenti aggiuntivi per [Outlook in Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook) e le regole di accesso client in Exchange [Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) per assicurarsi che i componenti aggiuntivi per Outlook funzionino correttamente. Inoltre, la disabilitazione delle esperienze connesse può impedire il corretto funzionamento dei componenti aggiuntivi per Outlook. Per [altre informazioni, vedere](https://support.microsoft.com/topic/connected-experiences-in-office-8d2c04f7-6428-4e6e-ac58-5828d4da5b7c) Esperienze connesse in Office.  

Condividi con Teams usa lo stesso meccanismo di trasporto utilizzato quando un utente invia un canale tramite posta elettronica. Per la condivisione nelle chat, i messaggi di posta elettronica (inclusi gli allegati di posta elettronica) vengono copiati nel OneDrive del mittente. Per la condivisione su canali, i messaggi di posta elettronica e gli allegati vengono copiati nella **cartella Messaggi di** posta elettronica in SharePoint.

Il componente aggiuntivo Outlook per la condivisione in Teams usa il set di requisiti 1.7, come descritto in dettaglio nella documentazione relativa ai componenti aggiuntivi di [Outlook,](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook)che include dettagli sui componenti aggiuntivi di Outlook, i requisiti di ambiente per i componenti aggiuntivi di Outlook e i client di Outlook specifici supportati con il set di requisiti 1.7.

## <a name="enabling-or-disabling-share-to-teams"></a>Abilitazione o disabilitazione della condivisione in Teams

Il componente aggiuntivo Outlook per la condivisione in Teams può essere disabilitato o abilitato in modo selettivo per ogni utente usando i cmdlet di PowerShell seguenti.

> [!NOTE]
> La disabilitazione del componente aggiuntivo è possibile solo dopo l'installazione del componente aggiuntivo. Se si vuole applicare la disabilitazione per tutti gli utenti del tenant, eseguire periodicamente uno script.

Per disabilitare il componente aggiuntivo per Outlook usato da Condividi in Teams, eseguire il [cmdlet disponibile qui.](https://docs.microsoft.com/powershell/module/exchange/disable-app?view=exchange-ps) 

Per abilitare il componente aggiuntivo per Outlook usato da Condividi in Teams, eseguire il [cmdlet disponibile qui.](https://docs.microsoft.com/powershell/module/exchange/enable-app?view=exchange-ps)

## <a name="browsers-and-single-sign-on"></a>Browser e Single Sign-On

La condivisione con Teams, sia nei client desktop di Outlook sul Web che nei client desktop di Outlook, si basa su un browser WebView. Per [informazioni dettagliate](https://docs.microsoft.com/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins) sui client che usano browser specifici, vedere Browser usati dai componenti aggiuntivi di Office. 

> [!IMPORTANT]
> La condivisione con Teams richiede che i cookie di terze parti e l'accesso all'archiviazione locale siano abilitati per i browser degli utenti.

Condividi con Teams usa Single Sign-On (SSO), il che significa che gli utenti non devono fornire le proprie credenziali quando usano il componente aggiuntivo tramite Condividi con Teams. Per impostazione predefinita, SSO per Outlook sul Web supporta e https://outlook.office365.com/owa/extSSO.aspx https://outlook.office.com/owa/extSSO.aspx risponde agli URL. Per i domini vanity, gli amministratori devono aggiungere l'URL di risposta di Azure Active Directory appropriato.