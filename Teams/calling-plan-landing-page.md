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
description: Determinare quale Telefono Microsoft di chiamate di sistema migliore per l'organizzazione su Cloud Voice in Teams.
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: b88af706f79dd195e2f9363ff45e586a1123686f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102732"
---
# <a name="which-calling-plan-is-right-for-you"></a>Qual è il piano di chiamata adatto alle proprie esigenze? 

È stata completata la [guida introduttiva.](get-started-with-teams-quick-start.md) Si è implementato Teams nell'organizzazione, con [chat, team, canali e app](deploy-chat-teams-channels-microsoft-teams-landing-page.md). È possibile che sia stata distribuita [una conferenza & riunioni.](deploy-meetings-microsoft-teams-landing-page.md) Ora si è pronti per aggiungere carichi di lavoro vocali cloud e si è deciso di usare Telefono Microsoft System with Calling Plan per connettersi alla rete PSTN (Public Switched Telephone Network). 

Questo articolo descrive le decisioni di base relative alla distribuzione per i piani per chiamate e altre considerazioni da configurare, in base alle esigenze dell'organizzazione. È anche consigliabile leggere [Cloud Voice in Microsoft Teams](cloud-voice-landing-page.md) per altre informazioni sulle offerte vocali cloud di Microsoft.


## <a name="learn-more-about-calling-plans"></a>Altre informazioni sui Piani per chiamate

Gli articoli seguenti forniscono altre informazioni sulla distribuzione e l'uso di Piani per chiamate Microsoft:

- [Sistema telefonico in Microsoft 365 o Office 365](what-is-phone-system-in-office-365.md)
- [Piani per chiamate Microsoft 365 o Office 365](calling-plans-for-office-365.md)
- [Configurare i piani per chiamate](set-up-calling-plans.md)


## <a name="core-deployment-decisions"></a>Decisioni chiave per la distribuzione

Per usare Microsoft come gestore di telefonia, è necessario ottenere le licenze del piano per chiamate e assegnarle agli utenti Sistema telefonico telefonici. 

Sono disponibili due tipi di Piani per chiamate:

- Piani per chiamate nazionali 
- Piani per chiamate nazionali e internazionali

|Chiedersi|Azione |
|------------|-------|
|I Piani per chiamate sono disponibili nella mia area? Quali località utente avranno il servizio Piano per le chiamate? | Per altre informazioni, vedere [Disponibilità di paesi e aree geografica per audioconferenze e piani per chiamate.](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) | 
Gli utenti hanno bisogno di chiamate internazionali? | Per altre informazioni, vedere [Piani per chiamate Microsoft 365 o Office 365](calling-plans-for-office-365.md). |
Gli utenti hanno licenze per i Piani per chiamate? | Per acquistare e assegnare licenze, vedere [Passaggio 2: Acquistare e assegnare licenze.](set-up-calling-plans.md#step-2-buy-and-assign-licenses) |
Tutti gli utenti hanno un numero di telefono DID (Direct Inward Dial) ? | Per ottenere i numeri di telefono, vedere [Passaggio 3: Ottenere numeri di telefono](set-up-calling-plans.md#step-3-get-phone-numbers). |
|||

### <a name="transfer-phone-numbers-to-microsoft-365-or-office-365"></a>Trasferire i numeri di telefono Microsoft 365 o Office 365

È facile trasferire i numeri di telefono dal provider di servizi corrente a Teams. Dopo aver portato i numeri di telefono in Teams, Microsoft diventerà il provider di servizi e ti addebiterà tali numeri di telefono. Per altre informazioni, vedere [Trasferire i numeri di telefono Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).


### <a name="phone-numbers-and-emergency-locations"></a>Numeri di telefono e posizioni di emergenza

Con Piani per chiamate in Microsoft 365 o Office 365, ogni utente dell'organizzazione deve avere un numero di telefono DID (Direct InWard Dial) univoco e un indirizzo di emergenza convalidato corrispondente. È anche possibile specificare una posizione per gli interventi di emergenza all'interno dell'indirizzo di emergenza, ad esempio un numero di ufficio o un numero di piano. 

|Chiedersi|Azione |
|:------------|:-------|
|Quanto è dettagliato l'indirizzo di emergenza e le informazioni sulla posizione? |Per altre informazioni, vedere [Che cosa sono le località di emergenza, gli indirizzi e il routing delle chiamate?](/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing).


### <a name="calling-identity"></a>Identità chiamante

Per impostazione predefinita, tutte le chiamate in uscita usano il numero di telefono assegnato come identità chiamante (ID chiamante). Il destinatario della chiamata può velocemente identificare e decidere se accettare o rifiutare la chiamata.

|Chiedersi|Azione |
|:------------|:-------|
|Si vuole mascherare o disabilitare l'ID chiamante? | Per modificare o bloccare l'ID chiamante, vedere [Impostare l'ID chiamante per un utente.](set-the-caller-id-for-a-user.md) |
|||