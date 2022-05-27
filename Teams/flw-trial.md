---
title: Gestire la versione di valutazione in prima linea in Teams
author: daisyfell
ms.author: daisyfeller
ms.reviewer: samanro
manager: pamgreen
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Informazioni su come configurare un Teams di 90 giorni per la versione di valutazione dei dipendenti in prima linea per l'organizzazione.
ms.localizationpriority: medium
ms.collection:
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 098cb4cd84616a9b26ea7df5c1451219fd5b5f0e
ms.sourcegitcommit: 8ce73ea99be607f5cdccb22a5366bc96e8fb09c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2022
ms.locfileid: "65758297"
---
# <a name="manage-the-frontline-trial-in-teams"></a>Gestire la versione di valutazione in prima linea in Teams

> [!NOTE]
> Questa esperienza di prova sarà disponibile a breve. È possibile verificare quando questa opzione è disponibile per l'organizzazione cercando un messaggio nel [Centro messaggi](https://go.microsoft.com/fwlink/p/?linkid=2070717) nel centro Amministrazione Microsoft 365.

L'esperienza di valutazione in prima linea di Microsoft Teams consente agli utenti dell'organizzazione che si trovano in Teams di avviare un'esperienza di Teams per l'intero team in prima linea, purché gli altri membri siano in Azure Active Directory (Azure AD). È possibile disabilitare questa caratteristica per gli utenti dell'organizzazione usando il [modulo AllowSelfServicePurchase di PowerShell](/microsoft-365/commerce/subscriptions/allowselfservicepurchase-powershell).

## <a name="what-services-are-included"></a>Quali servizi sono inclusi

La versione di valutazione include tutti gli elementi della [licenza di Microsoft 365 F3](https://www.microsoft.com/microsoft-365/enterprise/f3) con le eccezioni seguenti:

- La versione di valutazione in prima linea include Exchange Foundation anziché Exchange Kiosk. Gli utenti potrebbero non avere altre funzionalità di Teams a causa di questo cambiamento.

## <a name="eligibility"></a>Ammissibilità

> [!NOTE]
> È possibile verificare se l'organizzazione fa parte del progetto pilota di valutazione cercando un annuncio nel [Centro messaggi](https://go.microsoft.com/fwlink/p/?linkid=2070717) nel centro Amministrazione Microsoft 365. L'organizzazione dovrà far parte del progetto pilota di valutazione per consentire agli utenti di avviare o partecipare a una versione di valutazione. Questa offerta non è disponibile per i clienti GCC, GCC High, DoD o EDU.

La versione di valutazione in prima linea può ospitare un massimo di 300 utenti per versione di valutazione.

Gli utenti possono avviare una versione di valutazione in prima linea per il proprio team se:

- Avere una licenza attiva che consente loro di accedere a Teams.
- In precedenza non è stata avviata una versione di valutazione per i dipendenti in prima linea.

> [!IMPORTANT]
> Se l'utente che ha avviato la versione di valutazione lascia l'organizzazione prima del termine del periodo di valutazione, l'amministratore dovrà monitorare la versione di valutazione, contattare il team per vedere chi sta usufruendo di queste caratteristiche e decidere quali utenti è necessario aggiornare a una licenza a pagamento.

Gli utenti possono partecipare a una versione di valutazione di frontline worker se hanno un indirizzo di posta elettronica gestito Azure Active Directory dominio.

Gli utenti possono partecipare se hanno già avviato una versione di valutazione, ma non possono avviarne un'altra.

> [!NOTE]
> Gli utenti che non hanno accesso a Teams possono essere aggiunti al team di valutazione solo al momento della creazione del team. Gli utenti Teams esistenti possono comunque essere aggiunti alla versione di valutazione dopo la creazione del team.

## <a name="set-up-the-trial"></a>Configurare la versione di valutazione

Gli utenti idonei possono avviare una versione di valutazione in prima linea accedendo all'app Attività in Teams [dall'app](https://teams.microsoft.com/_#/apps/com.microsoft.teamspace.tab.planner/sections/mytasks) desktop o Web. Al momento, l'avvio di una versione di valutazione in prima linea tramite dispositivi mobili non è supportato. Quando viene avviata una versione di valutazione, all'intero team verrà assegnata automaticamente la licenza di valutazione in prima linea. Agli utenti con licenze a pagamento esistenti che concedono l'accesso a Teams verranno assegnate anche licenze di valutazione, ma manterranno le funzionalità delle licenze esistenti per tutta la durata della versione di valutazione e manterranno le licenze a pagamento esistenti al termine della versione di valutazione. L'utente che ha avviato la versione di valutazione riceverà notifiche tramite posta elettronica nel corso della versione di valutazione.

## <a name="manage-the-frontline-trials-experience"></a>Gestire l'esperienza delle versioni di valutazione in prima linea

Gli amministratori possono impedire agli utenti finali di avviare la versione di valutazione frontline all'interno dell'organizzazione usando il modulo **AllowSelfServicePurchase** PowerShell. Questo vale solo per le licenze di valutazione. [Informazioni su come usare il modulo AllowSelfServicePurchase PowerShell](/microsoft-365/commerce/subscriptions/allowselfservicepurchase-powershell).

### <a name="manage-teams-for-users-who-have-the-frontline-trial-license"></a>Gestire Teams per gli utenti che hanno la licenza di valutazione in prima linea

È possibile gestire gli utenti che hanno la licenza di valutazione in prima linea, proprio come si gestiscono gli utenti con una normale licenza a pagamento. Per altre informazioni, vedere [Gestire le impostazioni di Teams per l'organizzazione](/microsoftteams/manage-teams-overview).

### <a name="remove-a-trial-license"></a>Rimuovere una licenza di valutazione

È possibile rimuovere la licenza di valutazione in prima linea tramite PowerShell o il interfaccia di amministrazione di Microsoft 365.

[Informazioni su come rimuovere con PowerShell](/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell).

[Informazioni su come rimuovere nell'interfaccia di amministrazione](/microsoft-365/admin/add-users/delete-a-user).

## <a name="upgrade-users-from-frontline-trial"></a>Aggiornare gli utenti dalla versione di valutazione in prima linea

Gli utenti possono contattare l'utente per chiedere licenze al termine della versione di valutazione. Per aggiornare gli utenti sono necessari privilegi di amministratore.

### <a name="when-to-upgrade"></a>Quando eseguire l'aggiornamento

Verso la fine della versione di valutazione di 90 giorni, è necessario contattare gli utenti per verificare chi deve continuare a usare una licenza a pagamento. Assicurarsi di eseguire questa operazione prima della scadenza dell'abbonamento di valutazione in prima linea per evitare interruzioni delle esperienze degli utenti.

> [!IMPORTANT]
> Se la licenza di valutazione in prima linea termina e a un utente non viene assegnata immediatamente una licenza che include Teams, perde l'accesso a Teams. Dopo 30 giorni, i loro dati (file, messaggi e altro ancora) vengono eliminati. L'utente esiste ancora in Azure Active Directory. Se all'utente viene assegnata una nuova licenza per abilitare Teams funzionalità entro il periodo di 30 giorni, tutto il suo contenuto in Teams continuerà a esistere.

### <a name="choose-an-upgrade-path"></a>Scegliere un percorso di aggiornamento

> [!TIP]
> La versione di valutazione in prima linea si basa sulla [licenza Microsoft 365 F3](https://www.microsoft.com/microsoft-365/enterprise/f3).

A seconda degli abbonamenti attualmente disponibili nell'organizzazione, esistono tre modi per eseguire l'aggiornamento da una versione di valutazione in prima linea a una licenza a pagamento:

- **Aggiornare a un abbonamento di Microsoft 365 esistente.** Usare questa opzione se l'organizzazione dispone di abbonamenti ad altri prodotti Office che non includono Teams. Per altre informazioni, vedere [Eseguire l'aggiornamento a un piano diverso](/microsoft-365/commerce/subscriptions/upgrade-to-different-plan). Per visualizzare gli utenti attivi per un abbonamento esistente, accedere a **Utenti >** [Utenti attivi](https://go.microsoft.com/fwlink/p/?linkid=834822) nell'interfaccia di amministrazione di Microsoft 365.

- **Aggiungere utenti a un abbonamento di Microsoft 365 esistente.** Usare questa opzione se l'organizzazione non ha licenze di Teams a pagamento sufficienti per coprire il team in prima linea. Per altre informazioni, vedere [Acquistare o rimuovere licenze](/microsoft-365/commerce/licenses/buy-licenses). Per aggiungere utenti a un abbonamento esistente che dispone già di abbastanza licenze disponibili, vedere [Spostare gli utenti a un abbonamento diverso](/microsoft-365/commerce/subscriptions/move-users-different-subscription). Per visualizzare gli utenti attivi per un abbonamento esistente, accedere a **Utenti >** [Utenti attivi](https://go.microsoft.com/fwlink/p/?linkid=834822) nell'interfaccia di amministrazione di Microsoft 365.

- **Acquistare un nuovo abbonamento di Microsoft 365.** Usare questa opzione se l'organizzazione non ha abbonamenti a prodotti Office o se l'organizzazione vuole acquistare un abbonamento diverso da quello esistente per coprire gli utenti in prima linea. Per altre informazioni, vedere [Microsoft 365 for frontline workers](https://www.microsoft.com/microsoft-365/enterprise/frontline).

Se non sei sicuro di quale Microsoft 365 abbonamento a cui eseguire l'aggiornamento, vedi [Microsoft 365 for frontline workers](https://www.microsoft.com/microsoft-365/enterprise/frontline). Per ulteriore assistenza nella scelta di un abbonamento o se l'organizzazione necessita di più di 300 licenze, contattare il [partner Microsoft](https://www.microsoft.com/solution-providers/home) o il rappresentante dell'account Microsoft.

### <a name="assign-paid-licenses"></a>Assegnare licenze a pagamento

Per assegnare le licenze appena acquisite, vedere [Assegnare le licenze agli utenti](/microsoft-365/admin/manage/assign-licenses-to-users).  

Dopo aver assegnato le nuove licenze, annullare l'assegnazione delle licenze di Teams Exploratory. Per altre informazioni, vedere [Annullare l'assegnazione delle licenze degli utenti](/microsoft-365/admin/manage/remove-licenses-from-users).

## <a name="faq"></a>Domande frequenti

**Durata della versione di valutazione** <br>
La versione di valutazione in prima linea dura 90 giorni.

**Cosa devono fare gli amministratori al termine della versione di valutazione in prima linea di 90 giorni?** <br>
Al termine della versione di valutazione di 90 giorni, è necessario contattare gli utenti per verificare chi deve continuare a usare una licenza a pagamento. Sarà quindi necessario [aggiornare gli utenti](#upgrade-users-from-frontline-trial).

**Cosa succede se l'utente che ha avviato la versione di valutazione lascia l'organizzazione?** <br>
L'amministratore dovrà monitorare la versione di valutazione per il resto del periodo di 90 giorni ed eseguire l'aggiornamento alle licenze a pagamento per gli utenti che ne hanno bisogno al termine della versione di valutazione.

**Che cos'è il criterio di conservazione dei dati?** <br>
Per informazioni sulla conservazione dei dati, [vedere le informazioni sull'abbonamento Microsoft 365](/microsoft-365/commerce/subscriptions/what-if-my-subscription-expires?).

**Cosa succede se un utente rileva un errore durante l'avvio della versione di valutazione in prima linea?** <br>
Assicurarsi che l'organizzazione, l'utente che avvia la versione di valutazione e gli utenti aggiunti alla versione di valutazione soddisfino i [criteri di idoneità](#eligibility).