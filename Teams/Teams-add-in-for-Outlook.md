---
title: Usare il componente aggiuntivo Riunione di Microsoft Teams in Outlook
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams installa un componente aggiuntivo in Outlook che consente agli utenti di pianificare una riunione di Teams da Outlook.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 26eb3af88b6e16de0535d25d4b5205a72626b7b2
ms.sourcegitcommit: df4dde0fe6ce9e26cb4b3da4e4b878538d31decc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/15/2020
ms.locfileid: "43521532"
---
<a name="use-the-teams-meeting-add-in-in-outlook"></a>Usare il componente aggiuntivo Riunione di Teams in Outlook
=======================================

Il componente aggiuntivo Riunione di Teams consente agli utenti di pianificare una riunione di Teams da Outlook. Il componente aggiuntivo è disponibile per Outlook in Windows, Mac, Web e dispositivi mobili.

## <a name="teams-meeting-add-in-in-outlook-for-windows"></a>Componente aggiuntivo Riunione di Teams in Outlook per Windows

Il componente aggiuntivo Riunione di Teams viene installato automaticamente per gli utenti che hanno Microsoft Teams e Office 2010, Office 2013 oppure Office 2016 nel loro PC Windows. Gli utenti vedranno il componente aggiuntivo Riunione di Teams sulla barra multifunzione del Calendario di Outlook.

![Screenshot del componente aggiuntivo Riunione di Teams sulla barra multifunzione di Outlook](media/Teams-add-in-for-Outlook.png)

> [!NOTE]
> - Ci sono altre considerazioni se l'organizzazione esegue sia team che Skype for business. In alcune circostanze, il componente aggiuntivo teams non è disponibile in Outlook. Per informazioni dettagliate, vedere [eseguire l'aggiornamento da Skype for business a teams](https://docs.microsoft.com/microsoftteams/upgrade-to-teams-on-prem-overview#meetings) .
> - Le autorizzazioni utente per eseguire il file Regsvr32.exe sono un requisito minimo per installare il componente aggiuntivo Riunione di Teams nel computer.
> - Se gli utenti non vedono il componente aggiuntivo Riunione di Teams, puoi chiedere loro di chiudere Outlook e Teams, quindi di riavviare prima il client Team, poi di accedere a Teams e infine di riavviare il client Outlook nell’ordine appena esposto.
> - Se si usa un'installazione di Office Outlook da Microsoft Store, il componente aggiuntivo Riunione di Teams non è supportato. Gli utenti che richiedono questo componente aggiuntivo possono installare la versione a portata di clic di Office, come descritto nell’articolo [Office su Windows 10 in modalità S](https://support.office.com/article/faq-office-on-windows-10-in-s-mode-717193b5-ff9f-4388-84c0-277ddf07fe3f).

## <a name="teams-meeting-add-in-in-outlook-for-mac"></a>Componente aggiuntivo Riunione di Teams in Outlook per Mac

Il pulsante Riunione di Teams in Outlook per Mac viene visualizzato nella barra multifunzione di Outlook per Mac se Outlook sta eseguendo la build di produzione 16.24.414.0 e versioni successive e se è attivato con un abbonamento al client Office 365.

Le coordinate della riunione, ossia il collegamento per unirsi a Teams e i numeri telefonici di accesso esterno, verranno aggiunte all'invito alla riunione dopo che l'utente avrà fatto clic su **Invia**.  

## <a name="teams-meeting-add-in-in-outlook-web-app"></a>Componente aggiuntivo Riunione di Teams in Outlook Web App

Il pulsante Riunioni di Teams in Outlook Web App verrà visualizzato come parte della creazione di un nuovo evento se l'utente possiede una versione precedente del nuovo Outlook sul web. Per informazioni su come gli utenti possono provare a usare la versione precedente del nuovo Outlook sul web, vedere il [Blog di Outlook](https://techcommunity.microsoft.com/t5/Outlook-Blog/Designed-to-be-fast-The-Outlook-on-the-web-user-experience-gets/ba-p/234909?utm_source=t.co&utm_medium=referral).

![Screenshot del componente aggiuntivo Riunione di Teams in Outlook Web App](media/teams-meeting-add-in-web.png)

Le coordinate della riunione, ossia il collegamento per unirsi a Teams e i numeri telefonici di accesso esterno, verranno aggiunte all'invito alla riunione dopo che l'utente avrà fatto clic su **Invia**.  

## <a name="teams-meeting-add-in-in-outlook-mobile-ios-and-android"></a>Componente aggiuntivo Riunione di Teams in Outlook Mobile (per iOS e Android)

Il pulsante Riunione di Teams compare nelle build più recenti dell'app di Outlook per iOS e Android.

![Screenshot del componente aggiuntivo Riunione di Teams in Outlook Mobile](media/teams-meeting-add-in-mobile.png)

Le coordinate della riunione, ossia il collegamento per unirsi a Teams e i numeri telefonici di accesso esterno, verranno aggiunte all'invito alla riunione dopo che l'utente avrà fatto clic su **Invia**.  

## <a name="teams-meeting-add-in-in-and-findtime-for-outlook"></a>Componente aggiuntivo Riunione di Teams in TrovaOrario per Outlook
TrovaOrario è un componente aggiuntivo per Outlook che aiuta gli utenti a raggiungere un consenso tra le aziende per stabilire l’orario di riunione. Una volta che gli invitati della riunione hanno fornito il loro orario preferito, TrovaOrario invia l'invito alla riunione per conto dell'utente. Se viene selezionata l'opzione **Riunione online** in TrovaOrario, verrà programmata una riunione di Skype for Business o di Microsoft Teams. (TrovaOrario userà qualsiasi opzione impostata dall'organizzazione come canale predefinito per le riunioni online.)

> [!NOTE]  
> Se è stato impostato Skype for Business nella [dashboard di TrovaOrario](https://findtime.microsoft.com/UserDashboard), verrà usata questa impostazione anziché Microsoft Teams. Se si vuole usare Microsoft Teams, eliminare l'opzione Skype for Business nella dashboard.

Per altre informazioni, vedere [Pianificare riunioni con TrovaOrario](https://support.office.com/article/scheduling-meetings-with-findtime-4dc806ed-fde3-4ea7-8c5e-b5d1fddab4a6).

## <a name="authentication-requirements"></a>Requisiti di autenticazione

Il componente aggiuntivo Riunione di Teams richiede agli utenti di accedere a Teams con l'Autenticazione moderna. Se gli utenti non usano questo metodo per accedere, saranno comunque in grado di usare il client teams, ma non saranno in grado di pianificare le riunioni online di teams usando il componente aggiuntivo per Outlook. È possibile correggere eseguendo una delle operazioni seguenti:

- Se l'Autenticazione moderna non è configurata per l'organizzazione, è consigliabile eseguirne la configurazione.
- Se l'Autenticazione moderna è configurata ma è stata annullata nella finestra di dialogo, è consigliabile richiedere agli utenti di eseguire di nuovo l'accesso con l'autenticazione a più fattori.

Per altre informazioni su come configurare l'autenticazione, vedere [Modelli di identità e autenticazione in Microsoft Teams](identify-models-authentication.md).

## <a name="enable-private-meetings"></a>Attivare riunioni private

È necessario attivare **Consenti pianificazione per le riunioni private** nell'interfaccia di amministrazione di Microsoft Teams per distribuire il componente aggiuntivo. Nell'interfaccia di amministrazione, andare su **Riunioni** > **Criteri riunione** e nella sezione **Generale**, infine attivare **Consenti la pianificazione di riunioni private**.

![Screenshot delle impostazioni dell'interfaccia di amministrazione di Microsoft Teams.](media/teams-add-in-for-outlook-image1.png)

Il client Teams installa il componente aggiuntivo corretto determinando se gli utenti hanno bisogno della versione a 32 o a 64 bit.

> [!NOTE]
> Gli utenti potrebbero dover riavviare Outlook dopo l'installazione o l'aggiornamento di Teams per ottenere il componente aggiuntivo più recente.

## <a name="teams-upgrade-policy-and-the-teams-meeting-add-in-for-outlook"></a>Criteri di aggiornamento di Teams e del componente aggiuntivo Riunione di Teams per Outlook

I clienti possono [scegliere il percorso di aggiornamento da Skype for Business a Teams](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md). Gli amministratori tenant possono usare la modalità di coesistenza di Teams per definire questo percorso per gli utenti. Gli amministratori tenant hanno la possibilità di consentire agli utenti di usare Teams insieme a Skype for Business (modalità Isole). 

Quando gli utenti in modalità Isole pianificano una riunione in Outlook, in genere prevedono di decidere se pianificare una riunione di Skype for Business o di Teams. In Outlook sul web, Outlook Windows e Outlook Mac, gli utenti possono vedere i componenti aggiuntivi di Skype for Business e Teams in modalità Isole. A causa di alcune limitazioni nel rilascio iniziale, Outlook Mobile supporta solo la creazione di riunioni di Skype for Business **o** di Teams. Per altri dettagli, vedere la tabella seguente.

| Modalità di coesistenza nell’interfaccia di amministrazione di Teams | Provider di riunioni predefinito in Outlook Mobile |
| --------------------------------------|---------------------------------------------|
| Isole | Skype for Business |
| Solo Skype for Business | Skype for Business |
| Collaborazione di Skype for Business con Teams | Skype for Business |
| Collaborazione e riunioni di Skype for Business con Teams | Teams |
| Solo Teams | Teams |

## <a name="other-considerations"></a>Altre considerazioni

Il componente aggiuntivo Riunione di Teams è ancora in fase di sviluppo, pertanto è importante tenere presente quanto segue:

- Il componente aggiuntivo è adatto a riunioni programmate con partecipanti specifici, non alle riunioni in un canale. Le riunioni nei canali devono essere programmate direttamente in Teams.
- Il componente aggiuntivo non funzionerà se un Proxy di autenticazione si trova nel percorso di rete relativo ai servizi di Teams e del PC dell'utente.
- Gli utenti non possono programmare gli eventi live all’interno di Outlook. Andare su Teams per pianificare gli eventi live. Per altre informazioni, vedere [Che cosa sono gli eventi live di Microsoft Teams?](teams-live-events/what-are-teams-live-events.md).

## <a name="troubleshooting"></a>Risoluzione dei problemi

Se non si riesce a trovare il componente aggiuntivo Riunione di Teams per Outlook per l'installazione, provare a eseguire questa procedura di risoluzione dei problemi.

- Assicurarsi che siano stati applicati tutti gli aggiornamenti disponibili per il client desktop di Outlook.
- Riavviare il client desktop di Teams.
- Disconnettersi e quindi eseguire di nuovo l'accesso al client desktop di Teams.
- Riavviare il client desktop di Outlook. Verificare che Outlook non sia in uso in modalità amministratore.
- Assicurarsi che il nome dell'account utente connesso non contenga spazi. (Si tratta di un problema noto che verrà risolto in un prossimo aggiornamento.)
- Assicurarsi che il Single Sign-On (SSO) sia abilitato.

Se l'amministratore ha configurato Microsoft Exchange per [controllare l'accesso a Exchange Web Server (EWS)](https://docs.microsoft.com/exchange/client-developer/exchange-web-services/how-to-control-access-to-ews-in-exchange), un eventuale delegato non potrà pianificare una riunione di Teams per conto del suo superiore. La soluzione per questa configurazione è in fase di sviluppo e verrà rilasciata in futuro. 

Per informazioni generali su come disabilitare i componenti aggiuntivi, vedere [Visualizzare, gestire e installare componenti aggiuntivi nei programmi di Office](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D).

Altre informazioni su [riunioni e chiamate in Microsoft Teams](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8).
