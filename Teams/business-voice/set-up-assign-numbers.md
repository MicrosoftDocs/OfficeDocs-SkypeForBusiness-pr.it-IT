---
title: Assegnare numeri di telefono di VoIP aziendale agli utenti
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: Informazioni su come assegnare Microsoft 365 Business Voice numeri di telefono agli utenti dell'organizzazione.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 70cd47d9cb1163381ded1ee8ca1eeec0868fd2fc
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58582480"
---
# <a name="step-5-assign-business-voice-phone-numbers-to-your-users"></a>Passaggio 5: Assegnare numeri di telefono di VoIP aziendale agli utenti

Prima che gli utenti possano usare Teams per effettuare o ricevere chiamate telefoniche da o verso le normali linee telefoniche, è necessario assegnare loro i numeri di telefono. Nei Microsoft Teams client, il numero di telefono assegnato a un utente viene elencato nella tastiera del telefono quando l'utente fa clic su **Chiamate**. Eseguire le operazioni seguenti per ogni utente che necessita di un numero di telefono.

![Numero di telefono dell'utente visualizzato in Teams.](../media/teams-phone-number.png)

> [!NOTE]
> Se i numeri di telefono non sono visualizzati, attendere. Potrebbero essere necessario diverse ore prima che i nuovi numeri di telefono diventino disponibili in Teams.

Il video seguente mostra come completare questi passaggi nell'interfaccia Teams di amministrazione.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4OFYO]

1. Aprire l'Microsoft Teams di amministrazione e accedere con un utente che è un amministratore globale (in genere si tratta dell'account usato per iscriversi per Microsoft 365).
1. Nel riquadro di spostamento sinistro passare a Numeri <a href="https://admin.teams.microsoft.com/phone-numbers" target="_blank">   >  **Telefono vocali**</a>.
1. Nella pagina **Telefono numeri** selezionare un numero non assegnato nell'elenco e quindi fare clic su **Modifica**.  
1. Nel riquadro **Modifica,** in **Assegnato a,** cercare l'utente in base al nome visualizzato o al nome utente e quindi fare clic su **Assegna.**
1. In **Posizione di** emergenza è possibile selezionare la [](set-up-emergency-locations.md) posizione per gli interventi di emergenza aggiunta nel passaggio Configurare le posizioni per gli interventi di emergenza oppure, se è necessario creare una nuova posizione per un altro ufficio o un ufficio domestico, fare clic su Aggiungi una **posizione.**
1. Decidere se inviare un messaggio di posta elettronica di benvenuto con informazioni sul numero di telefono all'utente. Se vuoi:
    - **Portare i numeri di telefono esistenti** in Business Voice (chiamata portabilità dei numeri di telefono),  **deselezionare Utente di** posta elettronica con informazioni sul numero di telefono .
    - **Usare i nuovi numeri di telefono** selezionati da Voce aziendale, *selezionare* Utente di posta elettronica con informazioni sul numero **di telefono.**
1. Fare clic su **Salva**.
1. Ripetere i passaggi precedenti per ogni utente a cui si vuole assegnare un numero di telefono.

> [!NOTE]
> A causa della latenza tra Microsoft 365 o Office 365 e Teams, possono essere necessario fino a 24 ore prima che gli utenti siano abilitati. Se il numero di telefono non viene assegnato correttamente dopo 24 ore, contattare il supporto per i prodotti [aziendali - Guida per gli amministratori.](/microsoft-365/admin/contact-support-for-business-products) Opzioni di assistenza

> [!div class="nextstepaction"]
> [Passaggio successivo: Configurare un operatore automatico](set-up-auto-attendant.md?tabs=general-info#steps)
