---
title: Assegnare Teams Sistema telefonico numeri di telefono agli utenti
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
description: Informazioni su come assegnare Microsoft Teams Sistema telefonico numeri di telefono agli utenti dell'organizzazione.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9ac68e38975eaece18554a1aa04f18734da2c851
ms.sourcegitcommit: e86e3824c300c24e022d5cb1848338278a5a96a8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/03/2022
ms.locfileid: "63053015"
---
# <a name="step-5-assign-teams-phone-system-phone-numbers-to-your-users"></a>Passaggio 5: Assegnare Teams Sistema telefonico numeri di telefono agli utenti

Prima che gli utenti possano usare Teams per effettuare o ricevere chiamate telefoniche da o verso le normali linee telefoniche, è necessario assegnare loro i numeri di telefono. Nei Microsoft Teams client, il numero di telefono assegnato a un utente è elencato nella tastiera del telefono quando l'utente fa clic su **Chiamate**. Eseguire le operazioni seguenti per ogni utente che necessita di un numero di telefono.

> [!NOTE]
> Se i numeri di telefono non sono visualizzati, attendere. Potrebbero essere necessario diverse ore prima che i nuovi numeri di telefono diventino disponibili in Teams.

1. Aprire l Microsoft Teams di amministrazione e accedere con un utente amministratore globale. In genere si tratta dell'account usato per iscriversi per Microsoft 365.
1. Nel riquadro di spostamento sinistro passare a <a href="https://admin.teams.microsoft.com/phone-numbers" target="_blank">**Voce** >  **Telefono numeri**</a>.
1. Nella pagina **Telefono numeri** selezionare un numero non assegnato nell'elenco e quindi fare clic su **Modifica**.  
1. Nel riquadro **Modifica** , in **Assegnato a**, cercare l'utente in base al nome visualizzato o al nome utente e quindi fare clic su **Assegna**.
1. In **Posizione di** emergenza è possibile selezionare la posizione per gli interventi di emergenza aggiunta [](set-up-emergency-locations.md) nel passaggio Configurare le posizioni per gli interventi di emergenza oppure, se è necessario creare una nuova posizione per un altro ufficio o un ufficio domestico, fare clic su Aggiungi una **posizione**.
1. Decidere se inviare un messaggio di posta elettronica di benvenuto con informazioni sul numero di telefono all'utente. Se vuoi:
    - **Portare i numeri di telefono esistenti** in Sistema telefonico (chiamata portabilità dei numeri di *telefono),* **deselezionare Utente di posta elettronica con informazioni sul numero di telefono**.
    - **Usare i nuovi numeri di telefono** selezionati da Sistema telefonico, *selezionare* **Utente di posta elettronica con informazioni sui numeri di telefono**.
1. Fare clic su **Salva**.
1. Ripetere i passaggi precedenti per ogni utente a cui si vuole assegnare un numero di telefono.

> [!NOTE]
> Dopo aver assegnato un piano per chiamate Microsoft a un utente, possono essere richieste fino a 24 ore prima che vedano la tastiera del telefono nel Teams client. Se la tastiera del telefono non viene visualizzata tra 24 ore, controllare la configurazione [della tastiera del telefono](/microsoftteams/dial-pad-configuration). Se necessario, è anche possibile [contattare il supporto tecnico](/microsoft-365/admin/contact-support-for-business-products).

> [!div class="nextstepaction"]
> [Passaggio successivo: Configurare un operatore automatico](set-up-auto-attendant.md?tabs=general-info#steps)
