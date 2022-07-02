---
title: Gestire l'esperienza Microsoft Teams Exploratory
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: reference
audience: Admin
ms.reviewer: baluc
ms.service: msteams
search.appverid: MET150
ms.localizationpriority: high
description: Gli utenti di Microsoft 365 o Office 365 che non hanno una licenza di Microsoft Teams possono iniziare a usare una licenza Teams Exploratory.
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: 374761a64f64649dba67f9bfb8760f363fa94f2e
ms.sourcegitcommit: 79ada2140b110239deff96e4854ebd5dd9b77881
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2022
ms.locfileid: "66605695"
---
# <a name="manage-the-microsoft-teams-exploratory-license"></a>Gestire la licenza di Microsoft Teams Exploratory

L'esperienza Microsoft Teams Exploratory consente agli utenti dell'organizzazione che hanno Azure Active Directory (AAD) e non hanno una licenza per Teams di iniziare a usare un'esperienza esplorativa di Teams. Gli amministratori possono attivare o disattivare questa funzionalità per gli utenti dell'organizzazione.

## <a name="whats-in-the-teams-exploratory-experience"></a>Contenuto dell'esperienza Teams Exploratory

I piani di servizio che un amministratore visualizzerà nell'ambito dell'esperienza Teams Exploratory sono i seguenti:

- Exchange Online (Piano 1)
- Flow per Microsoft 365 o Office 365
- Insights by MyAnalytics
- Microsoft Forms (Piano E1)
- Microsoft Planner
- Microsoft Search
- Microsoft StaffHub
- SKU Microsoft Stream per Microsoft 365 e Office 365 E1 <sup>1</1>
- Microsoft Teams
- Gestione di dispositivi mobili per Microsoft 365 o Office 365
- App di Office Mobile per Office 365
- Office Online
- Power Apps per Microsoft 365 o Office 365
- SharePoint Online (Piano 1)
- Sway
- To-Do (Piano 1)
- Whiteboard (Piano 1)
- Yammer Enterprise

  <sup>1</sup> Il passaggio dall’uso di Microsoft Stream all’uso di [OneDrive for Business e SharePoint per le registrazioni delle riunioni](tmr-meeting-recording-change.md) avverrà in modo graduale. Al momento dell’avvio, sarà possibile acconsentire esplicitamente a questa esperienza. Se si vuole continuare a usare Stream, a novembre sarà necessario rifiutare esplicitamente. All'inizio del 2021, tutti i clienti dovranno usare OneDrive for Business e SharePoint per le nuove registrazioni delle riunioni.

## <a name="whos-eligible"></a>Chi è idoneo

Gli utenti soddisfano i criteri per un'esperienza Teams Exploratory se:

- Hanno un indirizzo di posta elettronica gestito nel dominio di Azure Active Directory.
- Appartengono a un tenant con un abbonamento a pagamento.
- Non hanno una licenza di Teams attiva.
- Nonsono in un tenant in cui sono stati creati i criteri di assegnazione delle licenze.

Gli utenti devono essere abilitati all'iscrizione per app e versioni di valutazione (nell'interfaccia di amministrazione di Microsoft 365). Per altre informazioni, vedere [Gestire l'esperienza Teams Exploratory](#manage-the-teams-exploratory-experience) più avanti in questo articolo.

## <a name="who-isnt-eligible"></a>Chi non è idoneo

Gli utenti non soddisfano i criteri se:

- Attualmente disponi di Teams da una licenza a pagamento o una licenza di valutazione oppure in precedenza disponevi di una licenza di valutazione
- si trovano in un tenant che usava/riceveva almeno un'offerta speciale COVID.

L'organizzazione non è idonea per questa offerta se è un Syndication Partner Customer oppure un cliente GCC, GCC High, DoD o EDU.

## <a name="how-users-sign-up-for-the-teams-exploratory-experience"></a>Come aderire all'esperienza Teams Exploratory

Gli utenti idonei possono aderire all'esperienza Teams Exploratory eseguendo l'accesso a Teams dal desktop o sul Web ([teams.microsoft.com](https://teams.microsoft.com)). Al momento, l'abilitazione di Teams Exploratory tramite dispositivi mobili non è supportata. Al momento dell’iscrizione, questa licenza verrà loro assegnata automaticamente e l'amministratore del tenant riceverà una notifica tramite posta elettronica la prima volta che un utente dell'organizzazione avvia l'esperienza Teams Exploratory.

## <a name="manage-the-teams-exploratory-experience"></a>Gestire l'esperienza Teams Exploratory

L'esperienza Teams Exploratory deve essere avviata da singoli utenti finali e non può essere avviata per conto dei dipendenti.

L'esperienza Teams Exploratory include una licenza di Exchange Online, la cui assegnazione deve essere eseguita dall'amministratore. Se l'utente non ha già una licenza di Exchange e l'amministratore non ha ancora assegnato la licenza di Exchange Online, l'utente non potrà pianificare riunioni in Teams e potrebbe non avere accesso ad altre funzionalità di Teams.

Gli amministratori possono impedire agli utenti finali di eseguire l'esperienza Teams Exploratory all'interno dell'organizzazione usando l'interruttore **Consenti agli utenti di installare le versioni di valutazione di app e servizi**.

### <a name="prevent-users-from-installing-trial-apps-and-services"></a>Impedire agli utenti di installare le versioni di valutazione di app e servizi

È possibile disattivare la possibilità di installare versioni di valutazione di app e servizi, che non consentirebbero agli utenti di eseguire l'esperienza Teams Exploratory.

1. Nell'interfaccia di amministrazione di Microsoft 365, passare a **Impostazioni** > **Impostazioni organizzazione**, selezionare **Servizi**, quindi **App e servizi di proprietà dell'utente**.

    ![pagina Servizi nell'interfaccia di amministrazione.](media/iw-trial-services.png)

2. Eliminare il segno di spunta da **Consenti agli utenti di installare le versioni di valutazione di app e servizi**.

    ![pagina App e servizi di proprietà degli utenti nell'interfaccia di amministrazione.](media/iw-trial-user-owned-apps-services.png)

    > [!NOTE]
    > Se l'organizzazione non è idonea per l'esperienza Teams Exploratory, l'opzione **Consenti agli utenti di installare le versioni di valutazione di app e servizi** non è disponibile.

### <a name="manage-availability-for-a-user-with-a-license-that-includes-teams"></a>Gestire la disponibilità per un utente con una licenza che include Teams

Un utente a cui è stata assegnata una licenza che include Teams non è idoneo per l'esperienza Teams Exploratory. Quando il piano di servizio Teams è attivato, l'utente può accedere e usare Teams. Se il piano di servizio è disabilitato, l'utente non può accedere e l'esperienza Teams Exploratory non è disponibile. È necessario avere i privilegi di amministratore.

Per disattivare l'accesso a Teams:

1. Nell'interfaccia di amministrazione di Microsoft 365 selezionare **Utenti** > **Utenti attivi**.

2. Selezionare la casella accanto al nome dell'utente.

3. Nella riga **Licenze di prodotto** scegliere **Modifica**.

4. Nel riquadro **Licenze di prodotto** spostare l'interruttore nella posizione **No**.

    ![pagina Licenze di prodotto nell'interfaccia di amministrazione.](media/iw-trial-enable-3.png)

### <a name="manage-teams-availability-for-users-who-are-already-using-the-teams-exploratory-experience"></a>Gestire la disponibilità di Teams per gli utenti che usano già l'esperienza Teams Exploratory

Se un utente usa già l'esperienza Teams Exploratory, è possibile disattivarla rimuovendo la licenza o il piano di servizio. Per procedere in tal senso, è necessario disporre dei privilegi di amministratore.

Per disattivare la licenza dell'esperienza Teams Exploratory:

1. Nell'interfaccia di amministrazione di Microsoft 365 selezionare **Utenti** > **Utenti attivi**.

2. Selezionare la casella accanto al nome dell'utente.

3. Nella riga **Licenze di prodotto** scegliere **Modifica**.

4. Nel riquadro **Licenze di prodotto** spostare l'interruttore relativo alla licenza Exploratory nella posizione **No**.

    > [!NOTE]
    > L'interruttore Teams Exploratory verrà visualizzato dopo che il primo utente dell'organizzazione ha avviato l'esperienza Teams Exploratory.

### <a name="manage-teams-for-users-who-have-the-teams-exploratory-license"></a>Gestire Teams per gli utenti che hanno la licenza di Teams Exploratory

Gli utenti che hanno una licenza di Teams Exploratory possono essere gestiti nello stesso modo in cui si gestiscono gli utenti con una normale licenza a pagamento. Per altre informazioni, vedere [Gestire le impostazioni di Teams per l'organizzazione](enable-features-office-365.md).

### <a name="upgrade-users-from-teams-exploratory"></a>Aggiornare gli utenti da Teams Exploratory

Per aggiornare gli utenti da Teams Exploratory, è necessario disporre dei privilegi di amministratore. Per altre informazioni, vedere [Aggiornare gli utenti dalla versione di valutazione di Teams Exploratory](upgrade-from-teams-exploratory.md).

> [!NOTE]
> Se allo scadere della licenza di Teams Exploratory non viene immediatamente eseguito l'aggiornamento a un abbonamento che include Teams, l'utente perderà l'accesso a Teams dopo un periodo di prova di 30 giorni. Altri 30 giorni, trascorsi i quali i dati verranno eliminati. L'utente esiste ancora in Azure Active Directory. Una volta assegnata una nuova licenza all'utente per abilitare nuovamente le funzionalità di Teams, tutto il contenuto sarà ancora disponibile se l'utente viene aggiunto entro il periodo di tolleranza.

### <a name="remove-a-teams-exploratory-license"></a>Rimuovere una licenza di Teams Exploratory

- Se si vuole rimuovere questa licenza con PowerShell, vedere [Rimuovere le licenze dagli account utente con Office 365 PowerShell](/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)

- Se si vuole rimuovere questa licenza tramite il portale di amministrazione, vedere [Eliminare un utente dall'organizzazione](/microsoft-365/admin/add-users/delete-a-user)

## <a name="what-is-the-data-retention-policy"></a>Quali sono i criteri di conservazione dei dati

Vedere le [Informazioni sull'abbonamento a Microsoft 365](/microsoft-365/commerce/subscriptions/what-if-my-subscription-expires?view=o365-worldwide).

## <a name="how-long-does-the-teams-exploratory-experience-last"></a>Durata dell'esperienza di Teams Exploratory

Teams Exploratory è disponibile con un abbonamento di 12 mesi, dall'iscrizione iniziale degli utenti, per tutti i nuovi clienti. Il nuovo abbonamento a Teams Exploratory inizia dal momento dell’iscrizione del primo utente e scadrà dopo 12 mesi. La data di fine verrà applicata a tutti gli utenti dello stesso tenant, con un periodo di 12 mesi a partire dalla data di iscrizione del primo utente.

> [!NOTE]
> La data di fine è configurata a livello di organizzazione, il che significa che verrà applicata a tutti gli utenti della stessa organizzazione. Ad esempio, l'utente 1 inizia l'abbonamento il 1° gennaio 2021. Pertanto, la data di fine dell'abbonamento sarà il 31 dicembre 2021. Un altro utente, l’utente 2, inizia l'abbonamento il 1° ottobre 2021. L'utente 2 può usare Teams Exploratory per due mesi, perché la data di fine sarà il 31 dicembre 2021 poiché fa parte dell'abbonamento della stessa organizzazione dell'utente 1.

### <a name="what-should-administrators-do-at-the-end-of-the-12-month-teams-exploratory-experience"></a>Cosa devono fare gli amministratori alla fine dei 12 mesi

Alla fine dell'abbonamento di 12 mesi, gli amministratori devono convertire tutti gli utenti di Teams Exploratory in una licenza a pagamento che include Teams. È fondamentale assicurarsi che questa operazione venga completata prima che scada l'abbonamento a Teams Exploratory per evitare l’interruzione dell'esperienza utente.


> [!NOTE]
> I clienti verranno disabilitati e sarà loro impedito l'avvio di una nuova licenza per la versione di valutazione Exploratory per tre mesi dopo la scadenza della precedente.

Per altre informazioni, vedere [Aggiornare gli utenti da Teams Exploratory](#upgrade-users-from-teams-exploratory), in questo articolo.
