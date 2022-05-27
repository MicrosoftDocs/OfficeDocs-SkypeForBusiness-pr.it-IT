---
title: Condividi con Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
ms.localizationpriority: medium
search.appverid: MET150
description: Informazioni sulla funzionalità Condividi in Teams, che consente agli utenti di condividere messaggi di posta elettronica e allegati di posta elettronica da Outlook a qualsiasi chat o canale in Teams.
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2a768424033ff300a079fc0b505d1e9ce32a970e
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2022
ms.locfileid: "65682027"
---
# <a name="share-to-teams-from-outlook"></a>Condividere in Teams da Outlook

Condividi con Teams da Outlook (Condividi in Teams) consente agli utenti di condividere messaggi di posta elettronica, allegati inclusi, da Outlook a qualsiasi chat o canale in Teams.

## <a name="outlook-add-in-for-share-to-teams"></a>Outlook componente aggiuntivo Per condividere in Teams 

La caratteristica Condividi in Teams richiede un componente aggiuntivo per Outlook. Questo componente aggiuntivo viene installato automaticamente ogni volta che un utente accede all'app Web Teams o al client desktop Teams.

> [!NOTE]
> Assicurarsi di esaminare [i componenti aggiuntivi per Outlook in regole di accesso client e Exchange Online](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook) [in Exchange Online](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) per assicurarsi che i componenti aggiuntivi per Outlook funzionino correttamente. Inoltre, la disabilitazione delle esperienze connesse può impedire il corretto funzionamento dei componenti aggiuntivi per Outlook. Per altre informazioni, vedere [Esperienze connesse in Office](https://support.microsoft.com/topic/connected-experiences-in-office-8d2c04f7-6428-4e6e-ac58-5828d4da5b7c).  

Condividi con Teams usa lo stesso meccanismo di trasporto usato quando un utente invia un'e-mail a un canale. Per la condivisione in chat, i messaggi di posta elettronica (inclusi gli allegati) vengono copiati nella OneDrive del mittente. Per la condivisione nei canali, i messaggi di posta elettronica e gli allegati vengono copiati nella cartella **Messaggi di posta elettronica** in SharePoint.

Il componente aggiuntivo Outlook per Share to Teams usa il set di requisiti 1.7, come descritto in dettaglio nella [documentazione di Outlook componenti aggiuntivi](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook), che include dettagli su Outlook componenti aggiuntivi, requisiti di ambiente per Outlook componenti aggiuntivi e client specifici Outlook supportati con il requisito 1.7.

## <a name="enabling-or-disabling-share-to-teams"></a>Abilitazione o disabilitazione di Condividi per Teams

Il componente aggiuntivo Outlook per Condividere in Teams può essere disabilitato o abilitato in modo selettivo per singoli utenti usando i cmdlet di PowerShell seguenti.

> [!NOTE]
> La disabilitazione del componente aggiuntivo è possibile solo dopo l'installazione del componente aggiuntivo. Se si vuole applicare la disabilitazione per tutti gli utenti del tenant, eseguire periodicamente uno script.

Per disabilitare il componente aggiuntivo per Outlook usato da Condividi per Teams, eseguire il [cmdlet disponibile qui](/powershell/module/exchange/disable-app).

Per abilitare il componente aggiuntivo per Outlook usato da Condividi per Teams, eseguire il [cmdlet disponibile qui](/powershell/module/exchange/enable-app).

## <a name="browsers-and-single-sign-on"></a>Browser e Single Sign-On

La condivisione con Teams, sia nei client desktop Outlook sul web che in Outlook, si basa su una visualizzazione Web del browser. Vedere [Browser usati da Office Componenti aggiuntivi](/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins) per informazioni dettagliate sui client che usano browser specifici. 

> [!IMPORTANT]
> La condivisione con Teams richiede l'abilitazione dei cookie di terze parti e dell'accesso all'archiviazione locale per i browser degli utenti.

Condividi con Teams usa Single Sign-On (SSO), il che significa che gli utenti non devono fornire le proprie credenziali quando usano il componente aggiuntivo tramite Condividi per Teams. SSO per Outlook sul web supporta <https://outlook.office365.com/owa/extSSO.aspx> gli URL di risposta per <https://outlook.office.com/owa/extSSO.aspx> impostazione predefinita. Per i domini personali, gli amministratori devono aggiungere l'URL di risposta appropriato Azure Active Directory.
