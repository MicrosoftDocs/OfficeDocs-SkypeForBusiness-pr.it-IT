---
title: Piani di chiamata in Microsoft Teams
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
description: Determinare quale piano di chiamate di sistema telefonico Microsoft migliorerà la propria organizzazione con la voce cloud in teams.
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

Hai completato l' [Introduzione](get-started-with-teams-quick-start.md). Si è implementato Teams nell'organizzazione, con [chat, team, canali e app](deploy-chat-teams-channels-microsoft-teams-landing-page.md). Forse hai distribuito [riunioni & conferenze](deploy-meetings-microsoft-teams-landing-page.md). Ora si è pronti per aggiungere carichi di lavoro cloud Voice e si è deciso di usare il sistema telefonico Microsoft con il piano chiamate per connettersi alla rete PSTN (Public Switched Telephone Network). 

In questo articolo vengono illustrate le decisioni di distribuzione principali per i piani di chiamata e altre considerazioni che è consigliabile configurare, in base alle esigenze dell'organizzazione. Per altre informazioni sulle offerte vocali di Microsoft Cloud, dovresti anche leggere [cloud Voice in Microsoft teams](cloud-voice-landing-page.md) .


## <a name="learn-more-about-calling-plans"></a>Ulteriori informazioni sui piani per le chiamate

Gli articoli seguenti includono ulteriori informazioni sulla distribuzione e l'uso di piani di chiamata Microsoft:

- [Sistema telefonico in Microsoft 365 o Office 365](what-is-phone-system-in-office-365.md)
- [Piani di chiamata per Microsoft 365 o Office 365](calling-plans-for-office-365.md)
- [Configurare i piani per chiamate](set-up-calling-plans.md)


## <a name="core-deployment-decisions"></a>Decisioni chiave per la distribuzione

Per usare Microsoft come gestore di telefonia, è necessario ottenere le licenze per il piano di chiamata e assegnarle agli utenti del sistema telefonico. 

Sono disponibili due tipi di piani per le chiamate:

- Piani per chiamate nazionali 
- Piani per chiamate nazionali e internazionali

|Chiedersi|Azione |
|------------|-------|
|I piani di chiamata sono disponibili nell'area personale? Quali posizioni utente avranno il servizio di piano chiamante? | Per altre informazioni, vedere [disponibilità di paesi e aree geografiche per i piani di audioconferenza e chiamate](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md). | 
I miei utenti hanno bisogno di chiamate internazionali? | Per altre informazioni, vedere [chiamare piani per Microsoft 365 o Office 365](calling-plans-for-office-365.md). |
Gli utenti hanno licenze per i piani di chiamata? | Per acquistare e assegnare licenze, vedere [passaggio 2: acquistare e assegnare licenze](set-up-calling-plans.md#step-2-buy-and-assign-licenses). |
I miei utenti hanno ciascuno un numero di telefono diretto verso l'interno? | Per ottenere i numeri di telefono, vedere [passaggio 3: ottenere i numeri di telefono](set-up-calling-plans.md#step-3-get-phone-numbers). |
|||

### <a name="transfer-phone-numbers-to-microsoft-365-or-office-365"></a>Trasferire i numeri di telefono a Microsoft 365 o Office 365

È facile trasferire i numeri di telefono dal provider di servizi corrente in teams. Dopo aver convertito i numeri di telefono in teams, Microsoft diventerà il proprio provider di servizi e gli verrà addebitato il numero di telefono. Per altre informazioni, vedere [trasferire i numeri di telefono in teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).


### <a name="phone-numbers-and-emergency-locations"></a>Numeri di telefono e posizioni di emergenza

Con i piani per le chiamate in Microsoft 365 o Office 365, ogni utente dell'organizzazione deve avere un numero di telefono univoco diretto (DID) e un indirizzo di emergenza convalidato corrispondente. È anche possibile specificare una posizione di emergenza all'interno dell'indirizzo di emergenza, ad esempio un numero di ufficio o un numero di piano. 

|Chiedersi|Azione |
|:------------|:-------|
|Come si vuole che siano dettagliate le informazioni sull'indirizzo di emergenza e sulla posizione? |Per altre informazioni, vedere [quali sono le posizioni di emergenza, gli indirizzi e il routing delle chiamate?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing).


### <a name="calling-identity"></a>Chiamata dell'identità

Per impostazione predefinita, tutte le chiamate in uscita usano il numero di telefono assegnato come identità di chiamata (ID chiamante). Il destinatario della chiamata può identificare rapidamente il chiamante e decidere se accettare o rifiutare la chiamata.

|Chiedersi|Azione |
|:------------|:-------|
|Si vuole mascherare o disabilitare l'ID chiamante? | Per modificare o bloccare l'ID chiamante, vedere [impostare l'ID chiamante per un utente](set-the-caller-id-for-a-user.md). |
|||




