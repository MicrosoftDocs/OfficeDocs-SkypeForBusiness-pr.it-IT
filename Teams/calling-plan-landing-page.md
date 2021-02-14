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
description: Determinare quale piano per le chiamate del sistema telefonico Microsoft sarà più adatto per l'organizzazione su Cloud Voice in Teams.
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 71fe92646a3a2976e9a4d393e54ea56a7669b400
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031852"
---
# <a name="which-calling-plan-is-right-for-you"></a>Qual è il piano di chiamata adatto alle proprie esigenze? 

La guida introduttiva [è stata completata.](get-started-with-teams-quick-start.md) Si è implementato Teams nell'organizzazione, con [chat, team, canali e app](deploy-chat-teams-channels-microsoft-teams-landing-page.md). Potresti aver distribuito Riunioni [o conferenze &.](deploy-meetings-microsoft-teams-landing-page.md) Ora sei pronto per aggiungere carichi di lavoro vocali nel cloud e hai deciso di usare il Sistema telefonico Microsoft con piano per le chiamate per connetterti alla rete PSTN (Public Switched Telephone Network). 

Questo articolo descrive le decisioni di distribuzione di base per i piani per chiamate, oltre a considerazioni aggiuntive che è possibile configurare, in base alle esigenze dell'organizzazione. Per altre informazioni sulle offerte vocali cloud di Microsoft, è consigliabile leggere anche [Cloud Voice in Microsoft Teams.](cloud-voice-landing-page.md)


## <a name="learn-more-about-calling-plans"></a>Ulteriori informazioni sui Piani per chiamate

Gli articoli seguenti forniscono altre informazioni sulla distribuzione e l'utilizzo dei Piani per chiamate Microsoft:

- [Sistema telefonico in Microsoft 365 o Office 365](what-is-phone-system-in-office-365.md)
- [Piani per chiamate per Microsoft 365 o Office 365](calling-plans-for-office-365.md)
- [Configurare i piani per chiamate](set-up-calling-plans.md)


## <a name="core-deployment-decisions"></a>Decisioni chiave per la distribuzione

Per utilizzare Microsoft come gestore telefonico, è necessario ottenere le licenze del Piano per chiamate e assegnarle agli utenti del Sistema telefonico. 

Sono disponibili due tipi di Piani per chiamate:

- Piani per chiamate nazionali 
- Piani per chiamate nazionali e internazionali

|Chiedersi|Azione |
|------------|-------|
|I Piani per chiamate sono disponibili nella mia area? Quali località utente hanno il servizio Piano per chiamate? | Per ulteriori informazioni, consulta La [disponibilità del Paese e dell'area geografica per Audioconferenze e Piani per chiamate.](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) | 
Gli utenti devono effettuare chiamate internazionali? | Per ulteriori informazioni, consulta [Piani per chiamate per Microsoft 365 o Office 365.](calling-plans-for-office-365.md) |
Gli utenti hanno licenze di Piani per chiamate? | Per acquistare e assegnare licenze, vedere [il passaggio 2: Acquistare e assegnare licenze.](set-up-calling-plans.md#step-2-buy-and-assign-licenses) |
Gli utenti hanno ciascuno un numero di telefono di chiamata diretta verso l'interno (DID)? | Per ottenere i numeri di telefono, [vedi Passaggio 3: Ottenere i numeri di telefono.](set-up-calling-plans.md#step-3-get-phone-numbers) |
|||

### <a name="transfer-phone-numbers-to-microsoft-365-or-office-365"></a>Trasferire numeri di telefono a Microsoft 365 o Office 365

È facile trasferire i numeri di telefono dal provider di servizi corrente a Teams. Dopo il portabilità dei numeri di telefono in Teams, Microsoft diventa il tuo provider di servizi e ti addebita i numeri di telefono. Per altre informazioni, vedere [Trasferire numeri di telefono in Teams.](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)


### <a name="phone-numbers-and-emergency-locations"></a>Numeri di telefono e posizioni di emergenza

Con i Piani per chiamate in Microsoft 365 o Office 365, ogni utente dell'organizzazione deve avere un numero di telefono DID (Direct Inward Dial) univoco e un indirizzo di emergenza convalidato corrispondente. Puoi anche specificare una posizione per gli interventi di emergenza all'interno dell'indirizzo per gli interventi di emergenza (ad esempio, un numero di ufficio o un numero di piano). 

|Chiedersi|Azione |
|:------------|:-------|
|Quanto sono dettagliati i dati sull'indirizzo e sulla posizione per gli interventi di emergenza? |Per ulteriori informazioni, consulta Cosa sono il routing delle chiamate, gli indirizzi e le posizioni [per gli interventi di emergenza?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing)


### <a name="calling-identity"></a>Identità delle chiamate

Per impostazione predefinita, tutte le chiamate in uscita usano il numero di telefono assegnato come identità chiamante (ID chiamante). Il destinatario della chiamata può velocemente identificare e decidere se accettare o rifiutare la chiamata.

|Chiedersi|Azione |
|:------------|:-------|
|Si vuole mascherare o disabilitare l'ID chiamante? | Per modificare o bloccare l'ID chiamante, vedere [Impostare l'ID chiamante per un utente.](set-the-caller-id-for-a-user.md) |
|||




