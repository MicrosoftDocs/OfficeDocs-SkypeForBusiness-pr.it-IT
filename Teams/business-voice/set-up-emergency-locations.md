---
title: Configurare le Microsoft 365 Business Voice per gli interventi di emergenza
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: Informazioni su come configurare le posizioni di emergenza per Microsoft 365 Business Voice.
appliesto:
- Microsoft Teams
ms.openlocfilehash: ade5e4d7ca978f2ed8690230e6a0636849155bc9da3a7602aa9d09710faa93d0
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54345513"
---
# <a name="step-1-set-up-a-business-voice-emergency-location"></a>Passaggio 1: Configurare una posizione di emergenza di Business Voice

Una posizione per gli interventi di emergenza viene usata quando qualcuno nell'organizzazione chiama i servizi di emergenza, come il fuoco, la polizia o l'eliambulanza. Quando una persona chiama un servizio di emergenza, l'indirizzo configurato come indirizzo di emergenza dell'organizzazione viene inviato al servizio. Questo passaggio configura la posizione principale per gli interventi di emergenza per l'organizzazione. Questa posizione verrà associata al numero di telefono principale dell'azienda in un passaggio successivo.

Se si hanno utenti in più posizioni, ad esempio uffici privati o uffici in altre città, è possibile configurare altre posizioni per gli interventi di emergenza. È anche possibile configurare posizioni specifiche all'interno di una posizione. I luoghi possono essere edifici, piani, uffici o altri luoghi in cui gli utenti possono essere in una posizione diversa. Dopo aver completato la configurazione iniziale di Business Voice, è possibile aggiungere altre posizioni e posizioni.

Il video seguente mostra come completare questi passaggi nell'interfaccia Teams di amministrazione.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWEZGE]

## <a name="add-an-emergency-location"></a>Aggiungere una posizione per gli interventi di emergenza

1. Aprire l Microsoft Teams di amministrazione di Microsoft Teams e accedere con un utente che è un amministratore globale (in genere si tratta dell'account usato per iscriversi per Microsoft 365).
1. Nel riquadro di spostamento sinistro passare a Posizioni <a href="https://admin.teams.microsoft.com/locations" target="_blank">   >  **indirizzi di emergenza.**</a>
1. Fare clic su **Aggiungi**.
1. Immettere un nome e una descrizione per la posizione.
1. Selezionare il paese o l'area geografica e quindi immettere l'indirizzo.

   > [!NOTE]
   > In Belgio, Francia, Germania, Irlanda, Paesi Bassi e Spagna è importante comprendere che per attivare correttamente un numero di telefono in Microsoft 365 o Office 365, l'indirizzo configurato nella posizione di emergenza, usata per acquisire il numero, deve corrispondere al codice di area del numero di telefono.

1. Se l'indirizzo non viene trovato e si vuole modificarlo manualmente, attivare **Modifica l'indirizzo manualmente.**
1. Fare clic su **Salva**.

> [!div class="nextstepaction"]
> [Passaggio successivo: Configurare i numeri di telefono](set-up-phone-numbers.md)
