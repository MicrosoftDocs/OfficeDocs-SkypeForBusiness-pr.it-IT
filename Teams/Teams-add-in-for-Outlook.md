---
title: Usare il componente aggiuntivo Riunione di Microsoft Teams in Outlook
author: HowlinWolf-92
ms.author: v-mahoffman
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
ms.localizationpriority: high
search.appverid: MET150
description: Microsoft Teams installa un componente aggiuntivo in Outlook che consente agli utenti di pianificare una riunione di Teams da Outlook.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 756f9a8092fea24eb6690baa0768f295bd84e2c1
ms.sourcegitcommit: 8ddafd0901b6b4f4109f3b6e687ae7fae667d61c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2022
ms.locfileid: "62353401"
---
# <a name="use-the-teams-meeting-add-in-in-outlook"></a>Usare il componente aggiuntivo Riunione di Teams in Outlook

Il componente aggiuntivo Riunione di Teams consente agli utenti di pianificare una riunione di Teams da Outlook. Il componente aggiuntivo è disponibile per Outlook in Windows, Mac, Web e dispositivi mobili.

## <a name="teams-meeting-add-in-in-outlook-for-windows"></a>Componente aggiuntivo Riunione di Teams in Outlook per Windows

Il componente aggiuntivo Riunione di Teams viene installato automaticamente per gli utenti che hanno Microsoft Teams e Office 2013, Office 2016 oppure Office 2019 nel loro PC Windows. Gli utenti vedranno il componente aggiuntivo Riunione di Teams sulla barra multifunzione del Calendario di Outlook.

![Screenshot del componente aggiuntivo Riunione di Teams sulla barra multifunzione di Outlook.](media/Teams-add-in-for-Outlook.png)

> [!NOTE]
> - Non sono presenti **URL diretti** che portino al componente aggiuntivo di Teams.
> - Sono da prendere in considerazione elementi aggiuntivi se l'organizzazione esegue sia Teams che Skype for Business. In alcune circostanza, il componente aggiuntivo Teams non è disponibile in Outlook. Vedere [Aggiornare da Skype for Business a Teams](upgrade-to-Teams-on-prem-tools.md) per ulteriori informazioni.
> - Le autorizzazioni utente per eseguire il file Regsvr32.exe sono un requisito minimo per installare il componente aggiuntivo Riunione di Teams nel computer.
> - Se gli utenti non vedono il componente aggiuntivo Riunione di Teams, puoi chiedere loro di chiudere Outlook e Teams, quindi di riavviare prima il client Team, poi di accedere a Teams e infine di riavviare il client Outlook nell’ordine appena esposto.
> - Se si usa un'installazione di Office Outlook da Microsoft Store, il componente aggiuntivo Riunione di Teams non è supportato. Gli utenti che richiedono questo componente aggiuntivo possono installare la versione a portata di clic di Office, come descritto nell’articolo [Office su Windows 10 in modalità S](https://support.office.com/article/faq-office-on-windows-10-in-s-mode-717193b5-ff9f-4388-84c0-277ddf07fe3f).

## <a name="teams-meeting-add-in-in-outlook-for-mac"></a>Componente aggiuntivo Riunione di Teams in Outlook per Mac

Il pulsante Riunione di Teams in Outlook per Mac viene visualizzato nella barra multifunzione di Outlook per Mac se Outlook sta eseguendo la build di produzione 16.24.414.0 e versioni successive e se è attivato con un abbonamento al client Microsoft 365 oppure Office 365.

Le coordinate della riunione, ossia il collegamento per unirsi a Teams e i numeri telefonici di accesso esterno, verranno aggiunte all'invito alla riunione dopo che l'utente avrà fatto clic su **Invia**.  

## <a name="teams-meeting-add-in-in-outlook-web-app"></a>Componente aggiuntivo Riunione di Teams in Outlook Web App

Il pulsante Riunioni di Teams in Outlook Web App verrà visualizzato come parte della creazione di un nuovo evento se l'utente possiede una versione precedente del nuovo Outlook sul web. Per informazioni su come gli utenti possono provare a usare la versione precedente del nuovo Outlook sul web, vedere il [Blog di Outlook](https://techcommunity.microsoft.com/t5/Outlook-Blog/Designed-to-be-fast-The-Outlook-on-the-web-user-experience-gets/ba-p/234909?utm_source=t.co&utm_medium=referral).

![Screenshot del componente aggiuntivo Riunione di Teams in Outlook Web App.](media/teams-meeting-add-in-web.png)

Le coordinate della riunione, ossia il collegamento per unirsi a Teams e i numeri telefonici di accesso esterno, verranno aggiunte all'invito alla riunione dopo che l'utente avrà fatto clic su **Invia**.  

## <a name="teams-meeting-add-in-in-outlook-mobile-ios-and-android"></a>Componente aggiuntivo Riunione di Teams in Outlook Mobile (per iOS e Android)

Il pulsante Riunione di Teams compare nelle build più recenti dell'app di Outlook per iOS e Android.

![Screenshot del componente aggiuntivo Riunione di Teams in Outlook Mobile.](media/teams-meeting-add-in-mobile.png)

Le coordinate della riunione, ossia il collegamento per unirsi a Teams e i numeri telefonici di accesso esterno, verranno aggiunte all'invito alla riunione dopo che l'utente avrà fatto clic su **Invia**.  

## <a name="teams-meeting-add-in-and-findtime-for-outlook"></a>Componente aggiuntivo Riunione di Teams e TrovaOrario per Outlook

TrovaOrario è un componente aggiuntivo per Outlook che aiuta gli utenti a raggiungere un consenso tra le aziende per stabilire l'orario della riunione. Una volta che gli invitati della riunione hanno fornito il loro orario preferito, TrovaOrario invia l'invito alla riunione per conto dell'utente. Se viene selezionata l'opzione **Riunione online** in TrovaOrario, verrà programmata una riunione di Skype for Business o di Microsoft Teams. (TrovaOrario userà qualsiasi opzione impostata dall'organizzazione come canale predefinito per le riunioni online.)

> [!NOTE]  
> Se è stato impostato Skype for Business nella [dashboard di TrovaOrario](https://findtime.microsoft.com/UserDashboard), verrà usata questa impostazione anziché Microsoft Teams. Se si vuole usare Microsoft Teams, eliminare l'opzione Skype for Business nella dashboard.

Per altre informazioni, vedere [Pianificare riunioni con TrovaOrario](https://support.office.com/article/scheduling-meetings-with-findtime-4dc806ed-fde3-4ea7-8c5e-b5d1fddab4a6).

## <a name="authentication-requirements"></a>Requisiti di autenticazione

Il componente aggiuntivo Riunione di Teams richiede agli utenti di accedere a Teams con l'Autenticazione moderna. Se non viene usato questo metodo per eseguire l'accesso, sarà possibile comunque usare il client Teams, ma non sarà possibile pianificare [riunioni online di Teams](https://www.microsoft.com/microsoft-teams/online-meetings) usando il componente aggiuntivo per Outlook. È possibile correggere eseguendo una delle operazioni seguenti:

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

Quando gli utenti in modalità Isole pianificano una riunione in Outlook, in genere prevedono di decidere se pianificare una riunione di Skype for Business o di Teams. In Outlook sul web, Outlook Windows e Outlook Mac, gli utenti possono vedere i componenti aggiuntivi di Skype for Business e Teams in modalità Isole per impostazione predefinita. È possibile configurare un'impostazione criterio per le riunioni di Teams per controllare se gli utenti in modalità Isole possono usare solo il componente aggiuntivo Riunione di Teams o sia Riunione di Teams che Riunione di Skype for Business.

A causa di alcune limitazioni nel rilascio iniziale, Outlook Mobile supporta solo la creazione di riunioni di Skype for Business **o** di Teams. Per altri dettagli, vedere la tabella seguente.

| Modalità di coesistenza nell’interfaccia di amministrazione di Teams | Provider di riunioni predefinito in Outlook Mobile |
| --------------------------------------|---------------------------------------------|
| Isole | Skype for Business |
| Solo Skype for Business | Skype for Business |
| Collaborazione di Skype for Business con Teams | Skype for Business |
| Collaborazione e riunioni di Skype for Business con Teams | Teams |
| Solo Teams | Teams |

### <a name="set-whether-users-in-islands-mode-can-only-use-the-teams-meeting-add-in-or-both-the-teams-meeting-and-skype-for-business-meeting-add-ins"></a>Impostare se gli utenti in modalità Isole possono usare solo il componente aggiuntivo Riunione di Teams o sia Riunione di Teams che Riunione di Skype for Business 

Come amministratore, è possibile configurare un'impostazione criterio per le riunioni di Teams per controllare quale componente aggiuntivo per le riunioni di Outlook viene usato per *gli utenti in modalità Isole*. È possibile specificare se gli utenti possono usare solo il componente aggiuntivo Riunione di Teams o sia Riunione di Teams che Riunione di Skype for Business per programmare le riunioni in Outlook.

È possibile applicare questo criterio agli utenti in modalità Isole e che hanno impostato il parametro **AllowOutlookAddIn** su **True** nel loro criterio per le riunioni di Teams. Per la procedura su come impostare questo criterio, vedere [Impostazioni dei criteri di riunione - Generale](meeting-policies-in-teams-general.md#meeting-provider-for-islands-mode).

## <a name="other-considerations"></a>Altre considerazioni

Il componente aggiuntivo Riunione di Teams è ancora in fase di sviluppo, pertanto è importante tenere presente quanto segue:

- Il componente aggiuntivo Riunione di Teams richiede una cassetta postale di Exchange per gli utenti primari che programmano le riunioni. Assicurarsi di avere almeno una cassetta postale di Exchange configurata nel profilo Outlook e usala per programmare le riunioni di Teams tramite il componente aggiuntivo. Per i requisiti di Exchange, vedere [Come interagiscono Exchange e Teams](./exchange-teams-interact.md).
- Il componente aggiuntivo è adatto a riunioni programmate con partecipanti specifici, non alle riunioni in un canale. Le riunioni nei canali devono essere programmate direttamente in Teams.
- Il componente aggiuntivo non funzionerà se un Proxy di autenticazione si trova nel percorso di rete relativo ai servizi di Teams e del PC dell'utente.
- Gli utenti non possono programmare gli eventi live all’interno di Outlook. Andare su Teams per pianificare gli eventi live. Per altre informazioni, vedere [Che cosa sono gli eventi live di Microsoft Teams?](teams-live-events/what-are-teams-live-events.md).

Altre informazioni su [riunioni e chiamate in Microsoft Teams](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8).

## <a name="troubleshooting"></a>Risoluzione dei problemi

Usare i seguenti passaggi per risolvere i problemi con il componente aggiuntivo Riunione di Teams.

> [!NOTE]
> Questo scenario può essere gestito anche usando la [versione da riga di comando di Assistente supporto e ripristino di Microsoft](/office365/troubleshoot/administration/sara-command-line-version) con SaRAcmd.exe -S TeamsAddinScenario -AcceptEula -CloseOutlook.

### <a name="teams-meeting-add-in-in-outlook-for-windows-does-not-show"></a>Il componente aggiuntivo Riunione di Teams in Outlook per Windows non viene visualizzato

Se non si riesce a trovare il componente aggiuntivo Riunione di Teams per Outlook per l'installazione, provare a eseguire questa procedura di risoluzione dei problemi.

[Scaricare](https://aka.ms/SaRA-TeamsAddInScenario) ed eseguire l'[Assistente supporto e ripristino Microsoft](https://aka.ms/SaRA_Home) per eseguire i passaggi di risoluzione dei problemi automatizzati e le relative correzioni.

In alternativa, eseguire manualmente i seguenti passaggi:

- Gli utenti di Windows 7 sono tenuti a installare l'[aggiornamento per Universal C Runtime in Windows](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows) affinché funzioni il componente aggiuntivo Riunione di Teams.
- Controllare che l'utente disponga di un criterio di aggiornamento di Teams che abiliti la programmazione delle riunioni in Teams. Vedere [Aggiornare da Skype for Business a Teams](/microsoftteams/meeting-policies-in-teams-general) per ulteriori informazioni.
- Controllare che l'utente disponga di un criterio di Riunione di Teams che consenta il componente aggiuntivo per Outlook. Per altri dettagli, vedere [Impostazioni dei criteri di riunione - Generale](./meeting-policies-in-teams-general.md#outlook-add-in).
- Assicurarsi che l'utente abbia installato il client desktop di Teams. Il componente aggiuntivo per le riunioni non verrà installato se si utilizza solo il client Web di Teams.
- Assicurarsi che l'utente abbia installato Outlook 2013 o versioni successive.
- Assicurarsi che l'utente disponga delle autorizzazione per eseguire regsvr32.exe.
- Assicurarsi che siano stati applicati tutti gli aggiornamenti disponibili per il client desktop di Outlook.
- Eseguire la procedura seguente:
  - Riavviare il client desktop di Teams.
  - Disconnettersi e quindi eseguire di nuovo l'accesso al client desktop di Teams.
  - Riavviare il client desktop di Outlook. (Verificare che Outlook non sia in esecuzione in modalità amministratore.)

Qualora non fosse ancora possibile visualizzare il componente aggiuntivo, assicurasi che non sia disabilitato in Outlook.

- In Outlook, scegliere **File**, quindi **Opzioni**.
- Selezionare la scheda **Componenti aggiuntivi** della finestra di dialogo **Opzioni Outlook**.
- Confermare che il **Componente aggiuntivo Riunione di Teams per Microsoft Office** sia nell'elenco dei **Componenti aggiuntivi applicazioni attivi**
- Se il componente aggiuntivo Riunione di Teams compare nell'elenco **Componenti aggiuntivi applicazioni disabilitati**, selezionare **Componenti aggiuntivi COM** in **Gestisci**, quindi **Vai…**
- Impostare la casella di controllo accanto a **Componente aggiuntivo Riunione di Teams per Microsoft Office**.
- Scegliere **OK** in tutte le finestre di dialogo e riavviare Outlook.

Per informazioni generali su come gestire i componenti aggiuntivi, vedere [Visualizzare, gestire e installare componenti aggiuntivi nei programmi di Office](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D).

Qualora il componente aggiuntivo non venisse ancora visualizzato, seguire i seguenti passaggi per verificare le impostazioni del Registro di sistema.

> [!NOTE]
> La modifica non corretta del Registro di sistema potrebbe danneggiare gravemente il sistema. Prima di apportare modifiche al Registro di sistema, si consiglia di effettuare il backup di qualsiasi dato importante sul computer.
- Avviare RegEdit.exe
- Passare a HKEY_CURRENT_USER\Software\Microsoft\Office\Outlook\Addins
- Verificare che TeamsAddin.FastConnect esista.
- In TeamsAddin.FastConnect, verificare che LoadBehavior esista e sia impostato su 3.
  - Se LoadBehavior ha un valore diverso da 3, portarlo a 3 e riavviare Outlook.

### <a name="delegate-scheduling-does-not-work"></a>La programmazione delegata non funziona

Se l'amministratore ha configurato Microsoft Exchange per [controllare l'accesso a Exchange Web Server (EWS)](/exchange/client-developer/exchange-web-services/how-to-control-access-to-ews-in-exchange), un eventuale delegato non potrà pianificare una riunione di Teams per conto del suo superiore. La soluzione per questa configurazione è in fase di sviluppo e verrà rilasciata in futuro. Come soluzione temporanea, l'amministratore può aggiungere la stringa seguente all'elenco EWS consentiti: "*SchedulingService*". 


## <a name="related-topics"></a>Argomenti correlati

- [Risoluzione dei problemi di Teams](/MicrosoftTeams/troubleshoot/teams)

- [Schedule a Teams meeting from Outlook](https://support.microsoft.com/office/schedule-a-teams-meeting-from-outlook-883cc15c-580f-441a-92ea-0992c00a9b0f)
