---
title: Piani per chiamate in Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
f1.keywords:
- NOCSH
ms.reviewer: crowe
search.appverid: MET150
description: Determinare il piano per le chiamate del sistema telefonico Microsoft più adatto alla tua organizzazione in Cloud Voice in Teams.
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: e11c6f6cbb53808ba259afd90420ac9855c9731d
ms.sourcegitcommit: d87991ed2d3e4d70edb048378763a17ff689b710
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/07/2022
ms.locfileid: "66682475"
---
# <a name="which-calling-plan-is-right-for-you"></a>Qual è il piano di chiamata adatto alle proprie esigenze?

Hai completato la [guida introduttiva](get-started-with-teams-quick-start.md). Si è implementato Teams nell'organizzazione, con [chat, team, canali e app](deploy-chat-teams-channels-microsoft-teams-landing-page.md). Forse hai distribuito [riunioni & conferenze](deploy-meetings-microsoft-teams-landing-page.md). Ora sei pronto per aggiungere carichi di lavoro vocali cloud e hai deciso di usare Microsoft Phone System con piano per chiamate per connetterti alla rete PSTN (Public Switched Telephone Network).

Questo articolo descrive le decisioni di distribuzione di base per i piani per chiamate, oltre a considerazioni aggiuntive che può essere necessario configurare in base alle esigenze dell'organizzazione. È anche consigliabile leggere [Cloud Voice in Microsoft Teams](cloud-voice-landing-page.md) per altre informazioni sulle offerte di voce cloud di Microsoft.

## <a name="learn-more-about-calling-plans"></a>Scopri di più sui Piani per chiamate

Negli articoli seguenti vengono fornite ulteriori informazioni sulla distribuzione e l'utilizzo dei piani per chiamate Microsoft:

- [Sistema telefonico in Microsoft 365 o Office 365](what-is-phone-system-in-office-365.md)
- [Piani per chiamate per Microsoft 365 o Office 365](calling-plans-for-office-365.md)
- [Configurare i piani per chiamate](set-up-calling-plans.md)

## <a name="core-deployment-decisions"></a>Decisioni chiave per la distribuzione

Per utilizzare Microsoft come gestore di telefonia, devi ottenere le licenze per il Piano per chiamate e assegnarle agli utenti del Sistema telefonico.

Sono disponibili due tipi di Piani per chiamate:

- Piani per chiamate nazionali
- Piani per chiamate internazionali

|Chiedersi|Azione |
|------------|-------|
|I Piani per chiamate sono disponibili nella mia area? Quali posizioni degli utenti avranno il servizio Piano per chiamate? | Per ulteriori informazioni, vedi [Disponibilità del paese e dell'area geografica per i piani per audioconferenze e chiamate](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md). |
Gli utenti hanno bisogno di chiamate internazionali? | Per altre informazioni, vedere [Piani per chiamate per Microsoft 365 o Office 365](calling-plans-for-office-365.md). |
Gli utenti hanno licenze per Piani per chiamate? | Per acquistare e assegnare licenze, vedere [Passaggio 2: Acquistare e assegnare licenze](set-up-calling-plans.md#step-2-buy-and-assign-licenses). |
Ognuno dei miei utenti ha un numero di telefono di chiamata diretta verso l'interno (DID)? | Per ottenere i numeri di telefono, vedi [Passaggio 3: Ottenere numeri di telefono](set-up-calling-plans.md#step-3-get-phone-numbers). |
|||

### <a name="transfer-phone-numbers-to-microsoft-365-or-office-365"></a>Trasferire numeri di telefono in Microsoft 365 o Office 365

È facile trasferire i numeri di telefono dal provider di servizi corrente a Teams. Dopo il trasferimento dei numeri di telefono in Teams, Microsoft diventa il tuo provider di servizi e ti addebiterà i numeri di telefono. Per altre informazioni, vedere [Trasferire numeri di telefono in Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).

### <a name="phone-numbers-and-emergency-locations"></a>Numeri di telefono e posizioni di emergenza

Con i Piani per chiamate in Microsoft 365 o Office 365, ogni utente dell'organizzazione deve avere un numero di telefono univoco di chiamata diretta diretta (DID) e un indirizzo di emergenza convalidato corrispondente. Puoi anche specificare una posizione per gli interventi di emergenza all'interno dell'indirizzo per gli interventi di emergenza (ad esempio, un numero di ufficio o un numero di piano).

|Chiedersi|Azione |
|:------------|:-------|
|Quanto è dettagliato l'indirizzo per gli interventi di emergenza e le informazioni sulla posizione? |Per altre informazioni, vedi [Che cosa sono le posizioni, gli indirizzi e il routing delle chiamate per gli interventi di emergenza?](/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing).

### <a name="calling-identity"></a>Identità chiamante

Per impostazione predefinita, tutte le chiamate in uscita usano il numero di telefono assegnato come identità chiamante (ID chiamante). Il destinatario della chiamata può velocemente identificare e decidere se accettare o rifiutare la chiamata.

|Chiedersi|Azione |
|:------------|:-------|
|Si vuole mascherare o disabilitare l'ID chiamante? | Per modificare o bloccare l'ID chiamante, vedere [Impostare l'ID chiamante per un utente](set-the-caller-id-for-a-user.md). |
|||
