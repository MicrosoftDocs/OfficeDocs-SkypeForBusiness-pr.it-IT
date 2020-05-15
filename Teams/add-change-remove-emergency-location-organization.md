---
title: Aggiungere, modificare, rimuovere posizioni di emergenza
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
description: "Informazioni su come aggiungere, modificare o rimuovere una posizione di emergenza per l'organizzazione nell'interfaccia di amministrazione di Microsoft teams. "
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 72730a326c6239b195d77f8a7bdde1b376da646f
ms.sourcegitcommit: 000515147632c6278bcda4505a1038014dda8e2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "44232487"
---
# <a name="add-change-or-remove-an-emergency-location-for-your-organization"></a>Aggiungere, modificare o rimuovere un percorso per l'organizzazione di emergenza

Una posizione di emergenza deve essere associata a un numero di telefono, ma quando ciò accade può variare tra paesi e aree geografiche. Ad esempio, negli Stati Uniti è necessario associare un percorso di emergenza quando si assegna il numero di telefono all'utente. Nel Regno Unito è necessario associare un percorso di emergenza al numero di telefono quando si ottengono i numeri di telefono da Office 365 o si trasferiscono i numeri di telefono dal provider di servizi corrente.

Indipendentemente dal paese o dall'area geografica in cui ci si trova, è possibile aggiungere una posizione o un luogo in un luogo di emergenza e rimuovere una posizione di emergenza. A seconda del numero di posizioni fisiche nell'organizzazione, è possibile creare posizioni per edifici, pavimenti e uffici. Vedere [gestire le chiamate di emergenza](what-are-emergency-locations-addresses-and-call-routing.md).
  
Per informazioni su come ottenere un piano per le chiamate e sulla quantità di costi, vedere licenze per i [componenti aggiuntivi](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)per i team.

È possibile gestire le posizioni di emergenza per l'organizzazione nell'interfaccia di amministrazione di Microsoft teams oppure usando PowerShell.
  
## <a name="add-an-emergency-location"></a>Aggiungere una posizione di emergenza

### <a name="using-the-microsoft-teams-admin-center"></a>Usando l'interfaccia di amministrazione di Microsoft Teams.

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams **fare clic su**  >  **indirizzi di emergenza**.
2. Fare clic su **Aggiungi posizione**.
3. Immettere un nome e una descrizione per la posizione.
4. Selezionare il paese o l'area geografica e quindi immettere l'indirizzo.

   > [!NOTE]
   > In Belgio, Francia, Germania, Irlanda, Paesi Bassi e Spagna è importante capire che per attivare correttamente un numero di telefono in Office 365 l'indirizzo impostato nella posizione di emergenza, usato per acquisire il numero, deve corrispondere al prefisso del numero di telefono.
5. Se l'indirizzo non viene trovato e si vuole modificare manualmente l'indirizzo, attivare **Consenti di modificare manualmente la maschera di indirizzo se non è possibile trovare l'indirizzo selezionato**.
6. Fare clic su **Salva**.

### <a name="using-powershell"></a>Utilizzo di PowerShell

Vedere [New-CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/new-csonlineliscivicaddress).
    
## <a name="change-an-emergency-location"></a>Modificare la posizione per gli interventi di emergenza

### <a name="using-the-microsoft-teams-admin-center"></a>Usando l'interfaccia di amministrazione di Microsoft Teams.

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams **fare clic su**  >  **indirizzi di emergenza**.
2. Nell'elenco selezionare la posizione che si vuole modificare e quindi fare clic su **modifica**.
3. Apportare le modifiche desiderate.
4. Fare clic su **Salva**.

> [!NOTE]
> È possibile modificare le informazioni relative all'indirizzo per una posizione solo se l'indirizzo non è convalidato. Se l'indirizzo è già convalidato ed è necessario modificare l'indirizzo, eliminare la posizione e quindi creare una nuova posizione con l'indirizzo corretto.

### <a name="using-powershell"></a>Utilizzo di PowerShell

Vedere [set-CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/set-csonlineliscivicaddress).
    
## <a name="remove-an-emergency-location"></a>Rimuovere una posizione di emergenza

### <a name="using-the-microsoft-teams-admin-center"></a>Usando l'interfaccia di amministrazione di Microsoft Teams.

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams **fare clic su**  >  **indirizzi di emergenza**.
2. Nell'elenco selezionare la posizione che si desidera rimuovere e quindi fare clic su **Elimina**.

### <a name="using-powershell"></a>Utilizzo di PowerShell

Vedere [Remove-CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/remove-csonlineliscivicaddress).

## <a name="related-topics"></a>Argomenti correlati

- [Gestire le chiamate di emergenza](what-are-emergency-locations-addresses-and-call-routing.md)
- [Aggiungere, modificare o rimuovere un luogo per una posizione di emergenza per l'organizzazione](add-change-remove-emergency-place-organization.md)
- [Gestire i numeri di telefono per la propria organizzazione](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Termini e condizioni per le chiamate al numero di emergenza](/microsoftteams/emergency-calling-terms-and-conditions)
