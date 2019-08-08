---
title: Usare il componente aggiuntivo riunione di Microsoft teams in Outlook
author: ChuckEdmonson
ms.author: chucked
manager: serdars
audience: Admin
ms.date: 06/25/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
localization_priority: Normal
search.appverid: MET150
description: Microsoft teams installa un componente aggiuntivo in Outlook che consente agli utenti di pianificare una riunione di Teams da Outlook.
ms.custom:
- NewAdminCenter_Update
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8e2c7bae819037d0140fab1fed3625e250b8a4c1
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36242064"
---
<a name="use-the-teams-meeting-add-in-in-outlook"></a>Usare il componente aggiuntivo riunione teams in Outlook
=======================================

Il componente aggiuntivo riunione teams consente agli utenti di pianificare una riunione Teams da Outlook. Il componente aggiuntivo è disponibile per Outlook in Windows, Mac, Web e mobile.

## <a name="teams-meeting-add-in-in-outlook-for-windows"></a>Componente aggiuntivo riunione teams in Outlook per Windows

Il componente aggiuntivo riunione teams viene installato automaticamente per gli utenti che dispongono di Microsoft teams e Office 2010, Office 2013 o Office 2016 installato nel PC Windows. Gli utenti vedranno il componente aggiuntivo riunione teams sulla barra multifunzione del calendario di Outlook.

![Screenshot del componente aggiuntivo riunione teams sulla barra multifunzione di Outlook](media/Teams-add-in-for-Outlook.png)

> [!NOTE]
> - Se gli utenti non vedono il componente aggiuntivo riunione teams, indicano loro di chiudere Outlook e teams, quindi riavviare prima il client teams, quindi accedere a teams e quindi riavviare il client Outlook in questo ordine specifico.
> - Gli utenti di Windows 7 devono installare l' [aggiornamento per Universal C Runtime in Windows](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows) in Windows per il componente aggiuntivo riunione teams per il lavoro.

## <a name="teams-meeting-add-in-in-outlook-for-mac"></a>Componente aggiuntivo riunione teams in Outlook per Mac

Il pulsante riunione teams in Outlook per Mac verrà visualizzato nella barra multifunzione di Outlook per Mac se Outlook è in uso per la build di produzione 16.24.414.0 e versioni successive.

Le coordinate della riunione (i numeri di collegamento e di accesso esterno per i team) verranno aggiunte all'invito alla riunione dopo che l'utente ha fatto clic su **Invia**.  

## <a name="teams-meeting-add-in-in-outlook-web-app"></a>Componente aggiuntivo riunione teams in Outlook Web App

Il pulsante riunioni teams in Outlook Web App verrà visualizzato come parte della nuova creazione di eventi se l'utente si trova in una versione iniziale del nuovo Outlook sul Web. Vedere il [Blog di Outlook](https://techcommunity.microsoft.com/t5/Outlook-Blog/Designed-to-be-fast-The-Outlook-on-the-web-user-experience-gets/ba-p/234909?utm_source=t.co&utm_medium=referral) per informazioni su come gli utenti possono provare la versione iniziale del nuovo Outlook sul Web.

![Screenshot del componente aggiuntivo riunione teams in Outlook Web App](media/teams-meeting-add-in-web.png)

Le coordinate della riunione (i numeri di collegamento e di accesso esterno per i team) verranno aggiunte all'invito alla riunione dopo che l'utente ha fatto clic su **Invia**.  

## <a name="teams-meeting-add-in-in-outlook-mobile-ios-and-android"></a>Componente aggiuntivo riunione teams in Outlook Mobile (iOS e Android)

Il pulsante riunione teams viene visualizzato nelle build più recenti dell'app Outlook iOS e Android.

![Screenshot del componente aggiuntivo riunione teams in Outlook Mobile](media/teams-meeting-add-in-mobile.png)

Le coordinate della riunione (i numeri di collegamento e di accesso esterno per i team) verranno aggiunte all'invito alla riunione dopo che l'utente ha fatto clic su **Invia**.  

## <a name="teams-meeting-add-in-in-and-findtime-for-outlook"></a>Componente aggiuntivo riunione teams in e FindTime per Outlook
FindTime è un componente aggiuntivo per Outlook che consente agli utenti di raggiungere un consenso per un periodo di riunione tra le aziende. Quando gli invitati alla riunione hanno fornito i loro orari preferiti, FindTime invia l'invito alla riunione per conto dell'utente. Se l'opzione **riunione online** è selezionata in FindTime, FindTime programmerà una riunione Skype for business o Microsoft teams. FindTime utilizzerà l'impostazione impostata dall'organizzazione come canale di riunione online predefinito.

> [!NOTE]  
> Se è stata salvata un'impostazione di Skype for business nel [dashboard di Findtime](https://findtime.microsoft.com/UserDashboard), Findtime utilizzerà quella invece di Microsoft teams. Se si vuole usare Microsoft teams, eliminare l'impostazione Skype for business nel dashboard.

Per altre informazioni, vedere [pianificare le riunioni con FindTime](https://support.office.com/article/scheduling-meetings-with-findtime-4dc806ed-fde3-4ea7-8c5e-b5d1fddab4a6) .

## <a name="authentication-requirements"></a>Requisiti di autenticazione

Il componente aggiuntivo riunione teams richiede agli utenti di accedere a teams con l'autenticazione moderna. Se gli utenti non usano questo metodo per accedere, saranno comunque in grado di usare il client teams, ma non saranno in grado di pianificare le riunioni online di teams usando il componente aggiuntivo per Outlook. Per risolvere questo problema, è possibile eseguire una delle operazioni seguenti:

- Se l'autenticazione moderna non è configurata per l'organizzazione, è necessario configurare l'autenticazione moderna.
- Se è stata configurata l'autenticazione moderna, ma la finestra di dialogo è stata annullata, è consigliabile richiedere agli utenti di accedere di nuovo con l'autenticazione a più fattori.

Per ulteriori informazioni su come configurare l'autenticazione, vedere [modelli di identità e autenticazione in Microsoft teams](identify-models-authentication.md).

## <a name="enable-private-meetings"></a>Abilitare riunioni private

**Consenti la pianificazione per le riunioni private** deve essere abilitata nell'interfaccia di amministrazione di Microsoft teams per il componente aggiuntivo per la distribuzione. Nell'interfaccia di amministrazione passare a**criteri riunione** **riunioni** > e, nella sezione **generale** , attivare o disattivare la **pianificazione delle riunioni private** .

![Screenshot delle impostazioni nell'interfaccia di amministrazione di Microsoft teams.](media/teams-add-in-for-outlook-image1.png)

Il client teams installa il componente aggiuntivo corretto determinando se gli utenti necessitano della versione a 32 bit o 64 bit.

> [!NOTE]
> Gli utenti potrebbero dover riavviare Outlook dopo un'installazione o un aggiornamento di teams per ottenere il componente aggiuntivo più recente.

## <a name="teams-upgrade-policy-and-the-teams-meeting-add-in-for-outlook"></a>Criteri di aggiornamento dei team e il componente aggiuntivo riunione team per Outlook

I clienti possono [scegliere il viaggio di aggiornamento da Skype for business a teams](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md). Gli amministratori del tenant possono usare la modalità di coesistenza di teams per definire questo viaggio per gli utenti. Gli amministratori del tenant hanno la possibilità di consentire agli utenti di usare teams insieme a Skype for business (modalità isole). 

Quando gli utenti che si trovano in modalità Isola pianificano una riunione in Outlook, in genere si aspettano di poter scegliere se pianificare una riunione di Skype for business o di teams. In Outlook sul Web, Outlook Windows e Outlook Mac, gli utenti possono visualizzare i componenti aggiuntivi Skype for business e teams in modalità Islands. A causa di alcune limitazioni della versione iniziale, Outlook Mobile può supportare solo la creazione di riunioni Skype for business **o** teams. Per informazioni dettagliate, vedere la tabella seguente.

| Modalità di coesistenza nell'interfaccia di amministrazione di Teams | Provider di riunioni predefinito in Outlook Mobile |
| --------------------------------------|---------------------------------------------|
| Isole | Skype for business |
| Solo Skype for business | Skype for business |
| Collaborazione tra Skype for business e teams | Skype for business |
| Skype for business con la collaborazione e le riunioni di Teams | Squadre |
| Solo Teams | Squadre |

## <a name="other-considerations"></a>Altre considerazioni

Il componente aggiuntivo riunione teams è ancora in costruzione, quindi tieni presente quanto segue:

- Il componente aggiuntivo è per le riunioni pianificate con partecipanti specifici, non per le riunioni in un canale. Le riunioni di canale devono essere pianificate all'interno di teams.
- Il componente aggiuntivo non funzionerà se un proxy di autenticazione si trova nel percorso di rete dei servizi PC e teams dell'utente.
- Gli utenti non possono pianificare eventi dinamici dall'interno di Outlook. Accedere a teams per pianificare gli eventi dinamici. Per altre informazioni, vedere [che cosa sono gli eventi live di Microsoft teams?](teams-live-events/what-are-teams-live-events.md).

## <a name="troubleshooting"></a>Risoluzione dei problemi

Se non è possibile installare il componente aggiuntivo riunione teams per Outlook, provare a eseguire questi passaggi per la risoluzione dei problemi.

- Verificare che siano stati applicati tutti gli aggiornamenti disponibili per il client desktop Outlook.
- Riavviare il client desktop teams.
- Disconnettersi e quindi accedere di nuovo al client desktop teams.
- Riavviare il client desktop di Outlook. Verificare che Outlook non sia in uso in modalità amministratore.
- Verificare che il nome dell'account utente connesso non contenga spazi. (Si tratta di un problema noto e verrà risolto in un aggiornamento futuro).
- Verificare che Single Sign-on (SSO) sia abilitato.

Se l'amministratore ha configurato Microsoft Exchange per [controllare l'accesso a Exchange Web Server (EWS)](https://docs.microsoft.com/en-us/exchange/client-developer/exchange-web-services/how-to-control-access-to-ews-in-exchange), un delegato non potrà programmare una riunione di teams per conto del boss. La soluzione per questa configurazione è in fase di sviluppo e verrà rilasciata in futuro. 

Per informazioni generali su come disabilitare i componenti aggiuntivi, vedere [visualizzare, gestire e installare componenti aggiuntivi nelle applicazioni di Office](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D).

Leggi altre informazioni sulle [riunioni e le chiamate in Microsoft teams](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8).
