---
title: Condividere con Teams
author: HowlinWolf-92
ms.author: v-mahoffman
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
ms.localizationpriority: medium
search.appverid: MET150
description: Informazioni sulla caratteristica Condividi in Teams, che consente agli utenti di condividere messaggi di posta elettronica e allegati di posta elettronica da Outlook a qualsiasi chat o canale in Teams.
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9367a865c1eb3a8b71c60f492a8b222431c98d73
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60832940"
---
# <a name="share-to-teams-from-outlook"></a>Condividere con Teams da Outlook

Condividi con Teams da Outlook (Condividi a Teams) consente agli utenti di condividere messaggi di posta elettronica, inclusi gli allegati, da Outlook a qualsiasi chat o canale in Teams.

## <a name="outlook-add-in-for-share-to-teams"></a>Outlook componente aggiuntivo per la condivisione Teams 

La caratteristica Condividi Teams richiede un componente aggiuntivo per Outlook. Questo componente aggiuntivo viene installato automaticamente ogni volta che un utente accede all'app Web di Teams o al client desktop Teams utente.

> [!NOTE]
> Assicurarsi di esaminare i componenti aggiuntivi per Outlook [in Exchange Online](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook) e regole di accesso client [in Exchange Online](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) per assicurarsi che i componenti aggiuntivi per Outlook funzionino correttamente. Inoltre, la disabilitazione delle esperienze connesse può impedire il corretto funzionamento dei componenti aggiuntivi Outlook componenti aggiuntivi. Per [altre informazioni, vedere Esperienze connesse in Office.](https://support.microsoft.com/topic/connected-experiences-in-office-8d2c04f7-6428-4e6e-ac58-5828d4da5b7c)  

Condividi con Teams usa lo stesso meccanismo di trasporto di quando un utente invia un canale tramite posta elettronica. Per la condivisione nelle chat, i messaggi di posta elettronica (inclusi gli allegati di posta elettronica) vengono copiati nella cartella del mittente OneDrive. Per la condivisione su canali, i messaggi di posta elettronica e gli allegati vengono copiati nella cartella **Messaggi di** posta elettronica SharePoint.

Il componente aggiuntivo Outlook per la condivisione su Teams usa il set di requisiti 1.7, come descritto nella documentazione dei componenti aggiuntivi di [Outlook,](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook)che include dettagli sui componenti aggiuntivi di Outlook, i requisiti di ambiente per i componenti aggiuntivi Outlook e i client Outlook specifici supportati con il set di requisiti 1.7.

## <a name="enabling-or-disabling-share-to-teams"></a>Abilitazione o disabilitazione di Condividi Teams

Il Outlook per la condivisione a Teams può essere disabilitato o abilitato in modo selettivo per singolo utente usando i cmdlet di PowerShell seguenti.

> [!NOTE]
> La disabilitazione del componente aggiuntivo è possibile solo dopo l'installazione del componente aggiuntivo. Se si vuole applicare la disabilitazione per tutti gli utenti del tenant, eseguire periodicamente uno script.

Per disabilitare il componente aggiuntivo per Outlook usato da Share to Teams, eseguire il [cmdlet disponibile qui.](/powershell/module/exchange/disable-app?view=exchange-ps) 

Per abilitare il componente aggiuntivo per i Outlook usati da Share per Teams, eseguire il [cmdlet disponibile qui.](/powershell/module/exchange/enable-app?view=exchange-ps)

## <a name="browsers-and-single-sign-on"></a>Browser e Single Sign-On

La condivisione Teams, sia nei client desktop Outlook sul web che Outlook desktop, si basa su un webview del browser. Vedere [Browser usati Office componenti aggiuntivi per](/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins) informazioni dettagliate sui client che usano i browser specifici. 

> [!IMPORTANT]
> La condivisione con Teams richiede che i cookie di terze parti e l'accesso all'archiviazione locale siano abilitati per i browser degli utenti.

Condividi con Teams usa Single Sign-On (SSO), il che significa che gli utenti non devono fornire le proprie credenziali quando usano il componente aggiuntivo tramite Condividi per Teams. SSO per Outlook sul web supporta e https://outlook.office365.com/owa/extSSO.aspx risponde URL per impostazione https://outlook.office.com/owa/extSSO.aspx predefinita. Per i domini vanity, gli amministratori devono aggiungere l'URL Azure Active Directory risposta appropriata.