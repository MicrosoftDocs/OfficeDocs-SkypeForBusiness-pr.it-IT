---
title: Errori dei canali condivisi in Microsoft Teams
author: MikePlumleyMSFT
ms.author: mikeplum
manager: serdars
ms.reviewer: jasonlewis
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: normal
search.appverid: MET150
description: Informazioni su come usare correggi gli errori nei canali condivisi in Microsoft Teams.
ms.openlocfilehash: ecd05f1593817ed03d6e516e8915cd15694b6315
ms.sourcegitcommit: 3266fde54b92a18865d666b98e4e7e8322b9dedc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/26/2022
ms.locfileid: "67024163"
---
# <a name="shared-channels-errors-in-microsoft-teams"></a>Errori dei canali condivisi in Microsoft Teams

Se gli utenti visualizzano messaggi di errore quando provano ad aggiungere persone esterne all'organizzazione ai canali condivisi, controllare le impostazioni in questo articolo. 

## <a name="due-to-admin-policy-you-cant-add-external-people-to-the-channel-for-more-info-talk-to-your-admin"></a>A causa dei criteri di amministrazione, non è possibile aggiungere persone esterne al canale. Per altre info, contatta l'amministratore.

Teams usa Gruppi di Microsoft 365 per l'appartenenza al team. Le impostazioni Gruppi di Microsoft 365 guest devono essere attivate perché le persone esterne all'organizzazione possano essere aggiunte a un canale condiviso. Se gli utenti visualizzano questo errore, controllare le impostazioni di Gruppi di Microsoft 365 per gli utenti esterni all'organizzazione.

Per impostare le impostazioni di Gruppi di Microsoft 365 per gli utenti esterni all'organizzazione
1. Nel riquadro di spostamento sinistro della interfaccia di amministrazione di Microsoft 365 espandere **Impostazioni**.
1. Fare clic su **Impostazioni organizzazione**.
1. Nell'elenco fare clic su **Gruppi di Microsoft 365**.
1. Verificare che le caselle di controllo **Consenti ai proprietari del gruppo di aggiungere persone esterne all'organizzazione a Gruppi di Microsoft 365 come guest** e **Consenti ai membri del gruppo guest di accedere al contenuto del gruppo** siano entrambe selezionate.
1. Se sono state apportate modifiche, fare clic su **Salva modifiche**.

## <a name="due-to-admin-policy-you-cant-add-external-people-to-the-channel"></a>A causa dei criteri di amministrazione, non è possibile aggiungere persone esterne al canale

I criteri per i canali di Teams determinano come gli utenti possono interagire con i canali condivisi. Se gli utenti visualizzano questo messaggio di errore, controllare i criteri del canale per l'utente.

Per impostare il criterio per invitare persone esterne all'organizzazione a canali condivisi
1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, passare a Criteri di Teams > Teams.
1. Selezionare il criterio a cui è assegnato l'utente.
1. Verificare che **l'opzione Invita utenti esterni ai canali condivisi** sia **attivata**.
1. Se sono state apportate modifiche, selezionare **Applica**.

Per altre informazioni sui criteri per i canali di Teams, vedere [Gestire i criteri dei canali in Microsoft Teams](teams-policies.md).

## <a name="you-cant-share-this-channel-with-people-from-this-org"></a>Non puoi condividere questo canale con persone di questa organizzazione

Se gli utenti visualizzano questo errore, non potranno condividere il canale con gli utenti dell'altra organizzazione dalle impostazioni di accesso tra tenant di Azure Active Directory. Ciò può essere dovuto alle impostazioni in ingresso nell'organizzazione o alle impostazioni in uscita nell'altra organizzazione.

Per controllare le impostazioni in ingresso per l'organizzazione
1. In [Azure Active Directory](https://aad.portal.azure.com) selezionare **Identità esterne** e quindi **impostazioni di accesso tra tenant**.
1. Selezionare il collegamento di accesso in ingresso per l'organizzazione da controllare.
1. Nella scheda **Connessione diretta B2B** scegli **Personalizza impostazioni**.
1. Nella scheda **Utenti e gruppi esterni** verificare che siano selezionati **Consenti accesso** e **Tutti gli utenti e i gruppi esterni** oppure, se si è scelto **Seleziona utenti e gruppi esterni**, assicurarsi che l'utente invitato sia un membro dei gruppi selezionati.
1. Se sono state apportate modifiche, selezionare **Salva** e chiudere il pannello **delle impostazioni di accesso in ingresso** .

Se gli utenti continuano a visualizzare l'errore, contattare l'organizzazione con cui collaborano. Le impostazioni in uscita dell'organizzazione potrebbero non consentire la condivisione con l'organizzazione. Per informazioni sulla configurazione di canali condivisi tra organizzazioni, vedere [Collaborare con partecipanti esterni in un canale condiviso](/microsoft-365/solutions/collaborate-teams-direct-connect).

## <a name="we-couldnt-find-any-matches-make-sure-the-email-address-is-correct-or-talk-to-your-admin"></a>Non è stato possibile trovare corrispondenze. Verificare che l'indirizzo di posta elettronica sia corretto o rivolgersi all'amministratore

Se gli utenti visualizzano questo errore, Microsoft 365 non è in grado di trovare l'indirizzo di posta elettronica specificato nell'organizzazione esterna. È necessario confermare l'indirizzo con l'organizzazione esterna.

