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
ms.openlocfilehash: dc543096965a3abc51964c5006795cf385a4cb55
ms.sourcegitcommit: 34f407a6a40317056005e3bf38ce58f792c04810
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/19/2020
ms.locfileid: "46814102"
---
<a name="use-the-teams-meeting-add-in-in-outlook"></a>Usare il componente aggiuntivo Riunione di Teams in Outlook
=======================================

Il componente aggiuntivo Riunione di Teams consente agli utenti di pianificare una riunione di Teams da Outlook. Il componente aggiuntivo è disponibile per Outlook in Windows, Mac, Web e dispositivi mobili.

## <a name="teams-meeting-add-in-in-outlook-for-windows"></a>Componente aggiuntivo Riunione di Teams in Outlook per Windows

Il componente aggiuntivo riunione teams viene installato automaticamente per gli utenti che dispongono di Microsoft teams e Office 2013, Office 2016 o Office 2019 installato nel PC Windows. Gli utenti vedranno il componente aggiuntivo Riunione di Teams sulla barra multifunzione del Calendario di Outlook.

![Screenshot del componente aggiuntivo Riunione di Teams sulla barra multifunzione di Outlook](media/Teams-add-in-for-Outlook.png)

> [!NOTE]
> - Non esiste **alcun URL diretto** che si collega al componente aggiuntivo teams.
> - Ci sono altre considerazioni se l'organizzazione esegue sia team che Skype for business. In alcune circostanze, il componente aggiuntivo teams non è disponibile in Outlook. Per informazioni dettagliate, vedere [eseguire l'aggiornamento da Skype for business a teams](https://docs.microsoft.com/microsoftteams/upgrade-to-teams-on-prem-overview#meetings) .
> - Le autorizzazioni utente per eseguire il file Regsvr32.exe sono un requisito minimo per installare il componente aggiuntivo Riunione di Teams nel computer.
> - Se gli utenti non vedono il componente aggiuntivo Riunione di Teams, puoi chiedere loro di chiudere Outlook e Teams, quindi di riavviare prima il client Team, poi di accedere a Teams e infine di riavviare il client Outlook nell’ordine appena esposto.
> - Se si usa un'installazione di Office Outlook da Microsoft Store, il componente aggiuntivo Riunione di Teams non è supportato. Gli utenti che richiedono questo componente aggiuntivo possono installare la versione a portata di clic di Office, come descritto nell’articolo [Office su Windows 10 in modalità S](https://support.office.com/article/faq-office-on-windows-10-in-s-mode-717193b5-ff9f-4388-84c0-277ddf07fe3f).

## <a name="teams-meeting-add-in-in-outlook-for-mac"></a>Componente aggiuntivo Riunione di Teams in Outlook per Mac

Il pulsante riunione teams in Outlook per Mac verrà visualizzato nella barra multifunzione di Outlook per Mac se Outlook è in uso per la build di produzione 16.24.414.0 e versioni successive e viene attivato con un abbonamento a Microsoft 365 o Office 365 client.

Le coordinate della riunione, ossia il collegamento per unirsi a Teams e i numeri telefonici di accesso esterno, verranno aggiunte all'invito alla riunione dopo che l'utente avrà fatto clic su **Invia**.  

## <a name="teams-meeting-add-in-in-outlook-web-app"></a>Componente aggiuntivo Riunione di Teams in Outlook Web App

Il pulsante Riunioni di Teams in Outlook Web App verrà visualizzato come parte della creazione di un nuovo evento se l'utente possiede una versione precedente del nuovo Outlook sul web. Per informazioni su come gli utenti possono provare a usare la versione precedente del nuovo Outlook sul web, vedere il [Blog di Outlook](https://techcommunity.microsoft.com/t5/Outlook-Blog/Designed-to-be-fast-The-Outlook-on-the-web-user-experience-gets/ba-p/234909?utm_source=t.co&utm_medium=referral).

![Screenshot del componente aggiuntivo Riunione di Teams in Outlook Web App](media/teams-meeting-add-in-web.png)

Le coordinate della riunione, ossia il collegamento per unirsi a Teams e i numeri telefonici di accesso esterno, verranno aggiunte all'invito alla riunione dopo che l'utente avrà fatto clic su **Invia**.  

## <a name="teams-meeting-add-in-in-outlook-mobile-ios-and-android"></a>Componente aggiuntivo Riunione di Teams in Outlook Mobile (per iOS e Android)

Il pulsante Riunione di Teams compare nelle build più recenti dell'app di Outlook per iOS e Android.

![Screenshot del componente aggiuntivo Riunione di Teams in Outlook Mobile](media/teams-meeting-add-in-mobile.png)

Le coordinate della riunione, ossia il collegamento per unirsi a Teams e i numeri telefonici di accesso esterno, verranno aggiunte all'invito alla riunione dopo che l'utente avrà fatto clic su **Invia**.  

## <a name="teams-meeting-add-in-and-findtime-for-outlook"></a>Componente aggiuntivo riunione teams e FindTime per Outlook

FindTime è un componente aggiuntivo per Outlook che consente agli utenti di raggiungere il consenso in un periodo di riunione tra le aziende. Una volta che gli invitati della riunione hanno fornito il loro orario preferito, TrovaOrario invia l'invito alla riunione per conto dell'utente. Se viene selezionata l'opzione **Riunione online** in TrovaOrario, verrà programmata una riunione di Skype for Business o di Microsoft Teams. (TrovaOrario userà qualsiasi opzione impostata dall'organizzazione come canale predefinito per le riunioni online.)

> [!NOTE]  
> Se è stato impostato Skype for Business nella [dashboard di TrovaOrario](https://findtime.microsoft.com/UserDashboard), verrà usata questa impostazione anziché Microsoft Teams. Se si vuole usare Microsoft Teams, eliminare l'opzione Skype for Business nella dashboard.

Per altre informazioni, vedere [pianificare le riunioni con FindTime](https://support.office.com/article/scheduling-meetings-with-findtime-4dc806ed-fde3-4ea7-8c5e-b5d1fddab4a6).

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

Quando gli utenti in modalità Isole pianificano una riunione in Outlook, in genere prevedono di decidere se pianificare una riunione di Skype for Business o di Teams. In Outlook sul Web, Outlook Windows e Outlook Mac, gli utenti possono visualizzare i componenti aggiuntivi Skype for business e teams in modalità Islands per impostazione predefinita. È possibile configurare un'impostazione di criteri riunione teams per controllare se gli utenti in modalità isole possono usare solo il componente aggiuntivo riunione teams o sia la riunione teams che i componenti aggiuntivi per le riunioni di Skype for business.

A causa di alcune limitazioni nel rilascio iniziale, Outlook Mobile supporta solo la creazione di riunioni di Skype for Business **o** di Teams. Per altri dettagli, vedere la tabella seguente.

| Modalità di coesistenza nell’interfaccia di amministrazione di Teams | Provider di riunioni predefinito in Outlook Mobile |
| --------------------------------------|---------------------------------------------|
| Isole | Skype for Business |
| Solo Skype for Business | Skype for Business |
| Collaborazione di Skype for Business con Teams | Skype for Business |
| Collaborazione e riunioni di Skype for Business con Teams | Teams |
| Solo Teams | Teams |

### <a name="set-whether-users-in-islands-mode-can-only-use-the-teams-meeting-add-in-or-both-the-teams-meeting-and-skype-for-business-meeting-add-ins"></a>Imposta se gli utenti in modalità isole possono usare solo il componente aggiuntivo riunione teams o sia la riunione teams che i componenti aggiuntivi per riunioni Skype for business

Come amministratore, puoi configurare un'impostazione di criteri riunione teams per controllare quale componente aggiuntivo riunione di Outlook viene usato per *gli utenti che si trovano in modalità isole*. Puoi specificare se gli utenti possono usare solo il componente aggiuntivo riunione teams o sia la riunione teams che i componenti aggiuntivi per le riunioni di Skype for business per pianificare le riunioni in Outlook.

Puoi applicare questo criterio solo agli utenti che si trovano in modalità isole e avere il parametro **AllowOutlookAddIn** impostato su **true** nei criteri della riunione teams. Per istruzioni su come impostare questo criterio, vedere [impostare il provider della riunione per gli utenti in modalità isole](meeting-policies-in-teams.md#meeting-policy-settings---meeting-provider-for-islands-mode).

## <a name="other-considerations"></a>Altre considerazioni

Il componente aggiuntivo Riunione di Teams è ancora in fase di sviluppo, pertanto è importante tenere presente quanto segue:

- Il componente aggiuntivo riunione teams richiede una cassetta postale di Exchange per l'utente principale che pianifica la riunione. Verificare di avere almeno una cassetta postale di Exchange configurata nel profilo di Outlook e usarla per pianificare le riunioni di teams con il componente aggiuntivo. Per i requisiti di Exchange, vedere [come interagiscono Exchange e teams](https://docs.microsoft.com/microsoftteams/exchange-teams-interact).
- Il componente aggiuntivo è adatto a riunioni programmate con partecipanti specifici, non alle riunioni in un canale. Le riunioni nei canali devono essere programmate direttamente in Teams.
- Il componente aggiuntivo non funzionerà se un proxy di autenticazione si trova nel percorso di rete del PC e dei servizi Teams dell'utente.
- Gli utenti non possono programmare gli eventi live all’interno di Outlook. Andare su Teams per pianificare gli eventi live. Per altre informazioni, vedere [Che cosa sono gli eventi live di Microsoft Teams?](teams-live-events/what-are-teams-live-events.md).

Altre informazioni su [riunioni e chiamate in Microsoft Teams](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8).

## <a name="troubleshooting"></a>Risoluzione dei problemi

Eseguire la procedura seguente per risolvere i problemi relativi al componente aggiuntivo riunione teams.

### <a name="teams-meeting-add-in-in-outlook-for-windows-does-not-show"></a>Il componente aggiuntivo riunione teams in Outlook per Windows non viene visualizzato

Se non si riesce a trovare il componente aggiuntivo Riunione di Teams per Outlook per l'installazione, provare a eseguire questa procedura di risoluzione dei problemi.

[Scaricare](https://aka.ms/SaRA-TeamsAddInScenario) ed eseguire l' [Assistente per il ripristino del supporto tecnico Microsoft](https://aka.ms/SaRA_Home) per eseguire procedure e correzioni automatiche per la risoluzione dei problemi.

In alternativa, eseguire manualmente le operazioni seguenti:

- Gli utenti di Windows 7 devono installare l' [aggiornamento per Universal C Runtime in Windows](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows) per il componente aggiuntivo riunione teams per il lavoro.
- Verificare che l'utente disponga di un criterio di aggiornamento di teams che consente la pianificazione delle riunioni in teams. Per altre informazioni, vedere [eseguire l'aggiornamento da Skype for business a teams](https://docs.microsoft.com/microsoftteams/upgrade-to-teams-on-prem-overview#meetings) .
- Verificare che l'utente disponga di un criterio di riunione teams che consenta il componente aggiuntivo per Outlook. Per altre informazioni, vedere [gestire i criteri di riunione in teams](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams#allow-the-outlook-add-in) .
- Verificare che l'utente abbia installato il client desktop teams. Il componente aggiuntivo riunione non verrà installato quando si usa solo il client Web teams.
- Verificare che l'utente abbia installato Outlook 2013 o versione successiva.
- Verificare che l'utente disponga delle autorizzazioni per l'esecuzione di regsvr32.exe.
- Verificare che siano stati applicati tutti gli aggiornamenti disponibili per il client desktop Outlook.
- Eseguire la procedura seguente:
  - Riavviare il client desktop di Teams.
  - Disconnettersi e quindi eseguire di nuovo l'accesso al client desktop di Teams.
  - Riavviare il client desktop di Outlook. Verificare che Outlook non sia in uso in modalità amministratore.

Se il componente aggiuntivo non è ancora visibile, verificare che non sia disabilitato in Outlook.

- In Outlook scegliere **file** e quindi **Opzioni**.
- Selezionare la scheda **componenti** aggiuntivi della finestra di dialogo **Opzioni di Outlook** .
- Verificare che il **componente aggiuntivo riunione Microsoft teams per Microsoft Office** sia elencato nell'elenco **componenti aggiuntivi attivi dell'applicazione**
- Se il componente aggiuntivo riunione teams è elencato nell'elenco componenti aggiuntivi per l' **applicazione disabilitata** , **selezionare componenti aggiuntivi com** in **Gestisci** e quindi selezionare **Vai...**
- Impostare la casella di controllo accanto a **Microsoft teams Meeting Add-in per Microsoft Office**.
- Scegliere **OK** per tutte le finestre di dialogo e riavviare Outlook.

Per informazioni generali su come gestire i componenti aggiuntivi, vedere [visualizzare, gestire e installare componenti aggiuntivi nelle applicazioni di Office](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D).

Se il componente aggiuntivo non viene ancora visualizzato, eseguire la procedura seguente per verificare le impostazioni del registro di sistema.

> [!NOTE]
> La modifica in modo non corretto del registro di sistema può danneggiare gravemente il computer. Prima di apportare modifiche al registro di sistema, è consigliabile eseguire il backup di tutti i dati valutati nel computer.
- Avviare RegEdit.exe
- Passare a HKEY_CURRENT_USER \Software\Microsoft\Office\Outlook\Addins
- Verificare che esista TeamsAddin. FastConnect.
- In TeamsAddin. FastConnect verificare che LoadBehavior esista e sia impostato su 3.
  - Se LoadBehavior ha un valore diverso da 3, cambiarlo in 3 e riavviare Outlook.

### <a name="delegate-scheduling-does-not-work"></a>La pianificazione del delegato non funziona

Se l'amministratore ha configurato Microsoft Exchange per [controllare l'accesso a Exchange Web Server (EWS)](https://docs.microsoft.com/exchange/client-developer/exchange-web-services/how-to-control-access-to-ews-in-exchange), un eventuale delegato non potrà pianificare una riunione di Teams per conto del suo superiore. La soluzione per questa configurazione è in fase di sviluppo e verrà rilasciata in futuro. Come soluzione alternativa, l'amministratore può aggiungere la stringa seguente all'elenco Consenti EWS: "*SchedulingService*". 


## <a name="related-topics"></a>Argomenti correlati

[Risoluzione dei problemi di Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
