---
title: Ritirare Microsoft Teams gratuito (classico) per l'organizzazione
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.reviewer: alyake
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-meetings
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.custom:
- Licensing
- admindeeplinkMAC
description: Informazioni su come rimuovere le licenze teams free (classiche) e assegnare licenze a pagamento di Teams per gli utenti dell'organizzazione.
ms.openlocfilehash: 7e9596f631c461e3c1e9134b279c232e384aba6b
ms.sourcegitcommit: ff5411084dc34754462d5fd67b64db7a7e76f1e1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2023
ms.locfileid: "69823295"
---
# <a name="retire-microsoft-teams-free-classic-for-your-organization"></a>Ritirare Microsoft Teams gratuito (classico) per l'organizzazione

> [!NOTE]
> Se si è un utente di Teams Free (classico), si perderà l'accesso a Teams a metà aprile 2023, a meno che l'amministratore IT non effettui le azioni seguenti in questo articolo.

A metà aprile 2023 Microsoft ritirerà la licenza **di Microsoft Teams gratuito (classico)**.

Questo articolo fornisce agli amministratori IT istruzioni su come ritirare le licenze **di Microsoft Teams gratuito (classico)** dell'organizzazione e passare alle licenze di Teams a pagamento.

Se non sposti le licenze teams gratuite degli utenti alle licenze Teams a pagamento entro metà aprile 2023, gli utenti perderanno l'accesso a Teams.

Per completare questo processo, è possibile scegliere uno dei due metodi seguenti:

- [Usare la interfaccia di amministrazione di Microsoft 365.](#use-microsoft-365-admin-center-to-replace-licenses)
- [Usare Microsoft PowerShell.](#use-microsoft-powershell-to-replace-licenses)

Se l'organizzazione decide di non eseguire la migrazione a una licenza di Teams a pagamento, è possibile esportare i contenuti dell'organizzazione da Teams. Per istruzioni su come esportare il contenuto di Teams, vedere [Esportare il contenuto con le API di esportazione di Microsoft Teams](/microsoftteams/export-teams-content).

## <a name="use-microsoft-365-admin-center-to-replace-licenses"></a>Usare interfaccia di amministrazione di Microsoft 365 per sostituire le licenze

Se alla tua organizzazione sono stati assegnati pochi utenti con la licenza **Teams Free (classica),** ti consigliamo di usare il interfaccia di amministrazione di Microsoft 365 per rimuovere e assegnare le licenze.

### <a name="check-users-current-teams-licensing"></a>Controllare le licenze correnti di Teams degli utenti

1. Accedi alla [interfaccia di amministrazione di Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=2024339).
1. Nel menu a sinistra passare a **Utenti** > e selezionare [**Utenti attivi**](https://go.microsoft.com/fwlink/p/?linkid=834822) per visualizzare le licenze assegnate agli utenti.
    1. La colonna **Licenza** mostrerà **Microsoft Teams gratuito (classico)** accanto agli utenti a cui è assegnata la licenza.
1. Nel menu a sinistra, vai a **Fatturazione** > e seleziona [**Licenze**](https://go.microsoft.com/fwlink/p/?linkid=842264) per vedere se hai licenze teams a pagamento disponibili.
    1. Se l'organizzazione ha licenze disponibili, passare a [Assegnare licenze a pagamento di Teams](#assign-paid-teams-licenses) per assegnare tali licenze agli utenti con licenze **Teams Free (classiche** ).
1. Determinare il numero di licenze Teams a pagamento che è necessario acquistare, se presenti.

### <a name="purchase-paid-teams-licenses"></a>Acquistare licenze di Teams a pagamento

1. Nel [interfaccia di amministrazione di Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=2024339) passare a **Fatturazione** > e selezionare **Acquisto di servizi**.
1. Selezionare **Visualizza prodotti** per visualizzare tutte le licenze disponibili.
1. Selezionare il filtro della categoria **Comunicazione e collaborazione** per visualizzare le licenze di Teams.
1. Scegliere la licenza di Teams a pagamento che si vuole sostituire **a Teams Free (classico).**
    1. È consigliabile la [licenza **di Teams Essentials**](https://admin.microsoft.com/adminportal/home#/catalog/offer-details/microsoft-teams-essentials-aad-identity-/2D7C59AC-F814-43E0-8E8E-E4EA91A09CAF), disponibile fino a 300 postazioni.
    1. Se hai bisogno di più di 300 postazioni, ti consigliamo di acquistare [licenze Microsoft 365 E1](https://admin.microsoft.com/Adminportal/Home#/catalog/offer-details/office-365-e1/CF4A479A-2119-4EF2-83D1-37CF8460EADA).
1. Immettere il numero di licenze da acquistare e quindi scegliere una frequenza di fatturazione.
1. Seleziona il pulsante **Acquista** per completare il processo di acquisto.

#### <a name="purchase-licenses-in-the-admin-center-marketplace"></a>Acquistare licenze nell'interfaccia di amministrazione Marketplace

Alcuni tenant hanno accesso a interfaccia di amministrazione di Microsoft 365 Marketplace. Per questi tenant, si acquistano licenze in Marketplace.

1. Nella [interfaccia di amministrazione di Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=2024339) seleziona **Marketplace** dal menu a sinistra.
1. Selezionare la scheda **Tutti i prodotti** .
1. Selezionare il filtro della categoria **Comunicazione e collaborazione** per visualizzare le licenze di Teams.
1. Scegliere la licenza di Teams a pagamento che si vuole sostituire **a Teams Free (classico).**
1. Immettere il numero di licenze da acquistare e quindi scegliere una frequenza di fatturazione.
1. Seleziona il pulsante **Acquista** per completare il processo di acquisto.

### <a name="assign-paid-teams-licenses"></a>Assegnare licenze di Teams a pagamento

1. Quando si è pronti a sostituire le licenze **di Teams Free (classico),** nel interfaccia di amministrazione di Microsoft 365 passare a **Utenti** > [**attivi**](https://admin.microsoft.com/adminportal/home#/users).
1. Selezionare tutti gli utenti con la licenza **Teams Free (classica)** elencata nella colonna **Licenze** .
1. Nella parte superiore dell'interfaccia di amministrazione selezionare l'opzione **Gestisci licenze di prodotto** .
1. Nel riquadro destro selezionare **Sostituisci**.
    1. Se si seleziona l'opzione **Sostituisci** , è necessario selezionare di nuovo tutte le licenze che si desidera assegnare agli utenti. Se selezioni solo la nuova licenza a pagamento di Teams, le altre licenze assegnate agli utenti verranno rimosse dagli utenti e sostituite con la licenza teams.
    1. Se gli utenti hanno esigenze di licenza diverse, completare questo processo in batch per evitare che gli utenti con licenze non corrette.
1. Nel riquadro di corsa, scegli la nuova licenza a pagamento di Teams e le eventuali altre licenze a cui gli utenti devono essere assegnati, quindi seleziona il pulsante **Salva modifiche** .

## <a name="use-microsoft-powershell-to-replace-licenses"></a>Usare Microsoft PowerShell per sostituire le licenze

Se all'organizzazione è assegnato un numero elevato di utenti della licenza **Teams Free (classica),** è consigliabile usare PowerShell per annullare l'assegnazione in blocco e assegnare licenze agli utenti.

Prima di completare questo processo, sono necessarie licenze teams a pagamento per gli utenti a cui è assegnata la licenza **Teams Free (classica).** Per acquistare licenze per tali utenti, vedere [Acquistare licenze di Teams a pagamento](#purchase-paid-teams-licenses).

1. Connettere il tenant di Microsoft 365 [all'SDK di PowerShell di Microsoft Graph](/powershell/microsoftgraph/get-started).
1. Aprire l'app desktop Microsoft PowerShell.
1. [Impostare le autorizzazioni di utenti e organizzazioni per API Graph](/microsoft-365/enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell#use-the-microsoft-graph-powershell-sdk).
1. [Rimuovere le licenze **di Teams Free (classico)** dagli account utente](/microsoft-365/enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell#removing-licenses-from-user-accounts).
1. [Assegnare licenze teams a pagamento agli utenti](/microsoft-365/enterprise/assign-licenses-to-user-accounts-with-microsoft-365-powershell#assigning-licenses-to-user-accounts).

Per altre informazioni sul processo Graph PowerShell SDK, vedere [Usare Microsoft Graph PowerShell SDK](/microsoft-365/enterprise/view-licenses-and-services-with-microsoft-365-powershell).
