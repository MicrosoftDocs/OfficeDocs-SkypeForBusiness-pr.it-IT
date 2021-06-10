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
ms.openlocfilehash: af5c2f6029b0c5314c507de7734abf8c479af709
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098222"
---
# <a name="share-to-teams-from-outlook"></a>Condividere in Teams da Outlook

Condividi a Teams da Outlook (Condividi a Teams) consente agli utenti di condividere messaggi di posta elettronica, inclusi gli allegati, da Outlook a qualsiasi chat o canale in Teams.

## <a name="outlook-add-in-for-share-to-teams"></a>Outlook componente aggiuntivo per la condivisione Teams 

La caratteristica Condividi Teams richiede un componente aggiuntivo per Outlook. Questo componente aggiuntivo viene installato automaticamente ogni volta che un utente accede all'app Web Teams o al client desktop Teams client desktop.

> [!NOTE]
> Verificare che i componenti aggiuntivi per Outlook [in Exchange Online](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook) e regole di accesso client [in Exchange Online](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) per assicurarsi che i componenti aggiuntivi per Outlook funzionino correttamente. Inoltre, la disabilitazione delle esperienze connesse può impedire il corretto funzionamento dei componenti aggiuntivi Outlook per gli utenti. Vedere [Esperienze connesse in Office](https://support.microsoft.com/topic/connected-experiences-in-office-8d2c04f7-6428-4e6e-ac58-5828d4da5b7c) per altre informazioni.  

Condividi con Teams usa lo stesso meccanismo di trasporto di quando un utente invia un canale tramite posta elettronica. Per la condivisione nelle chat, i messaggi di posta elettronica (inclusi gli allegati di posta elettronica) vengono copiati nella cartella del mittente OneDrive. Per la condivisione su canali, i messaggi di posta elettronica e gli allegati vengono copiati nella cartella **Messaggi di** posta elettronica in SharePoint.

Il componente aggiuntivo Outlook per la condivisione su Teams usa il set di requisiti 1.7, come descritto nella documentazione dei componenti aggiuntivi di [Outlook,](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook)che include dettagli sui componenti aggiuntivi Outlook, i requisiti di ambiente per i componenti aggiuntivi Outlook e i client Outlook specifici supportati con il set di requisiti 1.7.

## <a name="enabling-or-disabling-share-to-teams"></a>Abilitazione o disabilitazione della condivisione Teams

Il Outlook per la condivisione a Teams può essere disabilitato o abilitato in modo selettivo in base all'utente usando i cmdlet di PowerShell seguenti.

> [!NOTE]
> La disabilitazione del componente aggiuntivo è possibile solo dopo l'installazione del componente aggiuntivo. Se si vuole applicare la disabilitazione per tutti gli utenti del tenant, eseguire periodicamente uno script.

Per disabilitare il componente aggiuntivo per Outlook usato da Share to Teams, eseguire il [cmdlet disponibile qui.](/powershell/module/exchange/disable-app?view=exchange-ps) 

Per abilitare il componente aggiuntivo per i Outlook usati da Share per Teams, eseguire il [cmdlet disponibile qui.](/powershell/module/exchange/enable-app?view=exchange-ps)

## <a name="browsers-and-single-sign-on"></a>Browser e Single Sign-On

Share to Teams, sia in Outlook web che nei client desktop Outlook desktop, si basa su un browser WebView. Vedere [Browser usati Office componenti aggiuntivi per](/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins) informazioni dettagliate sui client che usano i browser specifici. 

> [!IMPORTANT]
> La condivisione Teams richiede che i cookie di terze parti e l'accesso all'archiviazione locale siano abilitati per i browser degli utenti.

Condividi con Teams usa Single Sign-On (SSO), il che significa che gli utenti non devono fornire le proprie credenziali quando usano il componente aggiuntivo tramite Condividi per Teams. SSO per Outlook sul Web supporta e https://outlook.office365.com/owa/extSSO.aspx risponde URL per impostazione https://outlook.office.com/owa/extSSO.aspx predefinita. Per i domini vanity, gli amministratori devono aggiungere l'URL Azure Active Directory risposta appropriata.