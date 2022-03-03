---
title: Configurare le Microsoft Teams Sistema telefonico con le località di emergenza del piano di chiamata
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
description: Scopri come configurare le località di emergenza per Microsoft Teams Sistema telefonico con piano chiamate.
appliesto:
- Microsoft Teams
ms.openlocfilehash: db47c18edafcac62e00bae659b78c25acab6c417
ms.sourcegitcommit: e86e3824c300c24e022d5cb1848338278a5a96a8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/03/2022
ms.locfileid: "63053025"
---
# <a name="step-1-set-up-a-teams-phone-system-emergency-location"></a>Passaggio 1: Configurare una posizione Teams Sistema telefonico per gli interventi di emergenza

Una posizione per gli interventi di emergenza viene usata quando qualcuno nell'organizzazione chiama i servizi di emergenza, come il fuoco, la polizia o l'eliambulanza. Quando una persona chiama un servizio di emergenza, l'indirizzo configurato come indirizzo di emergenza dell'organizzazione viene inviato al servizio. Questo passaggio configura la posizione principale per gli interventi di emergenza per l'organizzazione. Questa posizione verrà associata al numero di telefono principale dell'azienda in un passaggio successivo.

Se si hanno utenti in più posizioni, ad esempio uffici privati o uffici in altre città, è possibile configurare altre posizioni per gli interventi di emergenza. È anche possibile configurare posizioni specifiche all'interno di una posizione. I luoghi possono essere edifici, piani, uffici o altri luoghi in cui gli utenti possono essere in una posizione diversa. È possibile aggiungere altre località e località dopo aver completato la configurazione iniziale Teams Sistema telefonico piano per chiamate.

## <a name="add-an-emergency-location"></a>Aggiungere una posizione per gli interventi di emergenza

1. Aprire l Microsoft Teams di amministrazione e accedere con un utente amministratore globale. In genere si tratta dell'account usato per iscriversi per Microsoft 365.
2. Nel riquadro di spostamento sinistro passare a <a href="https://admin.teams.microsoft.com/locations" target="_blank">**Indirizzi** **LocationsEmergency** > </a>.
3. Fare clic su **Aggiungi**.
4. Immettere un nome e una descrizione per la posizione.
5. Selezionare il paese o l'area geografica e quindi immettere l'indirizzo.

   > [!NOTE]
   > In Belgio, Francia, Germania, Irlanda, Paesi Bassi e Spagna è importante comprendere che per attivare correttamente un numero di telefono in Microsoft 365 o Office 365, l'indirizzo configurato nella posizione di emergenza, usata per acquisire il numero, deve corrispondere al codice di area del numero di telefono.

6. Se l'indirizzo non viene trovato e si vuole modificarlo manualmente, attivare **Modifica l'indirizzo manualmente**.
7. Fare clic su **Salva**.

> [!div class="nextstepaction"]
> [Passaggio successivo: Configurare i numeri di telefono](set-up-phone-numbers.md)
