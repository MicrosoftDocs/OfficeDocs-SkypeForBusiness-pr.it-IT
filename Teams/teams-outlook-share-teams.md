---
title: Condividere in Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
ms.localizationpriority: medium
search.appverid: MET150
description: Informazioni sulla funzionalità Condividi in Teams, che consente agli utenti di condividere e-mail e allegati di posta elettronica da Outlook a qualsiasi chat o canale in Teams.
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e2ac9a38e16000829b391e77dffdd718ed349299
ms.sourcegitcommit: f5546acf02ec644225f6d0fb41f38b1912da6adf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/21/2022
ms.locfileid: "66952760"
---
# <a name="share-to-teams-from-outlook"></a>Condividere in Teams da Outlook

La condivisione in Teams da Outlook (Condividi a Teams) consente agli utenti di condividere e-mail, allegati inclusi, da Outlook a qualsiasi chat o canale in Teams.

## <a name="outlook-add-in-for-share-to-teams"></a>Componente aggiuntivo di Outlook per la condivisione in Teams 

La funzionalità Condividi in Teams richiede un componente aggiuntivo per Outlook. Questo componente aggiuntivo viene installato automaticamente ogni volta che un utente accede all'app Web di Teams o al client desktop di Teams.

> [!NOTE]
> Assicurarsi di esaminare [i componenti aggiuntivi per Outlook in regole di accesso client e Exchange Online](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook) [in Exchange Online](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) per assicurarsi che i componenti aggiuntivi per Outlook funzionino correttamente. Inoltre, la disabilitazione delle esperienze connesse può impedire il corretto funzionamento dei componenti aggiuntivi per Outlook. Per altre informazioni, vedere [Esperienze connesse in Office](https://support.microsoft.com/topic/connected-experiences-in-office-8d2c04f7-6428-4e6e-ac58-5828d4da5b7c) . Le cassette postali condivise non sono supportate dal componente aggiuntivo. 

La condivisione con Teams usa lo stesso meccanismo di trasporto usato quando un utente invia un'e-mail a un canale. Per la condivisione in chat, i messaggi di posta elettronica (inclusi gli allegati) vengono copiati nel OneDrive del mittente. Per la condivisione nei canali, i messaggi di posta elettronica e gli allegati vengono copiati nella cartella **dei messaggi di Email** in SharePoint.

Il componente aggiuntivo di Outlook per Condividi in Teams usa il set di requisiti 1.7, come descritto [nella documentazione dei componenti aggiuntivi per Outlook](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook), che include dettagli sui componenti aggiuntivi per Outlook, requisiti di ambiente per i componenti aggiuntivi di Outlook e client di Outlook specifici supportati con il set di requisiti 1.7.

## <a name="enabling-or-disabling-share-to-teams"></a>Abilitazione o disabilitazione della condivisione in Teams

Il componente aggiuntivo di Outlook per La condivisione in Teams può essere disabilitato o abilitato in modo selettivo per ogni utente usando i cmdlet di PowerShell seguenti.

> [!NOTE]
> La disabilitazione del componente aggiuntivo è possibile solo dopo l'installazione del componente aggiuntivo. Se si vuole applicare la disabilitazione per tutti gli utenti del tenant, eseguire periodicamente uno script.

Per disabilitare il componente aggiuntivo per Outlook usato da Condividi in Teams, eseguire il [cmdlet disponibile qui](/powershell/module/exchange/disable-app).

Per abilitare il componente aggiuntivo per Outlook usato da Condividi su Teams, eseguire il [cmdlet disponibile qui](/powershell/module/exchange/enable-app).

## <a name="browsers-and-single-sign-on"></a>Browser e Single Sign-On

La condivisione in Teams, sia nei client desktop di Outlook sul web che in Outlook, si basa su una visualizzazione Web del browser. Vedere [Browser usati dai componenti aggiuntivi per Office](/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins) per informazioni dettagliate sui client che usano browser specifici. 

> [!IMPORTANT]
> La condivisione con Teams richiede che i cookie di terze parti e l'accesso all'archiviazione locale siano abilitati per i browser degli utenti.

La condivisione con Teams usa Single Sign-On (SSO), il che significa che gli utenti non devono fornire le proprie credenziali quando usano il componente aggiuntivo tramite Condividi su Teams. SSO per Outlook sul web supporta <https://outlook.office365.com/owa/extSSO.aspx> gli URL di risposta per <https://outlook.office.com/owa/extSSO.aspx> impostazione predefinita. Per i domini personali, gli amministratori devono aggiungere l'URL di risposta appropriato di Azure Active Directory.
